---
title: 設定 SharePoint 管道
description: 本主題說明如何設定 Microsoft SharePoint 管道以處理傳入的電子發票。
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ea3e14ed00b0661d3923c1839135378a8a550499
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451713"
---
# <a name="configure-a-sharepoint-channel"></a>設定 SharePoint 管道

[!include [banner](../includes/banner.md)]

作為設定 Microsoft SharePoint 通道以處理傳入文件的先決條件，請完成[設定 SharePoint 連線](e-invoicing-create-sharepoint-connection.md)中所述的步驟。

然後，您可以使用 SharePoint 通道從儲存在 SharePoint 資料夾中的文件中匯入電子廠商發票。

1. 在 SharePoint 網站上，建立以下資料夾：

    - **主資料夾** – 服務將從中處理文件的資料夾。
    - **存檔資料夾** – 將儲存已處理文件的資料夾。
    - **錯誤資料夾** – 如果處理失敗，系統會將文件移動到的資料夾。

2. 在 Regulatory Configuration Service (RCS) 中，選擇您建立的電子發票功能。 確保選擇狀態為 **草稿** 的版本。
3. 在 **設定** 索引標籤，選擇 **新增**。
4. 在 **建立功能設定** 下拉式對話方塊的 **新增** 欄位群組中，選擇 **自訂設定** 選項。
5. 在 **設定類型** 欄位群組，選擇 **資料管道** 選項。
6. 在 **選擇資料通道** 欄位，選擇 **SharePoint 資料夾**。
7. 選取 **建立**。
8. 選擇您建立的行，然後選擇 **編輯**。
9. 在 **資料管道** 索引標籤的 **參數** 區段中，設定以下必填欄位。

    | 欄位                 | 描述 |
    |-----------------------|-------------|
    | 資料管道          | 輸入唯一名稱以標識資料管道。 名稱最多可以有 10 個字元。 它將在適用性規則和通訊流程中連接的應用程式中參考。 |
    | SharePoint 位址    | 輸入 SharePoint URL。 例如，輸入 `<domain>.sharepoint.com`。 |
    | 應用程式識別碼        | 輸入包含 SharePoint 使用者帳戶識別碼的 Azure Key Vault 秘密的名稱。 此秘密必須在 Key Vault 中建立並在您的服務環境中設定。 此值是來自 [設定 SharePoint 連線](e-invoicing-create-sharepoint-connection.md)的 **應用程式 (用戶端) 識別碼** 值。 |
    | 應用程式秘密    | 輸入包含 SharePoint 使用者帳戶識別碼的 Azure Key Vault 秘密的名稱。 此值是來自 [設定 SharePoint 連線](e-invoicing-create-sharepoint-connection.md)的 **應用程式註冊秘密** 值。 |
    | 網站名稱             | 輸入 SharePoint 網站名稱。 |
    | 文件庫名稱 | 輸入 SharePoint 文件庫的名稱。 |
    | 逾時               | 輸入系統應等待回應的最大時間，以毫秒 (ms) 為單位。 預設值為 10,000 毫秒 (10 秒)。 |
    | 主資料夾           | 指定檔案匯入來源，或服務應處理的檔案源自的資料夾。 |
    | 封存資料夾        | 指定應儲存已處理檔案的資料夾。 |
    | 錯誤資料夾          | 指定處理失敗時系統應將檔案移動到的資料夾。 |
    | 檔案大小上限         | 輸入處理的單一檔案的最大大小 (以位元組為單位)。 預設值為 20,000,000 位元組。 |
    | 檔案數量上限      | 輸入處理的單一動作的檔案數量上限。 如果您不想限制檔案數量，請將值設定為 **0** (零)。 |
    | 檔案篩選器           | 輸入字串以按檔案名稱進行篩選。 此為選填欄位。 支援簡單的遮罩，如 **\*smth\*.ext**，其中的每個星號 (\*) 表示字元出現零次或多次。 例如，輸入 **\*.pdf** 來設定管道以讀取 PDF 檔案。 |
    | 自訂檔案名稱      | 輸入來自用戶端的自訂檔案名稱。 |

10. 在 **適用性規則** 索引標籤，根據需要查看和更新條件。 **管道** 欄位的值必須等於您在上一步中 **資料管道** 欄位中输入的值。
11. 選取 **儲存**，然後關閉此頁面。
