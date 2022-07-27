---
title: 為 IoT 智慧設定 Azure 資源
description: 本主題介紹如何建立和設定 IoT 智慧所需的 Microsoft Azure 資源。
author: tonyafehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: tfehr
ms.custom: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d50458be9196206978a8d146ecd5b8c2a0a1fa8c
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449469"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>為 IoT 智慧設定 Azure 資源

[!include [banner](../../includes/banner.md)]

本主題介紹如何建立和設定 IoT 智慧所需的 Microsoft Azure 資源。

## <a name="create-azure-resources"></a>建立 Azure 資源

按照以下步驟建立 IoT 中樞、Redis 快取和 Microsoft Dynamics 365 Supply Chain Management 可以存取的金鑰保存庫。

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>確認 Microsoft Dynamics ERP 微服務第一方應用程式識別碼在您的租用戶中

請按照以下步驟確認 Microsoft Dynamics ERP 微服務第一方應用程式的應用程式識別碼位於您的租用戶中。

1. 登入 Azure 入口網站：<https://portal.azure.com>。
2. 移至 **Azure Active Directory**。
3. 前往 **企業應用程式**。
4. 在 **應用程式類型** 欄位選擇 **Microsoft 應用程式**。
5. 在搜尋欄位輸入 **Microsoft Dynamics ERP 微服務**。
6. 確認 **Microsoft Dynamics ERP 微服務** 在清單中。 其他應用程式具有類似名稱。 因此，請確保您找到正確的應用程式。 應用程式識別碼是 **0cdb527f-a8d1-4bf8-9436-b352c68682b2**。

    如果應用程式不在清單中，您必須將其新增到您的租用戶：

    1. 在 Azure 入口網站的工具列上，選擇按鈕以開啟 Azure Cloud Shell。
    2. 執行命令 **Install-Module AzureAD**。 輸入 **Y** 以安裝模組。
    3. 執行命令 **Get-InstalledModule -Name "AzureAD"** 以確認模組已經安裝。
    4. 執行命令 **Connect-AzureAD -Confirm** 以執行驗證。
    5. 執行命令 **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**。

    您現在可以重複步驟 1 到 6 以確認應用程式識別碼是否在您的租用戶中。

### <a name="create-a-key-vault-resource"></a>建立金鑰保存庫資源

若要建立金鑰保存庫資源，請按照以下步驟操作。

1. 在 Azure 入口網站建立或前往資源群組。
2. 選擇 **新增**。
3. 在 **新增** 頁面的搜尋欄位中輸入 **金鑰保存庫**。 然後選取 **建立**。
4. 在 **建立金鑰保存庫** 頁面的 **金鑰保存庫名稱** 欄位輸入名稱。
5. 查看預設值，然後選擇 **檢閱 + 建立**。
6. 選擇 **建立**。

金鑰保存庫是在背景建立的。

### <a name="create-an-iot-hub-resource"></a>建立 IoT 中樞資源

若要建立 IoT 中樞資源，請按照以下步驟操作。

1. 建立或前往資源群組。
2. 選擇 **新增**。
3. 在 **新增** 頁面的搜尋欄位中輸入 **IoT 中樞**。 然後選取 **建立**。
4. 在 **IoT 中樞名稱** 欄位中輸入名稱。
5. 查看預設值，然後選擇 **檢閱 + 建立**。
6. 選擇 **建立**。

IoT 中樞是在背景建立的。

> [!NOTE]
> 我們建議您為每個環境僅建立一個 IoT 中樞資源。

### <a name="create-a-redis-cache-resource"></a>建立 Redis 快取資源

若要建立 Redis 快取資源，請按照以下步驟操作。

1. 建立或前往資源群組。
2. 選擇 **新增**。
3. 在 **新增** 頁面的搜尋欄位中輸入 **適用於 Redis 的 Azure 快取**。 然後選取 **建立**。
4. 在 **DNS 名稱** 欄位中輸入名稱。
5. 查看預設值，然後選擇 **建立**。

Redis 快取是在背景建立的。

> [!NOTE]
> 我們建議您為每個環境僅建立一個 Redis 快取。

現在已建立所有資源。

## <a name="configure-the-azure-resources"></a>設定 Azure 資源

### <a name="configure-the-iot-hub"></a>設定 IoT 中樞

若要設定 IoT 中樞，請按照以下步驟操作。

1. 在您的資源中，選擇 IoT 中樞資源。
2. 在左側功能窗格中選擇 **內建端點**。
3. 在 **取用者群組** 貼上以下取用者群組。 這些取用者群組對應於開箱即用情境。

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>設定金鑰保存庫

若要設定金鑰保存庫，請按照以下步驟操作。

1. 在您的資源中，選擇金鑰保存庫資源。
2. 在左側功能窗格中選擇 **存取原則**。
3. 選擇 **新增存取原則**。
4. 在 **新增存取原則** 頁面的 **秘密權限** 欄位選擇 **取得** 和 **清單**。
5. 按一下 **選擇主體**。
6. 在 **主體** 對話方塊搜尋並選擇 **Microsoft Dynamics ERP 微服務**。 然後選擇 **選擇**。
7. 選擇 **新增**。
8. 選擇 **儲存**。

該應用程式現在可以存取金鑰保存庫中的秘密。

### <a name="save-the-iot-hub-connection-string-secret"></a>儲存 IoT 中樞連接字串秘密

若要儲存 IoT 中樞連接字串的秘密，請按照以下步驟操作。

1. 在您的資源中，選擇 IoT 中樞資源。
2. 在左側功能窗格中選擇 **內建端點**。
3. 複製 **事件中樞相容端點** 欄位之中的值。
4. 前往金鑰保存庫資源。
5. 在左側功能窗格中選擇 **秘密**。
6. 選擇 **產生/匯入**。
7. 在 **名稱** 欄位中，輸入名稱。
8. 在 **值** 欄位貼上您之前複製的端點值。
9. 選擇 **建立**。

### <a name="save-the-redis-cache-connection-string-secret"></a>儲存 Redis 快取連接字串秘密

若要儲存 Redis 快取連接字串的秘密，請按照以下步驟操作。

1. 在您的資源中，選擇 Redis 快取資源。
2. 選擇 **存取金鑰**。
3. 複製 **主連接字串** 欄位之中的值。
4. 前往金鑰保存庫資源。
5. 在左側功能窗格中選擇 **秘密**。
6. 選擇 **產生/匯入**。
7. 在 **名稱** 欄位中，輸入名稱。
8. 在 **值** 欄位貼上您之前複製的連接字串。
9. 選擇 **建立**。

> [!NOTE]
> 您更新其中一個連接字串時，您還必須更新秘密值。

您現在已完成佈建所需的 Azure 資源。 下一步是[在 Microsoft Dynamics Lifecycle Services (LCS) 之中安裝 IoT 智慧增益集](iot-lcs-setup.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
