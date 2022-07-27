---
title: 對基準預測進行手動調整
description: 本主題說明如何對基準預測進行手動調整並檢視預測的詳細資料。
author: ChristianRytt
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d00061efa551c9fe2ad9d0e441bba44e70b071c
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450030"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>對基準預測進行手動調整

[!include [banner](../includes/banner.md)]

本主題說明如何對基準預測進行手動調整並檢視預測的詳細資料。 

在進行手動調整前，務必先瞭解各個頁面上的一些概念。

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>調整後的需求預測頁面的網格
**調整後的需求預測** 頁面包含具下列結構的網格：

-   第一欄會顯示產生預測的項目、項目分配索引鍵、公司等。 此頁面子標題會提供目前網格內顯示的預測維度的描述。 例如，若頁面上的子標題為 **公司 / 站點 / 項目分配索引鍵**，且網格列的一個標題為 **USMF / 1 / D\_Alloc**，則該列顯示的預測適用於 USMF 公司、站點 1 及 **D\_Alloc** 項目分配索引鍵。
-   後續欄代表已產生預測的預測貯體。 每列標題是該列顯示的預測貯體的第一個日期。
-   儲存格內的值代表該特定預測貯體的一個項目、項目分配索引鍵等的預測。

## <a name="forecast-aggregation-and-de-aggregation"></a>預測彙總和解除彙總
此頁面子標題會顯示預測彙總的等級。 

例如，若頁面子標題為 **公司 / 站點 / 分配索引鍵 / 品項編號 / 顏色 / 尺寸 / 配置 / 樣式**，則沒有預測彙總，且會顯示項目及其維度等級的預測。 若要變更彙總，請使用 **變更預測維度** 頁面 (可由應用程式功能表開啟)。 

若要修改預測，請按一下任何可用的儲存格，並輸入調整後的預測值。 編輯後的儲存格會立刻變成粗體，代表其中呈現的預測並非需求預測服務所建立，而是經過手動調整的。 

若您變更彙總讓此頁面顯示更多彙總資料，則可使用 **需求預測明細** 頁面，檢視組成彙總預測的個別預測明細。 

例如，您已在項目等級產生預測，但也知道此項目所有站點的需求將因促銷或其他類似事件而上升。 此時，您可於 **變更預測維度** 頁面，將彙總設為 **公司 / 項目分配索引鍵 / 項目**。 您可在 **調整後的需求預測** 網格中，調整該項目所有站點的全域預測。 若要檢視您的變更對所有站點的影響，請開啟 **需求預測明細** 頁面。 在此頁面上，您將看到該項目在每個站點、調整後的預測數量及原始預測數量的一條明細。 

在彙總等級調整預測數量時，系統會使用加權分配，將變更分配至組成彙總的所有明細。 

您也可在 **需求預測明細** 頁面進行手動調整，方法是修改彙總網格內的 **總數量** 值或 **數量** 儲存格。

## <a name="viewing-details-of-the-forecast"></a>檢視預測的詳細資料
您可開啟 **需求預測詳細資料** 頁面，檢視預測相關的詳細資訊。 

**需求預測詳細資料** 頁面會以圖形和表格格式顯示下列資訊：

-   預測的基準歷史需求。
-   主計劃目前使用的預測。
-   新的需求預測值及手動調整後的金額。
-   預測值的信賴區間。
-   產生預測使用的預測模型。 若您正檢視彙總資料，則會看到所有彙總時間序列使用的所有方法清單。
-   內部模型準確性 (MAPE)。 如需預測準確性的詳細資訊，請參閱[監控預測準確性](monitor-forecast-accuracy.md)。

**附註：**

- *需求預測詳細資料上的預測模型選擇* 功能可增加 **需求預測詳細資料** 頁面的設定，讓您選取要納入的預測模型。 從 Supply Chain Management 版本 10.0.21 開始，此功能預設開啟。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區並搜尋 *需求預測詳細資料上的預測模型選擇* 功能，然後開啟或關閉此功能。
- 此頁面 **預測** 區段顯示的信賴區間，代表信賴區間上下限之間的差距。 若要檢視上下限的值，請將滑鼠懸停在 **以圖形方式顯示歷史需求與預測** 區段內的圖表。
- 若您使用需求預測 Microsoft Azure Machine Learning，可指定所產生預測應具備的信賴等級百分比。 信賴區間是由一系列的值組成，這些值可作為需求預測的良好估計值。 95% 的信賴等級百分比，表示需求預測超出信賴區間範圍的風險為 5%。

您也可手動調整 **需求預測詳細資料** 頁面上的預測，方法是修改 **預測** 區段內 **預測** 列的值。

## <a name="additional-resources"></a>其他資源

[監控預測準確性](monitor-forecast-accuracy.md)

[產生統計基準線預測](generate-statistical-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]