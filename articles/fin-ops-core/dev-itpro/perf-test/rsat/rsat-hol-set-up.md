---
title: 設定和安裝 Regression Suite Automation Tool 教學課程
description: 本主題是介紹如何設定和安裝 Regression Suite Automation Tool (RSAT) 的教學課程。
author: tonyafehr
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 5dcdd14f54b9c0ad39794ff98ede29332c246513
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460560"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>設定和安裝 Regression Suite Automation Tool 教學課程

本主題是教學課程，可幫助您設定並開始使用 RSAT 以及與使用 RSAT 相關的工具。

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> 使用您的網際網路瀏覽器工具下載此頁面並將其儲存為 PDF 格式。

## <a name="key-concepts"></a>關鍵概念

- 了解支援 Regression Suite Automation Tool (RSAT) 之各種應用程式所需的安裝和先決條件設定。
- 了解工作記錄器功能以及 Microsoft Dynamics Lifecycle Services (LCS) 和 Microsoft Azure DevOps，如何與讓您建立、設定、執行、調查和回報測試案例。
- 授權功能使用者使用工作記錄器記錄業務工作，然後將工作記錄轉換為一套自動化測試，而無需編寫原始程式碼。

## <a name="before-you-begin"></a>在您開始之前

### <a name="prerequisites"></a>先決條件

- 本教學課程需要執行 Microsoft Dynamics 365 for Finance and Operations 版本 10.0 (2019 年 4 月) 或更高版本的環境。 對於使用 Microsoft Dynamics 365 for Finance and Operations 企業版 7.3 的客戶，還支援平台更新 20 (PU20) 或更高版本。
- 使用者必須對環境具有管理員權限。
- 您必須有權存取客戶租戶 LCS 和 Azure DevOps (以前稱為 Microsoft Visual Studio Team Services \[VSTS\])。
- 建立和管理測試套件的使用者必須擁有 Azure DevOps 測試方案或測試管理員授權。 以下授權還將使您可以存取測試方案：
    - Visual Studio 企業授權
    - Visual Studio 測試專業授權
    - MSDN 平台訂閱者授權
- RSAT 必須能夠透過網站瀏覽器存取測試環境。
- 若要產生和編輯測試參數，您必須安裝好 Microsoft Excel。

## <a name="configure-azure-devops"></a>設定 Azure DevOps

### <a name="user-eligibility"></a>使用者資格

確保使用者是在 Azure DevOps 中建立的，並且具有提供對 Azure 測試方案的存取權限的訂閱級別。 僅當使用者將建立和管理測試案例時才需要 Azure DevOps 測試方案授權 (也就是說，並非所有 RSAT 使用者都需要此授權)。 如需授權要求的相關資訊，請參閱[授權要求](/azure/devops/test/manual-test-permissions#license-requirements)。

### <a name="create-a-new-azure-devops-project"></a>建立新 Azure DevOps 專案

RSAT 使用 Azure Devops 進行測試案例和測試套件管理、報表和調查測試執行結果。

> [!NOTE]
> 您可以使用現有的 Azure DevOps 專案。 但是，如果您的現有 Azure DevOps 專案設定為具有自訂範本，則當您將測試案例從商業流程建模工具 (BPM) 同步到 Azure DevOps 時，您將收到「VSTS 同步失敗」錯誤 (請參閱 [測試從 BPM 到 Azure DevOps 的同步作業](#test-the-synchronization-from-bpm-to-azure-devops)區塊)。 如果自訂範本遵循以下最佳做法，您將能夠將測試案例同步到 Azure DevOps。 (在錯誤訊息中列出了這些最佳做法。)

- 不要刪除任何工作項類型或現成欄位。
- 不要刪除工作項類型的任何狀態。
- 不要將任何必填欄位新增到工作項類型。

![帶有最佳做法清單的錯誤訊息。](./media/setup_rsa_tool_02.png)

否則，對於本教學課程，我們建議您建立一個新的 Azure DevOps 專案。 如需相關資訊，請參閱[使用自訂 Azure DevOps (VSTS) 流程範本同步到 BPM 時的問題](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/)。

1. 開啟 Azure DevOps 網址 (`https://dev.azure.com/<Azure DevOps Name>`)。
2. 選取 Azure DevOps 頁右上角的 **建立專案**。

    ![建立專案按鈕。](./media/setup_rsa_tool_03.png)

3. 填入以下欄位，然後選取 **建立**：

    - **專案名稱**
    - **版本控制** - 選取 **Team Foundation 版本控制**。 請注意，預設選項，**Git** 不支援。
    - **工作項目流程**

    ![建立新專案對話方塊。](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>建立個人存取權杖

在本教學課程中，您將使用 LCS 商業流程建模工具 (BPM) 建立測試案例庫並將您的測試案例與 Azure DevOps 同步。 您將需要個人存取權杖將 BPM 與 Azure DevOps 同步。

1. 選取 Azure DevOps 專案頁面右上角的設定檔圖示，然後選取 **安全性**。

    ![安全性命令。](./media/setup_rsa_tool_05.png)

2. 在左窗格中的 **安全性** 下，選取 **個人存取權杖**。 然後選取 **新權杖**。

    ![使用者設定中個人存取權杖索引標籤上的新權杖按鈕。](./media/setup_rsa_tool_06.png)

3. 填入以下欄位，然後選取 **建立**：

    - **姓名**
    - **到期 (UTC)** - 選取 **自訂定義**，然後使用日期選取器選取最後一個可用日期。
    - **範圍** – 選取 **完全存取** 選項。

    ![建立一個新的個人存取權杖對話方塊。](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > 記下建立的個人存取權杖。 稍後設定 RSAT 設定時將需要它。

    ![個人存取權杖。](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>設定 LCS 專案

您的主測試庫需要一個 Lifecycle Services (LCS) 專案。 LCS 商業流程建模工具 (BPM) 用作測試案例的主測試庫。 BPM 用於跨 LCS 專案管理和分發測試庫。 例如，構建測試庫的 Microsoft 合作夥伴或獨立軟體廠商 (ISV) 將以 BPM 庫的形式發佈測試案例。 在 BPM 中，測試案例是按業務流程組織的。 BPM 沒有定義測試通過的執行順序或頻率。 這些詳情在 Azure DevOps 中進行管理，如本主題後面所述。  

對於您的 LCS 專案，您可以使用現有的客戶實作或合作夥伴專案。

### <a name="update-the-lcs-language"></a>更新 LCS 語言

> [!NOTE]
> 針對要使使用者介面 (UI) 正確顯示業務流程，必須將 LCS 偏好語言設定為 **英文 (美國)**。

1. 進入 LCS 實作專案。
2. 選取右上角的 **設定** 按鈕 (齒輪符號)，然後選取 **語言偏好設定**。

    ![更新語言偏好設定。](./media/setup_rsa_tool_09.png)

3. 在 **偏好語言** 欄位，選取 **英文 (美國)**，然後選取 **儲存**。

    ![使用者設定中的語言偏好設定索引標籤。](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>設定 LCS 以連線到 Azure DevOps 專案

如果您之前建立了新的 Azure DevOps 專案，請設定 LCS 專案以連線到它。 否則，如果您的 LCS 專案已連線到您的 Azure DevOps 專案，您可以繼續下一章節。

1. 進入 LCS 實作專案。
2. 選取 **選單** 按鈕，然後選取 **專案設定**。

    ![專案設定命令。](./media/setup_rsa_tool_11.png)

3. 在左窗格中，選取 **Visual Studio Team Services**，然後選取 **設定 Visual Studio Team Services**。

    ![專案設定中的 Visual Studio Team Services 索引標籤。](./media/setup_rsa_tool_12.png)

4. 在 **Azure DevOps 網站網址** 欄位，輸入 Azure DevOps 網站的網址。 在 **個人存取權杖** 欄位，輸入之前建立的個人存取權杖。

    > [!NOTE]
    > 儘管 VSTS 現在稱為 Azure DevOps，但要將 LCS 連線到 Azure DevOps 專案，請使用舊網址。 例如，本教學課程中使用的 Azure DevOps 網址是 `https://dev.azure.com/D365FOFastTrack/`。 但是，在下圖中，它輸入為 `https://D365FOFastTrack.visualstudio.com/`。

    ![設定 Visual Studio Team Services 中的步驟 1。](./media/setup_rsa_tool_13.png)

5. 選取 **繼續**。
6. 在 **Visual Studio Team Services 專案** 欄位，選取所選網站上的 VSTS 專案以與 LCS 專案連結。 將 **流程範本** 欄位預設為 **敏捷**。 如需自訂範本，請參閱[建立新的 Azure DevOps 專案](#create-a-new-azure-devops-project)章節中的最佳做法指南。 然後選取 **繼續**。

    ![設定 Visual Studio Team Services 中的步驟 2。](./media/setup_rsa_tool_14.png)

7. 查看您的設定，然後選取 **儲存**。

    ![設定 Visual Studio Team Services 中的步驟 3。](./media/setup_rsa_tool_15.png)

8. 選取 **授權** 即可授權 LCS 代表您存取已設定的 Azure DevOps 網站並打開與 VSTS 整合的功能。

    ![授權按鈕。](./media/setup_rsa_tool_16.png)

9. 將出現一個訊息方塊，指出「您將被重新導向到一個永久網站，以授權 LCS 代表您連線到 Visual Studio Team Services。 是否要繼續？」 選取 **是**。

    ![訊息方塊。](./media/setup_rsa_tool_17.png)

10. 選取 **接受**。

    ![授權存取。](./media/setup_rsa_tool_18.png)

11. 如果您被授權為使用者，您應該回傳到 LCS 專案設定頁面的 UI。

    ![授權的使用者。](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>建立新的 BPM 庫

1. 進入 LCS 實作專案。
2. 選取 **選單** 按鈕，然後選取 **商業流程建模工具**。

    ![商業流程建模工具命令](./media/setup_rsa_tool_20.png)

3. 選取 **新建資源庫**。

    ![新建資源庫按鈕。](./media/setup_rsa_tool_21.png)

4. 在 **資源庫名稱** 欄位，輸入名稱，然後選取 **建立**。 對於本教學課程，將 BPM 庫命名為 **RSAT**。

    ![建立新資源庫對話方塊。](./media/setup_rsa_tool_22.png)

5. 開啟新的 **RSAT** BPM 庫。
6. 選取 **樣本核心業務流程** 流程，然後在右側選取 **編輯模式**。

    ![編輯模式按鈕。](./media/setup_rsa_tool_23.png)

7. 將 **名稱** 欄位和 **描述** 欄位的值更改為 **建立產品**。 然後選取 **儲存**。

    ![名稱和描述欄位。](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>環境

### <a name="version-requirement"></a>版本要求

需要執行版本 10 的測試或沙箱環境。 對於使用 7.3 版的客戶，還支援平台更新 20 或更高版本。

> [!NOTE]
> RSAT 必須能夠透過網站瀏覽器存取您的測試環境。

### <a name="user-criteria"></a>使用者標準

使用者必須對此環境具有管理員權限。

### <a name="set-up-help-settings-to-connect-with-lcs"></a>設定說明設定以連線 LCS

此為連線 LCS 的必要步驟，以便工作記錄可以透過用戶端儲存到 LCS 中相應的 BPM 庫。

1. 開啟用戶端。
2. 進入 **系統管理\>安裝\>系統參數**。
3. 在 **說明** 索引標籤上的 **Lifecycle Services 說明設定** 欄位中，選取相關的 LCS 專案 (本教學課程的 **RSAT**)。

    ![說明索引標籤上的 Lifecycle Services 說明設定欄位。](./media/setup_rsa_tool_25.png)

    BPM 庫填入在適當的 LCS 專案下。

4. 選取 **儲存**。
5. 您可能需要重新整理瀏覽器才能看到更新的說明內容。

    ![關於重新整理瀏覽器的通知。](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>工作記錄

> [!NOTE]
> 確保您的所有工作記錄都在主儀表板上啟動。 保持個人記錄簡短，並專注於一項業務工作，例如建立銷售訂單。

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>建立工作記錄並將其儲存到 BPM 庫

建立相應的工作記錄，您可以將其附加到在新 BPM 庫中建立的簡單業務流程。

1. 開啟用戶端。
2. 在主儀表板上，選取 **設定** 按鈕 (齒輪符號)，然後選取 **工作記錄器**。

    ![在設定選單上選取工作記錄器。](./media/setup_rsa_tool_27.png)

3. 建立 **建立記錄**。

    ![建立記錄按鈕。](./media/setup_rsa_tool_28.png)

4. 填入 **記錄名稱** 和 **錄音描述** 欄位，然後選取 **開始**。

    ![記錄名稱和記錄描述欄位。](./media/setup_rsa_tool_29.png)

5. 記錄建立產品的步驟。 完成後，選取 **停止** 停止記錄。

    ![建立產品的步驟。](./media/setup_rsa_tool_30.png)

6. 選取 **儲存到 Lifecycle Services**。

    ![將工作記錄儲存到 Lifecycle Services。](./media/setup_rsa_tool_31.png)

    資源庫資訊從 LCS 載入。

    ![正在載入資源庫資訊。](./media/setup_rsa_tool_32.png)

7. 選取要與工作記錄連結的 BPM 庫。 對於本教學課程，選取之前建立的 **RSAT** BPM 庫及其下的 **建立產品** 業務流程。 然後選取 **確定**。

    ![將工作記錄與 BPM 庫和業務流程連結。](./media/setup_rsa_tool_33.png)

    將顯示「儲存到 Lifecycle Services 已成功」訊息。

    ![有關成功儲存到 LCS 的訊息。](./media/setup_rsa_tool_34.png)

8. 如果您想在本地儲存工作記錄，然後透過 LCS 將其上傳到 BPM，請執行以下步驟：

    1. 記錄完成後，選取 **儲存到這台電腦**。

        ![儲存至這台電腦。](./media/setup_rsa_tool_35.png)

    2. 在瀏覽器的通知欄中，選取 **儲存** 或 **另存為** 以將檔案儲存在這台電腦上。

        ![通知欄。](./media/setup_rsa_tool_36.png)

    3. 進入 **RSAT** BPM 庫，然後選取要儲存工作記錄的業務流程。
    4. 在 **概述** 索引標籤，選取 **上傳**。

        ![上傳按鈕。](./media/setup_rsa_tool_37.png)

    5. 選取 **瀏覽**，然後選取您之前儲存的 .axtr 檔案。 然後選取 **上傳**。

        ![選取要上傳的 .axtr 檔案。](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>測試從 BPM 到 Azure DevOps 的同步處理

現在工作記錄已附加到業務流程，您必須驗證業務流程和相關的工作記錄是否可以透過使用 LCS 中的 VSTS 同步功能作為功能和測試案例 (分別) 同步到 Azure DevOps。

> [!NOTE]
> 在 Azure DevOps 中建立的相應工作項類型會有所不同，具體取決於您在使用 Azure DevOps 設定 LCS 專案時選取的流程範本，如[建立新的 Azure DevOps 專案](#create-a-new-azure-devops-project)章節中所述。

1. 進入 BPM 庫，然後開啟您之前建立的 **RSAT** 庫。
2. 選取省略符號按鈕 (**...**)，然後選取 **VSTS 同步**。

    ![省略符號選單上的 VSTS 同步命令。](./media/setup_rsa_tool_39.png)

    VSTS 同步完成後，左側會出現一個 **要求** 索引標籤，其中包含相應的 Azure DevOps 工作項目。

    > [!NOTE]
    > 在 Azure DevOps 中建立的工作項目將以 BPM 庫名稱作為標題前綴。

    ![要求索引標籤。](./media/setup_rsa_tool_40.png)

3. 重新整理頁面。
4. 選取省略符號按鈕 (**...**)。您會看到一個額外的選項，**同步測試案例**。 選取此選項。

    ![省略符號選單上的同步測試案例命令。](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > 如果重新整理頁面後 **同步測試案例** 選項無法使用，請進入 BPM 的主頁，然後為整個資源庫本身選取 **同步測試案例**。 透過這種方式，您可以有效地強制對整個資懸庫進行同步。
    >
    > ![為整個資源庫選取同步測試案例。](./media/setup_rsa_tool_42.png)

    同步測試案例完成後，會在 **要求** 索引標籤上建立一個新的測試案例。

    ![要求索引標籤上的新測試案例。](./media/setup_rsa_tool_43.png)

5. 進入您的 Azure DevOps 專案，然後選取 **Boards\>工作項目**。

    ![Boards 下的工作項目命令。](./media/setup_rsa_tool_44.png)

6. 驗證您透過 BPM 同步建立的工作項目和測試案例是否存在。

    ![工作項目和測試案例。](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>安裝和設定 RSAT

RSAT 可以安裝在任何執行 Windows 10 並且可以透過網站瀏覽器 (Internet Explorer 或 Google Chrome) 連線到該環境的電腦上。

> [!NOTE]
> 在安裝該工具的新版本之前，我們建議您解除安裝以前的版本。

### <a name="install-an-authentication-certificate"></a>安裝身分驗證憑證

若要啟用身分驗證，您必須在執行 RSAT 的同一台電腦上產生並安裝憑證。

#### <a name="generate-a-certificate"></a>產生憑證

1. 若要產生憑證檔案，請以管理員身分打開 Microsoft Windows PowerShell 視窗，然後執行以下命令。

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. 透過在 **執行** 對話方塊中輸入 **certlm.msc** 開啟憑證管理員，並確認在 **個人\>憑證** 下建立了 **D365 自動測試憑證** 證書。

    > [!NOTE]
    > 請務必輸入 **certlm.msc**，而不是 **certmgr.msc**，因為憑證儲存在這台電腦上。

    ![D365 自動化測試憑證證書。](./media/setup_rsa_tool_46.png)

3. 按右鍵點選憑證，然後選取 **複製**。
4. 進入 **信任的根憑證授權單位\>憑證**。

    ![信任的根憑證授權單位資料夾下的憑證資料夾。](./media/setup_rsa_tool_47.png)

5. 在 **動作** 選單上，選取 **貼上** 以將憑證複製到 **信任的根憑證授權單位** 位置。

    ![動作選單上的貼上命令。](./media/setup_rsa_tool_48.png)

6. 若要獲取已安裝憑證的指紋，但不包含空格或特殊字元，請以管理員身分打開 Windows PowerShell 視窗，然後執行以下命令。

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > 儲存指紋，因為稍後在更新應用程式對象伺服器 (AOS) 的 .wif 檔案並設定 RSAT 設定時將需要它。

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>將 AOS 電腦設定為信任連線

> [!NOTE]
> 如果環境是第 2 層以上環境，則必須在 wif.config 檔案中更新該環境的 **所有** AOS 電腦的憑證指紋。

1. 與 AOS 電腦建立遠端桌面通訊協定 (RDP) 連線。 登入詳情可在 LCS 的環境詳情頁面上找到。
2. 開啟 Microsoft Internet Information Services (IIS)，然後在網站清單中找到 **AOSService**。

    ![AOSService 在網站清單中。](./media/setup_rsa_tool_49.png)

3. 按右鍵點選 **瀏覽** 以打開 **\<Drive\>: \\AosService\\WebRoot** 資料夾。 尋找 **wif.config** 檔案。

    ![WebRoot 資料夾中的 Wifi.config 檔案。](./media/setup_rsa_tool_50.png)

4. 透過為您的憑證和授權名稱新增新的授權分錄來更新 **wif.config** 檔案，如以下範例所示。

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > 如果多個使用者使用同一個應用程式，每個使用者必須產生單獨的指紋，並且每個指紋都必須新增到 **\<keys\>** 區塊。

5. 如果有不止一台 AOS 電腦，請為每台附加電腦重複步驟 3 到 4。

    > [!NOTE]
    > 與舊的第 2 層環境不同，新的第 2 層環境部署有兩個 AOS 執行個體。

6. 在所有 AOS 電腦上執行 **iisreset**。

    > [!NOTE]
    > 如果您沒有在第 1 層電腦上執行 **iisreset** 的管理員權限，請在 LCS 的環境詳情頁面上，選取維護 > 重新啟動服務。

#### <a name="tier-2-environment"></a>第 2 層以上環境

如果使用第 2 層以上 (標準驗收測試沙箱或更高) 環境，請在安裝 RSAT 的電腦上驗證或設定以下註冊表設定。 此為必需步驟，因為它可以幫助您避免身分驗證或 RSAT 連線錯誤。

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>安裝 RSAT

1. 進入<https://www.microsoft.com/download/details.aspx?id=57357>，並選取 **下載**。
2. 選取所有檔案，然後選取 **下一個**。

    ![選取所有檔案。](./media/setup_rsa_tool_51.png)

3. 按兩下點選 .msi 套件以執行安裝程式。 然後，安裝完成後，選取 **結束**。

    ![RSAT 安裝程式檔案。](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>安裝 Selenium 和瀏覽器驅動程式

在舊版本的 RSAT 中，您必須安裝 Selenium 和瀏覽器驅動程式。 您不再需要安裝這些驅動程式，因為它們是自動安裝的。

1. 第一次開啟 RSAT 時，系統會提示您自動下載並安裝 Selenium。 如需相關資訊，請參閱[設定 RSAT](#configure-rsat)章節。
2. 在您可以執行測試案例之前，系統會提示您自動下載並安裝與在 RSAT 設定中選取的預設瀏覽器相對應的瀏覽器驅動程式。 如需相關資訊，請參閱[載入並執行測試案例](#load-and-run-test-cases)章節。

## <a name="get-started-with-rsat"></a>開始使用 RSAT

### <a name="create-a-test-plan-and-test-suites"></a>建立測試方案和測試套件

1. 進入 Azure DevOps 專案，然後選取 **測試方案**。

    ![測試方案命令。](./media/setup_rsa_tool_53.png)

2. 選取 **新的測試方案**。

    ![新建測試方案按鈕。](./media/setup_rsa_tool_54.png)

3. 填入 **名稱** 欄位，然後選取 **建立**。 對於本教學課程，命名測試方案 **RSAT 測試方案**。

    ![新建測試方案對話方塊。](./media/setup_rsa_tool_55.png)

4. 選取加號 (**+**)，然後選取 **靜態套件** 在新的測試方案下建立一個靜態套件。 將新的測試套件命名為 **T01 – 備貨**。

    > [!NOTE]
    > 如果您希望將 BPM 中的新測試案例自動拉入 RSAT 測試套件，您還可以建立基於查詢的套件。

    ![建立靜態套件。](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>將測試案例附加到測試套件

1. 選取 **新增現有的** 在右側將現有測試案例新增到測試套件。

    ![新增現有按鈕。](./media/setup_rsa_tool_57.png)

2. 在 **將測試案例新增到套件** 頁面上，選取 **執行查詢**，然後選取要新增到測試套件的測試案例。 對於本教學課程，選取 **建立一個新產品** 測試案例。 然後選取頁面右下角的 **新增測試案例** (下圖中未顯示此按鈕)。

    ![執行查詢按鈕。](./media/setup_rsa_tool_58.png)

    測試案例被新增到 **T01-備貨** 測試套件中。

    ![測試案例新增到測試套件。](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>設定 RSAT

1. 未結 RSAT。

    ![RSAT 圖示。](./media/setup_rsa_tool_60.png)

2. 您收到一條警告訊息，指出「Regression Suite Automation Tool 需要 Selenium，您要立即自動下載並安裝它嗎？」 選取 **是**。

    ![Regression Suite Automation Tool 需要 Selenium 的警告訊息。](./media/setup_rsa_tool_61.png)

3. 選取 **設定** 按鈕 (齒輪符號)，然後在出現的對話方塊中填入以下欄位：

    - **Azure DevOps 網址** – 輸入 Azure DevOps 專案的 URL，例如 `https://yourAzureDevOpsUrlHere.visualStudio.com`。
    - **存取權杖** - 輸入允許該工具連線到 Azure DevOps 的存取權杖。 使用您在本教學課程前面建立的個人存取權杖。 如需相關資訊，請參閱[使用個人存取權杖驗證存取權限](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate)。
    - **專案名稱** - 選取 Azure DevOps 專案的名稱。
    - **測試方案** – 選取包含您測試案例的 Azure DevOps 測試方案。 如需相關資訊，請參閱[建立測試方案和測試套件](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan)。 選取測試方案後，選取 **測試連線** 測試您與 Azure DevOps 的連線。
    - **主機名稱** – 輸入測試環境的主機名稱，如 **\<myaos\>.cloudax.dynamics.com**。 不包括 **https://** 或 **http://** 首碼。
    - **SOAP 主機名稱** – 輸入測試環境的 SOAP 主機名稱。 通常，SOAP 主機名稱與主機名稱相同，但它有一個 **soap** 尾碼。 舉例：**\<myaos\> soap.cloudax.dynamics.com**。 不包括 **https://** 或 **http://** 首碼。

        > [!NOTE]
        > 若要查詢主機名稱和 SOAP 主機名稱，請開啟 IIS 管理員，按右鍵點選 **網站\>AOSService**，然後選取 **編輯繫結**。 **主機名稱** 欄中的值為您提供主機名稱和 SOAP 主機名稱 (SOAP 主機名稱在 URL 中具有尾碼 **soap**)。

        ![主機名稱欄中的主機名稱和 SOAP 主機名稱。](./media/setup_rsa_tool_63.png)

    - **管理員使用者名稱** – 輸入測試環境中管理員使用者的電子郵件地址。
    - **指紋** – 輸入身分驗證憑證的指紋，如本教學課程前面所述。
    - **工作目錄** – 指定用於儲存測試自動化檔案的資料夾位置，例如 Excel 測試資料檔案。 例如，輸入或選取 **C:\\Temp\\RegressionTool**。

        > [!NOTE]
        > 如果資料夾名稱有空格，則執行失敗，因為找不到資料夾。 此問題是一個已知問題，應在該工具的最新版本中修復。

    - **預設瀏覽器** – 選取 **Internet Explorer** 或 **Google Chrome**。 確保已安裝適當的瀏覽器驅動程式。
    - **測試執行逾時** – 指定測試執行的逾時期限 (以分鐘為單位)。 當逾時期限過去時，所有有效視窗都將關閉，待處理的測試案例將失效。
    - **測試動作逾時** – 此欄位控制 Finance and Operation 環境伺服器請求的逾時期限 (以分鐘為單位)。 通常，預設值 (2 分鐘) 就足夠了。 但是，對於較慢的環境，如果發生與逾時相關的錯誤，您可能需要增加該值。
    - **公司名稱** – 輸入建立 Excel 參數檔案時用作預設公司的公司名稱。 您可以稍後透過編輯 Excel 參數檔案來更改公司。

    ![設定對話方塊。](./media/setup_rsa_tool_62.png)

4. 選取 **套用** 即可套用並儲存您的設定。

    若要將現行設定儲存到計算機上的設定檔案中，請選取 **另存為**。 若要從電腦上的設定檔案還原設定，請選取 **開啟**。

5. 選取 **關閉** 來關閉對話方塊。

### <a name="load-and-run-test-cases"></a>載入並執行測試案例

1. 選取 **載入** 以從 Azure DevOps 專案載入 **RSAT 測試方案** 測試方案。

    ![載入按鈕。](./media/setup_rsa_tool_64.png)

2. 從測試套件中選取 **建立新產品**，然後選取 **新建\>產生測試執行和參數檔案**。

    ![新建選單上的產生測試執行和參數檔案命令。](./media/setup_rsa_tool_65.png)

    Excel 參數檔案在您在 RSAT 設定中指定的本地資料夾中建立 (例如，**C:\\Temp\\RegressionTool**)。

    ![已建立 Excel 參數檔案。](./media/setup_rsa_tool_66.png)

3. 如果要儲存參數檔案，請選取 **上傳**。 所有選定測試案例的測試自動化檔案都將上傳到 Azure DevOps 以供將來使用。 (這些檔案包括 Excel 測試參數檔案。)

    這樣，您可以選取 **載入** 以直接從 Azure DevOps 載入測試案例中的參數檔案 (和自動化檔案)。 您不必重新產生參數檔案。 當您希望將修改保留在參數檔案中並且不希望它們被覆寫時，這種方法將變得很重要。

4. 若要驗證自動化檔案和參數檔案是否儲存到 Azure DevOps，請進入 Azure DevOps 專案，選取 **看板\>工作項目**，然後選取 **建立新產品** 測試案例。 在 **附件** 索引標籤，您應該看到四個檔案：

    - **.cs** – C\# 自動化檔案
    - **.dll** - 將自動化檔案編譯為組譯碼
    - **.xlsx** – Excel 參數檔案
    - **.xml** - 記錄檔案

    ![附件索引標籤上的檔案。](./media/setup_rsa_tool_67.png)

5. 選取要執行的測試案例，然後選取 **跑步**。

    > [!NOTE]
    > 在執行測試案例之前，如果您使用 Internet Explorer 作為瀏覽器，請確保在 **Windows 顯示設定\>縮放和配置** 中將桌面解析率設定為 **100%**。 如果您無法在虛擬機器 (VM) 上更改此設定，請在您嘗試從中存取 VM 的用戶端 (筆記型電腦) 上進行更改。 然後解析率設定將被 VM 顯示設定繼承。

    ![桌面解析率設定為 100%。](./media/setup_rsa_tool_68.png)

6. 如果系統中未安裝瀏覽器驅動程式，您會收到警告訊息，指出「此操作需要\<browser name\>驅動程式。 您要立即自動下載並安裝嗎？」 選取 **是**。

    ![Internet Explorer 的警告訊息。](./media/setup_rsa_tool_69.png)

    ![Chrome 的警告訊息。](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > 如果您使用 Chrome 作為瀏覽器並收到錯誤訊息，指出由於 Chrome 版本不正確而未建立工作階段，請從 <http://chromedriver.chromium.org/downloads> 將最新的 Chrome 驅動程式下載到 **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** 資料夾。

    ![Chrome 的錯誤訊息。](./media/setup_rsa_tool_71.png)

    執行測試案例，並且 **結果** 欄位已更新。

    ![更新了結果欄位。](./media/setup_rsa_tool_72.png)

    如果您按照本教學課程的編寫方式進行操作，則 **建立新產品** 測試案例將失敗，因為建立產品的工作記錄將產品名稱儲存為寫死值。 如果您重新執行相同的測試案例，您應該會收到一條錯誤訊息，因為該產品已經存在。

    ![結果欄位設定為失敗。](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>檢視測試結果

1. 按兩下點選失敗的測試案例。

    您會收到一則錯誤的訊息。

    ![錯誤訊息。](./media/setup_rsa_tool_73.png)

2. 選取 **詳情** 查看整個錯誤訊息。

    ![整個錯誤訊息。](./media/setup_rsa_tool_74.png)

3. 若要查看 Azure DevOps 中錯誤訊息的詳細版本，請選取 **在 Azure DevOps 中開啟**。 在 Azure DevOps，您可以查看測試案例的狀態和詳細的錯誤資訊。

    ![Azure DevOps 中的詳細錯誤資訊。](./media/setup_rsa_tool_75.png)

4. 若要直接查看 Azure DevOps 專案中的測試結果，請進入 **測試方案\>測試方案\>執行**。 按兩下點選要查看更多詳情的測試執行。

    ![Azure DevOps 中的測試執行清單。](./media/setup_rsa_tool_76.png)

5. **執行總結** 索引標籤表示測試案例失敗，但它不提供實際的錯誤訊息。 若要查看詳細的錯誤訊息，請選取 **測試結果** 索引標籤。

    ![執行摘要索引標籤。](./media/setup_rsa_tool_77.png)

    **測試結果** 索引標籤提供測試案例資訊以及結果和錯誤訊息。

    ![測試結果索引標籤。](./media/setup_rsa_tool_78.png)

6. 按兩下點選相關記錄即可查看詳細錯誤資訊。

    ![詳細的錯誤資訊。](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt** 中也提供了所有錯誤訊息。

7. 您還可以透過選取 **匯出** 從測試方案級別匯出測試執行結果。

    ![匯出測試方案。](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>修改 Excel 參數檔案

1. 未結 RSAT。
2. 選取測試案例，然後選取 **編輯** 打開 Excel 參數檔案。

    在 **EcoResProductCreate** 工作表，請注意 **產品編號** 欄位的值是寫死的。 在再次執行測試案例之前，您必須將此欄位更新為新的產品編號。

3. 若要為每次執行產生唯一的產品編號，而不必每次都重新打開 Excel 參數檔案並手動更新產品編號，請使用以下 Excel 公式。

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > 除了 **一般** 索引標籤，Excel 參數檔案包含測試案例存取的每個表單頁面的資料索引標籤。

    ![產品編號欄位。](./media/setup_rsa_tool_81.png)

4. 請選取 **儲存**，然後關閉 Excel 活頁簿。
5. 選取 **上傳** 將 Excel 參數檔案儲存到 Azure DevOps。

    ![成功上傳訊息。](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > 若要在特定使用者內容中執行測試案例，請在 Excel 參數檔案 **一般** 索引標籤上的 **測試使用者** 欄位中輸入使用者的電子郵件識別碼。 在最新版本的 RSAT 中，更新了 Excel 參數檔案中的欄位配置，但概念保持不變。
    >
    > ![測試使用者欄位。](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>驗證該結果

- 選取 **執行** 重新執行測試案例，並驗證測試案例是否通過。 您可以查看測試結果，如[查看測試結果](#view-the-test-results)章節所述。

    ![結果欄位設定為通過。](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>測試案例的鏈結

RSAT 的關鍵特性是測試案例的鏈結 (即測試將值傳遞給其他測試的能力)。 測試案例根據其在 Azure DevOps 測試方案中定義的順序執行。 (此順序也可以在測試工具本身中更新。) 因此，如果您想將變數從一個測試案例傳遞到另一個測試案例，測試的正確順序非常重要。

在本節中，您將在第一個測試案例中建立儲存的變數、建立第二個測試案例，並將儲存的變數從第一個測試案例傳遞給第二個測試案例。 然後，您將在 RSAT 中將測試案例作為鏈結的測試案例執行。

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>修改現有工作記錄以建立已儲存變數

1. 開啟用戶端。
2. 選取 **設定** 按鈕 (齒輪符號)，然後選取 **工作記錄器**。
3. 編輯 **編輯記錄**。

    ![編輯記錄按鈕。](./media/setup_rsa_tool_85.png)

4. 選取 **從 Lifecycle Services 開啟**。

    ![從 Lifecycle Services 開啟按鈕。](./media/setup_rsa_tool_86.png)

5. 選取 **選取 Lifecycle Services 內容庫**。

    ![選取 Lifecycle Services 內容庫按鈕。](./media/setup_rsa_tool_87.png)

    BPM 庫是從 LCS 載入的。

    ![載入 BPM 庫。](./media/setup_rsa_tool_88.png)

6. 從 LCS 載入 BPM 庫後，選取 **RSAT** BPM 庫和與工作記錄相關的 **建立新產品** 業務流程。 然後選取 **確定**。

    ![選取 BPM 庫和業務流程。](./media/setup_rsa_tool_89.png)

7. 在 **記錄名稱** 欄位中輸入相應工作記錄的名稱。 選取 **開始**。

    ![記錄名稱欄位中的工作記錄名稱。](./media/setup_rsa_tool_90.png)

8. 進入 **產品資訊管理\>產品**，並選取 **新建** 來打開原來記錄 **建立產品** 工作記錄的頁面。
9. 選取 **插入步驟**。

    > [!NOTE]
    > 新步驟將插入到您在窗格中選取的步驟 **後**。

    ![插入步驟按鈕。](./media/setup_rsa_tool_91.png)

10. 按右鍵點選 **產品編號** 欄位，然後選取 **工作記錄器\>複製**。

    ![複製命令。](./media/setup_rsa_tool_92.png)

11. 在窗格中新增了一個新步驟。 記下 **產品編號** 欄位中的值，因為稍後您將需要它。

    ![新增了新步驟。](./media/setup_rsa_tool_93.png)

12. 選取 **完成編輯**。
13. 選取 **儲存到 Lifecycle Services**，並將新工作記錄與與原始工作記錄相關的相同 BPM 庫和業務流程連結。 如需相關資訊，請參閱[建立工作記錄並將其儲存到 BPM 庫](#create-a-task-recording-and-save-it-to-the-bpm-library)章節。
14. 進入 BPM 庫，然後選取 **同步測試案例** 以覆寫 Azure DevOps 中附加到測試案例的工作記錄，如[測試從 BPM 到 Azure DevOps 的同步作業](#test-the-synchronization-from-bpm-to-azure-devops)章節中所述。
15. 開啟 RSAT，然後選取 **載入** 重新載入測試套件中的所有測試案例。 您必須透過選取測試案例然後選取 **新建\>產生測試執行和參數檔案** 為適當的測試案例重新產生自動化和參數檔案，如[載入和執行測試案例](#load-and-run-test-cases)章節所述。

    > [!NOTE]
    > 如果 Excel 參數檔案保持開啟狀態，則重新產生將失敗。 因此，請確保在產生新的 Excel 參數檔案之前關閉測試案例的 Excel 參數檔案。

16. 選取 **編輯** 打開新的 Excel 參數檔案。 您將在第 9 行看到新的 **已儲存的變數** 分錄。 此變數，**{{ EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**，儲存在工作記錄的 XML 檔案中，可用於後續測試。

    ![儲存的變數分錄。](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>建立新的測試案例

1. 進入 **RSAT** BPM 庫。
2. 選取 **樣本支援業務流程** 流程，然後在右側選取 **編輯模式**。
3. 將 **名稱** 欄位和 **描述** 欄位的值更改為 **發佈產品**。 然後選取 **儲存**。

    ![名稱和描述更改為發佈產品。](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>建立具有驗證功能的新工作記錄

- 建立工作記錄，將之前建立的產品發佈給 USRT 法律實體。 如需相關資訊，請參閱[建立工作記錄並將其儲存到 BPM 庫](#create-a-task-recording-and-save-it-to-the-bpm-library)章節。

    > [!NOTE]
    > 對於鏈結的測試案例，我們始終建議您透過 *手動鍵入欄位值* 來尋找或篩選您需要的記錄。 透過這種方式，該工具可以確定在後續測試案例中必須針對的記錄。

    ![具有驗證功能的新工作記錄。](./media/setup_rsa_tool_96.png)

    如上圖所示，在使用快速篩選器找到產品後，但在選取 **發佈產品** 之前，驗證 **產品編號** 欄位的值以確保產品 ID 是之前建立的產品 ID。 若要驗證該值，請按右鍵點選 **產品編號** 欄位，然後選取 **工作記錄器\>驗證\>目前的值**。

    ![驗證目前的值。](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>將工作記錄儲存到 BPM

1. 工作記錄完成後，選取 **儲存到 Lifecycle Services**。

    ![將完成的工作記錄儲存到 Lifecycle Services。](./media/setup_rsa_tool_98.png)

2. 資源庫資訊從 LCS 載入。

    ![從 LCS 載入資源庫資訊。](./media/setup_rsa_tool_99.png)

3. 選取要與工作記錄連結的 BPM 庫。 對於本教學課程，選取之前建立的 **RSAT** BPM 庫及其下的 **發佈產品** 業務流程。 然後選取 **確定**。

#### <a name="sync-bpm-to-azure-devops"></a>將 BPM 同步到 Azure DevOps

1. 進入 BPM 庫，然後開啟 **RSAT** 庫。
2. 選取 **VSTS 同步** 然後 **同步測試案例**。 如需相關資訊，請參閱[測試從 BPM 到 Azure DevOps 的同步作業](#test-the-synchronization-from-bpm-to-azure-devops)章節。

    同步完成後，**發佈產品** 業務流程的新工作項目和對應的測試案例會在 **看板\>工作項目** 的 Azure DevOps 中出現。

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>將新的測試案例新增到現有的測試套件中

1. 進入 **測試方案\>測試方案**，並選取 **RSAT 測試方案** 方案。
2. 選取 **新增現有**。
3. 在 **將測試案例新增到套件** 頁面上，選取 **執行查詢**。
4. 選取為 **發佈產品** 建立的新測試案例，然後選取頁面右下角的 **新增測試案例** (下圖中未顯示此按鈕)。

    ![將測試案例新增到套件頁面。](./media/setup_rsa_tool_100.png)

    測試套件現在有兩個測試案例。

    ![測試套件中的兩個測試案例。](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>將測試案例載入到 RSAT 中

1. 開啟 RSAT，然後選取 **載入**。
2. 測試案例已載入，您會收到一條警告，指出「此操作將覆寫 Excel 測試資料檔案，本機更改將遺失。 您確定要繼續嗎？」 選取 **是** 可更新本機系統中的 Excel 參數檔案，但不更新上傳到 Azure DevOps 的 Excel 參數檔案。

    ![此動作將覆寫 Excel 測試資料檔案。](./media/setup_rsa_tool_102.png)

    載入兩個測試案例，以及第一個測試案例的 Excel 參數檔案。 因為您在最後一次執行中選取了 **上傳**，參數檔案是從 Azure DevOps 中提取的。

    ![已載入測試案例。](./media/setup_rsa_tool_103.png)

3. 只選取第二個測試案例，然後選取 **新建\>產生測試執行和參數檔案**。

#### <a name="edit-the-excel-parameter-file"></a>編輯 Excel 參數檔案

1. 僅選取第二個測試案例，然後選取 **編輯** 打開相應的 Excel 參數檔案。
2. 將第一個測試案例中的 **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** 已儲存變數 (請參閱[修改現有工作記錄以建立已儲存變數](#modify-an-existing-task-recording-to-create-a-saved-variable)章節) 複製到使用產品編號的所有欄位中。 在這種情況下，您將變數複製到 **EcoResProductListPage** 工作表上的 **產品編號** 和 **驗證產品編號** 欄位中。

    ![產品編號和驗證產品編號欄位。](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > 變數只能在同一測試執行期間在測試之間傳遞。 變數的名稱必須完全相符。

3. 請選取 **儲存**，然後關閉 Excel 活頁簿。
4. 選取 **上傳** 儲存對 Excel 參數檔案所做的更改。

#### <a name="run-the-chained-test-cases"></a>執行鏈結的測試案例

1. 選取兩個測試案例，然後選取 **執行**。
2. 驗證兩個測試案例是否都已通過。

    ![兩個測試案例的結果欄位設定為通過。](./media/setup_rsa_tool_105.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]