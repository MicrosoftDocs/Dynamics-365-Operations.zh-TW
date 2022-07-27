---
title: 檢視計劃歷程與規劃記錄
description: 本主題說明如何檢視由規劃最佳化功能所觸發規劃作業的歷程。
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 757d2103bd629c0107a3f29599196a56ea56d431a66cf1e69c7b3cf3d817c087
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446730"
---
# <a name="view-plan-history-and-planning-logs"></a>檢視計劃歷程與規劃記錄

[!include [banner](../../includes/banner.md)]

本主題說明如何在 Microsoft Dynamics 365 Supply Chain Management 中檢視由規劃最佳化功能所觸發規劃作業的歷程。

若要檢視計劃的歷程，請移至 **總規劃**\>**設定**\>**計劃**\>**總計劃**，並選擇 **歷程**。 歷程隨即列出所選計劃的所有作業。 此清單包含已完成作業與使用中作業。

規劃最佳化總規劃執行的作業歷程只會保留每個總計劃的最多 60 條記錄。 只要您執行新的總規劃計算，就會刪除該計劃最舊的歷程記錄。

除了查看作業的開始時間和狀態外，您還可以查看特定作業的記錄。 此記錄包括其他資訊與警告。 並非所有的作業都有記錄。 若要查看作業的記錄，請選擇 **記錄**。 記錄項目在作業完成後只會儲存 30 天，之後將自動刪除。

如果當總規劃處理設定完成時，**在背景執行** FastTab 上的 **批次處理** 選項已啟用，則批次作業記錄會顯示在總規劃執行期間所產生任何警告與錯誤的詳細資訊。 例如，系統只會在批次作業記錄中擷取自動確認錯誤。 這些錯誤不會顯示在 **歷程** 頁面的記錄上。

若要檢視在總規劃執行期間發生的自動確認錯誤和其他警告或錯誤，請執行以下步驟。

1. 移至 **系統管理 \> 查詢 \> 批次作業**。
1. 找到並選擇代表您感興趣的總規劃執行的記錄。 (例如，**作業描述** 欄位的開頭可以是 *總規劃*。)
1. 視您為 **批次作業** 頁面使用的是 *增強型表單* 或 *傳統型 (未增強) 表單*，執行下列其中一個步驟：

    - 如果您使用的是增強型表單：在動作窗格上，選擇 **批次作業歷程**。 然後，在 **批次作業歷程** 頁面上，選擇動作窗格上的 **記錄**。
    - 如果您使用的是傳統型表單：在動作窗格的 **批次作業** 索引標籤上，選擇 **記錄**。

1. 選擇 **訊息詳細資料** 以開啟 **訊息詳細資料** 窗格，在此您可以檢視處理期間擷取的所有警告與錯誤。

## <a name="related-resources"></a>相關資源

- [規劃最佳化概觀](planning-optimization-overview.md)
- [開始使用規劃最佳化](get-started.md)
- [規劃最佳化適合度分析](planning-optimization-fit-analysis.md)
- [將篩選條件套用至計劃](plan-filters.md)
- [取消規劃作業](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
