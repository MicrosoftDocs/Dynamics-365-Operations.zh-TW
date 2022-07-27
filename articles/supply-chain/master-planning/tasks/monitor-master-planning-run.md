---
title: 監控主規劃執行
description: 本主題將說明生產規劃者員如何查看總體規劃運行是否正在進行。
author: ChristianRytt
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4db1173b35cd196ab39fae3cac3754439fab84d0
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449961"
---
# <a name="monitor-a-master-planning-run"></a>監控主規劃執行

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>使用甘特圖呈現總體規劃進度

您可以從 **查看總體規劃進度** 頁面，以甘特圖的形式查看歷史總體規劃進行的詳細資訊。 此功能可協助您瞭解在總體規劃各個階段所花費的時間。 對於目前作用中規劃作業，**查看總體規劃進度** 頁面可追蹤進度並查看估計的剩餘時間。

### <a name="turn-the-master-plan-progress-visualization-feature-on-or-off"></a>開啟或關閉總體規劃進度視覺效果功能

從 Supply Chain Management 版本 10.0.21 開始，此功能預設開啟。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往 [功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區並搜尋 *總體規劃進度視覺效果* 功能，然後開啟或關閉此功能。

### <a name="use-the-master-plan-progress-visualization-feature"></a>使用總體規劃進度視覺效果功能

**查看總體規劃進度** 頁面可以顯示歷史規劃作業和作用中規劃作業。 

若要檢視歷史規劃作業，可使用兩個選項。 

1. 依序前往 **總體規劃 \> 設定 \> 計劃 \> 主計劃**，然後在動作窗格上，選擇 **歷程記錄**。 選擇所需作業後，選擇 **查詢**，然後選擇 **檢視進度**
1. 依序前往 **總體規劃 \> 工作區 \> 總體規劃**，在總體規劃圖格上按一下 **歷程記錄**。 選擇所需作業後，選擇 **查詢**，然後選擇 **檢視進度**

若要檢視使用中規劃作業，可使用兩個選項。 
1. 依序前往 **總體規劃 \> 工作區 \> 總體規劃**，在動作窗格上選擇 **未完成的規劃進度**。 選擇所需作業後，選擇 **查詢**，然後選擇 **檢視進度**。
1. 依序前往 **總體規劃 \> 工作區 \> 總體規劃**，在總體規劃圖格上按一下 **檢視進度**。 選擇所需作業後，選擇 **查詢**，然後選擇 **檢視進度**

請注意，您只能在規劃作業正在處理時查看作用中的作業。

### <a name="analyze-a-master-planning-job"></a>分析總體規劃作業

在甘特圖中，您可以展開以下每個規劃程序來查看花費時間的其他相關詳細資訊：

- 正在初始化
- 刪除和插入資料
- 涵蓋範圍規劃
- 延遲
- 動作訊息
- 定案
- 自動確認

如果您想檢視使用動作訊息的影響，甘特圖是很實用的工具。

#### <a name="navigation-in-the-gantt-chart"></a>在甘特圖中進行導覽

- 若要展開所選群組並顯示詳細資訊，請在樹狀視圖中選取加號 (**+**)。
- 若要折疊所選群組，請在樹狀視圖中選取減號 (**–**)。
- 您可以使用鍵盤進行導覽。 使用 **向上鍵** 和 **向下鍵** 可在資料列之間移動。 使用 **向右鍵** 和 **向左鍵** 可展開及折疊群組。
- 若要開啟或關閉甘特圖中的所有層級，請選擇 **全部展開** 或 **全部摺疊**。
- 若要查看相關的處理時間，請將滑鼠游標懸停在工作上。 (工作是甘特圖中的最低層級。)

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>檢視其他總體規劃執行以比較作業

在 **顯示其他總體規劃執行** 欄位中選取作業，即可在甘特圖中查看其他執行的總體規劃並比較這兩個作業。

#### <a name="bom-level-display"></a>BOM 層級顯示

物料清單 (BOM) 顯示的層級涵蓋規劃、延遲、行動和確認。

- **涵蓋範圍規劃**：BOM 層級按預期顯示。 層級是由上到下計算。

    **範例：** BOM 層級 0、1、2

- **延誤**：BOM 層級顯示為涵蓋規劃 BOM 層級乘以 –1。 (換句話說，這類層級有負號。)

    **範例：** BOM 層級 –2、–1、0

- **動作訊息**：BOM 層級按預期顯示。 層級是由上到下計算。

    **範例：** BOM 層級 0、1、2

- **自動確認**：BOM 層級顯示為 999 減去涵蓋規劃 BOM 層級。

    **範例：** BOM 層級 999、998、997

下表總結了這些行為。

| 顯示的 BOM 層級 | 終端品項 | 子元件 | 原料 |
|---|---|---|---|
| 涵蓋範圍規劃 | 0 | 1 | 2 |
| 延遲 | 0 | –1 | –2 |
| 動作訊息 | 0 | 1 | 2 |
| 自動確認 | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>視覺化進度

當您檢視目前作用中的總體規劃作業石，進度將透過甘特圖中的顏色顯示。 以下顏色適用於藍色主題。 其他顏色主題所用的顏色會有所不同。

- **深藍色**：完成規劃工作。
- **橘色**：目前作用中的工作。
- **淺藍色**：預估剩餘工作。

顏色僅顯示於甘特圖的最低層級。 選擇 **全部展開** 可檢視總體規劃作業中的所有工作。 系統會根據歷史總體規劃作業預估剩餘工作。

## <a name="run-master-planning-and-track-processing-time"></a>執行總體規劃並追蹤處理時間

1. 在預設儀表板上，選擇 **總體規劃**。
1. 請在 **計劃** 欄位中輸入或選擇一個值。
1. 選擇 **執行**。
1. 將 **追蹤處理時間** 選項設為 **是**。
1. 在 **執行緒數目** 欄位中，輸入一個數字。
1. 在 **記錄內容包括** FastTab 上，選擇 **篩選**。
1. 在格線中，選擇 **欄位** 欄位設為 **品項編號** 的列。
1. 在 **條件** 欄位中，輸入值。
1. 選擇 **確定**。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]