---
title: 使用條碼資料來源產生條碼圖像
description: 本主題介紹如何使用條碼資料來源產生條碼圖像。
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: a5a396080d8b5dd4c2ed9a0eb15c1286e8799ebf
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460293"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>使用條碼資料來源產生條碼圖像

[!include[banner](../includes/banner.md)]

您可以使用[電子報表 (ER)](general-electronic-reporting.md)設計 ER 格式組件的架構，您可以執行這些組件來產生所需的電子和可列印輸出文件。 若要在 Microsoft Office 格式中產生輸出文件，您必須使用 Microsoft Excel 文件或 Microsoft Word 文件作為報告範本來指定報告配置。 [ER 作業設計工具](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base)允許您附加 Excel 或 Word 文件作為 ER 格式的範本。 附加範本中的以下命名元素與設定的格式組件的元素相關聯：

- Word 中的內容控制
- Excel 中的命名工作表、範圍、儲存格、形狀和圖像

這些命名元素用作執行 ER 格式時在產生的文件中輸入的資料的預留位置。 ER 格式元素已繫結到資料來源。 這些資料來源指定將在執行階段輸入到產生的文件中的資料。 如需相關資訊，[在使用 ER 產生的檔案中嵌入圖像和形狀](electronic-reporting-embed-images-shapes.md)

ER 現在支援 **條碼** 資料來源類型。 因此，您現在可以產生表示指定文字的條碼的圖像。 當您設定 ER 格式時，您可以指定 **條碼** 類型的資料來源來產生條碼圖像。 然後，您可以將這些圖像新增到產生的商業文件中，例如訂單、發票、裝箱單和收據。 您還可以將它們新增到各種標籤中，例如產品和貨架標籤，以及包裝和出貨標籤。

以下預留位置可在報告範本中用於輸入條碼圖像：

- Word 的[圖片](/office/client-developer/word/content-controls-in-word)內容控制
- Excel 中的[圖片](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344)物件

透過使用 **條碼** 類型的資料來源，您可以產生以下格式的條碼：

- 一維條碼：

    - Codabar
    - 編碼 39
    - 編碼 93
    - 編碼 128
    - EAN-8
    - EAN-13
    - ITF-14
    - 智慧型郵件
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- 二維條碼：

    - Aztec
    - 資料矩陣
    - QR 代碼

當您設定 **條碼** 資料來源，您可以定義用於產生圖像的特定轉譯參數：

- **寬度** – 以像素為單位指定條碼的寬度。 值為 **0** (零) 表示使用預設寬度。 不同格式的含義可能有所不同。
- **高度** – 以像素為單位指定條碼的高度。 值為 **0** (零) 表示使用預設高度。 不同格式的含義可能有所不同。
- **邊距** – 以像素為單位指定條碼邊距的大小。 邊距是條碼兩側必須保持清晰的區域 (靜區)。 值為 **0** (零) 表示使用預設邊距。 不同格式的含義可能有所不同。
- **輸出內容** – 將值設定為 **是** 產生包含編碼資訊的條碼圖像作為文字。 預設值為 **否**。
- **編碼** – 指定在產生的條碼圖像中編碼的字元類型。 在預設情況下，使用 **UTF-8** 編碼。

> [!IMPORTANT]
> 當您新增新 **條碼** 資料來源，您必須將其作為巢狀元素放置在另一個項目 (容器) 下。
>
> 當您將 **條碼** 資料來源繫結到格式中的儲存格元素，並且儲存格元素表示 Word 內容控制項或 Excel 圖片，資料來源在該繫結中顯示為具有單個參數的函數 **字串** 類型。 您必須使用此參數來指定應轉換為條碼圖像並在掃描產生的條碼時讀取的文字。

如需此函數的相關資訊，請完成本主題中的範例。

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>範例：產生包含對應付金額進行編碼的條碼的付款支票

這個範例顯示了 **系統管理員** 或 **電子報表函數顧問** 角色的使用者如何設定 ER 格式，該格式包含範本，用於產生包含條碼的 Excel 格式的輸出文件。 以下是所涉及步驟的概述。

1. [完成先決條件](#ExamplePrerequisites)
2. [啟用設定提供者](#ExampleProvider)
3. [匯入提供的 ER 解決方案](#ExampleImportSolution)。
4. [產生付款支票](#ExampleGenerateCheque)。
5. [查看產生的付款支票](#ExampleReviewGeneratedCheque)。
6. [修改提供的 ER 解決方案的格式](#ExampleModifyFormat)。

    1. [套用新的支票範本](#ExampleModifyFormatApplyTemplate)。
    2. [新增新的條碼資料來源](#ExampleModifyFormatAddDataSource)。
    3. [繫結新的格式元素 ](#ExampleModifyFormatBindFormatElement).
    4. [使修改後的版本可用於測試執行](#ExampleModifyFormatMakeVersionAvailable)。

        1. [完成修改格式版本](#CompleteToRun)。
        2. [使草稿版本可供使用](#MarkToRun)。

7. [產生付款支票](#ExampleGenerateCheque2)。
8. [將產生的支票轉換為 PDF](#ExampleConvertToPDF)。

在此範例中，您將使用提供的已設定為產生付款支票的 ER 解決方案。 此解決方案產生付款支票，其中應付金額以數字和文字形式寫入。 您將修改此 ER 解決方案，以便支票還包括產生的條碼，其中對應付金額進行了編碼，並且可以使用條碼掃描儀讀取。

這些步驟可以在 Microsoft Dynamics 365 Finance 中的 **USMF** 公司完成。

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>完成先決條件

若要完成此範例，您必須有權存取 Finance 中的 USMF 公司並擔任以下角色之一：

- 電子報表函數
- 系統管理員

如果您還沒有完成[在使用 ER 產生的文件中嵌入圖像和圖形](electronic-reporting-embed-images-shapes.md)主題中的範例，請下載以下設定的 ER 解決方案樣本。

| 內容描述         | 檔案名稱                   |
|-----------------------------|-----------------------------|
| ER 資料模型設定 | [支票.xml 的模型](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)      |
| ER 格式設定     | [支票列印格式.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |

此外，下載以下 Excel 檔案，其中包含所提供 ER 解決方案的修改範本。

| 內容描述 | 檔案名稱                 |
|---------------------|---------------------------|
| 報告範本     | [支票範本 Excel.xlsx](https://download.microsoft.com/download/3/b/d/3bd3b944-da8f-43b4-8533-3c1292a4c3ef/CheckTemplateExcel.xlsx) |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>啟用設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面，在 **設定提供者** 區段，確保列出 **Litware, Inc.** 樣本公司的[設定提供者](general-electronic-reporting.md#Provider)，並且被標記為有效。 如果沒有列出它，或者沒有被標記為有效，請按照[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)主題中的步驟進行。

![在本地化設定頁面上將範例公司設定為有效。](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>匯入提供的 ER 解決方案

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定** 區塊中，選取 **報表設定** 圖格。
3. 在 **設定** 頁面，如果設定樹狀結構中沒有 **支票的模型** 設定，請按照以下步驟匯入 ER 資料模型設定。

    1. 在動作窗格上，選取 **交換**\>**從 XML 檔案載入**。
    2. 在對話方塊中，選取 **瀏覽**，找到並選取 **支票.xml 的模型** 檔案，然後選取 **確定**。

4. 如果設定樹狀結構中沒有 **支票列印格式** 設定，請按照以下步驟匯入 ER 格式設定：

    1. 在動作窗格上，選取 **交換**\>**從 XML 檔案載入**。
    2. 在對話方塊中，選取 **瀏覽**，找到並選取 **支票資料列印格式.xml** 檔案，然後選取 **確定**。

5. 在設定樹狀結構中，展開 **支票模型**。
6. 查閱設定樹狀結構中匯入的 ER 設定清單。

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>產生付款支票

1. 進入 **現金和銀行管理**\>**銀行帳戶**\>**銀行帳戶**。
2. 在 **銀行帳戶** 頁面，選取 **USMF OPER** 帳戶。
3. 在銀行帳戶詳情頁面上，在動作窗格上，在 **設定** 索引標籤，在 **配置** 分組，選取 **支票**。
4. 在 **支票配置** 頁面，選取 **編輯**。
5. 在 **一般** FastTab 上，將 **常用電子匯出格式** 設定選項為 **是**。
6. 在 **導出格式設定** 欄位中，選取您之前匯入的 **支票列印格式** ER 格式。
7. 在動作窗格上，選取 **列印測試**。
8. 在對話方塊中，將 **可轉讓支票格式** 選項設定為 **是**，然後選取 **確定**。

    ![支票配置 - 列印測試對話方塊。](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>查看產生的付款支票

- 在 Excel 中打開產生的支票。
2. 查看產生的支票。

    ![在 Excel 中產生付款支票。](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>修改提供的 ER 解決方案的格式

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>套用新的支票範本

您可以使用 Excel 桌面應用程式打開您之前匯入的 **支票範本 Excel.xlsx** 檔案。 請注意，此範本與您在提供的 ER 解決方案中用於產生付款支票的範本不同。 此外，它還包括條碼圖像的 **AmountBarcode** 元素。

![Excel 範本中的 AmountBarcode 元素。](./media/er-barcode-data-source-cheque2.png)

您現在必須修改 ER 解決方案，然後[重新申請](modify-electronic-reporting-format-reapply-excel-template.md)修改後的範本。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定** 區段中，選取 **報告設定**。
3. 在 **設定** 頁面，在設定樹狀結構中，展開 **支票模型**，並選取 **支票列印格式**。
4. 在動作窗格上，選取 **設計工具**。
5. 在 ER 作業設計工具中，選取 **對應** 索引標籤，然後在左側的格式樹狀結構窗格中，選取 **展開/折疊**。
6. 請注意，所有儲存格格式元素都繫結到適當的資料來源。

    ![在 ER 作業設計工具中將儲存格格式元素繫結到資料來源。](./media/er-barcode-data-source-cells-bound.png)

7. 選取頁面右側的 **格式** 索引標籤。
8. 在行動窗格中，選取省略號 (**...**)，然後選取 **匯入**。
9. 在裡面 **匯入** 分組，選取 **從 Excel 更新**，然後選取 **更新範本**。
10. 在對話方塊中，瀏覽儲存在電腦上的 **支票範本 Excel.xlsx** 檔案，選取它，然後選取 **確定** 以確認應套用的所選範本。
11. 選取 **對應** 索引標籤，然後在左側的格式樹狀結構窗格中，選取 **展開/折疊**。
12. 請注意，**AmountBarcode** 儲存格元素已新增到格式中。 這個元素與 **AmountBarcode** 元素有關，該元素已被新增到修改後的 Excel 範本中，作為條碼圖像的預留位置。

    ![AmountBarcode 儲存格元素新增到 ER 作業設計工具中的格式。](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>新增新的條碼資料來源

接下來，您必須新增 **條碼** 類型的新資料來源。

1. 在 ER 作業設計工具中，在頁面右側的 **對應** 索引標籤上，選取 **列印** 資料來源。
2. 選取 **新增**，然後，在 **函數** 組，選取 **條碼** 資料來源類型。

    ![選取條碼資料來源類型。](./media/er-barcode-data-source-add.png)

3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **barcode**。
4. 在裡面 **條碼格式**，選取 **代碼 128**。
5. 在 **寬度** 欄位中，輸入 **500**。
6. 選取 **確定**。

    ![資料來源屬性對話方塊。](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>繫結新的格式元素

接下來，您必須將新格式元素繫結到剛剛新增的資料來源。

1. 在 ER 作業設計工具中，在頁面右側的 **對應** 索引標籤上，選取 **列印\\條碼** 資料來源。
2. 在左側的格式樹狀結構窗格中，選取 **AmountBarcode** 儲存格元素，然後選取 **繫結**。
3. 在動作窗格上，選取 **顯示詳情**。
4. 請注意，因為 **條碼** 資料來源在繫結中表示為包含單個參數的函數，繫結格式元素的名稱已自動作為該參數的參數。

    ![ER 作業設計工具中條形碼資料來源的詳情。](./media/er-barcode-data-source-bind1.png)

5. 選取 **編輯公式** 調整繫結程式。

    您不希望返回儲存格元素的名稱。 因此，您必須設定運算式，該運算式返回包含現行支票應付金額的文字。 因為父系 **ChequeLines** 範圍繫結到 **model.cheques** 資料來源，現行支票的應付金額可以在 **model.cheques.attributes.amount** 欄位的 **真實** 資料類型中獲得。

6. 在 **公式** 欄位中，輸入 **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**。
7. 選取 **儲存**，然後關閉[ER 公式設計工具](general-electronic-reporting-formula-designer.md)。
8. 請注意，繫結已被調整。

    ![在 ER 作業設計工具中調整了繫結。](./media/er-barcode-data-source-bind2.png)

9. 選取 **儲存**，然後關閉ER 作業設計工具。

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>使修改後的版本可用於測試執行

在預設情況下，當您執行 ER 格式時，只使用狀態為 **已完成** 和 **共用** 的版本。

如果您已完成更改，則可以使用現行草稿版本完成工作並使您的更改可供使用。 如需相關資訊，請參閱以下的[完成修改格式版本](#CompleteToRun)區段。

如果要繼續使用現行草稿版本，但必須使用它來產生支票，則必須明確指定要使用格式的草稿版本進行執行。 如需相關資訊，請參閱[使草稿版本可供使用](#MarkToRun)區段。

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>完成修改格式版本

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定** 區段中，選取 **報告設定**。
3. 在 **設定** 頁面，在設定樹狀結構中，展開 **支票模型**，並選取 **支票列印格式**。
4. 在 **版本** FastTab 上，選取有 **草稿** 狀態的記錄。
5. 選取 **更改狀態**，然後選取 **完成**。
6. 在對話方塊中，選取 **確定**。

現行版本的狀態從 **草稿** 更改到 **已完成**，以及建立有 **草稿** 狀態的新版本。 您可以使用這個新的草稿版本來套用其他更改。

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>使草稿版本可供使用

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定** 區段中，選取 **報告設定**。
3. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
4. 在對話方塊中，將 **可執行設定** 選項設定為 **是**，然後選取 **確定**。
5. 在設定樹狀結構中，展開 **支票模型**，並選取 **支票列印格式**。
6. 將 **執行草稿** 選項設定為 **是**。
7. 選取 **儲存**。

所選格式的草稿版本在執行所選格式時被標記為可用。

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>產生付款支票

1. 進入 **現金和銀行管理**\>**銀行帳戶**\>**銀行帳戶**。
2. 在 **銀行帳戶** 頁面，選取 **USMF OPER** 帳戶。
3. 在銀行帳戶詳情頁面上，在動作窗格上，在 **設定** 索引標籤，在 **配置** 分組，選取 **支票**。
4. 在 **支票配置** 頁面，在動作窗格上，選取 **列印測試**。
5. 在對話方塊中，將 **可轉讓支票格式** 選項設定為 **是**。
6. 選取 **確定**。
7. 查看產生的支票。 請注意，已產生條碼以對支票的應付金額進行編碼。

    ![在 Excel 中產生帶有條碼的付款支票。](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> 如果 **條碼** 資料來源的參數不符合條碼格式所特有的適當要求，就會出現例外狀況。 例如，當調用 **條碼** 資料來源為所提供的文字產生 [EAN-8](https://wikipedia.org/wiki/EAN-8) 條碼時，如果文字的長度超過 7 個字元，就會出現例外狀況。

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>將產生的支票轉換為 PDF

如中所述[產生可列印的 FTI 表格](er-generate-printable-fti-forms.md#finland)主題，您可以使用特殊字型在產生的文件中產生條碼。 在這種情況下，產生的文件的其他轉換可能取決於轉換環境中該字型的可用性。 例如，如果您嘗試將文件轉換為 PDF 格式或在缺少字型的環境中預覽，則條碼將無法正確呈現。

但是，當您使用 **條碼** 資料來源產生條碼，這些條碼的呈現不依賴於任何字型。 因此，您可以輕鬆地將包含條碼的文件轉換為 PDF 格式。 下圖顯示了根據設定的 ER [目的地](electronic-reporting-destinations.md)的設定，產生的付款支票已經[轉換](electronic-reporting-destinations.md#OutputConversionToPDF)為 PDF 的預覽。

![付款支票的 PDF 預覽。](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>限制

> [!NOTE]
> 產生的某些類型的條碼具有固定的外觀比例。 如果您打開了 **電子報表架構中 EPPlus 庫的使用** 函數，以便在 ER 中處理 Excel 文件，那麼這種行為是合理的。 在這種情況下，圖像被輸入到具有鎖定外觀比例的預留位置中。 因此，當範本中預留位置的尺寸對應於輸入圖像的比例時，產生的文件中的真實圖片可能會調整大小以保持所需的外觀比例。 若要防止調整圖片大小，請使用具有預期外觀比例的預留位置。

## <a name="additional-resources"></a>其他資源

- [電子報表概述](general-electronic-reporting.md)
- [電子報表目的地](electronic-reporting-destinations.md)
- [電子報表公式語言](er-formula-language.md)
- [NUMBERFORMAT 函數](er-functions-text-numberformat.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
