---
title: 在產生的報告中隱藏 Word 內容控制
description: 本主題說明如何設定電子報表 (ER) 格式以將報告產生為 Microsoft Word 檔案，其中內容控制被抑制。
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: f8e74902e939355aba9bbadd8e7f8f8aa46fe5c5
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460564"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>在產生的報告中隱藏 Word 內容控制

[!include [banner](../includes/banner.md)]

若要將報告產生為 Microsoft Word 文件，您必須將報告的範本設計為 Word 文件。 此範本必須包含 Word 內容控制作為將在執行階段填入的資料的預留位置。 若要使用作為報告範本創建的 Word 文件，您可以[設定](er-design-configuration-word.md)新的[電子報表 (ER)](general-electronic-reporting.md) [解決方案](er-quick-start1-new-solution.md)。 解決方案必須包含一個包含 ER 格式組件的 ER [設定](general-electronic-reporting.md#Configuration)。 此 ER 格式必須設定為使用設計的範本產生報告。

在 Dynamics 365 Finance 版本 10.0.6 及更高版本中，您可以設定 ER 格式的公式以隱藏產生文件中的某些 Word 內容控制。

以下步驟說明了指派給系統管理員或電子報表職能顧問角色的使用者如何設定 ER 格式，該格式將報告產生為 Word 檔案，並抑制產生的報告中使用 Word 設定的某些內容控制範本。

這些步驟可以在 GBSI 公司完成。

## <a name="prerequisites"></a>先決條件

若要完成這些步驟，您必須首先完成以下工作指南中的步驟：

- [設計用於產生 OPENXML 格式報告的設定](./tasks/er-design-reports-openxml-2016-11.md)
- [透過 Excel 範本重複使用 ER 設定以產生 Word 格式的報告](./tasks/er-design-configuration-word-2016-11.md)

完成這些工作指南的步驟後，將準備以下項目：

- 設定為以 Word 格式產生文件的 **樣本工作表報告** ER 格式
- 標記為 **可執行** 的 **樣本工作表報告** ER 格式的[草稿](general-electronic-reporting.md#component-versioning)版本
- 一種 **電子** 付款方式，設定為使用 **樣本工作表報告** ER 格式進行廠商付款處理

您還必須下載並儲存樣本報告的以下範本：

- [付款報告的繫結範本 2 (SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>查看下載的 Word 範本

1. 在 Word 桌面應用程式中，打開您之前下載的 **SampleVendPaymDocReportBounded2.docx** 範本檔案。
2. 驗證範本檔案是否包含摘要區段，該區段顯示已處理付款中已滿足的每個貨幣代碼的總付款金額。

    - 摘要區段位於 Word 文件的單獨資料表中。
    - 此表的第一資料列將資料表資料欄標題作為節標題。
    - 此表的第二資料列包含重複內容控制作為區段詳情。
    - 此內容控制對應到 **報告** 自訂 XML 組件的 **SummaryLines** 欄位。
    - 基於此對應，內容控制與可編輯 ER 格式的 **SummaryLines** 元素相關。

    > [!NOTE]
    > 重複內容控制由與已對應到的自訂 XML 組件的欄位匹配的 **SummaryLines** 金鑰標記。

    ![Word 範本配置。](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>選取現有的 ER 報表設定

對於以下步驟，您將重複使用在完成上述工作指南中的步驟時設定的現有 ER 設定。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 選取 **報表設定**。
3. 在 **設定** 頁面的設定樹狀結構中，展開 **付款模型**，然後選取 **樣本工作表報表**。
4. 選取 **設計工具** 編輯所選 ER 格式的草稿版本。

## <a name="replace-the-current-template-with-the-new-template"></a>用新範本替換現行範本

現行，SampleVendPaymDocReportBounded.docx 檔案用作範本以產生 Word 格式的輸出。 在以下步驟中，您將使用之前下載的新 Word 範本 SampleVendPaymDocReportBounded2.docx 替換此 Word 範本。

1. 在 **格式設計工具** 頁面上，選取 **附件**。
2. 在 **附件** 頁面，選取 **刪除** 來移除現有範本。
3. 選取 **是** 確認刪除。
4. 選取 **新建**\>**檔案**。
5. 選取 **瀏覽**，然後瀏覽並選取您之前下載的 **SampleVendPaymDocReportBounded2.docx** 檔案。
6. 選取 **確定**。
7. 關閉 **附件** 頁面。
8. 在 **格式設計工具** 頁，在 **範本** 欄位，輸入或選取 **SampleVendPaymDocReportBounded2.docx** 檔案。

## <a name="run-the-format-to-create-word-output"></a>執行格式以創建 Word 輸出

1. 進入 **應付帳款**\>**付款**\>**付款日記帳**。
2. 在 **廠商付款** 頁，在 **清單** 索引標籤，選取所有付款。
3. 選取 **付款狀態**\>**無**。
4. 選取 **產生付款**。
5. 在 **付款方式** 欄位中，選取 **電子**。
6. 在 **銀行帳戶** 欄位中，選取 **GBSI OPER**。
7. 選取 **確定**。
8. 在 **電子報表參數** 對話方塊，選取 **確定**，並分析產生的輸出。

    ![在廠商付款頁面上進行處理的付款。](./media/er-design-configuration-word-suppress-controls-image2.gif)

    輸出以 Word 格式顯示並包含摘要區段。

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>設定可編輯格式以隱藏摘要區段

如果要在產生的文件中隱藏摘要區段，則根據執行此 ER 格式的使用者的要求，您必須修改可編輯的 ER 格式。

1. 進入 **組織管理**\>**工作區**\>**電子報表**，然後開啟 ER 格式的草稿版本進行編輯。
2. 選取 **報表設定**。 
3. 在 **設定** 頁面的設定樹狀結構中，展開 **付款模型**\>**樣本工作表報表**。
4. 選取 **設計工具**。
5. 在 **格式設計工具** 頁面，展開 **Word**，並選取 **SummaryLines**。
6. 在 **對應** 索引標籤，新增一個新的資料來源，在執行階段詢問使用者是否應該禁止摘要區段：

    1. 選取 **新增根**。
    2. 在 **新增資料來源** 對話方塊，選取 **一般\使用者輸入參數** 以開啟 **「使用者輸入參數」資料來源屬性** 對話方塊。
    3. 在 **名稱** 欄位中，輸入 **uipSuppress**。
    4. 在 **標籤** 欄位，輸入 **Suppress summary section**。
    5. 在 **作業資料類型名稱** 欄位，選取或輸入 **NoYes**。
    6. 選取 **確定**。

7. 新增 **NoYes** 應用程式列舉類型的新資料來源：

    1. 選取 **新增根**。
    2. 在 **新增資料來源** 對話方塊，選取 **Dynamics 365 for Operations\列舉** 以開啟 **「列舉」資料來源屬性** 對話方塊。
    3. 在 **名稱** 欄位中，輸入 **enumNoYes**。
    4. 在 **標籤** 欄位，輸入 **Suppress options**。
    5. 在 **作業資料類型名稱** 欄位，選取或輸入 **NoYes**。
    6. 選取 **確定**。

8. 對於選定的 **SummaryLines** 格式元素，設定公式以指定何時應隱藏與選定格式元素相關的 Word 內容控制項：

    1. 在 **對應** 索引標籤，在 **已移除** 區段，選取 **編輯** 開啟 **[公式設計工具](general-electronic-reporting-formula-designer.md)** 頁。
    2. 在 **公式** 欄位中，輸入公式 `uipSuppress = enumNoYes.Yes`。
    3. 選取 **儲存**，關閉 **公式設計工具** 頁面。

        > [!NOTE]
        > **在執行所有其他格式元素後**，此公式將應用於產生的文件。 若要套用此公式，需要標記為格式元素的 Word 內容控制項，設定用於 (在這種情況下為 **SummaryLines**) 該公式在產生的文件中找到。 然後，該內容控制項連同包含它的 Word 表中的行一起被完全刪除。 從產生的文件中刪除摘要區段的詳情資料列。
        >
        > 在設計階段，您可能會為格式元素設定 **移除** 公式，即使您正在使用的 Word 範本中沒有任何內容控制項具有與為其設定 **移除** 屬性的格式元素的名稱相符的標記。 當您在設計階段驗證格式時，您會收到有關此不一致的[警告](er-components-inspections.md#i14)。
        >
        > 在執行階段，如果您正在使用的 Word 範本中沒有任何內容控制項具有與設定了 **移除** 屬性的格式元素的名稱相符的標記，則會引發異常。

    4. 在 **對應** 索引標籤，在 **已移除** 區段，將 **與父系** 選項設定為 **是**。

        > [!NOTE]
        > 您必須將此選項設定為 **是** 以刪除整個 Word 表作為包含摘要區段詳情的行的父物件。 如果將此選項設定為 **否**，該章節標題資料列將保留在產生的文件中。

9. 選取 **儲存** 將更改儲存為可編輯格式。

    ![以 Word 格式產生的輸出。](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>執行修改後的格式以創建 Word 輸出

1. 進入 **應付帳款**\>**付款**\>**付款日記帳**。
2. 選取您創建的付款日記帳，然後選取 **明細**。
3. 在 **廠商付款** 頁面，選取所有資料列，然後選取 **付款狀態**\>**無**。
4. 選取 **產生付款**。
5. 在 **付款方式** 欄位中，選取 **電子**。
6. 在 **銀行帳戶** 欄位中，選取 **GBSI OPER**。
7. 選取 **確定**。
8. 在 **電子報表參數** 對話方塊，在 **隱藏摘要區段** 欄位，選取 **是**。
9. 選取 **確定**，並分析產生的輸出。

    ![產生 Word 格式的輸出。](./media/er-design-configuration-word-suppress-controls-image4.gif)

    請注意，輸出不包含摘要區段，因為它已被隱藏。

## <a name="additional-resources"></a>其他資源

- [設計用於產生 OPENXML 格式報告的設定](./tasks/er-design-reports-openxml-2016-11.md)
- [設計新的 ER 設定以產生 Word 格式的報告](er-design-configuration-word.md)
- [透過 Excel 範本重複使用 ER 設定以產生 Word 格式的報告](./tasks/er-design-configuration-word-2016-11.md)
- [檢查設定的 ER 組件以防止執行階段問題](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
