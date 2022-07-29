---
title: Finance Insights 的設定 - 版本 10.0.20 及更新版本
description: 本主題介紹如何設定您的系統以使用版本 10.0.20 及更新版本的 Finance Insights 中可用功能。
author: ShivamPandey-msft
ms.date: 06/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex,nofollow
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: cea6258d3a99ba33e73acd2508ec7b6c11d15859
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451506"
---
# <a name="configuration-for-finance-insights---version-10020-and-later"></a>Finance Insights 的設定 - 版本 10.0.20 及更新版本

[!include [banner](../includes/banner.md)]



Finance Insights 結合了 Microsoft Dynamics 365 Finance 的功能和 Dataverse、Azure 和 AI Builder，以便為您的組織提供強大的預測工具。 本主題介紹如何設定 Dynamics 365 Finance 版本 10.0.20，以便您的系統可以使用 Finance Insights 中的可用功能。

> [!NOTE]
> 本主題中描述的設定步驟僅適用於 Finance 版本 10.0.20 及更新版本。 若要在 10.0.19 及更早版本上設定 Finance Insights，請參閱 [Finance Insights 設定 - 最新版本 10.0.19](configure-for-fin-insites.md)。

## <a name="deploy-finance"></a>部署 Finance

按照以下步驟部署環境。

1. 在 Microsoft Dynamics Lifecycle Services (LCS) 中，建立或更新 Finance 環境。 該環境需要應用程式版本 10.0.20 或更新版本的財務和營運應用程式。
2. 環境必須是沙箱中的高可用性 (HA) 環境。 (這種類型的環境也稱為第 2 層環境。) 有關更多資訊，請參閱[環境規劃](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)。
3. 如果您在沙箱環境中設定 Finance Insights，您可能必須將生產資料複製到該環境，然後預測才會運作。 預測模型使用多年的資料來構建預測。 Contoso 示範資料不包含足夠的歷史資料來充分定型預測模型。 

## <a name="configure-dataverse"></a>設定 Dataverse

請按照以下步驟為 Finance Insights 設定 Dataverse。

1. 在 LCS 中，打開環境頁面，並驗證 **Power Platform 整合** 區段分已經設定好了。

    - 如果已經設定好了，應列出連結到 Finance 環境的 Dataverse 環境名稱。
    - 如果尚未設定，請按照下列步驟操作：

        1. 在 **Power Platform 整合** 區段，選擇 **設定**。 設定環境可能需要長達一個小時。
        2. 如果 Dataverse 環境已成功設定，應列出連結到 Finance 環境的 Dataverse 環境名稱。

        > [!NOTE]
        > 完成環境設定後，**不是** 選擇 **連結到應用程式的 CDS**。 Finance Insights 不需要此按鈕。 如果選擇它，您將無法在 LCS 中設定所需的環境增益集。

## <a name="configure-azure"></a>設定 Azure

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>使用 Azure Cloud Shell 設定 Finance Insights Data Lake 資源

# <a name="use-a-windows-powershell-script"></a>[使用 Windows PowerShell 指令碼](#tab/use-a-powershell-script)

提供了一個 Windows PowerShell 指令碼，以便您可以輕鬆設定[設定匯出到 Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) 中描述的 Azure 資源。 如果您希望手動進行設定，請跳過此程序，並改為完成[手動設定](#manual-setup)區段。

> [!NOTE]
> 使用以下程序上傳和執行 Windows PowerShell 指令碼。 如果在 Azure CLI 中使用 **試用** 選項或在電腦上執行指令碼，設定可能無法運作。

請按照以下步驟使用 Windows PowerShell 指令碼設定 Azure。 您必須有權建立 Azure 資源群組、Azure 資源和 Azure AD 應用程式。 有關所需權限的資訊，請參閱[查看 Azure AD 權限](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app)。

1. 在 [Azure 入口網站](https://portal.azure.com)中，前往您的目標 Azure 訂閱。
2. 在 **搜尋** 欄位右側選擇 **Cloud Shell**。
3. 選擇 **PowerShell**。
4. 如果系統提示您建立儲存體，則請建立。
5. 在 **Azure CLI** 索引標籤，選擇 **複製**。
6. 在記事本中，打開一個新文件，然後貼上 Windows PowerShell 指令碼。
7. 將檔案另存為 **ConfigureDataLake.ps1**。
8. 使用 Cloud Shell 中的上傳功能表選項將 Windows PowerShell 指令碼上傳到工作階段。
9. 執行 **.\ConfigureDataLake.ps1** 指令碼。
10. 按照提示執行指令碼。
11. 使用指令碼輸出中的資訊在 LCS 中安裝匯出到 Data Lake 指令碼。

### <a name="manual-setup"></a>手動設定

#### <a name="add-applications-to-the-azure-ad-tenant"></a>將應用程式新增到 Azure AD 租用戶

1. 在 [Azure 入口網站](https://portal.azure.com)中，前往 **Azure Active Directory**。
2. 選擇 **管理 \> 企業應用程式**。
3. 按應用程式識別碼搜尋以下應用程式。

    | 應用程式                              | 應用程式識別碼                               |
    |------------------------------------------|--------------------------------------|
    | Microsoft Dynamics ERP 微服務     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | Microsoft Dynamics ERP 微服務 CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | AI Builder 授權服務         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

如果您找不到上述任何應用程式，請嘗試以下步驟。

1. 在您的本機電腦上，在 **開始** 功能表，搜尋 **PowerShell**。
2. 選擇並按住 (或右鍵點擊) **Windows PowerShell**，然後選擇 **以管理員身份執行**。
3. 執行以下命令安裝 **AzureAD** 模組。

    `Install-Module -Name AzureAD`

4. 如果需要 NuGet 提供者才能繼續，請選擇 **是** 以進行安裝。
5. 如果您收到「不受信任的存放庫」訊息，請選擇 **是** 繼續。
6. 對於必須新增的每個應用程式，執行以下命令將應用程式新增到 Azure AD。 出現提示時，以 Azure AD 管理員身分登入。

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>建立 Azure 資源

> [!NOTE]
> 確保在 Dataverse 環境所在的同一 Azure AD 執行個體中建立以下資源。 你不能使用來自不同 Azure AD 執行個體的資源。

1. 建立儲存體帳戶：

    1. 在[ Azure 入口網站](https://portal.azure.com)建立儲存體帳戶。
    2. 在 **建立儲存體帳戶** 對話方塊中，設定以下欄位：

        - **位置** – 選擇您的環境所在的資料中心。
        - **效能** - 建議您選擇 **標準**。
        - **帳戶種類** – 您必須選擇 **StorageV2**。

    3. 在 **進階選項** 對話方塊中，對於 **Data Lake storage Gen2** 選項，選擇 **階層命名空間** 功能下的 **啟用**。 如果不啟用此功能，則無法使用財務和營運應用程式透過使用 Power BI 資料流等服務寫入的資料。
    4. 選擇 **查看和建立**。 部署完成後，新資源將顯示在 Azure 入口網站中。
    5. 前往您建立的儲存體帳戶。
    6. 在左側功能表中，選擇 **存取金鑰**。
    7. 複製並儲存儲存體帳戶的名稱。 稍後，當您設定金鑰保存庫密碼時，您必須提供此值。

2. 建立金鑰保存庫：

    1. 在 [ Azure 入口網站](https://portal.azure.com)建立金鑰保存庫。
    2. 在 **建立金鑰保存庫** 對話方塊的 **位置** 欄位，選擇您的環境所在的資料中心。
    3. 建立金鑰保存庫後，前往 **Key Vault 概觀**，然後複製並儲存 DNS 名稱。 稍後，當您設定 Data Lake 增益集時，您必須提供此值。

3. 建立並註冊 Azure AD 應用程式：

    1. 在 [Azure 入口網站](https://portal.azure.com)，前往 **Azure Active Directory**，然後選擇 **應用程式註冊**。
    2. 選擇 **新應用程式註冊**，並設定以下欄位：

        - **名稱** – 輸入應用程式的名稱。
        - **應用程式類型** - 選擇 **Web API**。
        - **重定導向 URI 設定** – 輸入您的 Dynamics 365 執行個體的 URL，例如 `https://yourdynamicsinstance.dynamics.com/auth`。

    3. 前往您剛剛建立的應用程式，然後複製並儲存其 **應用程式 (用戶端) 識別碼** 值。 稍後，當您設定金鑰保存庫密碼時，您必須提供此值。
    4. 前往 **API 權限**，然後按照以下步驟操作：

        1. 選擇 **新增權限**。
        2. 選取 **Azure Key Vault**。
        3. 選擇委派權限後，選擇 **user\_impersonation**。
        4. 選擇 **新增權限**。

    5. 在應用程式的功能表上，選擇 **憑證 \& 密碼**，然後按照以下步驟建立 Key Vault 密碼：

        1. 選擇 **新用戶端密碼**。
        2. 在 **金鑰描述** 欄位中，輸入名稱。
        3. 選擇持續時間，然後選擇 **新增**。 在 **值** 欄位中產生密碼。
        4. 複製並儲存用戶端密碼值。 稍後，當您設定金鑰保存庫密碼時，您必須提供此值。

4. 建立 Key Vault 密碼：

    1. 前往您之前建立的金鑰保存庫，然後選擇 **密碼**。
    2. 對於下表中的每個金鑰名稱，請執行以下步驟：

        1. 選取 **產生/匯入**。
        2. 在 **建立密碼** 對話方塊的 **上傳選項** 欄位，選擇 **手動**。
        3. 從資料表中建立金鑰名稱和值。
        4. 選擇 **啟用**，然後選擇 **建立**。 已建立密碼並將其新增到 Key Vault。

        | 密碼名稱                       | 密碼值                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | app-id                            | 您之前建立的應用程式的應用程式識別碼。                                      |
        | app-secret                        | 您之前儲存的用戶端密碼。                                                    |
        | storage-account-name              | 您之前建立的儲存體帳戶的名稱，例如 **storageaccount1**。       |

5. 授權應用程式存取金鑰保存庫：

    1. 在 [Azure 入口網站](https://portal.azure.com)，打開之前建立的金鑰保存庫。
    2. 選取存取原則。
    3. 對於下表中的每個應用程式，請執行以下步驟：

        1. 選擇 **新增存取原則** 以建立存取原則。
        2. 在 **密碼權限** 欄位中，從資料表中選擇權限。
        3. 在 **選擇主體** 欄位，從資料表中搜尋應用程式顯示名稱。
        4. 選擇 **選取**。
        5. 選取 **新增**。
        6. 選擇 **儲存**。

        | 應用程式                                              | 權限 |
        |----------------------------------------------------------|-------------|
        | 您建立的新應用程式的顯示名稱 | 取得、列出   |
        | **Microsoft Dynamics ERP 微服務**                 | 取得、列出   |

6. 指派角色以存取儲存體帳戶：

    1. 在 [Azure 入口網站](https://portal.azure.com)，打開之前建立的儲存體帳戶。
    2. 選擇 **存取控制 (IAM)**，然後選擇 **角色指派**。
    3. 選擇 **新增，新增角色指派**。
    4. 對於下表中的每個應用程式，請執行以下步驟：

        1. 從資料表中選擇角色。
        2. 離開 **指派存取權限** 欄位設定為 **Azure AD 使用者、群組或服務主體**。
        3. 在 **選取** 欄位中，輸入資料表中的應用程式。
        4. 選擇 **儲存**。

        | 應用程式                                              | 角色                        |
        |----------------------------------------------------------|-----------------------------|
        | 您建立的新應用程式的顯示名稱 | 負責人                       |
        | 您建立的新應用程式的顯示名稱 | 參與者                 |
        | 您建立的新應用程式的顯示名稱 | 儲存體帳戶參與者 |
        | 您建立的新應用程式的顯示名稱 | 儲存體 Blob 資料擁有者     |
        | **AI Builder 授權服務**                     | 儲存體 Blob 資料閱讀程式    |

# <a name="azure-cli"></a>[Azure CLI](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}
```
---

## <a name="configure-the-export-to-data-lake-add-in"></a>設定匯出到 Data Lake 增益集

按照以下步驟使用 LCS 將匯出到 Data Lake 增益集新增到環境中。

1. 登入 LCS，然後在頁面右側的環境名稱下，選擇 **詳細資料**。
2. 在 **環境增益集** 區段選擇 **安裝新的增益集**。
3. 選取 **匯出到 Data Lake** 增益集。
4. 輸入以下值。

    | 值                                                              | 描述 |
    |--------------------------------------------------------------------|-------------|
    | Key Vault 所在 Azure 訂閱的租用戶識別碼 | 儲存體帳戶、應用程式和金鑰保存庫所在的租用戶識別碼。 要取得此值，請打開 [Azure 入口網站](https://portal.azure.com)，前往 **Azure Active Directory**，並複製 **租用戶編號** 值。 |
    | 提供 Key Vault 的 DNS 名稱                             | 金鑰保存庫的 DNS 名稱，例如 `https://customkeyvault.vault.azure.net/`。 |
    | 提供包含儲存體帳戶名稱的密碼   | **storage-account-name** |
    | 用於存取 Data Lake 的 App ID 的密碼名稱          | **app-id** |
    | 應用程式用戶端密碼的密碼名稱                                  | **app-secret** |

5. 同意條款，然後選擇 **安裝**。

增益集將在幾分鐘內安裝。

## <a name="configure-the-finance-insights-add-in"></a>設定 Finance Insights 增益集

> [!NOTE]
> 如果您之前安裝了「取得 Insight 增益集」，請先將其卸載，然後再完成以下流程。

請按照以下步驟安裝 Finance Insights 增益集。

1. 登入 LCS，然後在頁面右側的環境名稱下，選擇 **詳細資料**。
2. 在 **環境增益集** 區段選擇 **安裝新的增益集**。
3. 設定 **Finance Insights** 增益集。
4. 同意條款，然後選擇 **安裝**。

增益集可能需要幾分鐘才能安裝。

## <a name="feedback-and-support"></a>意見反應及支援

如果您有興趣提供意見反應或需要支持，請發送電子郵件至 [Finance Insights](mailto:fiap@microsoft.com)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
