---
title: 設定義大利 FatturaPA 與 SDI 的直接整合
description: 本主題提供的資訊將幫助您開始使用適用於義大利的電子發票，並設定義大利 FatturaPA 與 Exchange 系統 (SDI) 的直接整合。
author: abaryshnikov
ms.date: 01/15/2022
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: abaryshnikov
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 73cb08c880d7b3459201acfc7aeaa8d0dee1674f
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451431"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>設定義大利 FatturaPA 與 SDI 的直接整合

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> 適用於義大利的電子開票功能目前可能不支援 Microsoft Dynamics 365 Finance和 Dynamics 365 Supply Chain Management 中可用於電子發票的所有功能。

本主題提供的資訊，將幫助您在 Finance 和 Supply Chain Management 中開始使用適用於義大利的電子開票功能。 指引您完成 Regulatory Configuration Services (RCS) 中與國家/地區相關的設定步驟。 這些步驟補充了[開始使用電子開票](e-invoicing-get-started.md)中描述的步驟。

## <a name="prerequisites"></a>先決條件

在完成此主題中的步驟之前，必須滿足以下先決條件：

- 完成[開始使用電子開票](e-invoicing-get-started.md)中的步驟。
- 匯入 **義大利 FatturaPA (IT)** 電子開票功能從全球存放庫匯入 RCS。 有關詳細資訊，請參閱前面提及的「開始使用電子開票」主題的[從 Microsoft 設定提供者匯入電子開票功能](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider)區段。
- 將所需憑證的連結新增到服務環境。 所需憑證包括數位簽章憑證、憑證主管機構 (CA) 憑證和用戶端憑證。 有關詳細資訊，請參閱「開始使用電子開票服務管理」主題的[建立數位憑證祕密](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret)區段。

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>義大利 FatturaPA (IT) 電子開票功能的特定國家/地區特定設定

在將應用程式設定部署到連接的 Finance 或 Supply Chain Management 應用程式之前，請完成以下程序。

本節補充了「開始使用電子開票」主題中的[應用程式設定的國家/地區特定設定](e-invoicing-get-started.md#country-specific-configuration-of-application-setup)章節。

### <a name="create-a-new-feature"></a>建立新功能

1. 登入 RCS。
2. 在 **電子報表** 工作區的 **設定提供者** 區段，將您公司的設定提供者標記為使用中。
3. 在 **全球化功能** 工作區的 **功能** 部分中，選擇 **電子發票** 圖格。
4. 在 **電子開票功能** 頁面，選擇 **新增** \> **根據現有功能**。
5. 在 **Microsoft 設定提供者** 下方，選擇 **義大利 FatturaPA (IT)** 作為基本功能，輸入名稱，然後選擇 **建立功能**。

### <a name="set-up-application-specific-parameters"></a>設定應用程式特定參數

1. 在 **電子開票功能** 頁面，選擇要編輯的功能。
2. 在 **版本** 索引標籤，驗證是已選擇 **草稿** 版本。
3. 在 **設定** 索引標籤，選擇設定，然後選擇 **應用程式特定參數**。
4. 在 **查詢** 區段，請確保已選擇 **Natura 沖銷費用子類別清單** 查詢。
5. 在 **條件** 區段中，選擇 **新增**。
6. 為系統中定義的每個子類別新增特定條件，然後儲存變更。

    > [!NOTE]
    > 在 **名稱** 資料行，您可以選擇 **\*空白\*** 或 **\*非空白\*** 預留位置值而不是特定值。

### <a name="configure-a-processing-pipeline-for-export"></a>設定用於匯出的處理管道

1. 在 **電子開票功能** 頁面，選擇要編輯的功能。
2. 在 **設定** 索引標籤，選擇 **銷售發票**，然後選擇 **編輯**。
3. 在 **處理管道** 區段，瀏覽動作並設定所有必填欄位：

    - 如果是 **簽署文件** 動作，在 **憑證名稱** 欄位，指定數位簽章憑證。
    - 如果是 **提交** 動作，請設定 **URL 位址** 和 **憑證** 欄位。 **憑證** 欄位的值是憑證鏈，第一個是根 CA 憑證 (caentrate.cer)，第二個是用戶端憑證。

4. 選擇 **驗證** 以確保已設定所有必填欄位。
5. 儲存變更，然後關閉頁面。
6. 在 **設定** 索引標籤，選擇 **專案發票**，然後選擇 **編輯**。
7. 對專案發票重複執行步驟 3 到 5。

### <a name="configure-the-processing-pipeline-for-import"></a>設定用於匯入的處理管道

1. 在 **電子開票功能** 頁面，選擇要編輯的功能。
2. 在 **設定** 索引標籤，選擇 **匯入發票**，然後選擇 **編輯**。
3. 在 **資料通道** 區段的 **參數** 索引標籤，在 **資料通道** 欄位，輸入一個字符串值。
4. 在 **適用性規則** 索引標籤，設定此設定欄位。 透過將上一步中為 **資料通到** 欄位設定的值傳遞到 **值** 欄位，您可以使用預設的 **通道** 子句。

    ![設定適用性規則。](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. 選擇 **驗證** 以確保已設定所有必填欄位。

### <a name="deploy-the-feature"></a>部署功能

1. 完成和發佈功能，並將其部署到服務環境。 有關詳細資訊，請參閱「開始使用電子開票」主題的[將電子開票功能部屬到服務環境](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment)區段。
2. 將該功能部署到連接的應用程式。 有關詳細資訊，請參閱「開始使用電子開票」主題的[將電子開票功能部屬到連接的應用程式](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application)區段。

### <a name="set-up-finance"></a>設定 Finance

1. 登入 Finance 環境。
2. 在 **電子報表** 工作區的 **設定提供者** 區段，選擇 **Microsoft** 圖格。
3. 選取 **存放庫** \> **全域** \> **打開**。
4. 選擇並匯入 **客戶發票內容模型** 和 **廠商發票匯入 (IT)** 設定。
5. 前往 **組織管理** \> **設定** \> **電子文件參數**。
6. 在 **功能** 索引標籤，尋找並選擇 **義大利電子發票** 功能，然後選擇 **啟用** 核取方塊。
7. 在 **電子文件** 索引標籤，確保根據 [設定應用程式設定](e-invoicing-get-started.md#configure-the-application-setup)中的資訊設定 **客戶發票日記帳** 和 **專案發票** 欄位。

### <a name="set-up-vendor-invoice-import"></a>設定廠商發票匯入 

1. 在 Finance 中，在 **電子報表** 工作區的 **設定提供者** 區段，將您公司的設定提供者標記為使用中。
2. 選取 **報表設定**。
3. 選擇 **自訂發票內容模型**，然後選擇 **建立設定**。
4. 選擇 **從名稱衍生：客戶發票內容，Microsoft** 以建立衍生設定。
5. 在 **草稿** 版本中，選擇 **設計工具**。
6. 在 **資料模型** 樹狀結構中，選擇 **將模型對應到資料來源**。
7. 在 **定義** 樹狀結構中，選擇 **DataChannel**，然後選擇 **設計工具**。
8. 在 **資料來源** 樹狀結構中，展開 **\$Context\_Channel** 容器。
9. 在 **值** 欄位，選取 **編輯**。 
10. 輸入資料通道的名稱。 名稱最多只能有 10 個字元。 其應與 RCS 中電子開票功能的資料通道的 **資料通道** 參數值相符。
11. 儲存變更，然後前往 **報表設定** \> **完整的設定版本**。
12. 在 **外部通道** 索引標籤的 **通道** 區段，選擇 **新增**。
13. 在 **通道** 欄位，輸入 **\$內容通道** 值。
14. 在 **描述** 和 **公司** 欄位中輸入值。
15. 在 **文件內容** 欄位中，選擇從 **客戶發票內容模型** 衍生的新設定。 對應描述應為 **資料通道內容**。
16. 在 **匯入來源** 索引標籤上，選擇 **新增**，然後設定以下值：

    - **名稱：** OutputFile
    - **資料實體名稱：** 廠商發票標題 (**資料實體：** VendorInvoiceHeaderEntity)
    - **模型對應：** 廠商發票匯入 (IT)

> [!NOTE]
> 如果有從其他來源匯入廠商發票，則可以建立多個外部通道和多個具有不同 **\$內容通道** 值的衍生設定。 例如，您可能想要匯入不同法律實體的廠商發票。

## <a name="proxy-server-setup"></a>Proxy 伺服器設定

本節提供的資訊將幫助您設置和設定 Proxy 服務，以便在 Exchange 系統 (SDI) 和電子開票服務之間進行通訊。

### <a name="create-an-app-registration"></a>建立應用程式註冊

1. 使用以下 Windows PowerShell 指令碼，建立服務對服務 (S2S) 驗證的自我簽署憑證。

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. 將 .pfx 憑證檔案儲存到金鑰保存庫，然後刪除本機複本。
3. 以管理員身分登入 [Azure 入口網站](https://portal.azure.com)。
4. 為 SDI Proxy 服務建立應用程式註冊。

    1. 前往 **應用程式註冊**，建立註冊，然後為其設定以下值：

        - **名稱：** SDI Proxy 用戶端
        - **支援的帳戶類型：** 僅限此組織目錄中的帳戶 (單一租用戶)

    2. 選擇 **註冊**，然後選擇剛剛建立的應用程式註冊。
    3. 前往 **API 權限**，並選擇 **授予管理員同意**。
    4. 前往 **憑證和密碼**，選擇 **上傳憑證**，然後上傳用於進行 S2S 驗證的 .cer 憑證檔案。
    5. 前往 **企業應用程式**，然後選擇您建立的應用程式。
    6. 儲存應用程式的 **應用程式識別碼** (用戶端識別碼) 和 **物件識別碼** 值。
    7. 開票服務團隊必須授與應用程式存取服務的權限。 將以下參數的值發送到 <D365EInvoiceSupport@microsoft.com>：

        - AAD 租用戶識別碼
        - LCS 環境識別碼
        - 應用程式識別碼
        - 物件識別碼

5. 在 RCS 中，將應用程式新增到服務環境的應用程式清單中。

    1. 前往 **全球化功能** \> **環境** \> **電子開票** \> **服務環境**，然後選擇您的環境。
    2. 在 **應用程式** 區段，在格線中新增一列，然後輸入應用程式的名稱和物件識別碼。

        ![將應用程式新增到服務環境。](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. 選擇 **儲存**，然後選擇 **發佈**。

### <a name="create-an-azure-virtual-machine"></a>建立 Azure 虛擬機器

1. 在 [Azure 入口網站](https://portal.azure.com)中，前往 **虛擬機器**，然後選擇 **新建**。
2. 在 **基本** 索引標籤，選擇您的訂閱和資源群組。 這些值應為金鑰保存庫和 Blob 儲存體所在的訂閱和資源群組。
3. 選取區域。 此值應為部署您的 Finance 環境的區域。
4. 新增管理員的使用者名稱和密碼，並將它們儲存到金鑰保存庫。
5. 在 **選擇入站埠** 欄位，選擇 **HTTPS (443)** 和 **RPD (3389)**。

    > [!NOTE]
    > 建議您在系統投入生產時停用 **RDP (3389)** 連接埠。 如果必須連接到虛擬機器 (VM) 以進行疑難排解，則可以重新啟用它。

    ![設定 [基本] 索引標籤上的欄位以建立 Azure VM。](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. 在 **磁碟** 索引標籤的 **進階** FastTab，選擇 **使用受控磁碟** 核取方塊。 清除 **暫時性 OS 磁碟** 核取方塊。

    ![設定 [磁碟] 索引標籤上的欄位以建立 Azure VM。](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. 在 **網路** 索引標籤的 **公用 IP** 欄位下，選擇 **新建**。

    ![設定 [網路] 索引標籤上的欄位以建立 Azure VM。](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. 在 **建立公用 IP 位址** 對話方塊，在 **SKU** 欄位群組，選擇 **標準** 選項。 在 **指派** 欄位群組，選擇 **靜態** 選項。

    ![建立公用 IP 位址。](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. 在 **管理** 索引標籤，清除 **自動關閉** 核取方塊以停用自動關閉。
10. 將 **客體 OS 系統更新** 欄位設定為 **手動**，然後設定其他原則。
11. 查看並建立 VM。
12. 在新 VM 中，前往 **身分識別** \> **系統指派**，並將 **狀態** 選項設定為 **開啟**。
13. 授與 VM 存取金鑰保存庫的權限。

    1. 在金鑰保存庫中，前往 **存取控制 (IAM)** \> **角色指派**。
    2. 選擇 **新增角色指派**，然後設定以下欄位：

        1. 在 **角色** 欄位，指定 **Key Vault 密碼使用者**。
        2. 在 **將存取權指派到** 欄位，指定 **虛擬機器**。
        3. 在 **訂閱** 欄位，指定您的訂閱。
        4. 在 **選擇** 欄位，指定您的 VM。

    3. 前往 **存取原則**。
    4. 選擇 **新增存取原則**，然後設定以下欄位：

        1. 在 **選擇主體** 欄位，選擇您的 VM。
        2. 在 **憑證** 區段，選擇 **清單** 和 **取得** 權限。

14. 在 [Azure 入口網站](https://portal.azure.com)，前往 **公用 IP 位址**，然後選擇在 VM 中建立的 IP 位址。
15. 前往 **設定**，然後設定網域名稱系統 (DNS) 名稱。

### <a name="prepare-the-proxy-service-environment"></a>準備 Proxy 服務環境

在託管 Proxy 服務的電腦上執行以下步驟。

1. 使用遠端桌面連線來連接到 VM。
2. 打開本機電腦憑證管理單元。 有關詳細資訊，請參閱[如何：使用 MMC 管理單元查看憑證](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in)。
3. 將用於生產的 **caentrate.cer** 憑證和用於測試的 **CAEntratetest.cer** 憑證匯入[信任的根憑證授權單位商店](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). (**CAEntratetest.cer** 是由主管機構提供的根 CA 憑證。)
4. 在控制面板中，**打開或關閉 Windows 功能**，如果是伺服器作業系統 (OS)，則前往 **伺服器管理器** \> **新增角色和功能**，並打開 Internet Information Services (IIS) 功能：

    - 網頁管理工具
        - IIS 管理控制台
    - 世界範圍 Web 服務
        - 應用程式開發功能
            - .NET Extensibility 4.7 (或 4.8)
            - ASP
            - ASP.NET 4.7 (或 4.8)
            - CGI
            - ISAPI 擴充
            - ISAPI 篩選
        - 一般 HTTP 功能
            - 預設文件
            - 目錄瀏覽
            - HTTP 錯誤
            - 靜態內容
        - 健康情況和診斷
            - HTTP 記錄
            - 追蹤
        - 效能功能
            - 靜態內容壓縮
        - 安全性
            - 要求篩選

    ![打開 IIS 功能。](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>在 IIS 中設定 SDI Proxy 服務

1. 在 Microsoft Dynamics Lifecycle Services (LCS) 中，前往共用資產庫，然後資產類型選擇 **資料封裝**。
2. 找到 **電子開票服務 Sdi Proxy**，並將其下載到 VM。
3. 設定服務。

    1. 將您下載的 **電子開票服務 Sdi Proxy** 封存資料夾解壓縮。
    2. 在 **src\\FattureService** 資料夾，打開 **appsettings.json** 檔案，並設定以下參數：

        - **KeyVaultUri** - 指定儲存開票服務用戶端憑證的金鑰保存庫地址。
        - **租用戶識別碼** - 指定客戶租用戶的全域唯一識別碼 (GUID)。
        - **環境識別碼** - 指定 LCS 環境的識別碼。
        - **用戶端識別碼** - 指定客戶租用戶中的中間服務應用程式註冊的應用識別碼。
        - **ClientCertificateName** – 指定金鑰保存庫中 S2S 憑證的名稱。
        - **SecurityServiceClientOptions.Endpoint** - 指定安全性服務的 URL。
        - **SecurityServiceClientOptions.Resource** - 指定獲取權杖的範圍。
        - **InvoicingServiceClientOptions.Endpoint** - 指定發票服務的端點。 此值應與用於 RCS 和 Finance 的端點相同。
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** - 指定服務環境的名稱。 此值應該是您 Finance 環境的名稱。
        - **通知資料夾** - 指定儲存傳入通知檔案的資料夾。

    3. 在 **web.config** 檔案，找到以下行，並新增 Proxy 伺服器憑證的指紋。

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > 當系統進入生產狀態時，您可以變更 web.config 檔案中的某些值，以幫助減少收集的記錄資訊量並節省磁碟空間。 在 **\<system.diagnostics\>\<source\>** 節點，將 **switchValue** 值變更為 **嚴重，錯誤**。 有關詳細資訊，請參閱 [MS 追蹤檢視器](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe)。

4. 打開 IIS 管理器。 在左側的樹狀結構中，保留在根節點中。 在右側，選擇 **伺服器憑證**。

    ![在 IIS 管理器中選擇服務憑證。](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. 打開功能表，然後選擇 **匯入**。
6. 在 **進口憑證** 對話方塊的 **憑證文件 (.pfx)** 欄位，為 Proxy 伺服器憑證指定 .pfx 檔案的路徑。

    ![指定Proxy 服務憑證檔案。](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. 選擇並按住 (或以滑鼠右鍵按一下) **網站**，然後選擇 **新增網站**。
8. 在 **新增網站** 對話方塊的 **網站名稱** 欄位，輸入網站的名稱。
9. 在 **物理路徑** 欄位，指向 **src\\FattureService** 資料夾。
10. 在 **繫結類型** 欄位中，選取 **https**。
11. 在 **主機名稱** 欄位，指定主機名稱。
12. 將 **IP 位址** 和 **連接埠** 欄位設定為預設值。
13. 確保已清除 **需要伺服器名稱指示** 核取方塊，因為 SDI 不支援該技術。
14. 在 **SSL 憑證** 欄位中，選擇您匯入的 Proxy 伺服器憑證。
15. 在 **應用程式集區** 欄位，為網站指定一個集區，並記下其名稱 (例如，**SdiAppPool**)。

    ![新增網站。](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. 網站建立完成後，打開功能表 **SSL 設定**。

    ![打開 SSL 設定功能表。](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. 選擇 **必填 SSL** 核取方塊，然後在 **客戶憑證** 欄位群組，選擇 **必填** 選項。

    ![設定 SSL 設定。](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. 打開 **目錄瀏覽**，然後選擇 **啟用**。
19. 在任意網路瀏覽器中，前往 **serverDNS/TrasmissioneFatture.svc**。 必須顯示有關該服務的標準頁面。

    ![在瀏覽器中檢查服務。](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. 建立以下資料夾來儲存記錄和檔案：

    - **C:\\Logs\\** – 在此處儲存記錄檔。 可透過 [MS 服務追蹤檢視器](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe)查看這些檔案。
    - **C:\\Files\\** – 在此處儲存所有回應檔案。

21. 在檔案總管中，授與 **網路服務** 和 **IIS AppPool\\SdiAppPool** (如果您使用的是預設集區，則為 **IIS AppPool\\DefaultAppPool**) 存取 **記錄** 和 **檔案** 資料夾。

    1. 選取並按住 (或右鍵按一下) 其中一個資料夾，然後選取 **屬性**。
    2. 在 **屬性** 對話方塊的 **安全性** 索引標籤，選擇 **編輯**。
    3. 如果未列出使用者，請新增使用者。
    4. 對其他資料夾重複步驟 1 到 3。

    ![向服務使用者新增權限。](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>隱私權注意事項 

啟用 **義大利電子發票** 功能可能需要發送有限的資料。 此資料包括組織的稅務登記識別碼。 管理員可以啟用和停用義大利電子發票功能。 若要停用該功能，請按照以下步驟操作。

1. 前往 **組織管理** \> **設定** \> **電子文件參數**。
2. 在 **功能** 索引標籤，選擇包含 **義大利電子發票** 功能的列，然後選擇 **立即停用**。

從這些外部系統匯入此 Dynamics 365 線上服務的資料受[隱私權聲明](https://go.microsoft.com/fwlink/?LinkId=512132)約束。 有關詳細資訊，請參閱特定國家/地區的功能文件中的「隱私權聲明」區段。

## <a name="additional-resources"></a>其他資源

- [電子開票概觀](e-invoicing-service-overview.md)
- [開始使用電子開票服務管理](e-invoicing-get-started-service-administration.md)
- [開始使用電子開票](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
