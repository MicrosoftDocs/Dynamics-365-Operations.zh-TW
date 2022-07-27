---
title: 生產訂單成本分析
description: 本文提供有關您可以對已完成和目前生產訂單執行的成本分析的資訊。 您可以使用價格計算頁面或成本估算和成本報告來分析估計成本和實際成本。 您可以查看有關每個組件項目、傳送作業和間接成本的估計和實際成本 (和數量) 的資訊。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage, ProdSetupHistoricalCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79634
ms.assetid: ded5da04-f787-49f7-b5e5-75c2a2b92930
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b0690a683cdefaeb5e441d3e2ea467a680a8fc1dd0905b6a94fd72bcbf36e1e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446817"
---
# <a name="production-order-cost-analysis"></a>生產訂單成本分析

[!include [banner](../includes/banner.md)]

本文提供有關您可以對已完成和目前生產訂單執行的成本分析的資訊。 您可以使用價格計算頁面或成本估算和成本報告來分析估計成本和實際成本。 您可以查看有關每個組件項目、傳送作業和間接成本的估計和實際成本 (和數量) 的資訊。

生產訂單實際成本的根據為報告的材料消耗和傳送作業。 您可以在 **生產過帳** 頁面上存取有關生產訂單的回報材料消耗、傳送作業和間接成本的詳細交易資料。

## <a name="variance-analysis-for-a-completed-production-order"></a>已完成生產訂單的差異分析
差異反映了報告的生產活動與生產項目標準成本計算的比較結果。 差異不會反映與生產訂單的估計成本的比較。 報告的生產活動包括材料消耗和傳送作業、相關的間接成本，以及報告為完成的數量。 計算以下四種差異類型：

-   批量差異
-   生產數量差異
-   生產價格差異
-   生產替代差異

下圖顯示了四個差異，說明生產訂單結束時生產訂單的實際成本與項目成本記錄中的計算成本之間的差異。 

![說明已完成生產訂單差異的差異。](./media/control.jpg) 

您可以使用 **差異** 頁面或 **生產差異** 報告來分析生產差異。 使用顯示選項按項目和營運資源，或按成本群組來查看詳細差異。 庫存參數中的成本明細策略可決定是否按成本群組追蹤差異。 您還可以使用 **單一**、**多個**，和 **總計** 來顯示選項以查看總結差異。 詳細差異的相關資訊可以協助您瞭解每個差異的來源。 若要在結束生產訂單前預測差異，請分析由 **成本估算和成本** 報告提供的詳細資訊。

## <a name="cost-analysis-for-current-production-orders"></a>目前生產訂單的成本分析
單獨的報告提供有關每種交易類型的資訊。 使用這些報告來分析報告的生產活動成本。 只顯示目前狀態為 **已開始** 或 **報告為完成** 生產訂單的相關資訊。

-   **處理中的材料**− 此報表列出了在指定交易日期，針對目前生產訂單報告的揀料單交易。 這份報告說明已發貨的組件數量和每筆交易的成本金額。 為單一組件項目使用選擇條件。 例如，您可以根據適用的生產訂單列印組件發貨數量的相關資訊。 發貨數量不會針對父系物料報告為已完成的數量進行更新。 因此，過程中的實際原料數量可能略為誇大。
-   **在製品**− 此報表列出了在指定交易日期，針對目前生產訂單報告的途程交易 (或作業交易)。 這份報告說明每筆交易報告的小時數、金額和數量 (良好數量和錯誤數量)。 另外包括作業編號、作業識別碼和營運資源等資訊。 此外，此報告顯示生產訂單的所有交易的總時間和金額，以及報告為已完成的數量。
-   **過程中的間接成本**− 這份報告列出了生產訂單產生的間接成本。 此向資料的根據為截至指定交易日期的傳送作業和組件已回報的消耗。 報告說明間接成本的類型 (附加費或費率)、間接成本的成本核算表代碼以及每筆交易的成本金額。 此報告不提供產生間接成本的途程卡或揀料單交易的相關資訊。
-   **過程中的生產成本**− 此報告列出了截至指定交易日期的生產訂單的材料消耗、傳送作業和間接成本的總和。
-   **過程中的完成項目**− 此報告列出了截至指定交易日期，列出目前生產訂單報告和報告為已完成之交易的相關資料。


## <a name="additional-resources"></a>其他資源

[生產差異的常見來源](common-sources-of-production-variances.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]