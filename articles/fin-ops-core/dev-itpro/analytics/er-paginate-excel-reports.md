---
title: 設計一種 ER 格式以在 Excel 中對產生的文件進行分頁
description: 本主題說明如何設計電子報表 (ER) 格式，以在 Microsoft Excel 中對產生的文件進行分頁。
author: NickSelin
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.openlocfilehash: ce29225c4bce24adc2abefc3d3d6f20774852af4
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2021
ms.locfileid: "8460583"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>設計一種 ER 格式以在 Excel 中對產生的文件進行分頁

[!include [banner](../includes/banner.md)]

本主題說明系統管理員或電子報表函數顧問角色的使用者如何設定[電子報表 (ER)](general-electronic-reporting.md)格式以在 Microsoft Excel 中產生輸出文件並管理文件分頁。

在此範例中，您將修改 Microsoft 提供的 ER 格式，該格式用於在[產生](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) Intrastat 聲明時列印控制報表。 此報表可讓您觀察報表的 Intrastat 交易。 您的修改將使您能夠管理產生的控制報表的分頁。

本主題中的程序可以在 **DEMF** 公司完成。 無需編碼。 在開始之前，請下載並儲存以下檔案。

| 描述       | 檔案名稱 |
|-------------------|-----------| 
| 報表範本 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| 報表範本 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>設定 ER 架構

按照[設定 ER 架構](er-quick-start2-customize-report.md#ConfigureFramework)中的步驟設定最小的 ER 參數集。 在開始使用 ER 架構設計標準 ER 格式的自訂版本之前，您必須完成此安裝。

## <a name="import-the-standard-er-format-configuration"></a>匯入標準 ER 格式設定

按照[匯入標準 ER 格式設定](er-quick-start2-customize-report.md#ImportERSolution1)中的步驟將標準 ER 設定新增到您現行的 Dynamics 365 Finance 實體。 匯入 **Intrastat 報表** 格式設定的 **1.9** 版。 基礎 **Intrastat 模型** 設定的基礎版本 1 會自動從存放庫中匯入。

## <a name="customize-the-standard-er-format"></a>自訂標準 ER 格式

### <a name="create-the-custom-er-format"></a>建立自訂 ER 格式

在此方案中，您是 Litware, Inc. 的代表，該公司現行被選為活動 ER 設定提供者。 您必須使用 **Intrastat 報表** 設定作為基礎來建立新的 ER 格式設定。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **Intrastat 模型**，然後選取 **Intrastat 報表**。 Litware, Inc. 將使用此 ER 格式設定的 1.9 版作為自訂版本的基礎。
3. 選取 **建立設定** 以打開下拉式對話方塊。 您可以使用此對話方塊為自訂付款格式建立新設定。
4. 在 **新建** 欄位組，選取 **名稱來源：Intrastat 報表，Microsoft**。
5. 在 **名稱** 欄位中，輸入 **Intrastat report Litware**。
6. 選取 **建立設定** 以建立新格式。

建立 **Intrastat 報表 Litware** ER 格式設定的 1.9.1 版。 此版本的 [狀態](general-electronic-reporting.md#component-versioning)為 **草稿**，可以進行編輯。 您自訂 ER 格式的目前內容與 Microsoft 提供格式的內容相符。

### <a name="make-the-custom-format-runnable"></a>使自訂格式可執行

現在您的自訂格式的第一個版本已經建立並且狀態為 **草稿**，您可以執行該格式進行測試。 若要執行報告，請使用參考您的自訂 ER 格式的付款方式處理廠商付款。 在預設情況下，當您從應用程式調用 ER 格式時，僅 [考慮](general-electronic-reporting.md#component-versioning)狀態為 **已完成** 或 **共用** 的版本。 此行為有助於防止使用具有未完成設計的 ER 格式。 但是，對於您的測試執行，您可以強制應用程式使用狀態為 **草稿** 的 ER 格式版本。 這樣，如果需要進行任何修改，您可以調整目前的格式版本。 如需相關資訊，請參閱[適用性](electronic-reporting-destinations.md#applicability)。

若要使用 ER 格式的草稿版本，您必須明確標記 ER 格式。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊，將 **執行設定** 選項設定為 **是**，然後選取 **確定**。
4. 選取 **編輯** 根據需要使目前的頁面處於可編輯狀態。
5. 在左側窗格的設定樹狀結構中，選取 **Intrastat 報表 Litware**。
6. 將 **執行草稿** 選項設定為 **是** 然後選取 **儲存**。

    ![在設定頁面上執行草稿選項。](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>設定外貿參數以使用自訂 ER 格式

按照以下步驟設定外貿參數，以便您可以使用自訂格式。

1. 進入 **稅收**\>**設定**\>**外貿**\>**外貿參數**。
2. 在 **外貿參數** 頁，在 **電子報表** FastTab，在 **檔案格式對應** 欄位，選取 **Intrastat 報表 Litware**。
3. 在 **報表格式對應** 欄位，選取 **Intrastat 報表 Litware**。
4. 選取 **儲存**。

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>設定自訂格式以使用下載的報表範本

### <a name="review-the-first-downloaded-excel-template"></a>查看第一個下載的 Excel 範本

1. 在 Excel 桌面應用程式中，打開您之前下載的 **ERIntrastatReportDemo1.xlsx** 範本檔案。
2. 驗證範本是否包含命名範圍，以在產生的文件中建立報表頁頭、報表詳情和報表頁尾區塊。

    ![Excel 範本 1 在桌面應用程式中的配置。](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>以自訂 ER 格式替換現行 Excel 範本

您必須將新的 Excel 範本新增到自訂 ER 格式。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在左側窗格的設定樹狀結構中，展開 **Intrastat 模型**\>**Intrastat 報表**，然後選取 **Intrastat 報表 Litware** 設定。
3. 選取 **設計工具**。
4. 在 **格式設計工具** 頁面上，在動作窗格上，選取 **顯示詳情**。
5. 確保選中 **Intrastat: Excel** 根格式組件，然後在動作窗格的 **匯入** 索引標籤上的 **匯入** 組中，選取 **從 Excel 更新**。
6. 在 **從 Excel 更新** 對話方塊，選取 **更新範本**。
7. 在 **開啟** 對話方塊中，瀏覽並選取您之前下載的 **ERIntrastatReportDemo1.xlsx** 檔案，然後選取 **開啟**。
8. 選取 **確定**。
9. 選取 **儲存**。

![新增新 Excel 範本後 ER 格式設計工具中的格式結構。](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>更改資料繫結以在產生的報表中顯示項目描述

1. 在 **格式設計工具** 頁面上，選取 **對應** 索引標籤。
2. 展開 **Intrastat**\>**報表明細**，並選取 **商品代碼** 組件。
3. 選取 **編輯公式**。
4. 將繫結公式從 `@.CommodityCode` 更改為 `CONCATENATE(@.CommodityCode, " ", @.ProductName)`。
5. 選取 **儲存**。

![為在 ER 格式設計工具中顯示項目描述而設定的繫結。](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>產生 Intrastat 報表控制報表

先，確保您在 **Intrastat** 頁面上有用於報表的 Intrastat 交易。

![Intrastat 頁面上的交易。](./media/er-paginate-excel-reports-transactions1.gif)

然後使用自訂 ER 格式產生 Intrastat 報表的控制報表。

1. 進入 **稅金**\>**報表**\>**外貿**\>**Intrastat**。
2. 在 **Intrastat** 頁面，在動作窗格上，選取 **輸出**\>**報表**。
3. 在 **Intrastat 報表** 對話方塊，請按照以下步驟執行報表：

    1. 設定 **開始日期** 和 **結束日期** 欄位以將特定的 Intrastat 交易加入到報表中。
    2. 將 **產生檔案** 選項設定為 **否**。
    3. 將 **產生報表** 選項設為 **是**。
    4. 選取 **確定**。

4. 下載並儲存產生的文件。
5. 在 Excel 中打開文件，然後查看文件。

    ![在桌面應用程式中產生的 Excel 文件。](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>設定自訂格式以對產生的文件進行分頁

### <a name="review-the-second-downloaded-excel-template"></a>查看第二個下載的 Excel 範本

1. 在 Excel 中，打開您之前下載的 **ERIntrastatReportDemo2.xlsx** 範本檔案。
2. 將此範本與 **ERIntrastatReportDemo1.xlsx** 範本進行比較，並驗證它是否包含幾個新的 Excel 名稱，以便在產生的文件中建立和填入特定於頁面的區塊：

    - 新增 **ReportPageHeader** 範圍以建立頁頭。
    - 新增 **ReportPageFooter** 範圍以建立頁尾。
    - 將 **ReportPageFooter\_PageLines** 儲存格設定為顯示每頁的交易數。
    - 將 **ReportPageFooter\_PageAmount** 儲存格設定為顯示每頁的交易總數。
    - 將 **ReportPageFooter\_PageWeight** 儲存格設定為顯示每頁的交易總重量。
    - 將 **ReportPageFooter\_RunningCounterLines** 儲存格設定為顯示從報表開始到目前頁面的交易執行計數器。
    - 將 **ReportPageFooter\_RunningTotalAmount** 儲存格設定為顯示從報表開頭到目前頁面的所有交易的總金額。
    - 將 **ReportPageFooter\_RunningTotalWeight** 儲存格設定為顯示從報表開頭到目前頁面的交易的總重量。

    ![Excel 範本 2 在桌面應用程式中的配置。](./media/er-paginate-excel-reports-template2a.gif)

    將此範本的 **CommodityCode** 儲存格設定為換行儲存格文字。 由於交易詳情列已設定為自動適應列高，因此當 **CommodityCode** 儲存格中的文字被換行時，整列的高度必須自動更改。

    ![將 CommodityCode 儲存格設定為換行儲存格文字。](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>以自訂 ER 格式重複替換現行 Excel 範本

1. 按照本主題的[替換自訂 ER 格式中的現行 Excel 範本](#replace-template)章節中的步驟進行動作。 但可在步驟 7 中，選取 **ERIntrastatReportDemo2.xlsx** 檔案。
2. 在 **格式設計工具** 頁面上，展開 **Intrastat**。
3. 命名已新增到可編輯 ER 格式的[範圍](er-fillable-excel.md#range-component)格式組件，以將結構與應用的 Excel 範本的結構同步：

    1. 選取與 Excel 名稱 **ReportPageHeader** 關聯的 **範圍** 組件。
    2. 在 **格式** 索引標籤，在 **名稱** 欄位，輸入 **報表頁頭**。
    3. 選取與 Excel 名稱 **ReportPageFooter** 關聯的 **範圍** 組件。
    4. 在 **格式** 索引標籤，在 **名稱** 欄位，輸入 **報表頁尾**。

4. 選取 **儲存**。

![替換 Excel 範本後 ER 格式設計工具中的格式結構。](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>改變格式結構實現文件分頁

1. 在 **格式設計工具** 頁面的左側窗格的格式樹狀結構中，選取 **Intrastat** 根組件。
2. 選取 **新增**。
3. 在 **新增** 對話方塊中，選取 **Excel** 組件組中的[頁面](er-fillable-excel.md#page-component)組件。
4. 在下拉式 **組件屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **報表頁**。 然後選取 **確定**。
5. 若要將 **報表頁頭** 組件用作每個產生頁面的頁頭，請執行以下步驟：

    1. 選取 **報表頁頭** 組件，然後選取 **剪下**。
    2. 選取 **報表頁** 組件，然後選取 **貼上**。
    3. 展開 **報表頁**。
    4. 若要強制 **頁面** 組件將此範圍 [視為](er-fillable-excel.md#page-component-structure)頁頭，請選取 **報表頁頭**，然後在 **格式** 索引標籤上的 **複寫方向** 欄位中，選取 **無複寫**。

6. 若要對產生的文件進行分頁以便考慮報表行上的內容，請執行以下步驟：

    1. 選取 **報表行** 組件，然後選取 **剪下**。
    2. 選取 **報表頁** 組件，然後選取 **貼上**。

7. 若要在報表行之後但在最終頁尾之前包含報表頁尾，請執行以下步驟：

    1. 選取 **報表頁尾** 組件，然後選取 **剪下**。
    2. 選取 **報表頁** 組件，然後選取 **貼上**。

8. 若要將 **報表頁尾** 組件用作每個產生頁面的頁尾，請執行以下步驟：

    1. 選取 **報表頁尾** 組件，然後選取 **剪下**。
    2. 選取 **報表頁** 組件，然後選取 **貼上**。
    3. 若要強制 **頁面** 組件將此範圍 [視為](er-fillable-excel.md#page-component-structure)頁尾，請選取 **報表頁尾**，然後在 **格式** 索引標籤上的 **複寫方向** 欄位中，選取 **無複寫**。

![實作文件分頁後格式化 ER 格式設計工具中的結構。](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>新增資料來源以計算頁尾總數

您必須設定新資料來源來計算頁面總數、執行計數器和執行總值，並將它們顯示在頁尾區塊。 我們建議您為此目的使用[資料收集](er-data-collection-data-sources.md)資料來源。

1. 在 **格式設計工具** 頁面上，選取 **對應** 索引標籤。
2. 選取 **新增根**，然後按照以下步驟動作：

    1. 在 **新增資料來源** 對話方塊，在 **一般** 區塊中，選取 **空白容器**。
    2. 在 **「空白容器」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Total**。
    3. 選取 **確定**。

3. 選取 **總計** 資料來源，選取 **新增**，然後按照以下步驟動作：

    1. 在 **新增資料來源** 對話方塊，在 **一般** 區塊中，選取 **空白容器**。
    2. 在 **「空白容器」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Page**。
    3. 選取 **確定**。

4. 再次選取 **新增**，然後按照以下步驟動作：

    1. 在 **新增資料來源** 對話方塊，在 **一般** 區塊中，選取 **空白容器**。
    2. 在 **「空白容器」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Running**。
    3. 選取 **確定**。

5. 選取 **Total.Page** 資料來源，選取 **新增**，然後按照以下步驟動作：

    1. 在 **新增資料來源** 對話方塊，在 **函數** 區塊中，選取 **資料收集**。
    2. 在 **「資料收集」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Amount**。
    3. 在 **項目類型** 欄位中，選取 **實數**。
    4. 將 **收集所有值** 選項設定為 **是**。
    5. 選取 **確定**。

6. 再次選取 **新增**，然後按照以下步驟動作：

    1. 在 **新增資料來源** 對話方塊，在 **函數** 區塊中，選取 **資料收集**。
    2. 在 **「資料收集」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Weight**。
    3. 在 **項目類型** 欄位中，選取 **實數**。
    4. 將 **收集所有值** 選項設定為 **是**。
    5. 選取 **確定**。

7. 選取 **Total.Running** 資料來源，選取 **新增**，然後按照以下步驟動作：

    1. 在 **新增資料來源** 對話方塊，在 **函數** 區塊中，選取 **資料收集**。
    2. 在 **「資料收集」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Amount**。
    3. 在 **項目類型** 欄位中，選取 **實數**。
    4. 將 **收集所有值** 欄位設定為 **是**。
    5. 選取 **確定**。

8. 再次選取 **新增**，然後按照以下步驟動作：

    1. 在 **新增資料來源** 對話方塊，在 **函數** 區塊中，選取 **資料收集**。
    2. 在 **「資料收集」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Weight**。
    3. 在 **項目類型** 欄位中，選取 **實數**。
    4. 將 **收集所有值** 欄位設定為 **是**。
    5. 選取 **確定**。

9. 再次選取 **新增**，然後按照以下步驟動作：

    1. 在 **新增資料來源** 對話方塊，在 **函數** 區塊中，選取 **資料收集**。
    2. 在 **「資料收集」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Lines**。
    3. 在 **項目類型** 欄位中，選取 **整數**。
    4. 將 **收集所有值** 欄位設定為 **是**。
    5. 選取 **確定**。

10. 選取 **儲存**。

### <a name="add-data-sources-to-control-page-footer-visibility"></a>新增資料來源以控制頁尾可見性

如果您計畫控制頁尾可見性，並且不打算在包含交易的最終頁面上包含頁尾，請設定新資料來源以計算所需的執行計數器。

1. 在 **格式設計工具** 頁面上，選取 **對應** 索引標籤。
2. 選取 **Total.Running** 資料來源，選取 **新增**。
3. 在 **新增資料來源** 對話方塊，在 **函數** 區塊中，選取 **資料收集**。
4. 在 **「資料收集」資料來源屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **Lines2**。
5. 在 **項目類型** 欄位中，選取 **整數**。
6. 將 **收集所有值** 選項設定為 **是**。
7. 選取 **確定**。
8. 選取 **儲存**。

![在 ER 格式設計工具中新增了資料來源。](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>設定繫結以收集總值

1. 在 **格式設計工具** 頁面，在格式樹狀結構中，展開 **報表行** 組件，然後選取巢狀 **發票值** 組件。
2. 選取 **編輯公式**。
3. 將繫結公式從 `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")` 更改為 `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`。

    > [!NOTE]
    > 除了將每個迭代交易的金額值放入 Excel 儲存格之外，此繫結還收集資料收集 **Total.Page.Amount** 資料來源中的值。

4. 選取巢狀 **重量** 組件。
5. 選取 **編輯公式**。
6. 將繫結公式從 `@.'$RoundedWeight'` 更改為 `Total.Page.Weight.Collect(@.'$RoundedWeight')`。

    > [!NOTE]
    > 除了將每個迭代交易的重量值放入 Excel 儲存格之外，此繫結還收集 **Total.Page.Weight** 資料來源中的值。

![用於在 ER 格式設計工具中收集總值的設定繫結。](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>設定繫結以填入頁尾總數

1. 在 **格式設計工具** 頁面的格式樹狀結構中，展 **開報表頁尾** 組件，選取參考 Excel **ReportPageFooter\_PageAmount** 儲存格的巢狀 **範圍** 組件，然後執行以下步驟：

    1. 在右窗格的資料來源樹狀結構中，選取 **Total.Page.Amount.Sum()** 項目。
    2. 選取 **繫結**。
    3. 選取 **編輯公式**。
    4. 將公式更新為 `Total.Page.Amount.Sum(false)`。

    > [!NOTE]
    > 您必須將此函數的參數指定為 **False** 以保留目前頁面的收集資料，因為需要此資料來計算執行總數、每頁總行數和執行行數。

2. 在格式樹狀結構中，選取參考 Excel **ReportPageFooter\_PageWeight** 儲存格的巢狀 **範圍** 組件，然後執行以下步驟：

    1. 在右窗格的資料來源樹狀結構中，選取 **Total.Page.Weight.Sum()** 項目。
    2. 選取 **繫結**。
    3. 選取 **編輯公式**。
    4. 將公式更新為 `Total.Page.Weight.Sum(false)`。

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>設定繫結以填入執行總數

1. 在 **格式設計工具** 頁面的格式樹狀結構中，展 **開報表頁尾** 組件，選取參考 Excel **ReportPageFooter\_RunningTotalAmount** 儲存格的巢狀 **範圍** 組件，然後執行以下步驟：

    1. 在右窗格的資料來源樹狀結構中，選取 **Total.Running.Amount.Collect()** 項目。
    2. 選取 **繫結**。
    3. 選取 **編輯公式**。
    4. 將公式更新為 `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))`。

    > [!NOTE]
    > `Total.Running.Amount.Sum(false)` 運算元回傳之前收集的金額執行總計。 `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` 運算元回傳目前頁面的總金額。 您必須將第二個運算元的巢狀函數的參數指定為 **True**，以便在將此值放入 `Total.Page.Amount` 執行總計收集時立即重設 `Total.Running.Amount` 資料收集。 指定的參數必須從 0 (零) 值開始收集下一頁總計。
    >
    > 調用 `Total.Running.Amount.Sum(false)` 函數在現行頁面的 Excel **ReportPageFooter\_RunningTotalAmount** 儲存格中輸入執行總計的金額。

2. 在格式樹狀結構中，選取參考 Excel **ReportPageFooter\_RunningTotalWeight** 儲存格的巢狀 **範圍** 組件，然後執行以下步驟：

    1. 在右窗格的資料來源樹狀結構中，選取 **Total.Running.Weight.Collect()** 項目。
    2. 選取 **繫結**。
    3. 選取 **編輯公式**。
    4. 將公式更新為 `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))`。

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>設定繫結填入頁面執行計數器

1. 在 **格式設計工具** 頁面的格式樹狀結構中，展 **開報表頁尾** 組件，選取參考 Excel **ReportPageFooter\_RunningCounterLines** 儲存格的巢狀 **範圍** 組件。
2. 選取 **編輯公式**。
3. 新增公式 `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))`。

    > [!NOTE]
    > 此公式回傳整個報表的收集金額值的數量。 此數字等於現行已迭代的交易數。 同時，公式將回傳值收集到 **Total.Running.Lines** 集合中。

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>設定繫結填入頁尾計數器

1. 在 **格式設計工具** 頁面的格式樹狀結構中，展 **開報表頁尾** 組件，選取參考 Excel **ReportPageFooter\_PageLines** 儲存格的巢狀 **範圍** 組件。
2. 選取 **編輯公式**。
3. 新增公式 `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)`。

    > [!NOTE]
    > 此公式將現行頁面上的交易數量計算為整個報表的 **Total.Page.Amount.Result** 中收集的交易數量與此階段儲存在 **Total.Running.Lines.Sum**。 由於目前頁面的交易數儲存在參考 Excel **ReportPageFooter\_RunningCounterLines** 儲存格的 **範圍** 組件繫結中的 **Total.Running.Lines** 中，因此尚未包括目前頁面上的交易數。 因此，此差異等於目前頁面上的交易數。

![在 ER 格式設計工具中設定了用於填入頁尾計數器的繫結。](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>設定組件可見性

您可以在產生的文件的特定頁面上更改頁頭和頁尾的可見性，以隱藏以下元素：

- 第一頁上的頁頭，因為報表頁頭已經包含欄標題
- 任何頁面上的頁頭，如果沒有交易，就會發生最後一頁的交易
- 任何頁面上的頁尾，如果沒有交易，就會發生最後一頁的交易

若要更改可見性，請更新 **報表頁頭** 和 **報表頁尾** 組件的 **已啟用** 屬性。

1. 在 **格式設計工具** 頁面的格式樹狀結構中，展開 **報表頁面** 組件，選取巢狀的 **報表頁頭** 組件，然後執行以下步驟：

    1. 為 **已啟用** 欄位選取 **編輯**。
    2. 在 **公式設計工具** 頁面的 **公式** 欄位中，輸入以下運算式：

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. 在格式樹狀結構中，選取巢狀的 **報表頁尾** 組件，然後按照以下步驟動作：

    1. 為 **已啟用** 欄位選取 **編輯**。
    2. 在 **公式設計工具** 頁面的 **公式** 欄位中，輸入以下運算式：

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` 構造用於計算目前頁面的交易數量。 `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` 構造用於將目前頁面上的交易數量新增到集合中，以正確處理下一頁頁尾的可見性。
    >
    > `Total.Running.Lines` 集合在這裡不能重新使用，因為基礎組件的 **已啟用** 屬性是在處理巢狀組件的繫結 **之後** 處理的。 處理 **已啟用** 屬性時，`Total.Running.Lines` 集合已經增加了目前頁面上的交易數。

3. 選取 **儲存**。

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>產生 Intrastat 報表控制報表 (更新)

1. 確保您在 **Intrastat** 頁面上有 24 筆交易。 重複本主題[產生 Intrastat 報表控制報表](#generate-intrastat-control-report)章節中的步驟以產生和查看控制報表。

    所有交易都顯示在第一頁上。 該頁總數和計數器等於報表總數和計數器。 頁面標題範圍隱藏在第一頁，因為報表標題已包含欄標題。 頁頭和頁尾隱藏在第二頁，因為該頁不包含交易。

    ![在桌面應用程式中產生的 Excel 文件。](./media/er-paginate-excel-reports-document2.gif)

2. 透過將 **項目編號** 代碼從 **D00006** 更改為 **L0010**，更新 **Intrastat** 頁面上的兩個交易記錄。 請注意，新項目的產品名稱 **主動式立體聲喇叭對** 比原始項目的產品名稱 **標準喇叭** 長。 這種情況會強制文字在產生文件的相應儲存格中換行。 現在必須更新文件分頁以及與頁面相關的匯總和計數。 重複[產生 Intrastat 報表控制報表](#generate-intrastat-control-report)章節中的步驟以產生和查看控制報表。

    目前，交易呈現在兩個頁面上，並且正確計算了頁面總數和計數器。 頁頭範圍在第一頁上正確隱藏，在第二頁上可見。 頁尾因包含交易在兩個頁面上都會顯示。

    ![更新了桌面應用程式中產生的 Excel 文件。](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>常見問題

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>有什麼方法可以識別頁面格式組件何時處理最終頁面？

**頁面** 組件[不會揭露](er-fillable-excel.md#page-component-limitations)已處理頁面數和產生文件中的總頁數的相關資訊。 不過，您可以設定 ER [公式](er-formula-language.md)以識別最後一頁。 範例如下：

- 使用 **報表頁面** 組件計算已處理的交易總數。 您可以使用公式 `COUNT(Total.Page.Amount.Result)` 進行此計算。 
- 根據為 **報表行** 組件設定的 `model.CommodityRecord` 繫結計算必須處理的交易總數。 您可以使用公式 `COUNT(model.CommodityRecord)` 進行此計算。
- 比較兩個數字以識別最後一頁。 當兩個值相等時，產生最後一頁。

> [!NOTE]
> 我們建議您僅在 **報表行** 組件的 **已啟用** 屬性不包含可能在執行階段為繫結[記錄清單](er-formula-supported-data-types-composite.md#record-list)的某些迭代[記錄](er-formula-supported-data-types-composite.md#record)回傳 [False](er-formula-supported-data-types-primitive.md#boolean) 的公式時使用此方法。

## <a name="additional-resources"></a>其他資源

- [設計用於產生 Excel 格式文件的設定](er-fillable-excel.md)
- [以電子報表 (ER) 格式使用資料收集資料來源](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
