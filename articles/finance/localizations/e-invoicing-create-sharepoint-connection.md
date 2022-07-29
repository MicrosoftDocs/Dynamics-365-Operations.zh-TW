---
title: 設定 SharePoint 連接
description: 本主題說明如何設定連接，以便電子開票可以存取 Microsoft SharePoint 網站。
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6b9fffc1f3525e69792517dd1c6ebdcfbe5a74d2
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451668"
---
# <a name="configure-a-sharepoint-connection"></a>設定 SharePoint 連接

[!include [banner](../includes/banner.md)]

電子開票服務可以讀取 Microsoft SharePoint 資料夾中的文件，並將文件上傳到 SharePoint。 為確保電子發票可以存取特定的 SharePoint 網站，您必須向電子開票服務提供網站認證。 此外，為確保安全儲存認證，請勿直接提供認證。 而是將其儲存在 Azure Key Vault 中，並提供 Azure Key Vault 密碼。

## <a name="grant-access-to-a-sharepoint-folder"></a>授予 SharePoint 資料夾的存取權

1. 在安裝了 Regulatory Configuration Service (RCS) 的租用戶中建立應用程式註冊。

    1. 登入 [Azure 入口網站](https://portal.azure.com/)。
    2. 前往 **應用程式註冊**。
    3. 選取 **新註冊**。
    4. 輸入名稱，例如 **電子發票的 SharePoint 應用程式**，然後完成註冊
    5. 選擇新的應用程式註冊。
    6. 在 **驗證** 索引標籤，啟用 **公開用戶端流程** 選項。
    4. 在 **憑證和密碼** 索引標籤，選擇 **新用戶端密碼** 以建立用戶端密碼。
    5. 複製建立的密碼的值。

    請遵循以下準則：

    - 不要為不同的服務使用相同的應用程式註冊。
    - 執行[密碼原則建議](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide)。
    - 設定密碼輪換。 在輪換期間，為應用程式註冊建立一個新的用戶端密碼，更新金鑰保存庫，然後刪除舊密碼。

2. 電子開票環境設定中，將 **應用程式註冊密碼** 和 **應用程式 (用戶端) 識別碼** 值作為兩個新密碼儲存在金鑰保存庫中。
3. 將您建立的密碼新增到在 RCS 中設定電子發票環境的 Key Vault 參數中。
4. 在 Azure 入口網站中，授予 SharePoint 的存取權。 此步驟應由租用戶管理員完成。

    1. 選取您建立的應用程式註冊。
    2. 在 **API 權限** 索引標籤，選取 **新增權限**。
    3. 選擇 **Microsoft Graph (應用程式權限)** \> **Sites.Selected**。
    4. 選擇 **授予 \<user&nbsp;name\> 的管理員同意**。
    5. 查看 **狀態** 欄位以確保已授予權限。

        ![在 API 權限索引標籤上授予的權限。](media/configured-permissions.jpg)

    6. 打開 [Graph 總管 - Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer)，然後登入。
    7. 在左側窗格的 **範例查詢** 索引標籤中，在 **SharePoint 網站** 下，選擇 **根據網站的相對路徑的取的 SharePoint 網站**。
    8. 填寫 **\{host-name\}** 和 **\{server-relative-path\}** 參數。 例如，例如，**\{host-name\}** 填寫 `<domain>.sharepoint.com`， **\{server-relative-path\}** 填寫 `sites/<siteName>`。

        > [!NOTE]
        > 對於預設網站，請將 **\{server-relative-path\}** 參數留空。

    9. 選擇 **執行查詢**，並儲存結果。
    10. 設定以下查詢。

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        在此查詢中，**\{site-id\}** 是上一個查詢回應中 **識別碼** 節點的值。

        以下是要求本文。

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        在此要求本文中，**\{app-id\}** 是 **應用程式 (用戶端) 識別碼** 值，**\{app-name\}** 是 **應用名稱** 值。

        ![POST 查詢。](media/app-id-query.jpg)

    11. 在 **修改權限** 索引標籤，選擇 **打開權限面板**，然後選擇 **網站** \> **Sites.FullControl.All** \> **同意**。
    12. 選取 **執行查詢**。

電子開票服務現在有權存取您的 SharePoint 網站了。
