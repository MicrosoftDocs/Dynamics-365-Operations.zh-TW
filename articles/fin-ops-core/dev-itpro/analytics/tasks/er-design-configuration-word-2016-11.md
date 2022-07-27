---
title: 透過 Excel 範本重複使用 ER 設定以產生 Word 格式的報表
description: 本主題介紹如何將設計用於將報表產生為 Excel 活頁簿的報表格式設定為將報表產生為 Word 文件。
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de8286c7612cd588b28cf4667340374906962dde
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460266"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>透過 Excel 範本重複使用 ER 設定以產生 Word 格式的報表

[!include [banner](../../includes/banner.md)]

若要將報表產生為 Microsoft Word 文件，您可以[設定](../er-design-configuration-word.md)新的[電子報表 (ER)](../general-electronic-reporting.md) 格式。 或者，您可以重複使用最初設計用於將報表產生為 Excel 活頁簿的 ER 格式。 在這種情況下，您必須將 Excel 範本替換為 Word 範本。

以下程序顯示了系統管理員角色或電子報表開發人員角色的使用者如何設定 ER 格式以透過重複使用旨在將報表產生為 Excel 檔案的 ER 格式來將報表產生為 Word 檔案。

這些程序可以在 GBSI 公司中完成。

## <a name="prerequisites"></a>先決條件

若要完成這些程序，您必須先按照[設計用於以 OPENXML 格式產生報表的設定](er-design-reports-openxml-2016-11.md)工作指南中的步驟。

您還必須下載並在本地儲存樣本報表的以下範本：

- [付款報告範本 (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [付款報表的繫結範本 (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

這些過程適用於 Dynamics 365 for Operations 1611 版 (2016 年 11 月) 中新增的函數。

## <a name="select-the-existing-er-report-configuration"></a>選取現有的 ER 報表設定

1. 在 Dynamics 365 Finance 中，進入 **組織管理**\>**工作區**\>**電子報表**。
2. 確保 **Litware, Inc.** 設定提供者被選取為 **作用中**。 如果不是，請按照[建立設定提供者並將其標記為作用中](er-configuration-provider-mark-it-active-2016-11.md)工作指南中的步驟。
3. 選取 **報表設定**。 您將重用現有的 ER 設定，該設定旨在產生 OPENXML 格式的報表輸出。
4. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **付款模型**，然後選取 **樣本工作表報表**。

    > [!NOTE]
    > 可以在 **版本** FastTab 上編輯所選 ER 格式的草稿版本。

5. 選取 **設計工具**。
6. 在 **格式設計工具** 頁面，請注意根格式元素的標題表明現行使用的是 Excel 範本。

![選取現有的設定。](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>查看下載的 Word 範本

1. 在 Word 桌面應用程式中，打開您之前下載的 **SampleVendPaymDocReport.docx** 範本檔案。
2. 驗證範本是否僅包含要產生為 ER 輸出的文件配置。

![桌面應用程式中的 Word 範本配置。](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>將 Excel 範本替換為 Word 範本並新增自訂 XML 組件

現行，Excel 文件用作範本以產生 OPENXML 格式的輸出。 您將使用之前下載的 SampleVendPaymDocReport.docx Word 範本檔案替換此範本。 您還將透過新增自訂 XML 組件來擴展 Word 範本。

1. 在 Finance 中，在 **格式設計工具** 頁面的 **格式** 索引標籤上，選取 **附件**。
2. 在 **附件** 頁面，選取 **刪除** 來移除現有的 Excel 範本。 選取 **是** 確認更改。
3. 選取 **新建**\>**檔案**。

    > [!NOTE]
    > 您必須選取已在 ER 參數中[設定](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)的文件類型來儲存 ER 格式的範本。

4. 選取 **瀏覽**，然後瀏覽並選取您之前下載的 **SampleVendPaymDocReport.docx** 檔案。
5. 選取 **確定**。
6. 關閉 **附件** 頁面。
7. 在 **格式設計工具** 頁，在 **範本** 欄位，輸入或選取 **SampleVendPaymDocReport.docx** 檔案以使用該 Word 範本，而不是以前使用的 Excel 範本。
8. 選取 **儲存**。

    除了儲存設定更改之外，**儲存** 操作更新附加的 Word 範本。 設計格式的階層將作為名為 **Report** 的新自訂 XML 組件新增到附加的 Word 文件中。 附加的 Word 範本包含將作為 ER 輸出產生的文件的配置以及 ER 在執行階段將在該範本中輸入的資料結構。

9. 請注意，根格式元素的標題表明現行使用的是 Word 範本。

    ![將 Excel 範本替換為 Word 範本並新增自訂 XML 組件。](../media/er-design-configuration-word-2016-11-image03.gif)

10. 在 **格式** 索引標籤，選取 **附件**。

您現在可以將 **報表** 自訂 XML 組件的元素對應到 Word 文件的內容控制項。

如果您熟悉將 Word 文件設計為包含對應到[自訂 XML 組件](/visualstudio/vsto/custom-xml-parts-overview)元素的[內容控制項](/office/client-developer/word/content-controls-in-word)的表單的過程，請完成下一個過程中的所有步驟來建立文件。 如需相關資訊，請參閱[建立使用者在 Words 中填入或列印的表單](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b)。 否則，跳過下一個程序。

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>獲取具有自訂 XML 組件的 Word 文件並進行資料對應

1. 在 Finance 中的 **附件** 頁面上，選取 **開啟** 以從 Finance 下載所選範本並將其作為 Word 文件儲存在本地。
3. 在 Word 桌面應用程式中，開啟剛剛下載的文件。
4. 在 **開發人員** 索引標籤上，選取 **XML 對應窗格**。

    > [!NOTE]
    > 如果 **開發人員** 索引標籤未出現在函數區上，請自訂函數區以新增它。

5. 在 **XML 對應** 窗格中，在 **自訂 XML 組件** 欄位，選取 **報表** 自訂 XML 組件。
6. 對應所選 **報表** 自訂 XML 組件的元素和 Word 文件的內容控制項。
7. 將更新後的 Word 文件在本地另存為 **SampleVendPaymDocReportBounded.docx**。

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>查看自訂 XML 組件對應到內容控制項的 Word 範本

1. 在 Word 桌面應用程式中，開啟 **SampleVendPaymDocReportBounded.docx** 範本檔案。
2. 驗證範本是否包含要產生為 ER 輸出的文件配置。 用作 ER 在執行階段將在此範本中輸入的資料的預留位置的內容控制項基於在 **報表** 自訂 XML 組件的元素和 Word 文件的內容控制項之間設定的對應。

![桌面應用程式中的 Word 範本預覽。](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>上傳自訂 XML 組件對應到內容控制項的 Word 範本

1. 在 Finance 中的 **附件** 頁面上，選取 **刪除** 以刪除在 **報表** 自訂 XML 組件的元素和內容控制項之間沒有對應的 Word 範本。 選取 **是** 確認更改。
2. 選取 **新建**\>**檔案** 以新增一個新範本檔案，該檔案包含 **報表** 自訂 XML 組件和內容控制項的元素之間的對應。

    > [!NOTE]
    > 您必須選取已在 ER 參數中[設定](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)的文件類型來儲存 ER 格式的範本。

3. 選取 **瀏覽**，然後瀏覽並選取您下載或透過完成 [獲取具有自訂 XML 組件以進行資料對應的 Word](#get-word-doc)部分中的過程準備的 **SampleVendPaymDocReportBounded.docx** 檔案。
4. 選取 **確定**。
5. 關閉 **附件** 頁面。
6. 在 **格式設計工具** 頁，在 **範本** 欄位，選取您剛剛下載的文件。
7. 選取 **儲存**。
8. 關上 **格式設計工具** 頁面。

## <a name="mark-the-configured-format-as-runnable"></a>將已設定格式標記為可執行

若要執行可編輯格式的草稿版本，您必須使其處於[可執行](../er-quick-start2-customize-report.md#MarkFormatRunnable)狀態。

1. 在 Finance 中，在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
2. 在 **使用者參數** 對話方塊，將 **執行設定** 選項設定為 **是**，然後選取 **確定**。
3. 選取 **編輯** 根據需要使目前的頁面處於可編輯狀態。
4. 對於現行選定的 **樣本工作表報表** 設定，將 **執行草稿** 選項設定為 **是**。
5. 選取 **儲存**。

## <a name="run-the-format-to-create-output-in-word-format"></a>執行格式以建立 Word 格式的輸出

1. 在 Finance 中，進入 **應付帳款**\>**付款**\>**付款日記帳**。
2. 在您之前輸入的付款日記帳中，選取 **行列**。
3. 在 **廠商付款** 頁面，選取格線中的所有行。
4. 選取 **付款狀態**\>**無**。

    ![在廠商付款頁面上進行處理的付款。](../media/er-design-configuration-word-2016-11-image05.png)

5. 在動作窗格上，選取 **產生付款**。
6. 在出現的對話方塊中，執行以下步驟：

    1. 在 **付款方式** 欄位中，選取 **電子**。
    2. 在 **銀行帳戶** 欄位中，選取 **GBSI OPER**。
    3. 選取 **確定**。

7. 在 **電子報表參數** 對話方塊中，選取 **確定**。
8. 產生的輸出以 Word 格式顯示，並包含已處理付款的詳情。 分析產生的輸出。

    ![產生 Word 格式的輸出。](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>其他資源

- [設計新的 ER 設定以產生 Word 格式的報表](../er-design-configuration-word.md)
- [在使用 ER 產生的檔案中嵌入圖像和形狀](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
