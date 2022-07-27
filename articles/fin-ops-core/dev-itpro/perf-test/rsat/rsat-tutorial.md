---
title: Regression Suite Automation Tool 教學課程
description: 本主題介紹如何使用 Regression Suite Automation Tool (RSAT)。 它描述了各種功能並提供了使用進階指令碼的範例。
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 2f31009424629221a8e4f130b0ec1879c6c6e3d4
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460559"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Regression Suite Automation Tool 教學課程

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> 使用您的網際網路瀏覽器工具下載此頁面並將其儲存為 pdf 格式。

本教學課程介紹了 Regression Suite Automation Tool (RSAT) 的一些進階功能，包括一個示範作業，並描述了策略和關鍵學習點。

## <a name="notable-features-of-rsat-and-task-recorder"></a>RSAT 和工作記錄器的顯著特點

### <a name="validate-a-field-value"></a>驗證欄位值

RSAT 允許您在測試案例中包含驗證步驟以驗證預期值。 如需此功能的相關資訊，請參閱文章[驗證預期值](rsat-validate-expected.md)。

以下範例顯示如何使用此功能來驗證現有庫存是否大於 0 (零)。

1. 在 **USMF** 公司的示範資料中，建立工作記錄，包含以下步驟：

    1. 請前往 **產品資訊管理\>產品\>已發佈的產品**。
    2. 使用快速篩選器尋找記錄。 例如，篩選 **項目編號** 欄位中的 **1000** 值。
    3. 選取 **現有庫存**。
    4. 使用快速篩選器尋找記錄。 例如，篩選 **站點** 欄位中的 **1** 值。
    5. 在清單中，標示選取的列。
    6. 驗證 **可用總量** 欄位的值為 **411.0000000000000000**。

2. 將工作記錄另存為 **開發人員記錄** 並將其附加到 Azure Devops 中的測試案例。
3. 將測試案例新增到測試方案中，並將測試案例載入到 RSAT 中。
4. 打開 Excel 參數檔案並轉到 **TestCaseSteps** 索引標籤。
5. 若要驗證現有庫存是否總是大於 **0**，請進入 **驗證可用總量** 庫存步驟並將其值從 **411** 更改為 **0**。 將 **運算子** 欄位的值從等號 (**=**) 更改為大於號 (**\>**)。
6. 儲存並關閉 Excel 參數檔案。
7. 選取 **上傳** 將您對 Excel 參數檔案所做的更改儲存到 Azure DevOps。

現在，如果庫存中指定項目的 **可用總量** 欄位的值大於 0 (零)，則無論實際的現有庫存值如何，測試都將通過。

### <a name="saved-variables-and-chaining-of-test-cases"></a>儲存的變數和測試案例的鏈結

RSAT 的關鍵特性之一是測試案例的鏈結，即測試將變數傳遞給其他測試的能力。 如需相關資訊，請參閱文章[將變數複製到鏈式測試案例](rsat-chain-test-cases.md)。

### <a name="derived-test-case"></a>衍生測試案例

RSAT 讓您可以對多個測試案例使用相同的工作記錄，從而使工作能夠以不同的資料設定執行階段。 請參閱文章[衍生測試案例](rsat-derived-test-cases.md)了解更多資訊。

### <a name="validate-notifications-and-messages"></a>驗證通知和訊息

此功能可用於驗證是否發生了動作。 例如，當建立、估計並啟動生產訂單時，應用程式會顯示「生產 - 啟動」訊息，通知您生產訂單已啟動。

![生產–啟動通知。](./media/use_rsa_tool_05.png)

您可以透過 RSAT 驗證此訊息，方法是在 Excel 參數檔案的 **MessageValidation** 索引標籤上輸入訊息文字以進行適當的記錄。

![訊息驗證索引標籤。](./media/use_rsa_tool_06.png)

執行階段測試案例後，將 Excel 參數檔案中的訊息與顯示的訊息進行比較。 如果訊息不相符，則測試案例將失敗。

> [!NOTE]
> 您可以在 Excel 參數檔案的 **MessageValidation** 索引標籤上輸入多條訊息。 這些訊息也可以是錯誤或警告訊息，而不是資訊性訊息。

### <a name="snapshot"></a>快照

此功能會截取工作記錄期間執行的步驟。 它對於審計或偵錯目的很有用。

- 若要在透過使用者介面執行階段 RSAT 時使用此功能，請打開 RSAT 安裝資料夾下的 **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** 檔案 (例如，**C:\\Program Files (x86)\\Regression Suite Automation Tool**)，並將以下元素的值從 **False** 更改到 **True**。

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- 若要在透過 CLI (例如，Azure DevOps) 執行階段 RSAT 時使用此功能，請打開 RSAT 安裝資料夾下的 **Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe.config** 檔案 (例如，**C:\\Program Files (x86)\\Regression Suite Automation Tool**)，並將以下元素的值從 **False** 更改到 **True**。

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

當您執行階段測試案例時，RSAT 會產生步驟的快照 (影像) 並將它們儲存在工作目錄中測試案例的播放資料夾中。 在播放資料夾中，會建立一個單獨的子資料夾，名為 **StepSnapshots**。 該資料夾包含執行階段的測試案例的快照。

## <a name="assignment"></a>指派

### <a name="scenario"></a>方案

1. 產品設計工具建立一個新發佈的產品。
2. 生產管理員啟動生產訂單以將庫存量提高到兩件。
3. 製造開始和結束生產訂單，並驗證現有數量為兩件。
4. 銷售團隊收到四件新產品的訂單。 因此，銷售團隊透過動態方案更新淨需求。 由於沒有額外的可用容量，預設訂單策略設定為「購買而不是製造」。 因此，建立了計劃訂購單。
5. 買方新增廠商，確定計劃訂購單，然後確認訂購單。
6. 當購買的貨物到達商店時，商店經營者會搜尋相關的訂購單並接收貨物。 由於訂單現已完成，因此可以根據銷售訂單揀貨和包裝貨物。
7. 財務會過帳採購發票和銷售發票。

下圖顯示了此場景的流程。

![示範場景的流程。](./media/use_rsa_tool_14.png)

下圖顯示了 LCS 商業流程建模工具中此場景的商業流程階層。

![示範場景的商業流程。](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>戰略——關鍵學習

### <a name="data"></a>資料

- 確保您有代表性的資料量 (生產/黃金設定資料的副本加上移轉的資料)。
- 當您透過工作記錄器產生新資料時，會建立不會與現有名稱衝突的測試名稱 (例如，使用前綴，例如 **RSATxxx**)。
- 使用 Azure 還原時間點在非第 1 層環境中重新執行階段測試。
- 儘管您可以使用 **RANDOM** 和 **NOW** Excel 函數來產生獨特的組合，但工作量相當大。 以下是一個範例。

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>工作記錄器

- 在開始記錄之前定義場景。 管理良好的專案具有預定義的測試場景。 若要構建測試案例，請考慮這些測試場景的結果的可預測性。
- 如果記錄由不同的角色執行，或者在下一步之前有等待時間或外部事件，則拆分記錄。
- 避免在清單中選取值。 而是使用文字格式，例如 **FIFO**、**AudioRM** 和 **SiteWH**。 在清單中選取時，會記錄值在清單中的位置，而不是值本身。 如果將項目新增到該清單中，則可以更改值的位置。 因此，您的記錄將使用不同的參數，並且場景的其餘部分可能會受到影響。
- 考慮多使用者行為。 例如，不要假設您新建立的銷售訂單將一直被自動選中。 相反，一律使用篩選器來查詢正確的順序。
- 使用工作記錄器中的複制函數來儲存新建立的產品的名稱，以便在鏈結的測試案例中使用它。
- 使用工作記錄器中的驗證函數來設定檢查點，以驗證步驟是否已正確執行階段。

### <a name="rsat"></a>RSAT

- 若要在另一家公司執行階段測試，您可以在 Excel 參數檔案的 **一般** 索引標籤上更改公司。 確保設定和資料在新選取的公司中可用。
- 您可以在 Excel 參數檔案的 **一般** 索引標籤上更改測試使用者。 指定將執行階段測試案例的使用者的電子郵件 ID。 這樣就可以使用指定使用者的安全權限執行階段測試案例了。
- 若要在測試開始之前等待，您可以在 Excel 參數檔案的 **一般** 索引標籤定義暫停。 此暫停可用於批次處理作業 (例如，如果必須在執行下一步之前執行階段工作流程。)

## <a name="advanced-scripting"></a>進階指令碼

### <a name="cli"></a>CLI

可以從 **命令提示** 或 **PowerShell** 視窗調用 RSAT。

> [!NOTE]
> 驗證 **TestRoot** 環境變數是否設定為 RSAT 安裝路徑。 (在 Microsoft Windows，開啟 **控制面板**，選取 **系統和安全\>系統\>進階系統設定**，然後選取 **環境變數**。)

1. 開啟 **命令提示** 或 **PowerShell** 視窗作為管理員。
2. 導覽到 RSAT 安裝目錄。

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. 列出所有命令。

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

顯示有關所有可用命令及其參數的說明。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>?：可選參數

`command`：``[command]`` 是下面指定的命令之一。

#### <a name="about"></a>關於

顯示目前的版本。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

清除螢幕。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>下載

將指定測試案例的附件下載到輸出目錄。
您可以使用 ``list`` 命令取得所有可用的測試案例。 使用第一欄中的任何值作為 **test_case_id** 參數。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="download-required-parameters"></a>下載：必要參數

+ `test_case_id`：表示測試案例 ID。
+ `output_dir`：表示輸出目錄。 該目錄必須存在。

##### <a name="download-examples"></a>下載：範例

`download 123 c:\temp\rsat`

`download 765 c:\rsat\last`

#### <a name="edit"></a>編輯

允許您在 Excel 程式中打開參數檔案並進行編輯。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>編輯必要參數

+ `excel_file`：必須包含現有 Excel 檔案的完整路徑。

##### <a name="edit-examples"></a>編輯：範例

`edit c:\RSAT\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>產生

在輸出目錄中為指定的測試案例產生測試執行和參數檔案。 您可以使用 ``list`` 命令取得所有可用的測試案例。 使用第一欄中的任何值作為 **test_case_id** 參數。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="generate-required-parameters"></a>產生：必要參數

+ `test_case_id`：表示測試案例 ID。
+ `output_dir`：表示輸出目錄。 該目錄必須存在。

##### <a name="generate-examples"></a>產生：範例

`generate 123 c:\temp\rsat`

`generate 765 c:\rsat\last`

#### <a name="generatederived"></a>generatederived

產生一個從提供的測試案例衍生的新測試案例。 您可以使用 ``list`` 命令取得所有可用的測試案例。 使用第一欄中的任何值作為 **test_case_id** 參數。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-required-parameters"></a>generatederived：必要參數

+ `parent_test_case_id`：表示父系測試案例 ID。
+ `test_plan_id`：表示測試方案 ID。
+ `test_suite_id`：表示測試套件 ID。

##### <a name="generatederived-examples"></a>generatederived：範例

`generatederived 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

僅在輸出目錄中為指定的測試案例產生測試執行檔案。 您可以使用 ``list`` 命令取得所有可用的測試案例。 使用第一欄中的任何值作為 **test_case_id** 參數。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="generatetestonly-required-parameters"></a>generatetestonly：必要參數

+ `test_case_id`：表示測試案例 ID。
+ `output_dir`：表示輸出目錄。 該目錄必須存在。

##### <a name="generatetestonly-examples"></a>generatetestonly：範例

`generatetestonly 123 c:\temp\rsat`

`generatetestonly 765 c:\rsat\last`

#### <a name="generatetestsuite"></a>generatetestsuite

為輸出目錄中的指定套件產生所有測試案例。 您可以使用 ``listtestsuitenames`` 命令取得所有可用的測試套件。 使用該資料欄中的任何值作為 **test_suite_name** 參數。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite：必要參數

+ `test_suite_name`：表示測試套件名稱。
+ `output_dir`：表示輸出目錄。 該目錄必須存在。

##### <a name="generatetestsuite-examples"></a>generatetestsuite：範例

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite Purchase c:\rsat\last`

#### <a name="help"></a>說明

與 [?](#section) 相同 命令。

#### <a name="list"></a> 個清單

列出所有可用的測試案例。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

列出所有可用的測試方案。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

列出指定測試套件的測試案例。 您可以使用 ``listtestsuitenames`` 命令取得所有可用的測試套件。 使用第一欄中的任何值作為 **suite_name** 參數。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite：必要參數

+ `suite_name`：所需套件的名稱。

##### <a name="listtestsuite-examples"></a>listtestsuite：範例

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitenames"></a>listtestsuitenames

列出所有可用的測試套件。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>播放

使用 Excel 檔案播放測試案例。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="playback-required-parameters"></a>播放：必要參數

+ `excel_file`：Excel 檔案的完整路徑。 檔案必須存在。

##### <a name="playback-examples"></a>播放：範例

`playback c:\RSAT\TestCaseParameters\sample1.xlsx`

`playback e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

一次播放多個測試案例。 您可以使用 ``list`` 命令取得所有可用的測試案例。 使用第一欄中的任何值作為 **test_case_id** 參數。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-required-parameters"></a>playbackbyid：必要參數

+ `test_case_id1`：現有測試案例的 ID。
+ `test_case_id2`：現有測試案例的 ID。
+ `test_case_idN`：現有測試案例的 ID。

##### <a name="playbackbyid-examples"></a>playbackbyid：範例

`playbackbyid 878`

`playbackbyid 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

使用 Excel 檔案一次播放多個測試案例。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="playbackmany-required-parameters"></a>playbackmany：必要參數

+ `excel_file1`：Excel 檔案的完整路徑。 檔案必須存在。
+ `excel_file2`：Excel 檔案的完整路徑。 檔案必須存在。
+ `excel_fileN`：Excel 檔案的完整路徑。 檔案必須存在。

##### <a name="playbackmany-examples"></a>playbackmany：範例

`playbackmany c:\RSAT\TestCaseParameters\param1.xlsx`

`playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

播放指定測試套件中的所有測試案例。
您可以使用 ``listtestsuitenames`` 命令取得所有可用的測試套件。 使用第一欄中的任何值作為 **suite_name** 參數。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="playbacksuite-required-parameters"></a>playbacksuite：必要參數

+ `suite_name`：所需套件的名稱。

##### <a name="playbacksuite-examples"></a>playbacksuite：範例

`playbacksuite suiteName`

`playbacksuite sample_suite`

#### <a name="quit"></a>放棄

關閉申請表。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

#### <a name="upload"></a>上傳

上傳屬於指定測試套件或測試案例的所有檔案。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="upload-required-parameters"></a>上傳：必要參數

+ `suite_name`：屬於指定測試套件的所有檔案將會上傳。
+ `testcase_id`：屬於指定測試案例的所有檔案將會上傳。

##### <a name="upload-examples"></a>上傳：範例

`upload sample_suite`

`upload 123`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

僅上傳屬於指定測試案例的記錄檔案。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording：必要參數

+ `testcase_id`：屬於指定測試案例的記錄檔案將會上傳。

##### <a name="uploadrecording-examples"></a>uploadrecording：範例

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>使用方式

顯示調用此應用程式的兩種方法：一種使用預設設定檔案，另一種提供設定檔案。

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

### <a name="windows-powershell-examples"></a>Windows PowerShell 範例

#### <a name="run-a-test-case-in-a-loop"></a>循環執行階段測試案例

您有一個建立新客戶的測試指令碼。 透過指令碼，可以透過在每次迭代執行階段之前隨機化以下資料來循環執行階段此測試案例：

- 客戶識別碼
- 客戶名稱
- 客戶地址

客戶識別碼的格式為 *ATCUS\<number\>*，其中 \<number\> 是介於 **000000001** 和 **999999999** 之間的值。

以下範例使用一個參數，**start**，定義使用的第一個數字。 是使用第二個參數，**nr**，定義必須建立的客戶數量。 對於每次迭代，Excel 參數檔案中的參數都會使用 UpdateCustomer 函數進行更改。 然後在 RunTestCase 函數中調用 RSAT 命令列。

在管理員模式下打開 Microsoft Windows PowerShell 整合指令碼環境 (ISE)，並將以下代碼粘貼到名為 **Untitled1.ps1** 的視窗中。

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>執行階段依賴於 Microsoft Dynamics 365 中資料的指令碼

以下範例使用開放式資料通訊協定 (OData) 調用來尋找訂購單的訂單狀態。 如果狀態不是 **已開票**，例如，您可以調用發佈發票的 RSAT 測試案例。

```powershell
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
