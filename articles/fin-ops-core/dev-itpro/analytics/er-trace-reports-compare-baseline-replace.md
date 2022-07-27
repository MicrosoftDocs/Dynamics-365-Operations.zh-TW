---
title: 改進追蹤產生的 ER 報表的結果以與基準值進行比較
description: 本主題介紹 Microsoft Dynamics 365 for Finance and Operations 版本 10.0.3 (2019 年 6 月) 中 ER 基準功能的改進。
author: NickSelin
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: b6e8299dd57730486c731cd38578bd5ff6b8a1754f145432e300c1217c6dd640
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460221"
---
# <a name="improve-tracing-the-results-of-generated-er-reports-to-compare-with-baseline-values"></a>改進追蹤產生的 ER 報表的結果以與基準值進行比較

[!include[banner](../includes/banner.md)]

本主題描述了對電子報表 (ER) 架構的基準功能進行的第一組改進。 這些改進在 Microsoft Dynamics 365 for Finance and Operations 版本 10.0.3 (2019 年 6 月) 及更高版本中提供。

## <a name="automate-the-setting-of-baseline-rules"></a>自動設定基準規則

[追蹤產生的報表結果並將它們與基準值進行比較](er-trace-reports-compare-baseline.md) 主題解釋了如何配置 ER 架構以收集有關 ER 格式執行的資訊並評估這些執行的結果。 本主題中的範例顯示了必須完成的步驟。

以下是一些步驟：

- 運行 ER 格式以產生出站檔案，並將檔案儲存在本地。
- 將本地儲存的檔案新增為為 ER 格式新增的基準的附件。
- 為新增的基準配置基準規則。 此配置包括以下步驟：

    - 指定用於產生出站檔案的 ER 格式元素。
    - 選取參考產生的出站檔案的附件。

> [!NOTE]
> 這些步驟必須手動完成，即使新的 ER 功能使它們能夠自動化。 若要了解有關此功能的更多資訊，請完成以下範例。

## <a name="example-automate-the-setting-of-baseline-rules"></a>範例：自動設定基準規則

若要完成此範例中的步驟，您必須先完成[追蹤產生的報表結果並將它們與基準值進行比較](er-trace-reports-compare-baseline.md)主題中範例中的步驟，直至整個「為設計的 ER 格式新增新基準」章節。

### <a name="review-added-baseline"></a>查看新增的基準

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 選取 **基準**。

    > [!NOTE]
    > 僅在目前公司的 **在偵錯模式下運行** ER 使用者參數打開時，動作窗格上的 **基準** 按鈕才可用。

已為選定的 **學習 ER 基準的格式** 格式新增了基準，但尚未為此基準新增基準規則。

![電子報表格式基準線頁面，尚無規則。](media/GER-BaselineSample-AddBaseline2.PNG "電子報表格式基準頁面的螢幕擷取畫面")

### <a name="make-a-new-baseline-rule"></a>制定新的基準規則

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在樹狀結構中，展開 **學習 ER 基準的模型**。
3. 在樹狀結構中，選取 **學習 ER 基準的模型\\學習 ER 基準的格式**。
4. 在 **版本** FastTab 上，選取 **執行**。
5. 在 **輸入識別碼** 欄位，輸入 **1**。
6. 將 **製作基準檔案** 選項設定為 **是**。
7. 選取 **確定**。
8. 選取 **基準**。

    ![電子報表格式基準線頁面，已選取基準。](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "電子報表格式基準頁面的螢幕擷取畫面")

    產生的出站檔案已自動附加到執行的 ER 格式的基準。 基準規則已自動新增到此基準，並且還包含對附加檔案的參考。

9. 在 **名稱** 欄位中，輸入 **Baseline 1**。
10. 在 **檔案名稱遮罩** 欄位，輸入 **.xml**。
11. 選取 **儲存**。

### <a name="run-the-format"></a>執行格式

您現在已準備好完成[追蹤產生的報表結果並將它們與基準值進行比較](er-trace-reports-compare-baseline.md)主題中範例中的剩餘步驟，從「運行設計的 ER 格式並查看記錄以分析結果」章節開始。

> [!NOTE]
> 當您刪除 **基準** FastTab 上自動新增的基準規則時，參考的附件不會自動刪除。

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>配置基準，使其忽略不斷變化的 ER 輸出部分

如果 ER 格式設計為包含在運行格式時更改的資訊，則必須要求該格式使用 ER 基準功能將產生的結果與基準值進行比較。 例如，該資訊可能是處理日期和時間或產生的不同格式文件的唯一識別碼 (全域唯一識別碼\[GUID\]等等)。 新的 ER 功能允許您配置基準規則，以便在運行格式時忽略 ER 格式的可變元素，以便將基準值與格式執行的結果進行比較。 若要了解有關此功能的更多資訊，請完成以下範例。

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>範例：配置基準，使其忽略不斷變化的 ER 輸出部分

若要完成此範例中的步驟，您必須先完成[追蹤產生的報表結果並將它們與基準值進行比較](er-trace-reports-compare-baseline.md)主題中範例中的步驟。

### <a name="modify-a-configured-er-format"></a>修改配置的 ER 格式

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在樹狀結構中，展開 **學習 ER 基準的模型**。
3. 在樹狀結構中，選取 **學習 ER 基準的模型\\學習 ER 基準的格式**。
4. 選取 **設計工具**。
5. 在樹狀結構中，選取 **輸出\\文件**。
6. 選取 **新增**。
7. 在下拉式對話方塊的樹狀結構中，選取 **XML\\屬性**。
8. 在 **名稱** 欄位中，輸入 **ProcessingDateTime**。
9. 選取 **確定**。
10. 在 **對應** 索引標籤，在樹狀結構中，選取 **輸出\\文件\\ProcessingDateTime**。
11. 選取 **編輯公式**。
12. 在 **公式** 欄位中，輸入以下運算式：**DATETIMEFORMAT(NOW(), "O")**
13. 選取 **儲存**，然後選取 **測試**。
14. 選取 **測試** 再次重新測試配置的運算式。

    ![公式設計工具頁面。](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "公式設計工具頁面的螢幕擷取畫面")

    > [!NOTE]
    > **測試結果** 索引標籤顯示配置的運算式在調用時回傳不同的日期和時間值。

15. 關閉 **公式設計工具** 頁面，然後選取 **儲存**。

    ![格式設計工具頁面。](media/GER-BaselineSample-FormatMappingDesign2.PNG "格式設計工具頁面的螢幕擷取畫面")

16. 關上 **格式設計工具** 頁面。

### <a name="remove-an-existing-baseline-rule"></a>刪除現有的基準規則

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 選取 **基準**。
3. 在基準清單中，選取為 **學習 ER 基準的格式** 格式配置的基準。
4. 在 **基準** FastTab 上，選取 **刪除** 來刪除您之前配置的基準規則。

![電子報表格式基準線頁面，已刪除。](media/GER-BaselineSample-AddBaseline3.PNG "電子報表格式基準頁面的螢幕擷取畫面")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>為設計的 ER 格式的繫結定義替換

1. 在 **設定** 頁面上，在 **替換** FastTab 上，選取 **選取組件**。
2. 在格式組件樹狀結構中，展開 **輸出**，展開 **輸出\\文件**，然後選中核取方塊 **輸出\\文件\\ProcessingDateTime**。
3. 選取 **確定**。

![電子報表格式基準線頁面，組件。](media/GER-BaselineSample-AddBaseline4.PNG "電子報表格式基準頁面的螢幕擷取畫面")

選定的 ER 格式組件已新增到 **替換** FastTab 上的組件清單中。 當基本 ER 格式在偵錯模式下執行階段，每個組件的格式繫結將替換為 **繫結** 欄中顯示的繫結。 若要更改 **替換** FastTab 上列出的組件的預設繫結，請選取 **編輯**。

### <a name="make-a-new-baseline-rule"></a>制定新的基準規則

按照本主題前面的「範例：自動設定基準規則」章節中的步驟進行動作。 通知警告您已使用基準設定產生出站檔案，並且已發生格式繫結的強制替換。

![配置頁面上的通知。](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "設定頁面上的通知螢幕擷取畫面")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>隱藏有關替換格式繫結的警告

透過設定特定的 ER 參數，您可以隱藏警告格式繫結替換的通知。 當使用 Regression Suite Automation Tool 在無人值手模式下替換格式繫結時，此隱藏動作非常有用。 在這種情況下，可以將警告視為正在運行的測試案例的失敗。

1. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，選取 **使用者參數**。
2. 將 **隱藏基準警告** 選項設定為 **是**，然後選取 **確定**。

### <a name="review-the-generated-baseline-file"></a>查看產生的基準檔案

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 選取 **基準**。
3. 選取 **附件**。
    > [!NOTE]
    > 產生的檔案包含來自在新增的基準規則中配置的繫結的處理日期和時間文字 (**"#"**)，而不是來自格式的繫結。
    
4. 關閉 **附件** 頁面。

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>執行設計的 ER 格式並查看記錄以分析結果

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在樹狀結構中，展開 **學習 ER 基準的模型**。
3. 在樹狀結構中，選取 **學習 ER 基準的模型\\學習 ER 基準的格式**。
4. 在 **版本** FastTab 上，選取 **執行**。
5. 在 **輸入識別碼** 欄位，輸入 **1**。
6. 選取 **確定**。
7. 進入 **組織管理**\>**電子報表**\>**設定偵錯記錄**。

執行記錄包含已產生檔案與已設定基準比較結果的相關資訊。 該記錄表明產生的檔案和基準是相等的，即使執行的格式包含在出站檔案中輸入不斷變化的日期和時間值的繫結。

> [!NOTE]
> 儘管已使用強制替換格式繫結的基準設定產生出站檔案，但您不會收到任何有關替換的警告。

## <a name="exchange-baseline-settings-between-environments"></a>在環境之間交換基準設定

### <a name="export-baseline-settings"></a>匯出基準線設定

新的 ER 功能允許您從目前環境中匯出所選 ER 格式的基準設定，並將它們儲存為 XML 檔案。 

若要匯出基準設定，在 **電子報表格式基準** 頁面，選取 **匯出**。

### <a name="import-baseline-settings"></a>匯入基準線設定

匯出的基準設定可以匯入到不同的環境中。 必須先將環境作為 ER 格式匯入。 您可以隨後匯入基準設定。

若要從本地儲存的 XML 檔案匯入基準設定，在 **電子報表格式基準** 頁面，選取 **匯入**，然後選取 **瀏覽** 選取 XML 檔案。

![匯入基準線設定對話方塊。](media/GER-BaselineSample-ImportBaseline1.PNG "匯入基準設定對話方塊的螢幕擷取畫面")

若要根據目前文件管理設定和所選文件類型從儲存在 Microsoft SharePoint Server 上的 XML 檔案匯入基準設定，請在 **電子報表格式基準** 頁面上選取 **從來源匯入**。 然後選取文件類型和 XML 檔案。 必須提前配置存取 SharePoint 資料夾所需的文件類型。

![從來源對話方塊匯入。](media/GER-BaselineSample-ImportBaseline2.PNG "從來源匯入對話方塊的螢幕擷取畫面")

> [!NOTE]
> 您可以使用工作記錄器記錄在 **從來源匯入** 對話方塊中選取所需文件類型和檔案名稱的步驟。 透過這種方式，您可以在 SharePoint Server 上保留所需的基準設定，然後在使用 Regression Suite Automation Tool 運行自動化測試時透過播放工作記錄來自動匯入它們。

## <a name="additional-resources"></a>其他資源

- [追蹤產生的報告結果並將它們與基準值做比較](er-trace-reports-compare-baseline.md)
- [工作記錄器資源](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
