---
title: 追蹤產生的報告結果並將它們與基準值做比較
description: 本主題說明如何將產生的電子報表 (ER) 報告的結果與基準報告值進行比較。
author: NickSelin
ms.date: 06/17/2019
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
ms.openlocfilehash: 9fabdef96b02747c84a76bf42997633842f185e9
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460219"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>追蹤產生的報告結果並將它們與基準值做比較

[!include[banner](../includes/banner.md)]

您可以追蹤產生傳出電子文件的電子報表 (ER) 格式的結果。 打開追蹤產生時 (透過使用 **在偵錯模式下執行** ER 使用者參數)，每次執行 ER 報告時，都會在 ER 格式執行記錄中產生一條新的追蹤記錄。 以下詳情儲存在產生的每個追蹤中：

- 驗證規則產生的所有警告
- 驗證規則產生的所有錯誤
- 儲存為追蹤記錄附件的所有產生檔案

您可以儲存任何 ER 格式的單個基準應用程式檔案。 當檔案描述執行報告的預期結果時，它們被視為基準檔案。 如果基準檔案可用於在打開追蹤產生時執行的 ER 格式，則除了前面提到的詳情之外，追蹤還會儲存產生的電子文件與基準檔案的比較結果。 您還可以一鍵取得產生的電子文件及其基準檔案在單個 ZIP 檔案中。 然後，您可以使用 WinDiff 等外部工具進行詳細比較。

您可以評估追蹤以分析產生的電子文件是否包含預期的內容。 當代碼庫已更改時 (例如，當您移轉到應用程式的新執行個體、安裝修補程式包或部署代碼修改時)，您可以在使用者驗收測試 (UAT) 環境中進行此評估。 透過這種方式，您可以確保評估不會影響所使用的 ER 報告的執行。 對於許多 ER 報告，可以在自動模式下進行評估。

若要進一步了解此功能，請播放 **ER 產生報告並比較結果 (第 1 章節)** 和 **ER 產生報告並比較結果 (第 2 章節)** 工作指南，它們是 **7.5.4.3 測試 IT 服務/解決方案 (10679)** 業務流程，並且可從[Microsoft Solution Center](https://go.microsoft.com/fwlink/?linkid=874684)下載。 這些工作指南向您解釋了設定 ER 架構以使用基準檔案來評估產生的電子文件的過程。

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>範例：追蹤產生的報告結果並將它們與基準值做比較

此程序說明如何設定 ER 架構以收集有關 ER 格式執行的資訊，然後評估這些執行的結果。 作為評估的一部分，將產生的文件與其基準檔案進行比較。 在此範例中，您將建立 Litware, Inc. 樣本公司的所需的 ER設定。 此程序適用於指派有系統管理員或電子報表開發人員角色的使用者。 這些步驟可以透過使用任何資料集來完成。

若要完成本範例中的步驟，您必須先完成[建立設定提供者並將其標記為作用中](tasks/er-configuration-provider-mark-it-active-2016-11.md)中的步驟。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定提供者** 區塊，確保列出 Litware, Inc. 樣本公司的設定提供者，並且將它標記為 **作用中**。 如果您沒有看到此設定廠商，請遵循[建立設定廠商並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)中的步驟。

### <a name="configure-document-management-parameters"></a>設定檔案管理參數

1. 進入 **組織管理**\>**文件管理**\>**文件類型**，並建立一個新的文件類型來儲存基準檔案。
2. 在 **分類** 欄位中，輸入 **Attach file**。
3. 在 **分組** 欄位中，輸入 **File**。

![檔案類型頁面。](media/GER-BaselineSample-SetupDocumentType.PNG "文件類型頁面的螢幕擷取畫面")

> [!NOTE]
> 必須為您計劃使用 ER 基準功能的每個資料集設定具有相同名稱的新文件類型。

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>設定 ER 參數以開始使用基準功能

1. 在 **電子報表** 工作區，在 **相關連結** 部分，選取 **電子報表參數**。

    ![電子報表工作區](media/GER-BaselineSample-ERWorkspace.PNG "電子報表工作區的螢幕擷取畫面")

2. 在 **附件** 索引標籤，在 **基準** 欄位，輸入或選取您剛剛建立的文件類型。

    ![電子報表參數頁面的附件索引標籤。](media/GER-BaselineSample-ERParameters.PNG "電子報表參數的螢幕擷取畫面")

3. 選取 **儲存**，然後關閉 **電子報表參數** 頁面。

### <a name="add-a-new-er-model-configuration"></a>新增新的 ER 模型配置

1. 在 **電子報表** 工作區的 **設定** 區塊中，選取 **報告設定** 圖格。
2. 在動作窗格上，選取 **建立設定**。
3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Model to learn ER baselines**。
4. 選取 **建立設定** 確認建立新的 ER 資料模型分錄。

![建立設定對話方塊，新增新的 ER 模型設定。](media/GER-BaselineSample-ModelAdd.PNG "建立設定下拉式對話方塊的螢幕擷取畫面")

### <a name="design-a-data-model"></a>設計資料模型

1. 在 **設定** 頁面，在動作窗格上，選取 **設計工具**。
2. 選取 **新增**。
3. 在下拉式對話方塊中，在 **名稱** 欄位中，輸入 **Root**。
4. 選取 **新增**。
5. 選取 **根參考**。
6. 選取 **確定**，然後選取 **儲存**。
7. 關上 **模型設計工具** 頁面。
8. 選取 **更改狀態**。
9. 選取 **完成**，然後選取 **確定**。

![設定頁面。](media/GER-BaselineSample-ModelComplete.PNG "設定頁面的螢幕擷取畫面")

### <a name="add-a-new-er-format-configuration"></a>新增新的 ER 格式設定

1. 在 **設定** 頁面，在動作窗格上，選取 **建立設定**。
2. 在下拉式對話方塊中，在 **新建** 欄位群組，選取 **根據資料模型模擬學習 ER 基準的格式**。
3. 在 **名稱** 欄位中，輸入 **Format to learn ER baselines**。
4. 選取 **建立設定** 確認建立新的 ER 格式分錄。

![建立設定對話方塊，新增新的 ER 格式設定。](media/GER-BaselineSample-FormatAdd.PNG "建立設定下拉式對話方塊的螢幕擷取畫面")

### <a name="design-a-format"></a>設計格式

對於此範例，您將建立一個簡單的 ER 格式來產生 XML 文件。

1. 在 **設定** 頁面，在動作窗格上，選取 **設計工具**。
2. 選取 **新增根**。
3. 在下拉式對話方塊中，執行以下步驟：

    1. 在樹狀結構中，選取 **常見\\檔案**。
    2. 在 **名稱** 欄位中，輸入 **Output**。
    3. 選取 **確定**。

4. 選取 **新增**。
5. 在下拉式對話方塊中，執行以下步驟：

    1. 在樹狀結構中，選取 **XML\\元素**。
    2. 在 **名稱** 欄位中，輸入 **Document**。
    3. 選取 **確定**。

6. 在樹狀結構中，選取 **輸出\\文件**。
7. 選取 **新增**。
8. 在下拉式對話方塊中，執行以下步驟：

    1. 在樹狀結構中，選取 **XML\\屬性**。
    2. 在 **名稱** 欄位中，輸入 **ID**。
    3. 選取 **確定**。

    ![格式設計工具頁面，在樹狀結構中選取的 XML 屬性。](media/GER-BaselineSample-FormatLayoutDesign.PNG "格式設計工具頁面的螢幕擷取畫面")

9. 在 **對應** 索引標籤上，選取 **刪除**。
10. 選取 **新增根**。
11. 在下拉式對話方塊的樹狀結構中，選取 **一般\\使用者輸入參數**，然後按照以下步驟動作：

    1. 在 **名稱** 欄位中，輸入 **ID**。
    2. 在 **標籤** 欄位，輸入 **Enter ID**。
    3. 選取 **確定**。

12. 在樹狀結構中，選取 **輸出\\文件\\識別碼**。
13. 選取 **繫結**，然後選取 **儲存**。

![格式設計工具頁面，對應索引標籤。](media/GER-BaselineSample-FormatMappingDesign.PNG "格式設計工具頁面的螢幕擷取畫面")

根據設計的結構，設定的格式將產生一個 XML 檔案。 此 XML 包含 **根** 元素，該元素的 **識別碼** 屬性設定為使用者在 ER 執行階段對話方塊中輸入的值。

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>為設計的 ER 格式產生新的基準檔案

1. 在 **設定** 頁面上，在 **版本** FastTab，選取 **執行**。
2. 在 **輸入識別碼** 欄位，輸入 **1**。
3. 選取 **確定**。

    ![電子報表參數對話方塊。](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "電子報表參數對話方塊的螢幕擷取畫面")

4. 儲存產生的 **out.Admin.xml** 檔案的本機副本，以便以後可以將其用作此 ER 格式的基準。

    ![有關設定頁面上產生的檔案的通知。](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "設定頁面上關於產生檔案的通知螢幕擷取畫面")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>設定 ER 參數以使用基準功能

1. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，選取 **使用者參數**。
2. 將 **在偵錯模式下執行** 選項設定為 **是**。
3. 選取 **確定**。

![使用者參數對話方塊。](media/GER-BaselineSample-ERUserParameters.PNG "使用參數對話方塊的螢幕擷取畫面")

### <a name="add-a-new-baseline-for-designed-er-format"></a>為設計的 ER 格式新增新基準

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在動作窗格上，選取 **基準**。

    ![設定頁面上的基準按鈕。](media/GER-BaselineSample-OpenBaselinePage.PNG "設定頁面上的基準按鈕的螢幕擷取畫面")

3. 在動作窗格上，選取 **新建**。
4. 選取您之前設計的 **學習 ER 基準的格式** ER 格式。
5. 選取 **儲存**。

![電子報表格式基準線頁面。](media/GER-BaselineSample-AddBaseline.PNG "電子報表格式基準頁面的螢幕擷取畫面")

為 **學習 ER 基準的格式** 格式新增了基準。

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>為新增的基準設定基準規則

1. 在 **電子報表格式基準** 頁面，在動作窗格上，選取 **附件** 按鈕 (迴紋針符號)。
2. 在動作窗格上，選取 **新建**\>**檔案**。 在 ER 參數中，該 **檔案** 文件類型之前應選取為用於儲存基準檔案的文件類型。
3. 選取 **瀏覽**，並選取之前執行已設定 ER 格式時產生的 **out.Admin.xml** 檔案。

    ![附件頁面。](media/GER-BaselineSample-UploadBaselineFile.PNG "附件頁面的螢幕擷取畫面")

4. 關閉 **附件** 頁面。
5. 在 **基準** FastTab 上，選取 **新建**。
6. 在 **名稱** 欄位中，輸入 **Baseline 1**。
7. 在 **檔案組件名稱** 欄位中，輸入或選取 **Output**。 此值表示設定的基準將與使用 **輸出** 格式元素產生的檔案進行比較。
8. 在 **檔案名稱遮罩** 欄位，輸入 **\*.xml**。

    > [!NOTE]
    > 您可以定義檔案名稱遮罩。 定義檔案名稱遮罩後，僅當產生的輸出檔案的名稱滿足該遮罩時，才會使用基準記錄來評估產生的輸出。

9. 如果僅當登入到特定公司的使用者執行 **學習 ER 基準的格式** ER 格式時才應使用設定的基準，請在 **公司** 欄位中選取這些公司。
10. 在 **基準** 欄位，輸入或選取 **out.Admin** 附件。
11. 選取 **儲存**。

![電子報表格式基準頁面，含已選取基準的基準 FastTab。](media/GER-BaselineSample-SetupBaselineLine.PNG "電子報表格式基準頁面的螢幕擷取畫面")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>執行設計的 ER 格式並查看記錄以分析結果

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在樹狀結構中，展開 **學習 ER 基準的模型**，然後選取 **學習 ER 基準的模型\\學習 ER 基準的格式**。
3. 在 **版本** FastTab 上，選取 **執行**。
4. 在 **輸入識別碼** 欄位，輸入 **1**。
5. 選取 **確定**。
6. 進入 **組織管理**\>**電子報表**\>**設定偵錯記錄**。

    ![具有相同基準的電子報表執行記錄頁面。](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "電子報表執行記錄頁面的螢幕擷取畫面")

    > [!NOTE]
    > 執行記錄包含已產生檔案與已設定基準比較結果的相關資訊。 在此範例中，記錄指示已產生檔案和基準相等。

7. 選取 **刪除全部**。

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>執行設計的 ER 格式並查看記錄以分析結果

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在樹狀結構中，展開 **學習 ER 基準的模型**，然後選取 **學習 ER 基準的模型\\學習 ER 基準的格式**。
3. 在 **版本** FastTab 上，選取 **執行**。
4. 在 **輸入識別碼** 欄位，輸入 **2**。
5. 選取 **確定**。
6. 進入 **組織管理**\>**電子報表**\>**設定偵錯記錄**。

    ![電子報表執行記錄頁，有不同的基準。](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "電子報表執行記錄頁面的螢幕擷取畫面")

    > [!NOTE]
    > 執行記錄包含已產生檔案與已設定基準比較結果的相關資訊。 在此範例中，該記錄指示已產生檔案和基準不同。

7. 選取 **公司**。

> [!NOTE]
> 已產生檔案和基準檔案以 ZIP 檔案的形式提供。 您可以使用 WinDiff 等外部比較工具來比較檔案並查看差異。

## <a name="additional-resources"></a>其他資源

- [設定電子報表 (ER) 架構](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
