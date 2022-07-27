---
title: 使用 GROUPBY 資料來源對記錄進行分組和彙總計算
description: 本主題說明如何在電子報表 (ER) 中使用 GROUPBY 類型資料來源。
author: NickSelin
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a6cdc486c5f799bdedafa38e90be989fd328c96
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460594"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>使用 GROUPBY 資料來源對記錄進行分組和彙總計算

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

當您設定 [電子報表 (ER)](general-electronic-reporting.md)模型對應或格式時，您可以 [新增](#AddMmDataSource2) **GroupBy** 類型的必要資料來源。

在設計階段，**GroupBy** 資料來源被設定為識別以下元素：

- [基礎資料來源](#BaseDataSource)，它包含將在執行階段分組的記錄
- 基礎資料來源的[分組欄位](#GroupingFields)，它將在執行階段用於記錄分組
- 指定在執行階段對每個被發現的組進行匯總計算的[彙總函數](#AggregateFunctions)

在執行階段，設定的 **GroupBy** 資料來源將在分組欄位中具有相同值的記錄分組，然後返回記錄清單。 每條記錄代表單一群組。 對於每個群組，資料來源公開初始記錄分組依據的欄位值、計算的彙總函數的值以及屬於該組的基本資料來源的記錄清單。

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a>彙總函數

在執行階段，每組記錄都會進行每次彙總計算。 這種計算是透過使用單個欄位的值或資料來源記錄中的運算式來完成的，該資料來源在 **GroupBy** 類型的可編輯資料來源中被選中進行分組。 現行支援以下彙總函數：

- **AVG** – 此函數返回組中值的平均值。 它只能用於數字欄位。
- **COUNT** – 此函數返回在組中找到的項目數。
- **Min** – 此函數返回組中值中的最小值。
- **Max** – 此函數返回組中值中的最大值。
- **SUM** – 這個函數返回一個組中所有數值的總和。 它只能用於數字欄位。

## <a name="execution-location"></a><a name="ExecutionLocation"></a>執行位置

當您編輯一個 **GroupBy** 資料來源並指定包含必須分組的記錄的基礎資料來源時，系統會自動檢測執行該 **GroupBy** 資料來源的最有效[位置](#ExecutionLocation)。 如果基礎資料來源是 [可查找的](er-functions-list-filter.md#usage-notes) (也就是說，如果它可以在資料庫級別執行)，應用程式資料庫也被指定為可編輯的 **GroupBy** 資料來源的執行位置。 否則，將應用程式伺服器記憶體指定為執行位置。

您可以透過選取適用於已設定資料來源的位置來手動更改自動檢測到的執行位置。 如果選取的執行位置不適用，在設計階段就會引發一個[驗證錯誤](er-components-inspections.md#i5)。

> [!TIP]
> 我們建議您使用資料庫位置對公開大量記錄的資料來源進行分組。

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a>記憶體消耗

在預設情況下，如果 **GroupBy** 資料來源在記憶體中執行，應用伺服器記憶體會被用來儲存屬於每個被發現的組的基礎資料來源的記錄，作為單個組的記錄。 若要幫助減少記憶體消耗，如果 **GroupBy** 資料來源被設定為僅計算彙總函數並且在執行階段不使用其組的記錄，則可以禁止記錄儲存。 若要以這種方式減少記憶體消耗，請在 **函數管理** 工作區啟用 **當記錄分組僅用於計算彙總時減少 ER 中的記憶體用量** 函數。

## <a name="alternatives"></a><a name="Alternatives"></a>替代方案

類似的彙總可以透過使用[不同](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions)類型的資料來源或 ER 內建函數來計算。

若要進一步了解此函數，請完成以下範例。

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a>範例：使用 GROUPBY 資料來源進行彙總計算和記錄分組

這個範例顯示了系統管理員或電子報表函數顧問角色的使用者如何設定 ER 模型對應，該對應有 **GROUPBY** 資料來源，用於計算彙總函數和分組記錄。 此模型對應用於在產生 Intrastat 聲明時列印控制報告。 該報告可讓您查看報告的 Intrastat 交易。

這個範例中的程序可以在 Microsoft Dynamics 365 Finance 的 **DEMF** 公司中完成。 

### <a name="prepare-sample-data"></a>準備樣本資料

確保您有 Intrastat 交易，以便在 **Intrastat** 頁面上報告。 您必須有不同傳輸代碼的交易，因為在這個範例中您將按 **傳輸** 欄位分組交易。

![在 Intrastat 頁面上準備 Intrastat 交易。](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>設定 ER 架構

按照[設定 ER 架構](er-quick-start2-customize-report.md#ConfigureFramework)中的步驟設定最小的 ER 參數集。 在開始使用 ER 架構設計 ER 模型對應之前，您必須完成此安裝。

### <a name="import-the-standard-er-format-configuration"></a>匯入標準 ER 格式設定

按照[匯入標準 ER 格式設定](er-quick-start2-customize-report.md#ImportERSolution1)中的步驟將標準 ER 設定新增到您現行的 Dynamics 365 Finance 實體。 從存放庫匯入 **Intrastat 模型** 設定的第 1 版。

### <a name="create-a-custom-data-model-configuration"></a>建立自訂資料模型設定

按照 [新增自訂資料模型設定](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration)中的步驟，手動新增一個新的 **Intrastat 模型 (Litware)** ER 資料模型設定，該設定由匯入的 **Intrastat 模型** 設定衍生而來。

### <a name="configure-a-custom-data-model-component"></a>設定自訂的資料模型組件

按照這些步驟，對衍生的 **Intrastat 模型 (Litware)** 資料模型進行必要的修改，這樣它就可以用來揭露具有所需細節的傳輸代碼。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在設定樹狀結構中，選取 **Intrastat 模型 (Litware)**。
3. 選取 **設計工具**。
4. 在 **資料模型設計工具** 頁面上，在模型樹狀結構中，選取 **Intrastat**。
5. 選取 **新建**，為選定的 **Intrastat** 節點新增新的巢狀節點。 在新增資料模型節點的下拉式對話方塊中，執行以下步驟：

    1. 在 **名稱** 欄位中，輸入 **Transport**。
    2. 在 **項目類型** 欄位中，選取 **記錄清單**。
    3. 選取 **新增** 以新增新節點。

6. 選取 **新建**，為您剛新增的 **傳輸** 節點新增新的巢狀節點。 在新增資料模型節點的下拉式對話方塊中，執行以下步驟：

    1. 在 **名稱** 欄位中，輸入 **Code**。
    2. 在 **項目類型** 欄位中，選取 **字串**。
    3. 選取 **新增** 以新增新節點。

7. 選取 **新建**，為 **傳輸** 節點新增另一個新巢狀節點。 在新增資料模型節點的下拉式對話方塊中，執行以下步驟：

    1. 在 **名稱** 欄位，輸入 **TotalInvoicedAmount**。
    2. 在 **項目類型** 欄位中，選取 **實數**。
    3. 選取 **新增** 以新增新節點。

8. 選取 **新建**，為 **傳輸** 節點新增另一個新巢狀節點。 在新增資料模型節點的下拉式對話方塊中，執行以下步驟：

    1. 在 **名稱** 欄位中，輸入 **NumberOfTransactions**。
    2. 在 **項目類型** 欄位中，選取 **整數**。
    3. 選取 **新增** 以新增新節點。

9. 選取 **新建**，為 **傳輸** 節點新增另一個新巢狀節點。 在新增資料模型節點的下拉式對話方塊中，執行以下步驟：

    1. 在 **名稱** 欄位，輸入 **Transaction**。
    2. 在 **項目類型** 欄位中，選取 **記錄清單**。
    3. 選取 **新增** 以新增新節點。

10. 對於您剛新增的 **交易** 節點，在 **節點** FastTab 上，選取 **切換項目參考**。
11. 在 **切換項目參考** 對話方塊中，在資料模型樹狀結構中，選取 **CommodityRecord**。 然後選取 **確定**。

![在 ER 資料模型設計工具中設定的資料模型。](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>完成自訂資料模型的設計

按照 [完成資料模型的設計](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration)中的步驟，完成衍生的 **Intrastat 模型 (Litware)** 資料模型的設計。

### <a name="create-a-new-model-mapping-configuration"></a>建立新模型對應設定

按照 [建立新的模型對應設定](er-quick-start1-new-solution.md#CreateModelMapping)的步驟，為衍生的 **Intrastat 模型 (Litware)** 設定手動新增新的 **Intrastat 樣本對應** ER 模型對應設定。

### <a name="add-a-new-model-mapping-component"></a>新增新的模型對應組件

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在設定樹狀結構中，展開 **Intrastat 模型** 設定。
3. 選取 **Intrastat 樣本對應** 設定。
4. 選取 **設計工具** 開啟對應清單。
5. 選取 **刪除** 來刪移除有的對應組件。
6. 選取 **新建** 來新增新的對應組件。
7. 在 **定義** 欄位中，選取 **Intrastat**。
8. 在 **名稱** 欄位中，輸入 **Intrastat mapping**。
9. 選取 **設計工具** 來設定新的對應。

### <a name="design-the-added-model-mapping-component"></a>設計新增的模型對應組件

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a>新增資料來源以存取申請表

設定資料來源以存取包含 Intrastat 交易詳情的申請表。

1. 在 **模型對應設計工具** 頁，在 **資料來源類型** 窗格，選取 **Dynamics 365 for Operations\\Table records**。
2. 在 **資料來源** 窗格中，選取 **新增根** 來新增新的資料來源，該資料來源將用於存取 **Intrastat** 表。 **Intrastat** 表中的每條記錄代表單一 Intrastat 交易。
3. 在 **資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Transaction**。
4. 在 **資料表** 欄位中，輸入 **Intrastat**。
5. 選取 **確定** 以新增新資料來源。

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a>新增資料來源以對 Intrastat 交易進行分組

設定 **GroupBy** 資料來源，對 Intrastat 交易進行分組，並計算出彙總函數。

1. 在 **模型對應設計工具** 頁面上，在 **資料來源類型** 窗格中，選取 **函數\\分組依據**。
2. 在 **資料來源** 窗格中，選取 **新增根** 以新增新的資料來源，該資料來源將被用於分組 Intrastat 交易和計算彙總函數。
3. 在 **資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **TransportRecord**。
4. 選取 **編輯分組依據** 設定分組條件。
5. 在 **編輯「分組依據」參數** 頁面上，在右窗格的資料來源清單中，選取 **交易** 資料來源，並展開它。
6. 選取 **新增欄位至\>分組內容**，表示 **交易** 資料來源被選為設定的 **GroupBy** 資料來源的<a name="BaseDataSource">基礎資料來源</a>。 **交易** 資料來源的記錄將被分組，該資料來源的欄位值將被用於彙總函數的計算。
7. 選取 **Transaction\Transport** 欄位，然後選取 **新增欄位至\>已分組欄位**，表示基本資料來源的 **傳輸** 欄位被選為設定的 **GroupBy** 資料來源的<a name="GroupingFields">分組標準</a>。 換句話說，**交易** 資料來源的記錄將根據 **傳輸** 欄位的值進行分組。 設定的 **GroupBy** 資料來源的每條記錄將代表在基礎資料來源的記錄中發現的單一傳輸代碼。
8. 選取 **Transaction\AmountMST** 欄位，然後按照以下步驟操作：

    1. 選取 **新增欄位至\>彙總欄位**，表示將為這個欄位計算<a name="AggregateFunctions">彙總函數</a>。
    2. 在 **彙總** 窗格中，在為選定的 **Transaction\AmountMST** 欄位新增的記錄中，在 **方法** 欄位中，選取 **總和** 函數。
    3. 在 **名稱** 選取性欄位，輸入 **TotalInvoicedAmount**。

    這些設定規定，對於每個傳輸組，將計算 **Transaction/AmountMST** 欄位的總金額。

9. 選取 **Transaction\RecId** 欄位，然後按照以下步驟操作：

    1. 選取 **新增欄位至\>彙總欄位**，表示將為這個欄位計算彙總函數。
    2. 在 **彙總** 窗格中，在為選定的 **Transaction\RecId** 欄位新增的記錄中，在 **方法** 欄位中，選取 **計數** 函數。
    3. 在 **名稱** 選取性欄位，輸入 **NumberOfTransactions**。

    這些設定規定，對於每個傳輸組，將計算該組的交易數量。

10. 選取 **儲存**。
11. 可編輯資料來源的審查<a name="ExecutionLocation">執行</a>參數。 注意，**自動檢測** 已經在 **執行位置** 欄位中自動選取，而 **執行地點** 欄位中包含 **SQL** 值。 這些設定指定所選的 **交易** 基礎資料來源現行是可查找的，您可以在資料庫級別執行可編輯的 **GroupBy** 資料來源。
12. 開啟 **執行位置** 欄位的查找，查看可用值的清單。 注意，您可以選取 **查找** 或 **在記憶體中** 來強制這個 **GroupBy** 資料來源在資料庫層面或應用程式伺服器記憶體中執行。
13. 選取 **儲存**，並關閉 **編輯「分組依據」參數** 頁面。
14. 選取 **確定** 完成 **GroupBy** 資料來源的設定。

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a>將 GroupBy 資料來源繫結到資料模型欄位

將設定的資料來源繫結到資料模型的欄位，以指定如何在執行階段使用應用程式資料填入資料模型。

1. 在 **模型對應設計工具** 頁面上，在 **資料模型** 窗格中，展開 **傳輸** 節點。
2. 在 **資料來源** 窗格中，展開 **TransportRecord** 資料來源。
3. 新增繫結以公開已發現的傳輸組清單：

    1. 在 **資料模型** 窗格中，選取 **傳輸** 項目。
    2. 在 **資料來源** 窗格中，選取 **TransportRecord** 資料來源。
    3. 選取 **繫結**。

4. 新增繫結，公開每個已發現傳輸組的傳輸代碼：

    1. 選取 **Transport.Code** 資料模型項目。
    2. 選取 **TransportRecord.grouped.TransportMode** 分組欄位。
    3. 選取 **繫結**。

5. 新增繫結以公開每個發現的傳輸組的計算彙總函數的值：

    1. 選取 **Transport.NumberOfTransactions** 資料模型項目。
    2. 選取 **TransportRecord.aggregated.NumberOfTransactions** 彙總欄位。
    3. 選取 **繫結**。
    4. 選取 **Transport.TotalInvoicedAmount** 資料模型項目。
    5. 選取 **TransportRecord.aggregated.TotalInvoicedAmount** 彙總欄位。
    6. 選取 **繫結**。

6. 新增繫結以公開屬於每個發現的傳輸組的交易記錄：

    1. 選取 **Transport.Transaction** 資料模型項目。
    2. 選取 **TransportRecord.lines** 欄位。
    3. 選取 **繫結**。

    您可以繼續設定 **Transport.Transaction** 資料模型項目和 **TransportRecord.lines** 資料來源欄位的巢狀項目的繫結，以便在執行階段公開屬於每個已發現的傳輸組的 Intrastat 交易的細節。

![在 ER 模型對應設計工具中設定的模型對應。](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>偵錯新增的模型對應組件

使用[ER 資料來源偵錯器](er-debug-data-sources.md)測試設定的模型對應。

1. 在 **模型對應設計工具** 頁面上，選取 **開始偵錯**。
2. 在 **偵錯資料來源** 頁面上，在左側窗格中，選取 **TransportRecord** 資料來源，然後選取 **讀取所有記錄**。
3. 展開 **TransportRecord** 資料來源，然後執行以下步驟：

    1. 選取 **TransportRecord.grouped.TransportMode** 資料來源。
    2. 選取 **取得價值**。
    3. 選取 **TransportRecord.grouped.NumberOfTransactions** 資料來源。
    4. 選取 **取得價值**。
    5. 選取 **TransportRecord.grouped.TotalInvoicedAmount** 資料來源。
    6. 選取 **取得價值**。

4. 在右側窗格中，選取 **展開全部**。

**TransportRecord** 資料來源公開了兩條記錄並提供了兩個傳輸代碼。 對於每個傳輸代碼，計算交易次數和總發票金額。

> [!NOTE]
> 當調用 **GroupBy** 資料來源時，使用「懶人閱讀」的方法來最佳化資料庫調用。 因此，**GroupBy** 資料來源中的一些欄位值只有在繫結到資料模型欄位時才會在 ER 資料來源偵錯器中計算。

![在偵錯資料來源頁面上的資料來源偵錯的結果。](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>常用問題

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>計算組總計時有什麼方法可以計算總計嗎？

是。 若要計算總計，請設定另一個 **GroupBy** 資料來源，將您之前設定的 **GroupBy** 資料來源作為基礎資料來源使用。 下面的插圖顯示了 **GroupBy** 類型的 **總計** 資料來源，它被用來計算彙總 **SUM** 函數，基於 **GroupBy** 類型的 **TransportRecord** 資料來源的 **SUM** 彙總。

![ER 模型對應設計工具中的總計資料來源。](./media/er-groupby-data-sources-configure-model-mapping2.png)

下面的圖示顯示了 **總計** 資料來源的偵錯結果。

![在偵錯資料來源頁面上的總計資料來源偵錯的結果。](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>其他資源

- [電子報表概述](general-electronic-reporting.md)
- [偵錯已執行 ER 格式的資料來源以分析資料流程和轉換](er-debug-data-sources.md)
- [以電子報表格式使用資料收集資料來源](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
