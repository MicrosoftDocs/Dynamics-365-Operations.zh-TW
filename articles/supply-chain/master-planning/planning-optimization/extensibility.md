---
title: 規劃最佳化擴充性
description: 本主題說明規劃最佳化支援的擴充性案例。
author: ChristianRytt
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e18801a02ae9e904eb5bc597f9f61ed42c537ab9
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2021
ms.locfileid: "8449388"
---
# <a name="planning-optimization-extensibility"></a>規劃最佳化擴充性

[!include [banner](../../includes/banner.md)]

本主題說明與總體規劃相關且規劃最佳化支援的擴充性案例。 Microsoft Dynamics 365 Supply Chain Management 版本 10.0.13 以上提供這些功能。

## <a name="custom-processing-when-master-planning-is-completed"></a>自訂總體規劃完成時的處理程序

在最常見的規劃最佳化擴充性案例中，自訂處理程序是在方案更新後完成。 例如，您可能會在已規劃的訂單表中新增一欄 (`ReqPO`)，或者您可能想從產生的方案中取得統計資訊。 要在這些案例中取得擴充效果，您可以從使用 `MpsMasterPlanningEvents` 類別中的 `jobCompletedSuccessfully` 方法著手。

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

這個擴充範例說明如何在已規劃的訂單上設定自訂的 `CstmOrderPriority` 欄位。

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

新增自訂邏輯時，請考慮以下限制和最佳做法：

- `jobCompletedSuccessfully` 方法是在交易範圍外被呼叫。 因此當自訂邏輯開始執行時，使用者即可查看該方案。 如果您透過自訂在已規劃的訂單上設定了其他欄位，請務必讓使用者知道這些欄位的值最終將保持一致 (也就是說，這些值可能在已規劃的工作完成後立即過期)。
- 另一個總體規劃工作可以在呼叫 `jobCompletedSuccessfully` 方法時啟動。 新工作可能會影響整個方案或部分方案。 如果已規劃的訂單或需求交易是在以 `jobCompletedSuccessfully` 規劃工作時建立或更新，新工作可能會更新或刪除這些訂單或交易。 擴充此事件時必須處理更新衝突例外狀況。
- 擴充此方法時，請避免使用單一交易範圍。 執行單一總體規劃可以產生數百萬個需求交易和數十萬個已規劃訂單。 如果在單一交易範圍內處理所有交易和已規劃訂單，會發生眾多 SQL 鎖定情況並中斷其他規劃程序。 另外，如果交易遭長時間保留，會在 SQL 資料庫中建立「幽靈記錄」。 幽靈記錄會對系統中的每個處理程序造成負面影響。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]