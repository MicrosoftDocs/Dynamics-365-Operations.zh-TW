---
title: 維護排程
description: 本主題說明資產管理中的維護排程。
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 40df8e6cba824f90e13b46cc258c76bef993a3e2dd9c35566d8c6a622ce4eb09
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446853"
---
# <a name="maintenance-schedule"></a>維護排程

[!include [banner](../../includes/banner.md)]

 

維護排程包含所有預期的預防性維護計劃、維護要求，和要執行的維護回合清單。某些排程明細可能已轉換為工單。

四個維護排程檢視略有不同，取決於您要查看的維護排程明細而定。

| 功能表項目                  | 內容描述                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 所有維護排程       | 已顯示所有維護排程明細。     |
| 我的資產排程        | 所有維護排程明細包含安裝在與您作為工作者相關的機能位置的資產 (在[維護工作者和工作者群組](../setup-for-objects/workers-and-worker-groups.md)中設定) 會顯示在此清單中。 |
| 開啟維護排程明細 | 狀態為「已建立」的維護排程明細 - 表示它們尚未轉換為工單或已捨棄 - 會顯示在此清單中。                                            |
| 開啟維護排程集區 | 與工單集區相關的維護排程明細會顯示在此清單中。                                                                                                                  |

>[!NOTE]
>如果一個維護排程明細包含在多個工單集區中 (請參閱 [工單集區](../work-orders/work-order-pools.md))，則在 **開啟維護排程集區** 中的每個集區都會顯示一筆記錄。 這樣做是為了最佳化工單集區上的篩選選項。

如要開啟維護排程：

1. 按一下 **資產管理** > **通用** > **維護排程** > **所有維護排程** 或 **開啟維護排程明細**，或 **開啟維護排程集區**。

2. 如要更新維護排程，請按一下 **維護計劃** 或 **維護回合**。 

3. 您可以透過選擇維護排程明細並按一下 **編輯** 以進行編輯。 例如，您可以輕鬆更新服務等級或負責該工作的工作者。 您只能編輯尚未連線到工單的維護排程明細。

4. 您可以刪除維護排程明細，方法是在清單頁面中選擇並按一下 **刪除**。

5. 您可以捨棄維護排程明細，方法是在清單頁面中選擇並按一下 **捨棄**。 例如，如果資產具有 2,000 公里維護計劃和 10,000 公里維護計劃，則此功能很實用。 然後，當 2,000 公里維護計劃建立的明細與 10,000 公里、20,000 公里、30,000 公里等一致時，您可能會想捨棄該明細。 如果您捨棄與維護計劃相關的維護排程明細，則在安排該維護計劃時，該明細將永遠不再出現。

6. 如果您希望所有選定的明細都包含在同一個工單集區中，您可以在 **所有維護排程** 選擇一定數量的維護排程明細，並按一下 **工單集區**。

7. 如果您想在多筆明細上進行相同的調整，您可以在 **所有維護排程** 或 **打開維護排程明細** 或 **開啟維護排程集區** 選擇一定數量的維護排程明細，並按一下 **調整排程**。 您可以變更與所選維護排程明細相關的預期開始和結束日期、服務等級以及負責的維護工作者群組，或負責的維護工作者。

- 當維護排程明細已關聯至工單時，工單識別碼將顯示在 **工單** 欄位。  
- 在 **所有資產** 詳細資料檢視 >**資產維護計劃** FastTab 中，您可以選擇資產的維護計劃。 稍後，如果您在 **所有資產** 中刪除與資產相關的維護計劃，您也會自動刪除所有根據該維護計劃狀態為「已建立」的維護排程明細。 也請參閱[建立資產](../objects/create-an-object.md)。

下圖顯示 **所有維護排程** 清單頁面。

![圖 1。](media/16-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]