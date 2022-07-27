---
title: 設計 ER 設定以填入 PDF 範本
description: 本主題提供有關如何設計電子報表 (ER) 格式以填入 PDF 範本的資訊。
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: a568ddd93bfbc7d536e951a13470b3dedb796e1b
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2022
ms.locfileid: "8460174"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>設計 ER 設定以填入 PDF 範本

[!include[banner](../includes/banner.md)]

本主題中的過程是範例，說明使用者如何在 **系統管理員** 角色或 **電子報表開發商** 角色可以設定電子報表 (ER) 格式，透過使用可填入的 PDF 文件作為報告範本，產生 PDF 文件。 這些步驟可以在任何一家公司執行 Dynamics 365 Finance 或 Regulatory Configuration Services (RCS)。

## <a name="prerequisites"></a>先決條件

在開始之前，您必須具有以下存取類型之一，具體取決於您用於完成本主題中的過程的服務：

- 以下其中一個角色的 Finance 存取權限：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

- 以下其中一個角色存取 RCS：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

您還必須完成[建立設定提供程式並將其標記為活動](tasks/er-configuration-provider-mark-it-active-2016-11.md)程序。

最後，下載以下檔案。

| 內容描述                       | 檔案名稱                                     |
|-------------------------------------------|-----------------------------------------------|
| 報告第一頁的範本 | [IntrastatReportTemplate1.pdf](https://download.microsoft.com/download/0/8/3/0832c82b-4448-4562-afbf-01e0efc8d999/IntrastatReportTemplate1.pdf)                  |
| 其他頁報告的範本    | [IntrastatReportTemplate2.pdf](https://download.microsoft.com/download/c/7/a/c7a8a806-2192-4034-9052-e8b84b527d5e/IntrastatReportTemplate2.pdf)                  |
| 樣本 ER 格式 - PDF                          | [Intrastat 報告 (PDF).版本.1.1.xml](https://download.microsoft.com/download/a/8/7/a87aea3e-3f60-404c-8899-c471d20e7ea9/IntrastatreportPDFversion1.1.xml)        |
| 樣本 ER 格式 - Excel                          | [Intrastat (從 Excel 匯入).版本.1.1.xml](https://download.microsoft.com/download/a/2/c/a2c0c145-d989-4e55-9d47-9647c02e4ee4/IntrastatimportfromExcelversion1.1.xml) |
| 樣本資料集                            | [Intrastat sample data.xlsx](https://download.microsoft.com/download/9/f/1/9f1c5b96-3800-475f-8cf6-1ddd42873758/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>設計格式設定

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>存取 Microsoft 提供的設定清單

1. 進入 **組織管理\>工作區\>電子報表**。
2. 確保有提供 **Litware, Inc.** 提供者並標記為活動。
3. 在 **Microsoft** 提供者的圖格上，選取 **存放庫**。

    > [!NOTE]
    > 如果 **LCS** 類型存放庫已存在，請跳過此過程的其餘步驟。

4. 選取 **新增**。
5. 在下拉式對話方塊中，在 **設定存放庫類型** 欄位組，選取 **LCS** 選項。
6. 選取 **建立存放庫**。
7. 選取 **確定**。

### <a name="get-the-model-configurations-provided-by-microsoft"></a>取得 Microsoft 提供的模型設定

1. 在 **設定存放庫** 頁面的左側上，選取 **顯示過濾器** 按鈕 (漏斗符號)。
2. 在 **類型** 欄位中為 **LCS** 的值新增過濾器，並使用 **開始於** 運算子。
3. 選取 **套用**。
4. 請選取 **打開**。
5. 在樹狀結構中，選取 **Intrastat 模型**。
6. 在 **版本** FastTab 上，選取版型 **1**。

    > [!NOTE]
    > 如果 **版本** FastTab 上的 **匯入** 按鈕無法使用，請跳過此過程的其餘步驟。

7. 選取 **匯入**。
8. 選取 **是** 確認所選版本的匯入 **Intrastat 模型** 模型設定。

### <a name="create-a-new-format-configuration"></a>建立新的格式設定

1. 在 **電子報表** 工作區中，選取 **報告設定** 圖格。
2. 在樹狀結構中，選取 **Intrastat 模型**。
3. 選取 **建立設定**。

    > [!NOTE]
    > 如果 **建立設定** 按鈕無法使用，您必須在 **電子報表參數** 頁面上打開設計模式，該頁面可以從 **電子報表** 工作區打開。

4. 在下拉式對話方塊中，在 **新建** 欄位群組，選取 **根據資料模型 Intrastat 的格式** 選項。
5. 在 **名稱** 欄位中，輸入 **Intrastat report (PDF)**。
6. 在 **描述** 欄位中，輸入 **Intrastat report in PDF format**。

    > [!NOTE]
    > 自動輸入有效的設定提供者。 此提供者將能夠維護此設定。 儘管其他提供者可以使用此設定，但他們將無法維護它。

7. 選取性：在 **格式類型** 欄位中，您可以選取特定格式的電子文件。 如果您選取 **PDF 格式**，在設計階段，ER 作業設計工具將僅提供僅適用於以 PDF 格式產生的文件的格式元素 (**PDF\檔案**、**PDF\PDF 合併** 等等)。 如果將此欄位留白，則將在設計時在 ER 作業設計工具中指定電子文件的格式，此時將新增第一個格式元素。 例如，如果您新增 **Excel\檔案** 作為第一個格式元素，ER 作業設計工具將為您提供僅適用於以 Excel 格式產生的文件的格式元素 (**Excel\儲存格**、**Excel\範圍** 等等)。 格式。
8. 選取 **建立設定**。

建立新的 ER 格式設定。 您可以使用此設定的草稿版本來儲存旨在產生 PDF 格式電子文件的 ER 格式組件。

### <a name="design-the-format-of-an-electronic-document"></a>設計電子文件的格式

接下來，在您建立的 ER 格式設定中，您將設計 ER 格式，以 PDF 格式產生 **Intrastat 控制** 報告。 該報告的第一頁必須顯示報告摘要和所報告的外貿交易的詳情。 其他頁面必須僅顯示所報告的外貿交易的詳情。 因為產生的報告頁面必須有不同的配置，所以在 ER 格式中將使用兩個不同的 PDF 格式的範本。

在任何 PDF 檢視器中，打開您下載的 PDF 範本。 請注意，每個範本都包含多個必須填入的欄位。 在每個範本中，外貿交易明細顯示為 42 資料列，每行有 9 個欄位。 資料列號出現在每個欄位名稱的末尾 (例如，**日期 1**…**日期 42** 和 **商品 1**…**商品 42**)。

下圖顯示了報告第一頁的 PDF 範本。

![範本 1。](media/rcs-ger-filloutpdf-template1.png)

下圖顯示了其他頁報告的 PDF 範本。

![範本 2。](media/rcs-ger-filloutpdf-template2.png)

1. 在 **設定** 頁面上，選取 **設計工具**。
2. 選取 **新增根**。
3. 在下拉式對話方塊的樹中，選取 **PDF\>PDF 合併**。

    當您選取 **PDF 合併** 元素作為格式的根元素，在執行時產生的所有 PDF 文件都將合併為一個最終的 PDF 文件。 如果您只需要一個 PDF 範本就可以使用您設計的 ER 格式產生所有需要的文件，您可以選取 **PDF 檔案** 作為根元素。

4. 在 **名稱** 欄位中，輸入 **Output**。
5. 在 **語言偏好設定** 欄位中，選取 **使用者偏好設定**。 該報告將以執行它的使用者的偏好語言產生。
6. 在 **文化偏好設定** 欄位中，選取 **使用者偏好設定**。 報告頁面上顯示的值和日期將根據執行報告的使用者的首選區域設定格式。
7. 選取 **確定**。
8. 在動作窗格上，**匯入** 索引標籤上，選取 **從 PDF 匯入**。

    當可填入的 PDF 文件被匯入作為該 ER 格式的範本時，所有需要的 ER 格式元素 (**PDF 檔案**、**欄位組** 和 **欄位** 元素) 都會根據被匯入的 PDF 文件的結構，以設計的格式自動建立。

9. 選取 **瀏覽**。 導航到並選取您之前下載作為先決條件的 **IntrastatReportTemplate1.pdf** 檔案。
10. 選取 **確定**。

    載入選定的檔案，填入 **從 PDF 匯入** 對話方塊中的 **範本** 欄位。

11. 將 **群組欄位** 選項設定為 **是**。 如果選定的 PDF 文件包含任何欄位組，它們將用於對建立的 ER 格式元素進行分組。 將為此目的建立 **欄位組** 格式元素。

    如果將這個選項設定為 **否**，所需的 ER 格式元素將被建立為平面的元素清單，這些元素巢狀在已建立的 **PDF 檔案** 格式元素下。

12. 選取 **確定**。

    ![從 PDF 對話方塊匯入。](media/rcs-ger-filloutpdf-importtemplate.png)

13. 在樹狀結構中，展開 **輸出**。

    請注意，**PDF 檔案** 組件已自動建立以管理在執行時產生的報告的第一頁的建立。

14. 在樹狀結構中，展開 **輸出\>PDF 檔案**。

    請注意，格式元素的結構化清單已根據您之前匯入的可填入 PDF 文件的結構以這種 ER 格式自動建立。

15. 在樹狀結構中，選取 **輸出\>PDF 檔案**。
16. 在 **名稱** 欄位中，輸入 **Page 1**。

    這個格式元素將被用來產生 **Intrastat 控制** 報告的第一頁。 該頁面將顯示報告摘要和外貿交易的詳情。

    如果您把 **語言偏好設定** 欄位留白，那麼父系 **PDF 合併** 元素的 **語言偏好設定** 設定將決定使用此格式元素產生的報告的語言。 您可以選取另一個值來覆蓋父元素的設定。

    如果您把 **文化偏好設定** 欄位留白，那麼父系 **PDF 合併** 元素的 **文化偏好設定** 設定將決定使用此格式元素產生的報告的地區設定。 語言環境決定了報告頁面上值和日期的格式。 您可以選取另一個值來覆蓋父元素的設定。

17. 在動作窗格上，選取 **匯入** 索引標籤。請注意，**從 PDF 更新** 按鈕已可用於選定的格式元素，**PDF 檔案**。

    您可以使用此按鈕將更新的 PDF 範本匯入到編輯的格式。 匯入更新的 PDF 範本時，格式元素清單將相應更改：

    - 對於更新後的 PDF 範本中的任何新欄位，都會以編輯後的 ER 格式建立新的格式元素。
    - 如果更新後的 PDF 範本不再包含與編輯後的 ER 格式中的任何現有格式元素對應的欄位，則會從 ER 格式中刪除這些格式元素。

18. 在 **格式** 索引標籤，選取 **附件**。

    請注意，匯入的 PDF 文件附加到已編輯的 ER 格式。

    ![PDF 附件預覽。](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. 透過匯入第二個 PDF 範本、為資料來源新增必要的繫結等來繼續設計此格式。
20. 選取 **儲存**。
21. 關閉頁面。
22. 選取 **刪除**。
23. 選取 **是**。

為了了解新的 **PDF 合併**、**PDF 檔案**、**欄位組** 和 **欄位** 格式元素如何用於產生 PDF 格式的文件，您可以匯入並分析 ER 格式的樣本。

### <a name="import-the-format-configuration"></a>匯入格式設定

接下來，您將匯入之前下載的 ER 格式樣本，產生 PDF 格式的 **Intrastat 控制** 報告。 此報告的第一頁必須顯示報告摘要和所報告的外貿交易的詳情。 其他頁面必須僅顯示所報告的外貿交易的詳情。

1. 在 **設定** 頁面上，選取 **Exchange\>從 XML 檔案載入**。
2. 選取 **瀏覽**。 導航到並選取您之前下載作為先決條件的 **Intrastat 報告 (PDF).版本.1.1.xml** 檔案。
3. 選取 **確定**。

## <a name="analyze-the-format-configuration"></a>分析格式設定

### <a name="format-layout"></a>格式設定

1. 在 **設定** 頁面上，在樹狀結構中，選取 **Intrastat 模型\>Intrastat 報告 (PDF)**。
2. 選取 **設計工具**。
3. 選取 **顯示詳情**。
4. 在樹狀結構中，展開 **輸出：PDF 合併**。

    請注意，此 ER 格式包含兩個 **PDF 檔案** 元素，每個元素都使用不同的 PDF 範本。 一個範本用於產生 PDF 格式報告的第一頁，另一個範本用於產生其他頁面。

5. 在樹狀結構中，展開 **輸出：PDF 合併\>第 1 頁：PDF 檔案 (IntrastatReportTemplate1)**。
6. 在樹狀結構中，展開 **輸出：PDF 合併\>第 N 頁：PDF 檔案 (IntrastatReportTemplate2)**。

    請注意，由於兩個 PDF 範本的內容不同，兩個 **PDF 檔案** 元素的巢狀格式元素的結構也不同。

### <a name="format-mapping"></a>格式對應

1. 在 **格式設計工具** 頁面上，選取 **對應** 索引標籤。
2. 在樹狀結構中，展開 **分頁\>頁面**。

    ![展開模型樹狀結構的公式設計工具頁面。](media/rcs-ger-filloutpdf-reviewformat.png)

    請注意以下詳情：

    - **PDF 檔案** 類型的 **輸出\>第 1 頁** 格式元素沒有繫結到任何資料來源，並且這個格式元素的 **啟用** 運算式是空的。 因此，在執行階段，**IntrastatReportTemplate1** PDF 範本在產生單個 PDF 文件時將只被填入一次。
    - **PDF 檔案** 類型的 **輸出\>第 N 頁** 格式元素被繫結到 **記錄清單** 類型的 **Paging.PageN** 資料來源，並且該格式元素的 **啟用** 運算式為空。 因此，在執行階段，**IntrastatReportTemplate2** PDF 範本將在產生單個 PDF 文件時為綁定記錄清單中的每條記錄填入。
    - 因為 **第 1 頁：PDF 檔案** 和 **第 N 頁：PDF 檔案** 格式元素是 **輸出：PDF 合併** 格式元素的子系，所有填入的 PDF 文件將合併為一個最終的 PDF 文件。
    - 將 **Paging.Page1** 和 **Paging.PageN** 資料來源設定為 **Paging.Pages** 資料來源記錄的過濾器。 將此資料來源設定為將整套外貿交易分成批次。 每個批次最多包含 42 條記錄。 以下 ER 運算式用於將交易拆分為批次：

        SPLITLIST(Totals.CommodityRecord,42)

    - **Paging.Pages** 資料來源包含返回批次中包含的每條記錄詳情的 **Paging.Pages.Enumerated** 元素。 這些詳情包括記錄在現行批次中的順序 (**Paging.Pages.Enumerated.Number** 欄位)。 **Paging.Pages.Enumerated.Number** 欄位在 **PDF 欄位** 格式元素的 **名稱** 運算式中被用來動態地產生欄位名稱，這個欄位名稱是基於批次中的交易編號。 然後使用產生的欄位名稱填入所使用的 PDF 範本中的正確 PDF 欄位。
    - 將 **PDF 組** 類型的 **輸出\>第 N 頁\>詳情 2** 格式元素繫結到 **記錄清單** 類型的 **Paging.PageN.Enumerated** 資料來源 (或 **\@.Enumerated** 如果使用了 **相對路徑** 視圖模式)。 因此，在執行階段，將為繫結記錄清單中的每條記錄填入此 PDF 組的巢狀元素。 透過這種方式，當 **Paging.PageN.Enumerated** 清單的 42 條記錄中的每一條的 N 次被填入以下 PDF 欄位時，實際上就產生了單獨的 PDF 列：日期 N、方向 N、商品 N 等。因此，在這方面，這個 **欄位組** 格式元素的行為類似於 **XML\>順序** 和 **文字\>順序** 格式元素的行為。

3. 在樹狀結構中，展開 **輸出\>第 N 頁\>Details2**。
4. 在樹狀結構中，選取 **輸出\>第 N 頁\>Details2\>PageFooter**。

    請注意，將此格式元素的 **名稱** 屬性定義為 **PageFooter**。 另請注意，格式元素的 **名稱** 運算式為空白。

5. 在樹狀結構中，選取 **輸出\>第 N 頁\>Details2\>修正 1**。

    請注意，將此格式元素的 **名稱** 屬性定義為 **修正 1**。 另請注意，將格式元素的 **名稱** 運算式定義為 **Paging.FldName("Correction",\@.Number)**。

![選取對應的格式設計工具。](media/rcs-ger-filloutpdf-reviewformat2.png)

請注意，**欄位** 格式元素用於填入可填入 PDF 文件的單個欄位，該文件被定義為父 **PDF 檔案** 格式元素的一個範本。 **PDF 檔案** 格式元素或其巢狀元素的繫結程序，如果它有任何巢狀元素，就指定在相應的 PDF 欄位中輸入的值。 **欄位** 格式元素的不同屬性可以用來指定哪個 PDF 欄位是由個別格式元素填入的：

- 在 **格式** 索引標籤上，格式元素的 **名稱** 屬性
- 在 **對應** 索引標籤上，格式元素的 **名稱** 運算式

因為這兩個屬性對於 **欄位** 格式元素來說都是選取性的，下面的規則被用來指定目標 PDF 欄位：

- 如果 **名稱** 屬性是空白，並且 **名稱** 運算式在執行階段返回空白字串，那麼在執行階段就會引發例外狀況，通知使用者在用於填入 PDF 文件的 PDF 範本中找不到一個 PDF 欄位。
- 如果定義了 **名稱** 屬性，而 **名稱** 運算式是空白的，那麼與格式元素的 **名稱** 屬性有相同名稱的 PDF 欄位就會被填入。
- 如果定義了 **名稱** 屬性，並且設定了 **名稱** 運算式，那麼與格式元素的 **名稱** 運算式返回的值同名的 PDF 欄位將被填入。

> [!NOTE]
> 可以透過以下方式填入 PDF 核取方塊：
>
> - 當相應的 **欄位** 格式元素繫結到有 **True** 值的 **布林值** 資料來源欄位
> - 當相應的 **欄位** 格式元素包含巢狀的 **字串** 格式元素，該元素會被繫結到資料來源欄位，該欄位的文字值為 **1**、**True** 或 **Yes**

## <a name="run-the-format-configuration"></a>執行格式設定

### <a name="import-the-format-configuration"></a>匯入格式設定

接下來，您將載入 **Intrastat (import from Excel)** 樣本 ER 格式。 此格式旨在解析模擬外貿交易的使用者選定 Microsoft Excel 活頁簿。

1. 在 **設定** 頁面上，選取 **Exchange\>從 XML 檔案載入**。
2. 選取 **瀏覽**。 導航到並選取您之前下載作為先決條件的 **Intrastat (從 Excel 匯入).版本.1.1.xml** 檔案。
3. 選取 **確定**。
4. 在樹狀結構中，選取 **Intrastat 模型\>Intrastat (import from Excel)**。
5. 選取 **編輯**。
6. 將 **模型對應的預設值** 選項設定為 **是**。

    > [!NOTE]
    > 如果您以前為 **Intrastat 模型** 設定或巢狀在 **Intrastat 模型** 設定下的另一個設定將 **預設為模型對應** 選項設定為 **是**，將此選項設定為 **否**。

    當 **模型對應的預設** 選項設定為 **是** 時，匯入的 **Intrastat (import from Excel)** ER格式被指定為 **Intrastat report (PDF)** 格式設定的預設資料來源。 然後，當執行 **Intrastat report (PDF)** 格式設定時，由 **Intrastat (import from Excel)** ER 格式解析的 Excel 活頁簿的內容將模擬出必須報告的外貿交易。 下圖顯示了 Excel 活頁簿的範例。

    ![具有樣本資料的 Excel 活頁簿。](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>執行格式設定

1. 在 **設定** 頁面上，在樹狀結構中，選取 **Intrastat 模型\>Intrastat 報告 (PDF)**。
2. 選取 **執行**。
3. 選取 **瀏覽**。 導航到並選取您之前下載作為先決條件的 **Intrastat sample data.xlsx** 檔案。
4. 選取 **確定**。
5. 在 **報告方向** 欄位中，選取 **兩者** 以在產生的 PDF 報告中填入匯入的 Excel 活頁簿中的所有交易。
6. 選取 **確定**。
7. 查看產生的 PDF 文件。

下圖顯示了產生的報告第一頁的範例。

![產生報告的第一頁。](media/rcs-ger-filloutpdf-generatedreport.png)

下圖顯示了產生的另一頁報告的範例。

![產生其他頁的報告。](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="limitations"></a>限制

在您計劃用作報告範本的 PDF 表單中，可填入欄位的名稱應該是唯一的。 對於每個此類欄位，在匯入 PDF 表單時，會以可編輯的 ER 格式建立具有相應名稱的單個格式元素。 如果 PDF 表單包含多個具有相同名稱的欄位，則會為不允許在執行階段單獨填入的欄位建立單個格式元素。

## <a name="frequently-asked-questions"></a>常用問題

### <a name="when-i-run-the-er-format-to-generate-a-report-in-pdf-format-why-do-i-get-the-following-errors--cannot-handle-iref-streams-the-current-implementation-of-pdfsharp-cannot-handle-this-pdf-feature-introduced-with-acrobat-6-and-a-pdf-name-must-start-with-a-slash-"></a>當我執行 ER 格式產生 PDF 格式的報告時，為什麼會出現以下錯誤：**無法處理 iref 流。PDFSharp 的現行實現無法處理 Acrobat 6 引入的此 PDF 函數。** 和 **PDF 名稱必須以斜線 (/) 開頭。**

ER 架構使用 PDFSharp 庫的 1.5 版來產生這些 PDF 報告。 PDF 1.5 的一些函數 (Adobe Reader 6.0) 尚未在此庫中實現。 因此，PDFSharp 還無法打開一些標記為 **適用於 PDF 1.5 或更高版本** 並可能導致收到錯誤。 使用以下解決方案之一來解決此問題：

-   當您使用自己的 PDF 範本時：將範本降級到更早的 Adobe 版本並開始使用 ER 格式的新範本。
-   當您使用另一個設定提供商與您共享的 ER 格式範本作為 ER 解決方案的一部分時：聯繫此 ER 解決方案的所有者並提供問題描述。
-   當您使用包含早期版本的 PDFSharp 庫的 ISV 解決方案時：聯繫解決方案的所有者並建議升級到較新的 PDFSharp 版本。

## <a name="additional-resources"></a>其他資源

- [ER 設計用於產生 OPENXML 格式報告的設定 (2016 年 11 月) ](tasks/er-design-reports-openxml-2016-11.md)
- [設計 ER 設定以產生 Word 格式的報告](tasks/er-design-configuration-word-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
