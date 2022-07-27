---
title: 安裝並連線 Warehouse Management 行動應用程式
description: 本主題說明如何在您的每台行動裝置上安裝 Warehouse Management 行動應用程式，並將其設定為連接到您的 Microsoft Dynamics 365 Supply Chain Management 環境。
author: Mirzaab
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 812dd30e0e444bc310fc81edd16958e0c0747885
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449988"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>安裝並連線 Warehouse Management 行動應用程式

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 本主題描述如何設定新版 Warehouse Management 行動應用程式。 如果您正在尋找有關如何設定舊版倉庫應用程式 (現已棄用) 的資訊，請參閱[安裝並連線倉庫應用程式](../../supply-chain/warehousing/install-configure-warehousing-app.md)。

本主題說明如何在您的每台行動裝置上下載並安裝 Warehouse Management 行動應用程式，並將該應用程式設定為連接到您的 Supply Chain Management 環境。 您可以手動設定每台裝置，也可以透過檔案或掃描 QR 代碼匯入連線設定。

## <a name="system-requirements"></a>系統要求

Warehouse Management 行動應用程式適用於 Windows 和 Google Android 作業系統。 如要使用該應用程式，您的行動裝置上必須安裝以下作業系統之一：

- Windows 10 (通用 Windows 平台 \[UWP\]) 2018 年 10 月更新 1809 (組建 10.0.17763) 或更高版本
- Android 4.4 或更高版本

## <a name="turn-warehouse-management-mobile-app-features-or-or-off-in-supply-chain-management"></a>在 Supply Chain Management 中開啟或關閉 Warehouse Management 行動應用程式功能

若要使用 Warehouse Management 行動應用程式，您的系統中必須開啟 *新倉庫應用程序的使用者設定、圖示和步驟標題*。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區並搜尋 *新版倉庫應用程式的使用者設定、圖示和步驟標題* 功能，然後開啟或關閉此功能。

## <a name="get-the-warehouse-management-mobile-app"></a>取得 Warehouse Management 行動應用程式

針對較小型的部署，您通常可以在每台裝置上從相關商店安裝應用程式，然後手動設定與您正在使用的環境的連線。

對於較大型的部署，您可以自動化應用程式部署和/或設定，如果您需要管理許多裝置，這會更為方便。 例如，您可能會使用行動裝置管理和行動應用程式管理解決方案，例如 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)。 如需有關如何使用 Intune 新增應用程式的資訊，請參閱[將應用程式新增到 Microsoft Intune](/mem/intune/apps/apps-add)。

### <a name="install-the-app-from-an-app-store"></a>從應用程式商店安裝應用程式

在單一裝置安裝應用程式最簡單的方法，就是從應用程式商店進行安裝，因為商店會一律提供最新的一般可用版本。 Microsoft Intune 還可以從應用程式商店取得應用程式。 使用以下連結之一從應用程式商店安裝應用程式：

- **Windows (UWP)：** [Microsoft Store 上的 Warehouse Management](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android：**[Google Play 商店的 Warehouse Management](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>從 Microsoft 應用程式中心下載應用程式

作為從應用程式商店安裝的替代方法，您可以改為從 Microsoft 應用程式中心下載該應用程式。 應用程式中心提供了您可以側載的可安裝套件。 除了目前版本，應用程式中心也允許您下載以前的版本，並可能提供預覽版，以及您可以試用的即將推出功能。如要從 Microsoft 應用程式中心下載 Warehouse Management 行動應用程式的目前、上一個或預覽版，請使用以下連結之一：

- **Windows (UWP)：** [Warehouse Management (Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    有關如何在 Windows 裝置上安裝下載的封裝並設定所需憑證的說明，請參閱[從應用程式中心安裝組建](/appcenter/distribution/installation)。

- **Android：** [Warehouse Management (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    如果您下載的是預覽版，則需要一些額外的步驟來進行安裝。 如需詳細資訊，請參閱[測試 Android 應用程式](/appcenter/distribution/testers/testing-android)。

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>在 Azure Active Directory 中建立 Web 服務應用程式

如要使 Warehouse Management 行動應用程式能夠與特定 Supply Chain Management 伺服器進行互動，您必須在 Azure Active Directory (Azure AD) 中為 Supply Chain Management 租用戶登錄 Web 服務應用程式。 以下程序顯示完成此工作的一種方法。 如需詳細資訊和替代方法，請參閱該程序後的連結。

1. 在 Web 瀏覽器中，前往 [https://portal.azure.com](https://portal.azure.com/)。
1. 輸入有權存取 Azure 訂閱的使用者名稱和密碼。
1. 請在 Azure 入口網站左側的瀏覽窗格中選擇 **Azure Active Directory**。

    ![Azure Active Directory。](media/app-connect-azure-aad.png "Azure Active Directory")

1. 確認您正在使用由 Supply Chain Management 使用的 Azure AD 執行個體。
1. 請在 **管理** 清單中選擇 **應用程式註冊**。

    ![應用程式註冊。](media/app-connect-azure-register.png "應用程式註冊")

1. 在工具列上，選擇 **新註冊** 以打開 **註冊應用程式** 精靈。
1. 輸入應用程式的名稱，選擇 **僅限此組織目錄中的帳戶** 選項，然後選擇 **註冊**。

    ![註冊應用程式精靈。](media/app-connect-azure-register-wizard.png "註冊應用程式精靈")

1. 您的新應用程式註冊已打開。 記下 **應用程式 (用戶端) 識別碼** 值，因為您之後將需要它。 此識別碼將在本主題後面稱為 *用戶端識別碼*。

    ![應用程式 (用戶端) 識別碼。](media/app-connect-azure-app-id.png "應用程式 (用戶端) 識別碼")

1. 請在 **管理** 清單中選擇 **憑證和密碼**。 然後依於您要設定應用程式以進行驗證方式，選擇以下按鈕之一。 (如需詳細資訊，請參閱本主題後面的[使用憑證或用戶端密碼進行驗證](#authenticate)部分。)

    - **上傳憑證** - 上傳憑證以用作秘密。 我們推薦這種方法，因為它更安全，也可以更完全的自動化。 如果您在 Windows 裝置上執行 Warehouse Management 行動應用程式，請在上傳憑證後記下 **指紋** 顯示的值。 當您在 Windows 裝置上設定憑證時，您將需要此值。
    - **新用戶端密碼** - 透過在 **密碼** 部分輸入密鑰描述和持續時間來建立密鑰，然後選擇 **新增**。 製作密鑰副本，並將其安全儲存。

    ![憑證和密碼。](media/app-connect-azure-authentication.png "憑證和密碼")

有關如何在 Azure AD 中設定 Web 服務應用程式的更多資訊，請參閱以下資源：

- 有關說明如何在 Azure AD 中使用 Windows PowerShell 設定 Web 服務應用程式的說明，請參閱[如何：使用 Azure PowerShell 建立使用憑證的服務主體](/azure/active-directory/develop/howto-authenticate-service-principal-powershell)。
- 有關如何在 Azure AD 中手動建立 Web 服務應用程式的完整詳細資訊，請參閱以下主題：

    - [快速入門：使用 Microsoft 識別平台註冊應用程式](/azure/active-directory/develop/quickstart-register-app)
    - [如何：使用入口網站建立一個可以存取資源的 Azure AD 應用程式和服務主體](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a><a name="user-azure-ad"></a>在 Supply Chain Management 中建立和設定使用者帳戶

如要使 Supply Chain Management 能夠使用您的 Azure AD 應用程式，請按照以下步驟操作。

1. 建立與 Warehouse Management 行動應用程式使用者憑證對應的使用者：

    1. 在 Supply Chain Management 中，前往 **系統管理 \> 使用者 \> 使用者**。
    1. 建立一個使用者。
    1. 指派 *Warehousing 行動裝置使用者* 角色給使用者。

    ![指派倉庫行動裝置使用者。](media/app-connect-app-users.png "指派倉庫行動裝置使用者")

1. 將您的 Azure AD 應用程式關聯至 Warehouse Management 行動應用程式使用者：

    1. 前往 **系統管理 \> 設定 \> Azure Active Directory 應用程式**。
    1. 在動作窗格上選擇 **新增** 以建立明細。
    1. 在 **用戶端識別碼** 欄位內，輸入您在上一區段中記下的用戶端識別碼。
    1. 在 **名稱** 欄位中，輸入名稱。
    1. **使用者識別碼** 欄位中，選擇您剛剛建立的使用者識別碼。

    ![Azure Active Directory 應用程式。](media/app-connect-aad-apps.png "Azure Active Directory 應用程式")

> [!TIP]
> 使用這些設定的其中一種方法，是在 Azure 中為每個實體裝置建立一個用戶端識別碼，然後將每個用戶端識別碼新增到 **Azure Active Directory 應用程式** 頁面。 然後，如果裝置遺失，您可以透過從該頁面刪除其用戶端識別碼，以輕鬆移除其對 Supply Chain Management 的存取權。 (此方法之所以有效，是因為保存在每個裝置上的連線憑證也指定了用戶端識別碼，如本主題稍後所述。)
>
> 此外，每個用戶端識別碼的預設語言、數字格式和時區設定，是由此處對應的 **使用者識別碼** 值設定的偏好設定所建立。 因此，您可以使用這些偏好設定來根據用戶端識別碼為每個裝置或裝置的集合建立預設設定。 但是，如果這些預設設定也為背景工作角色用於登入裝置的 *倉庫應用程式使用者帳戶* 進行了定義，則這些預設設定將被覆寫。 (如需詳細資訊，請參閱[行動裝置使用者帳戶](mobile-device-work-users.md)。)

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>使用憑證或用戶端密碼進行驗證

透過 Azure AD 進行驗證，可提供將行動裝置連線到 Supply Chain Management 的安全方式。 您可以使用用戶端密碼或憑證進行驗證。 如果您要匯入連線設定，我們建議您使用憑證而非用戶端密碼。 由於用戶端密碼一律必須安全的進行儲存，因此您無法從連線設定檔案或 QR 代碼將其匯入，如本主題後面所述。

在請求權杖時，憑證可用作證明應用程式身分識別的密碼。 憑證的公開部分會上傳到 Azure 入口網站中的應用程式登記，而完整憑證必須部署在已安裝 Warehouse Management 行動應用程式的每台裝置上。 您的組織負責在輪換等方面管理憑證。 您可以使用自我簽署憑證，但應一律使用不可匯出的憑證。

您必須在執行 Warehouse Management 行動應用程式的每台裝置上提供本機憑證。 如需在使用 Intune 時如何管理 Intune 控制裝置的憑證相關資訊，請參閱[在 Microsoft Intune 中使用憑證進行驗證](/mem/intune/protect/certificates-configure)。

## <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>為雲端和邊緣縮放單位設定 Warehouse Management 行動裝置應用程式

如果您計劃針對雲端或邊緣縮放單位執行 Warehouse Management 行動裝置應用程式，則需要一些額外的步驟。 如需說明，請參閱[為雲端和邊緣縮放單位設定 Warehouse Management 行動裝置應用程式](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md)。

## <a name="configure-the-application-by-importing-connection-settings"></a>透過匯入連線設定來設定應用程式

為了更輕易的在許多行動裝置上維護和部署應用程式，您可以匯入連線設定，而非在每台裝置上手動輸入。 本節匯說明如何建立和匯入設定。

### <a name="create-a-connection-settings-file-or-qr-code"></a>建立連線設定檔案或 QR 代碼

您可以從檔案或 QR 代碼匯入連線設定。 對於這兩種方法，您必須先建立一個使用 JavaScript Object Notation (JSON) 格式和語法的設定檔案。 該檔案必須包含一個連線清單，其中包含必須新增的個別連線。 下表總結了必須在連線設定檔案中指定的參數。

| 參數 | 描述 |
|---|---|
| ConnectionName | 指定連線設定的名稱。 長度上限為 20 個字元。 由於此值是連線設定的唯一識別碼，因此請確保它在清單中是唯一的。 如果裝置上已存在同名連線，則匯入檔案中的設定將覆寫該連線。 |
| ActiveDirectoryClientAppId | 指定您[在 Azure Active Directory 中建立 Web 服務應用程式](#create-service)部分中設定 Azure AD 時記下的用戶端識別碼。 |
| ActiveDirectoryResource | 指定 Supply Chain Management 的根 URL。 |
| ActiveDirectoryTenant | 指定您與 Supply Chain Management 伺服器一起使用的 Azure AD 網域名稱。 此值的形式為 `https://login.windows.net/<your-Azure-AD-domain-name>`。 範例如下：`https://login.windows.net/contosooperations.onmicrosoft.com`。 有關如何尋找您 Azure AD 網域名稱的詳細資訊，請參閱[查找使用者的重要識別碼](/partner-center/find-ids-and-domain-names)。 |
| 公司 | 在您希望應用程式連線的 Supply Chain Management 中指定法律實體。 |
| ConnectionType | (選擇性) 指定連線設定是否應使用憑證或用戶端密碼來連線到環境。 有效值為 *「certificate」* 和 *「clientsecret」*。 預設值為 *「certificate」*。<p>**注意：** 無法匯入用戶端密碼。</p> |
| IsEditable | (選擇性) 指定應用程式使用者是否應該能夠編輯連線設定。 有效值為 *「true」* 與 *「false」*。 預設值為 *「true」*。 |
| IsDefault | (選擇性) 指定連線是否為預設連線。 打開應用程式時，將自動預先選擇設為預設連線的連線。 只能將一個連線設為預設連線。 有效值為 *「true」* 與 *「false」*。 預設值為 *「False」*。 |
| CertificateThumbprint | (選擇性) 若為 Windows 裝置，您可以為連線指定憑證指紋。 若為 Android 裝置，應用程式使用者必須在第一次使用連線時選擇憑證。 |

以下範例顯示了包含兩個連線的有效連線設定檔案。 如您所見，連線清單 (在檔案中命名為 *「ConnectionList」*) 是一個物件，具有一個將每個連線儲存為物件的陣列。 每個物件都必須括在大括號 ({}) 中並以逗號分隔，並且陣列必須括在方括號 (\[\]) 中。

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

您可以將資訊儲存為 JSON 檔案，也可以產生具有相同內容的 QR 代碼。 如果您將資訊儲存為檔案，我們建議您使用預設名稱 (*connections.json*) 儲存，特別是如果您要將其儲存在每個行動裝置上的預設位置時。

### <a name="save-the-connection-settings-file-on-each-device"></a>在每台裝置上儲存連線設定檔案

通常，您將會使用裝置管理工具或指令碼將連線設定檔案分發到您管理的每台裝置。 如果您在每台裝置上儲存連線設定檔案時使用預設名稱和位置，Warehouse Management 行動應用程式會自動將其匯入，即使在安裝應用程式後的第一次執行期間也是如此。 如果您為檔案使用自訂名稱或位置，則應用程式使用者必須在首次執行期間指定值。 但是，該應用程式之後將繼續使用指定的名稱和位置。

每次啟動應用程式時，它都會從之前的位置重新匯入連線設定，以確定是否有任何變更。 該應用程式將僅更新與連線設定檔案中的連線同名的連線。 使用其他名稱的使用者建立的連線不會被更新。

您無法使用連線設定檔案移除連線。

如前所述，預設檔名是 *connections.json*。 預設檔案位置取決於您使用的是 Windows 裝置還是 Android 裝置：

- **Windows：** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android：** `Android\data\com.Microsoft.WarehouseManagement\files`

通常，該路徑是在應用程式第一次執行後自動建立的。 但是，如果您必須在安裝前將連線設定檔案傳輸到裝置，則您可以手動建立。

> [!NOTE]
> 如果該應用程式被解除安裝，則預設路徑及其內容都將被移除。

### <a name="import-the-connection-settings"></a>匯入連線設定

按照這些步驟以從檔案或 QR 代碼匯入連線設定。

1. 在您的行動裝置上啟動 Warehouse Management 行動應用程式。 首次啟動應用程式時，您將看到歡迎訊息。 選擇 **選擇一個連線**。

    ![歡迎訊息。](media/app-configure-welcome-screen.png "歡迎訊息")

1. 如果您要從檔案匯入連線設定，並且已在儲存檔案時使用了預設的名稱和位置，則應用程式可能已經找到該檔案。 在這種情況下，請跳至步驟 4。 否則，請選擇 **設定連線**，然後繼續執行步驟 3。

    ![設定連線。](media/app-configure-set-up-connection.png "設定連線")

1. 在 **連線設定** 對話方塊中，視您想匯入設定的方式，選擇 **從檔案新增** 或者 **從 QR 代碼新增**：

    - 如果您要從檔案匯入連線設定，請選擇 **從檔案新增**，瀏覽到本地裝置上的檔案，然後選擇該檔案。 如果您選擇了自訂位置，應用程式將儲存該位置，並在下次自動使用。
    - 如果您想透過掃描 QR 代碼來匯入連線設定，請選擇 **從 QR 代碼新增**。 該應用程式會提示您取得使用裝置相機的權限。 授予權限後，相機將啟動以讓您進行掃描。 根據裝置相機的拍攝品質和 QR 代碼的複雜程度，您可能會覺得正確掃描並不容易。 在這種情況下，請試著透過每個 QR 代碼僅產生一個連線來降低 QR 代碼的複雜性。 (目前，您只能使用裝置的相機掃描 QR 代碼。)

    ![連線設定功能表。](media/app-configure-connection-setup-flyout.png "連線設定功能表")

1. 成功載入連線設定後，選擇的連線將會顯示。

    ![已載入連線設定。](media/app-configure-select-connection.png "已載入連線設定")

1. 如果您使用的是 Android 裝置，並且正在使用憑證進行驗證，裝置會提示您選擇憑證。

    ![在 Android 裝置上選擇憑證提示。](media/app-configure-select-certificate.png "在 Android 裝置上選擇憑證提示")

1. 該應用程式會連線到您的 Supply Chain Management 伺服器並顯示登入頁面。

    ![登入頁面。](media/app-configure-sign-in-page.png "登入頁面")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>手動設定應用程式

如果您沒有檔案或 QR 代碼，您可以在裝置上手動設定應用程式，使其透過 Azure AD 應用程式連線至 Supply Chain Management 伺服器。

1. 在您的行動裝置上啟動 Warehouse Management 行動應用程式。
1. 如果應用程式在 **示範模式** 中開啟，請選擇 **連線設定**。 如果應用程式啟動時出現 **登入** 頁面，請選擇 **變更連線**。
1. 選擇 **設定連線**。

    ![設定連線。](media/app-configure-set-up-connection.png "設定連線")

1. 選擇 **手動輸入**。

    ![連線設定功能表。](media/app-configure-connection-setup-flyout.png "連線設定功能表")

    **新連線** 頁面會出現，並顯示手動輸入連線詳細資訊所需的設定。

    ![手動連線欄位。](media/app-configure-input-manually.png "手動連線欄位")

1. 輸入下列資訊：

    - **使用用戶端密碼** - 將此選項設為 _是_，以使用用戶端密碼向 Supply Chain Management 進行驗證。 將其設為 _否_ 以使用憑證進行驗證。 (如需詳細資訊，請參閱本主題之前介紹的[在 Azure Active Directory 中建立 Web 服務應用程式](#create-service)一節。)
    - **連線名稱** - 輸入新連線的名稱。 此名稱將在您下次打開連線設定時，出現在 **選擇連線** 欄位。 您輸入的名稱必須是唯一的。 (換句話說，如果在您裝置上有儲存任何其他連接名稱，它必須與這些連線名稱不同。)
    - **Active Directory 用戶端識別碼** - 輸入您[在 Azure Active Directory中建立 Web 服務應用程式](#create-service)部分中設定 Azure AD 時記下的用戶端識別碼。
    - **Active Directory 用戶端密碼** - 此欄位僅在 **使用用戶端密碼** 選項設為 _是_ 的時候才能使用。 輸入您[在 Azure Active Directory部分中建立 Web 服務應用程式](#create-service)設定 Azure AD 時記下的用戶端密碼。
    - **Active Directory 憑證指紋** - 此欄位僅適用於 Windows 裝置，並且僅在 **使用用戶端密碼** 選項設為 _否_ 時才適用。 輸入您[在 Azure Active Directory部分中建立 Web 服務應用程式](#create-service)設定 Azure AD 時記下的憑證指紋。
    - **Active Directory 資源** - 指定 Supply Chain Management 的根 URL。

        > [!IMPORTANT]
        > 不要以斜線 (/) 結束此值。

    - **Active Directory 租用戶** - 輸入您與 Supply Chain Management 伺服器一起使用的 Azure AD 網域名稱。 此值的形式為 `https://login.windows.net/<your-Azure-AD-domain-name>`。 範例如下：`https://login.windows.net/contosooperations.onmicrosoft.com`。 有關如何尋找您 Azure AD 網域名稱的詳細資訊，請參閱[查找使用者的重要識別碼](/partner-center/find-ids-and-domain-names)。

        > [!IMPORTANT]
        > 不要以斜線 (/) 結束此值。

    - **公司** - 在您希望應用程式連線的 Supply Chain Management 中輸入法律實體 (公司)。

1. 選擇該頁面右上角的 **儲存** 按鈕。
1. 如果您使用的是 Android 裝置，並且正在使用憑證進行驗證，裝置會提示您選擇憑證。
1. 該應用程式會連線到您的 Supply Chain Management 伺服器並顯示登入頁面。

## <a name="remove-access-for-a-device"></a>移除裝置的存取權限

如果裝置遺失或遭損害，您必須移除對 Supply Chain Management 的存取權限。 以下步驟描述了移除存取權限的建議流程。

1. 前往 **系統管理 \> 設定 \> Azure Active Directory 應用程式**。
1. 刪除與您要移除存取權限的裝置對應的明細。 記下用於裝置的用戶端識別碼，因為稍後將會用到。

    如果您只註冊了一個用戶端識別碼，並且有多個裝置使用相同的用戶端識別碼，則您必須將新的連線設定推送到這些裝置。 否則，他們將失去存取權限。

1. 登入 Azure 入口網站：[https://portal.azure.com](https://portal.azure.com/)。
1. 在左側功能窗格中，選擇 **Active Directory**，並確認您位於正確的目錄中。
1. 在 **管理** 清單中，選擇 **應用程式註冊**，然後選擇要設定的應用程式。 **設定** 頁面會出現並顯示設定資訊。
1. 確認應用程式的用戶端識別碼與您在步驟 2 中記下的用戶端識別碼相符。
1. 在工具列上，選擇 **刪除**。
1. 在出現的確認訊息中，選擇 **是**。

## <a name="additional-resources"></a>其他資源

- [行動裝置使用者設定](mobile-device-user-settings.md)
- [指派 Warehouse Management 行動應用程式的步驟圖示和標題](step-icons-titles.md)
- [為雲端和邊緣縮放單位設定 Warehouse Management 行動裝置應用程式](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
