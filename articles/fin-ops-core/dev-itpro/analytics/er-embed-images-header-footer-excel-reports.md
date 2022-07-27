---
title: 設計 ER 格式以產生 Excel 格式的報告，並在頁首或頁尾中嵌入圖像
description: 本主題說明如何使用電子報表 (ER) 產生在頁首或頁尾中嵌入圖像和形狀的業務文件。
author: NickSelin
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3f3f77a9e6104a31995c9ee398504982fe43ac9e
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460579"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>設計 ER 格式以產生 Excel 格式的報告，並在頁首或頁尾中嵌入圖像

[!include[banner](../includes/banner.md)]

本主題說明系統管理員或電子報表職能顧問角色的使用者如何執行這些工作：

- [電子報表 (ER)](general-electronic-reporting.md)架構的設定參數。
- 匯入由 Microsoft [提供](general-electronic-reporting.md#Provider)的 ER [設定](general-electronic-reporting.md#Configuration)，用於產生[普通發票](../../../finance/accounts-receivable/create-free-text-invoice-new.md)，基於 Microsoft Excel 格式的[範本](er-fillable-excel.md#excel-file-component)。
- 建立由 Microsoft 提供的標準ER格式設定的[自訂 (衍生) ](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization)版本。
- 修改自訂 ER 格式設定，使其產生在頁尾中有公司標誌圖像的普通發票報告。

本主題中的程序可以在 **USMF** 公司完成。 無需編碼。 在開始之前，請下載並儲存以下檔案。

| 描述        | 檔案名稱 |
|--------------------|-----------|
| 公司標誌圖片 | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>內容

- [設定法律實體](#ConfigureLegalEntity)
- [設定 ER 架構](#ConfigureFramework)

    - [設定 ER 參數](#ConfigureParameters)
    - [啟用 ER 設定提供者](#ActivateProvider)

        - [查看 ER 設定提供者清單](#ReviewProvidersList)
        - [新增新的 ER 設定提供者](#AddProvider)
        - [啟用新的 ER 設定提供者](#ActivateAddedProvider)

- [匯入標準 ER 格式設定](#ImportERSolution1)

    - [匯入標準 ER 設定](#ImportERFormat)
    - [查看匯入的 ER 設定](#ReviewImportedERSolution)

- [使用標準 ER 格式列印普通發票](#PrintInvoice1)

    - [設定列印管理](#ConfigurePrintManagement1)
    - [列印普通發票](#ProcessInvoice1)

- [自訂標準 ER 格式](#CustomizeProvidedFormat)

    - [建立自訂格式](#DeriveProvidedFormat)
    - [編輯自訂格式](#ConfigureDerivedFormat)
    - [將自訂格式標記為可執行](#MarkFormatRunnable)

- [使用自訂 ER 格式列印普通發票](#PrintInvoice2)

    - [設定列印管理](#ConfigurePrintManagement2)
    - [列印普通發票](#ProcessInvoice2)

- [其他資源](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>設定法律實體

1. 進入 **組織管理**\>**組織**\>**法律實體**。
2. 在 **法人實體** 頁上，在 **報告公司標誌圖片** FastTab，選取 **改變**。
3. 在 **選取要上傳的圖片檔案** 對話方塊，選取 **瀏覽**，並選取之前下載的 **Company logo.png** 檔案。
4. 選取 **儲存**，然後關閉 **法律實體** 頁。

![在法律實體頁面上選取的公司標誌圖像。](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>設定 ER 架構

作為電子報表函數顧問角色的使用者，您必須先設定最少的 ER 參數集，然後才能開始使用 ER 架構來設計標準 ER 格式的自訂版本。

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>設定 ER 參數

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **電子報表參數**。
3. 在 **電子報表參數** 頁的 **一般** 索引標籤上，將 **啟用設計模式** 選項設定為 **是**。
4. 在 **附件** 索引標籤上設定下列參數：

    - 在 **設定** 欄位中，選取 **檔案** 類型為 **USMF** 公司。
    - 在 **作業封存**、**臨時**、**基準** 和 **其他** 欄位中，選取 **檔案** 類型。

如需 ER 參數的相關資訊，請參閱[設定 ER 架構](electronic-reporting-er-configure-parameters.md)。

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>啟用 ER 設定提供者

新增的每個 ER 設定都被標記為歸 ER 設定提供者所有。 在 **電子報表** 工作區中啟用的 ER 設定提供者用於此目的。 因此，您必須先在 **電子報表** 工作區中啟用 ER 設定提供者，然後才能開始新增或編輯 ER 設定。

> [!NOTE]
> ER 設定只能由設定擁有者編輯。 在可以編輯 ER 設定之前，必須在 **電子報表** 工作區中啟用。

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>查看 ER 設定提供者清單

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **設定提供者**。
3. 在 **設定提供者資料表** 頁面，每個設定提供者記錄都有一個唯一的名稱和 URL。 查看此頁面的內容。 如果 **Litware, Inc.** (`https://www.litware.com`) 的記錄已存在，請跳過下一個程序[新增新的 ER 設定提供者](#AddProvider)。

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>新增新的 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **設定提供者**。
3. 在 **設定提供者** 頁面上，選取 **新建**。
4. 在 **名稱** 欄位中，輸入 **Litware, Inc.**
5. 在 **網址** 欄位，輸入 `https://www.litware.com`。
6. 選取 **儲存**。

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>啟用新的 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定提供者** 部分中，選取 **Litware, Inc.** 圖格，然後選取 **設定為有效狀態**。

如需 ER 設定提供者的相關資訊，請參閱[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)。

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>匯入標準 ER 格式設定

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>匯入標準 ER 設定

要將標準 ER 設定新增到 Dynamics 365 Finance 的現行執行個體中，您必須從為該執行個體設定的 ER [存放庫](general-electronic-reporting.md#Repository)中匯入這些設定。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定提供者** 區段，選取 **Microsoft** 圖格，然後選取 **存放庫**，查看 **Microsoft** 提供者的存放庫清單。
3. 在 **設定存放庫** 頁面，選取 **全域** 類型的存放庫，然後選取 **開啟**。 如果提示您需要授權才能連接到[Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md)，請遵循授權指示。
4. 在 **設定存放庫** 頁面上，在左側窗格的設定樹狀結構中，選取 **普通發票 (Excel)** 格式設定。
5. 在 **版本** FastTab 上，選取所選 ER 格式設定的最新版本 (例如，**240.112**)。
6. 選取 **匯入** 將所選版本從全域存放庫下載到現行 Finance 執行個體。

![在設定存放庫頁面上匯入標準 ER 設定。](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> 如果您在存取[全域存放庫](er-download-configurations-global-repo.md)時遇到問題，可以改為從 Microsoft Dynamics Lifecycle Services (LCS) [下載設定](download-electronic-reporting-configuration-lcs.md)。

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>查看匯入的 ER 設定

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定** 區塊中，選取 **報表設定** 圖格。
3. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，展開 **發票模型**。
4. 除了選定的 **普通發票 (Excel)** ER 格式，其他所需的 ER 設定已匯入。 確保以下 ER 設定可在設定樹狀結構中提供：

    - **發票模型** – 此設定包含資料模型 ER 組件，該組件表示開票業務領域的資料結構。
    - **發票模型對應** – 此設定包含模型對應 ER 組件，該組件描述如何在執行階段用應用程式資料填入資料模型。
    - **普通發票 (Excel)** – 此設定包含格式和格式對應 ER 組件。 格式組件基於 Excel 格式的範本指定報告設定。 格式對應組件包含模型資料來源，並指定如何使用此資料來源在執行階段填入報表配置。

![在設定頁面上匯入 ER 設定。](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>使用標準 ER 格式列印普通發票

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>設定列印管理

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 在 **普通發票** 頁面上，選取 **FTI-00000002** 發票，然後在動作窗格上的 **發票** 索引標籤，在 **列印管理** 分組，選取 **列印管理**。
3. 在 **列印管理安裝** 頁面上，在左側的樹狀結構中，展開 **模組 - 應收帳款\>檔案\>普統發票**，然後選取 **原始\<Default\>** 商品。
4. 在 **報告格式** 欄位，選取 **普通發票 (Excel)**。
5. 選取 **Esc** 鍵，離開 **列印管理安裝** 頁面，回到 **普通發票** 頁面。

![列印管理安裝頁面上標準 ER 格式的普通發票的列印管理安裝。](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>列印普通發票

1. 在 **普通發票** 頁面上，確保仍選取 **FTI-00000002** 發票，然後，在動作窗格上，在 **發票** 索引標籤，在 **檔案** 組，選取 **列印**\>**已選定**。
2. 下載產生的 Excel 格式發票，打開預覽。
3. 請注意，根據提供的 ER 格式的 Excel 範本的結構，產生的發票的頁尾包含有關現行頁碼和報表總頁數的資訊。

![產生的普通發票。](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>自訂標準 ER 格式

對於本節中的範例，您可以使用 Microsoft 提供的 ER 設定來產生 Excel 格式的普通發票。 但是，您必須新增自訂以將公司標誌圖像放在產生的發票的頁尾中。

在這種情況下，作為 Litware, Inc. 的代表，您必須建立 (衍生) 新的 ER 格式設定，該設定基於 Microsoft 提供的 **普通發票 (Excel)** 設定。

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>建立自訂格式

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面，在左窗格的設定樹狀結構中，展開 **發票模型**，然後選取 **普通發票 (Excel)**。 Litware, Inc. 將使用匯入的版本 (例如，**240.112**) 將此 ER 格式設定作為自訂版本的基礎。
3. 選取 **建立設定** 以打開下拉式對話方塊。 使用此對話方塊為自訂付款格式建立新設定。
4. 在 **新建** 欄位組，選取 **名稱來源：普通發票 (Excel)，Microsoft** 選項。
5. 在 **名稱** 欄位，輸入 **Free text invoice (Excel) custom**。
6. 選取 **建立設定**。

![在建立設定下拉式對話方塊中為自訂支付格式建立設定。](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

240.112.1 版的 **普通發票 (Excel) 自訂** ER 格式設定已建立。 此版本的 [狀態](general-electronic-reporting.md#component-versioning)為 **草稿**，可以進行編輯。 您自訂 ER 格式的目前內容與 Microsoft 提供格式的內容相符。

![在設定頁面上建立的 ER 格式設定的新版本。](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>編輯自訂格式

設定您的自訂格式，以便將公司標誌圖像放在報告每一頁的頁尾中。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面，在左窗格的設定樹狀結構中，展開 **付款模型**，然後選取 **普通發票 (Excel) 自訂**。
3. 在 **版本** FastTab 上，選取所選設定的所需版本 **240.112.1**。
4. 選取 **設計工具**。
5. 在 **格式設計工具** 頁面，選取 **顯示詳情** 查看有關格式元素的更多資訊。
6. 展開並查看以下元素：

    - **Excel** 類型的 **普通發票** 元素。 此元素用於產生 Excel 活頁簿格式的發票。
    - **工作簿** 類型的 **普通發票\\發票** 元素。 此元素用於產生已產生的 Excel 活頁簿的工作表。
    - **頁尾** 類型的 **普通發票\\發票\\頁尾** 元素。 此元素用於填入發票頁尾。

7. 選取 **普通發票\\發票\\頁尾** 元素。

    ![ER 作業設計工具中的頁尾元素。](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > 產生的發票的每個頁尾都包含有關現行頁碼和報表總頁數的資訊。 如您所見，**普通發票\\發票\\頁尾** 元素不包含子項目。 因此，正在使用的 Excel 範本設定為在每個報表頁尾的中心顯示分頁詳情。

8. 選取 **新增**，然後選取您要新增的格式元素的 **Excel\\圖片** 類型。

    1. 在 **對齊** 欄位中，選取 **正確**。
    2. 在 **縮放高度** 欄位中，選取 **相對的**。
    3. 在 **比例縮放** 欄位中，輸入 **70**。
    4. 選取 **確定**。

        > [!NOTE]
        > 將 **Excel\\圖片** 元素用於新增公司標誌圖像並將其與頁尾右側對齊。

    ![組件屬性對話方塊中圖片元素的屬性。](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. 在左側的格式結構樹中，選取您剛新增的 **圖片** 元素，然後在 **對應** 索引標籤上，展開 **模型** 資料來源。
10. 展開 **model.Payment**\>**model.InvoiceBase\> model.InvoiceBase.CompanyInfo**，然後選取 **model.InvoiceBase.CompanyInfo.Logo** 資料來源欄位。 [容器](er-formula-supported-data-types-composite.md#container)類型的資料來源欄位將公司標誌圖像作為媒體內容公開。
11. 選取 **綁定**。 **圖片** 格式元素現在與 **model.InvoiceBase.CompanyInfo.Logo** 資料來源欄位繫結。 因此，在執行階段，公司標誌圖像將放在產生的發票的頁尾中。

    ![在 ER 作業設計工具中與 model.InvoiceBase.CompanyInfo.Logo 資料來源欄位繫結的圖片格式元素。](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. 選取 **儲存**，然後關閉 **設計工具** 頁面。

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>將自訂格式標記為可執行

因為自訂格式的第一個版本已經建立並且狀態為 **草稿**，您可以執行該格式以進行測試。 若要執行報告，請使用參考您的自訂 ER 格式的付款方式處理廠商付款。 在預設情況下，當您從應用程式調用 ER 格式時，僅 [考慮](general-electronic-reporting.md#component-versioning)狀態為 **已完成** 或 **共用** 的版本。 此行為有助於防止使用具有未完成設計的 ER 格式。 但是，對於您的測試執行，您可以強制應用程式使用狀態為 **草稿** 的 ER 格式版本。 這樣，如果需要進行任何修改，您可以調整目前的格式版本。 如需相關資訊，請參閱[適用性](electronic-reporting-destinations.md#applicability)。

若要使用 ER 格式的草稿版本，您必須明確標記 ER 格式。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊，將 **執行設定** 選項設定為 **是**，然後選取 **確定**。
4. 選取 **編輯** 使現行頁面可編輯，然後在左窗格的設定樹狀結構中，選取 **普通發票 (Excel) 自訂**。
5. 將 **執行草稿** 選項設定為 **是**。

![在設定頁面上將自訂格式標記為可執行。](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>使用自訂 ER 格式列印普通發票

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>設定列印管理

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 在 **普通發票** 頁面上，選取 **FTI-00000002** 發票，然後在動作窗格上的 **發票** 索引標籤，在 **列印管理** 分組，選取 **列印管理**。
3. 在 **列印管理安裝** 頁面上，在左側的樹狀結構中，展開 **模組 - 應收帳款**\>**檔案**\>**普統發票**，然後選取 **原始****\<Default\>** 商品。
4. 在 **報告格式** 欄位，選取 **普通發票 (Excel) 自訂**。
5. 選取 **Esc**，離開 **列印管理安裝** 頁面，回到 **普通發票** 頁面。

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>列印普通發票

1. 在 **普通發票** 頁面上，確保仍選取 **FTI-00000002** 發票，然後，在動作窗格上，在 **發票** 索引標籤，在 **檔案** 組，選取 **列印**\>**已選定**。
2. 下載產生的 Excel 格式發票，打開預覽。
3. 請注意，根據自訂 ER 格式的結構，產生的發票的頁尾除了包含有關報表分頁的資訊外，還包含公司標誌圖像。

![在頁尾中產生帶有公司標誌圖像的普通發票。](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>其他資源

- [設計用於產生 Excel 格式文件的設定](er-fillable-excel.md)
- [在使用 ER 產生的文件中嵌入圖像和形狀](electronic-reporting-embed-images-shapes.md)
