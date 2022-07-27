---
title: 使用電子報表自動測試
description: 本主題說明如何使用電子報表 (ER) 架構的基準函數來自動化函數測試。
author: NickSelin
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: da69cc903197dbfae536c8494f126074c51aa77f9522d57f2673c97b1e682d9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460512"
---
# <a name="automate-testing-with-electronic-reporting"></a>使用電子報表自動測試

[!include[banner](../includes/banner.md)]

本主題說明您如何使用電子報表 (ER) 架構來自動化某些函數的測試。 本主題中的範例顯示了如何自動化廠商付款處理的測試。

該應用程式使用 ER 架構在廠商付款處理期間產生付款檔案和相應的文件。 ER 架構由資料模型、模型對應和格式組件組成，支援不同付款類型的付款處理和不同格式文件的產生。 這些組件可以從 Microsoft Dynamics Lifecycle Services (LCS) 下載並匯入到執行個體中。

您還可以自訂每個 Microsoft 組件並將其用作您自己的自訂組件的基礎。 透過建立自訂版本，您可以做出支援特定要求的改變。 例如，您可以調整 ER 資料模型和 ER 模型對應以存取客戶特定的應用程式資料，或者您可以更改 ER 格式以修改產生文件的配置。

您可以使用自訂 ER 格式來處理產生廠商付款的付款檔案以及處理控制報告。 ER 組件支援版本設定。 因此，Microsoft 可以為廠商付款處理提供更新版本的 ER 解決方案，並且您可以透過重訂基底自動將更新版本與您的自訂組件合併。 但是，您必須測試重訂基底的版本以確保它按預期工作。

ER 資料模型和 ER 模型對應對於許多 ER 格式很常用，這些格式用於處理不同類型的付款並產生特定於國家/地區的付款文件。 因此，非常希望自動化使用者驗收和整合測試，以便在多個公司中自動完成，但要考慮每個目標公司的國家/地區內容、使用不同的資料集等等。

如需如何根據您從設定提供者那裡收到的格式建立自訂版本的格式的相關資訊，請參閱[透過採用該格式的新基礎版本來 ER 升級您的格式](./tasks/er-upgrade-format.md)。

## <a name="key-concepts"></a>關鍵概念

函數強大的使用者可以編寫使用者驗收和整合測試，而無需編寫原始程式碼。

- 使用 ER 基準函數將產生的文件與主副本做比較。 如需相關資訊，請參閱[追蹤產生的報告結果並將它們與基準值做比較](er-trace-reports-compare-baseline.md)。
- 使用工作記錄器記錄測試案例，並包括基準評估。 如需相關資訊，請參閱[工作記錄器資源](../user-interface/task-recorder.md)。
- 針對所需的測試情境對測試案例進行分組。 如需相關資訊，請參閱[建立和自動化使用者驗收測試](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)。

    - 使用 LCS 中的商業流程建模工具 (BPM) 製作用於使用者驗收測試庫。
    - 使用 BPM 測試庫建立測試計畫和 Microsoft Azure DevOps Services (Azure DevOps) 中的測試套件。

函數強大的使用者可以執行使用者驗收和整合測試。

- 使用 Regression Suite Automation Tool (RSAT) 執行所需測試套件的測試案例。
- 向 Azure DevOps 報告測試結果，並使用該服務調查這些結果。

## <a name="prerequisites"></a>先決條件

在您完成本主題的任務之前，您必須完成以下先決條件：

- 部署支援測試自動化的拓撲。 您必須有權針對 **系統管理員** 角色存取此拓撲的執行個體。 此拓撲必須包含將在此範例中使用的示範資料。 如需相關資訊，請參閱[部署和使用支援持續構建和測試自動化的環境](../perf-test/continuous-build-test-automation.md)。
- 若要自動執行使用者驗收和整合測試，您必須在您正在使用的拓撲中安裝 RSAT 並以適當的方式設定。 如需如何安裝和設定 RSAT 並設定可與財務和營運應用程式和 Azure DevOps 相容的相關資訊，請參閱[Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)。 注意使用該工具的先決條件。 下圖顯示了 RSAT 設定的範例。 藍色矩形包圍指定存取 Azure DevOps 的參數。 綠色矩形包圍指定存取執行個體的參數。

    ![RSAT 設定](media/GER-Configure.png "RSAT 設定對話方塊的螢幕擷取畫面")

- 若要在套件中組織測試範例以確保正確的執行順序，以便您可以收集到測試執行記錄以進行進一步報告和調查，您必須從部屬的拓樸存取 Azure DevOps。
- 若要完成本主題中的範例，我們建議您下載[RSAT 測試的 ER 使用方式](https://go.microsoft.com/fwlink/?linkid=874684)。 此 ZIP 檔案包含以下任務指南：

    | 內容                                           | 檔案名稱和位置 |
    |---------------------------------------------------|------------------------|
    | 樣本任務記錄以準備測試用的資料 | 準備\\記錄.xml |
    | 處理廠商付款的樣本工作記錄   | 流程\\記錄.xml |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>準備應付帳款模組以處理廠商付款

1. 登入到您的執行個體。
2. 從 LCS 下載以下 ER 設定。 如需說明，請參閱[ER 匯入 Lifecycle Services 設定](./tasks/er-import-configuration-lifecycle-services.md)。

    - **付款模型** ER 模型設定
    - **付款模型對應 1611** ER 模型對應設定
    - **BACS (UK)** ER 格式設定

    ![電子報表設定](media/GER-Configurations.png "電子報表中設定頁面的螢幕擷取畫面")

3. 選取 **GBSI** 示範資料公司，在英國有國家/地區內容。
4. 設定應付帳款參數：

    1. 進入 **應付帳款 \>付款安裝 \>付款方式**。
    2. 選取 **電子** 付款方式。
    3. 設定所選的付款方式，使其使用您之前為廠商付款處理下載的 **BACS (UK)** ER 格式：

        1. 在 **檔案格式** FastTab 上，將 **常用電子匯出格式** 設定選項為 **是**。
        2. 在 **匯出格式設定** 欄位，選取 **BACS (UK)**。

    ![付款方式頁面。](media/GER-APParameters.png "付款方式頁面的螢幕擷取畫面")

    > [!NOTE]
    > 如果您擁有為支援自訂而建立的此 ER 格式衍生版本，您可以在 **電子** 付款方式中選取此設定。

5. 建立範例廠商付款：

    1. 進入 **應付帳款 \> 付款 \>付款日記帳**。
    2. 確保您沒有過帳付款日記帳。

        ![付款日記帳頁面。](media/GER-APJournal.png "付款日記帳頁面的螢幕擷取畫面")

    3. 選取 **明細**，然後輸入包含以下資訊的明細。

        | 欄位               | 範例值   |
        |---------------------|-----------------|
        | 廠商名稱         | GB\_SI\_000001  |
        | 借               | 1,000.00        |
        | 貨幣            | 英鎊             |
        | 沖銷帳戶類型 | 銀行            |
        | 沖銷帳戶      | GBSI OPER       |
        | 付款方式   | 電子      |

    ![廠商付款頁面。](media/GER-APJournalLines.png "廠商付款頁面的螢幕擷取畫面")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>準備 ER 架構以測試廠商付款處理

### <a name="configure-er-parameters"></a>設定 ER 參數

1. 進入 **組織管理\>電子報表\>電子報表參數**。
2. 在 **附件** 索引標籤上，在 **基準** 欄位中，選取 **檔案** 作為文件管理 (DM) 架構用於將與基準函數相關的文件儲存為 DM 附件的文件類型。

    ![電子報表參數頁面。](media/GER-ERParameters.png "電子報表參數頁面的螢幕擷取畫面")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>產生廠商付款相關文件的基準副本

1. 進入 **應付帳款 \> 付款 \>付款日記帳**。
2. 選取 **明細**。
3. 選取 **產生付款**。
4. 選取 **電子** 付款方式。
5. 選取 **GBSI OPER** 銀行帳戶。
6. 將 **列印控制報表** 選項設為 **是**。
7. 將產生的輸出下載為 ZIP 檔案。
8. 打開下載的檔案。
9. 從下載的檔案中擷取以下檔案：

    - 文字格式中的 **檔案** 付款檔案
    - XLSX 格式中的 **ERVendOutPaymControlReport** 控制報告檔案

    ![擷取的檔案。](media/GER-APJournalProcessed.png "Windows Explorer 中擷取的檔案名稱的螢幕擷取畫面")

### <a name="turn-on-the-er-baseline-feature"></a>打開 ER 基準函數

1. 進入 **組織管理\>電子報表\>設定**。
2. 在動作窗格上，於 **設定** 索引標籤上，選取 **使用者參數**。
3. 將 **在偵錯模式下執行** 選項設定為 **是**。

透過打開 **在偵錯模式下執行** 參數，您強制 ER 架構在執行任何產生輸出文件的 ER 格式後執行以下操作：

1. 確定是否為執行的 ER 格式的任何組件設定了基準。
2. 確定每個設定的基準是否適用於現行條件 (登入公司的公司代碼、產生的輸出檔案名稱和檔案副檔名等)。
3. 對於每個適用的基準，執行以下操作：

    1. 將執行 ER 格式期間產生的輸出與相應的基準進行比較。
    2. 將比較結果儲存在 ER 設定偵錯記錄中。

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>為廠商付款處理設定 ER 基準

1. 進入 **組織管理\>電子報表\>設定**。
2. 選取 **基準**。
3. 選取 **新建**。
4. 在 **參考** 欄位中，選取 **BACS (UK)** 格式。
5. 選取 **附件**。
6. 為廠商付款檔案新增新基準：

    1. 選取 **新建**。
    2. 在 **類型** 欄位中，選取您在 ER 參數中設定以儲存基準製造物 **檔案** DM 文件類型。
    3. 瀏覽以選取文字格式中本地儲存的 **檔案** 付款檔案。
    4. 在 **說明** 欄位中，輸入 **Payment TXT file**。

7. 為廠商付款的控制報告新增新基準：

    1. 選取 **新建**。
    2. 在 **類型** 欄位中，選取您在 ER 參數中設定以儲存基準製造物 **檔案** DM 文件類型。
    3. 瀏覽以選取 XLSX 格式中本地儲存的 **ERVendOutPaymControlReport** 控制報告檔案。
    4. 在 **說明** 欄位中，輸入 **Payment XLSX control report**。

    ![廠商付款檔案的基準和控制報告。](media/GER-BaselineAttachments.png "含選定付款 XLSX 控制報告的設定頁面的螢幕擷取畫面")

8. 關閉頁面。
9. 在 **基準** FastTab 上，選取 **新建** 為付款檔案設定基準：

    1. 命名明細 **付款檔案的基準設定**。
    2. 在 **檔案組件名稱** 欄位中，選取 **檔案** 將此基準套用在以 BACS (UK) 文字格式產生付款檔案的 ER 格式輸出。
    3. 在 **公司** 欄位中，選取 **GBSI** 在 **BACS (UK)** ER 格式於 GBSI 公司中執行時套用此基準。
    4. 在 **檔案名稱遮罩** 欄位中，輸入 **\*.TXT** 僅將此基準套用於具有 **.txt** 檔案副檔名的 **檔案** 格式組件。
    5. 在 **基準** 欄位中，選取 **付款 TXT 檔案** 以便此基準用於與產生的輸出進行比較。

10. 選取 **新建** 為控制報告設定基準：

    1. 命名明細 **控制報告的基準設定**。
    2. 在 **檔案組件名稱** 欄位中，選取 **ERVendOutPaymControlReport** 將此基準套用在產生控制報告的 ER 格式輸出。
    3. 在 **公司** 欄位中，選取 **GBSI** 在 **BACS (UK)** ER 格式於 GBSI 公司中執行時套用此基準。
    4. 在 **檔案名稱遮罩** 欄位中，輸入 **\*.XLSX** 僅將此基準套用於具有 **.xslx** 檔案副檔名的 **ERVendOutPaymControlReport** 格式組件。
    5. 在 **基準** 欄位中，選取 **付款 XLSX 控制報告** 以便此基準用於與產生的輸出進行比較。

    ![設定頁面上的基準 FastTab。](media/GER-BaselineRules.png "設定頁面上的基準 FastTab 的螢幕擷取畫面")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>記錄測試以驗證廠商付款處理

作為函數強大的使用者，您可以記錄自己的步驟來測試廠商付款處理。 我們建議您播放 (並根據需要編輯) 您之前下載的 **準備\\記錄.xml** 工作記錄。 此記錄用於將所有測試資料設定為正確狀態。 該步驟是必需的，因為測試可以進行多次，並且每次測試都必須使用處於相同狀態的資料。

### <a name="reset-user-settings"></a>重設使用者設定

1. 打開預設儀表板。
2. 選取 **設定** 按鈕 (齒輪符號)。
3. 選取 **使用者選項**。
4. 選取 **使用方式資料**。
5. 選取 **取消選取**。
6. 選取 **是** 以確認您要重設使用方式資料。
7. 關閉頁面。

### <a name="record-the-steps-to-prepare-data-for-testing"></a>記錄為測試準備資料的步驟

1. 選取 **設定** 按鈕 (齒輪符號)。
2. 選取 **工作記錄器**。
3. 選取 **播放錄製內容**。
4. 選取 **從這部電腦開啟**。
5. 選取 **瀏覽**，並選取本地儲存 **準備\\記錄.xml** 檔案。
6. 選取 **開始**。
7. 繼續選取 **播放下一個待處理步驟** 直到播放完錄製內容中的所有步驟。

此工作記錄執行以下操作：

1. 將已處理付款明細的狀態設定為 **無**。

    ![工作記錄步驟 3 到 4。](media/GER-Recording1Review1.png "工作記錄步驟 3 到 4 的工作")

2. 打開 **在偵錯模式下執行** ER 使用者參數。

    ![工作記錄步驟 9 到 10。](media/GER-Recording1Review2.png "工作記錄步驟 9 到 10 的螢幕擷取畫面")

3. 清理包含產生檔案與基準比較結果的 ER 偵錯記錄。

    ![工作記錄步驟 13 到 15。](media/GER-Recording1Review3.png "工作記錄步驟 13 到 15 的螢幕擷取畫面")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>記錄測試廠商付款處理的步驟

我們建議您播放 (並根據需要編輯) 您之前下載的 **處理\\記錄.xml** 工作記錄。 此記錄用於處理廠商付款並驗證產生的文件與相應基準的比較結果。

1. 選取 **設定** 按鈕 (齒輪符號)。
2. 選取 **工作記錄器**。
3. 選取 **播放錄製內容**。
4. 選取 **從這部電腦開啟**。
5. 選取 **瀏覽**，並選取本地儲存的 **處理\\記錄.xml** 檔案。
6. 選取 **開始**。
7. 繼續選取 **播放下一個待處理步驟** 直到播放完錄製內容中的所有步驟。

此工作記錄執行以下操作：

1. 開始廠商付款處理。
2. 選取正確的執行階段參數，並打開產生控制報告。

    ![工作記錄步驟 3 到 8。](media/GER-Recording2Review1.png "工作記錄步驟 3 到 8 的螢幕擷取畫面")

3. 存取 ER 偵錯記錄以紀錄產生輸出與相應基準的比較結果。

    在 ER 偵錯記錄中，比較的結果出現在 **產生的文字** 欄位。 **格式組件** 和 **格式化導致記錄分錄的路徑** 來為是指已將產生的輸出與基準進行比較的檔案組件。

    ![電子報表執行記錄頁面上的分錄。](media/GER-ERDebugLog.png "電子報表執行記錄頁面上的分錄的螢幕擷取畫面")

4. 現行輸出與基準的比較透過使用 **驗證** 工作記錄器選項記錄並選取 **現行值**。

    ![使用驗證選項與現行值進行比較。](media/GER-TRRecordValidation.png "使用驗證選項與現行值進行比較的螢幕擷取畫面")

    下圖顯示了工作記錄中記錄的驗證步驟的樣子。

    ![工作記錄步驟 13 和 15。](media/GER-Recording2Review2.png "工作記錄步驟 13 和 15 的螢幕擷取畫面")

## <a name="add-the-recorded-tests-to-azure-devops"></a>將記錄的測試新增到 Azure DevOps

1. 開啟 Azure DevOps 環境。
2. 當您[設定工具](#prerequisites)時，選取您在 RSAT 參數中定義的專案。
3. 當您[設定工具](#prerequisites)時，選取您在 RSAT 參數中定義的測試方案。
4. 為選定的測試方案建立新的測試案例：

    1. 命名測試案例 **準備資料以測試廠商電子付款的處理**。
    2. 從您之前下載的 **準備** 資料夾附上 **記錄.xml** 檔案。

5. 為選定的測試方案建立新的測試案例：

    1. 命名測試案例 **使用 ER 格式 BACS (UK) 測試廠商付款處理**。
    2. 從您之前下載的 **處理** 資料夾附上 **記錄.xml** 檔案。

    ![選定測試方案的新測試案例。](media/GER-RSAT-DevOps-Tests-Passed.png "選定測試方案的新測試案例的螢幕擷取畫面")

> [!NOTE]
> 注意新增測試的正確執行順序。

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>準備 RSAT 以執行記錄的測試

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>從 Azure DevOps 載入測試到 RSAT

1. 在現行拓撲中打開本地 RSAT 應用程式。
2. 選取 **載入** 將現行駐留在 Azure DevOps 的測試載入進 RSAT。

    ![載入到 RSAT 中的測試。](media/GER-RSAT-RSAT-Tests-Loaded.png "載入到 RSAT 中的測試的螢幕擷取畫面")

### <a name="create-automation-and-parameters-files"></a>建立自動化和參數檔案

1. 在 RSAT 中，選取您從 Azure DevOps 中載入的測試。
2. 選取 **新建** 建立 RSAT 自動化和參數檔案。

    ![在 RSAT 中建立的 RSAT 自動化和參數檔案。](media/GER-RSAT-RSAT-Tests-Initiated.png "在 RSAT 中建立的 RSAT 自動化和參數檔案的螢幕擷取畫面")

### <a name="modify-the-parameters-files"></a>修改參數檔案

1. 在 RSAT 中，選取 **準備資料以測試廠商電子付款的處理** 測試案例。
2. 選取 **編輯**。
3. 在打開的 Microsoft Excel 活頁簿，在 **一般** 工作表中，將公司代碼更改為 **GBSI**，因為這家公司將用於測試執行。
4. 在 RSAT 中，選取 **使用 ER 格式 BACS (UK) 測試廠商付款處理** 測試案例。
5. 選取 **編輯**。
6. 在打開的 Excel 活頁簿中，在 **一般** 工作表上，將公司代碼更改為 **GBSI**。
7. 在 **ERFormatMappingRunLogTable** 工作表上，請注意儲存格 A:3 和 C:3 包含 ER 偵錯記錄表中的欄位文字，這些欄位用於驗證輸出與基準的比較結果。 這些文字將用於評估在測試執行期間建立的 ER 偵錯記錄。

    ![ERFormatMappingRunLogTable 工作表。](media/GER-RSAT-RSAT-ExcelParameters.png "ERFormatMappingRunLogTable 工作表的螢幕擷取畫面")

## <a name="run-the-tests-and-analyze-the-results"></a>執行測試並分析結果

### <a name="run-the-tests-in-rsat"></a>在 RSAT 中執行測試

1. 在 RSAT 中，選取載入的測試。
2. 選取 **執行**。

請注意，測試案例透過使用網路瀏覽器在應用程式中自動執行。

### <a name="analyze-the-results-of-test-execution"></a>分析測試執行結果

測試執行的結果儲存在 RSAT 中。 請注意，兩個測試都通過了。

![在 RSAT 中通過的測試。](media/GER-RSAT-RSAT-Tests-Passed.png "在 RSAT 中通過的測試的螢幕擷取畫面")

請注意，測試執行的結果也會傳送到 Azure DevOps 以便您可以做進一步的分析。

![Azure DevOps 中的測試執行結果。](media/GER-RSAT-DevOps-Tests-Added.png "在 Azure DevOps 中測試執行結果的螢幕擷取畫面")

### <a name="simulate-a-situation-where-tests-fail"></a>模擬測試失敗的情況

當至少有一個產生的輸出與相應的基準不相符時，此測試套件必須失敗。 若要實現這種情況，您可以使用您的衍生版本 **BACS (UK)** 格式，將產生與相應基準具有不同內容的付款檔案。 若要模擬這種情況，您可以使用相同的 **BACS (UK)** 格式，但更改已處理付款明細上的付款金額。

1. 打開應用程式並進入 **應付帳款\>付款\>付款日記帳**。
2. 選取 **明細**。
3. 選取付款明細，然後選取 **付款狀態\>沒有**。
4. 在 **借方** 欄位中，請將值從 **1,000.00** 改為 **2,000.00**。
5. 選取 **儲存** 儲存您的更改。

### <a name="run-the-tests-in-rsat"></a>在 RSAT 中執行測試

1. 在 RSAT 中，選取載入的測試。
2. 選取 **執行**。

請注意，測試案例透過使用網路瀏覽器在應用程式中自動執行。

### <a name="analyze-the-results-of-test-execution"></a>分析測試執行結果

測試執行的結果儲存在 RSAT 中。 請注意，第二次測試在第二次執行期間失敗。

![RSAT 測試結果不合格。](media/GER-RSAT-RSAT-Tests-Failed.png "在 RSAT 中失敗的測試執行結果的螢幕擷取畫面")

請注意，測試執行的結果也會傳送到 Azure DevOps 以便您可以做進一步的分析。

![Azure DevOps 中的測試結果失敗。](media/GER-RSAT-DevOps-Tests-Failed.png "在 Azure DevOps 中失敗的測試執行結果的螢幕擷取畫面")

您可以存取每個測試的狀態。 您還可以存取執行記錄，以便分析任何失敗的原因。 在下圖中，執行記錄顯示失敗是由於產生的付款檔案與其基準之間的內容不同而發生的。

![用於分析在 Azure DevOps 中失敗的執行記錄。](media/GER-RSAT-DevOps-Tests-Failed-Log.png "在 Azure DevOps 中分析失敗的執行記錄的螢幕擷取畫面")

因此，正如您所見，任何 ER 格式的函數都可以透過使用 RSAT 作為測試平台並使用基於工作記錄器且使用 ER 基準函數的測試案例來自動評估。

## <a name="additional-resources"></a>其他資源

- [工作記錄器資源](../user-interface/task-recorder.md)
- [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [建立和自動化使用者驗收測試](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [部署和使用支援持續構建和測試自動化的環境](../perf-test/continuous-build-test-automation.md)
- [追蹤產生的報告結果並將它們與基準值做比較](er-trace-reports-compare-baseline.md)
- [ER 透過採用該格式的新基礎版本來升級您的格式](tasks/er-upgrade-format.md)
- [ER 匯入 Lifecycle Services 設定](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]