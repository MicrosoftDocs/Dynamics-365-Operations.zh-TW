---
title: 設定電子郵件管道
description: 本主題介紹如何設定電子郵件管道以接收電子發票。
author: dkalyuzh
ms.date: 02/09/2022
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
ms.openlocfilehash: 6a5896a033212cf0f29f686eec0ab6fb3bc1d2a6
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451686"
---
# <a name="configure-an-email-channel"></a>設定電子郵件管道

[!include [banner](../includes/banner.md)]

如果您建立的電子發票功能從透過電子郵件接收的附件文件中匯入電子廠商發票，您應該設定一個電子郵件帳戶管道。

1. 在 Regulatory Configuration Service (RCS) 中，選擇您建立的電子發票功能。 確保選擇狀態為 **草稿** 的版本。
2. 在 **設定** 索引標籤上，選取 **新增**。
3. 在 **建立功能設定** 下拉式對話方塊的 **新增** 欄位群組中，選擇 **自訂設定** 選項。
4. 在 **設定類型** 欄位群組，選擇 **資料管道** 選項。
5. 在 **選擇資料管道** 欄位，輸入 **接收電子郵件**。
6. 選取 **建立**。
7. 選擇您建立的行，然後選擇 **編輯**。
8. 在 **資料管道** 索引標籤的 **參數** 區段中，設定以下必填欄位。

    | 欄位                | 描述 |
    |----------------------|-------------|
    | 資料管道         | 輸入唯一名稱以標識資料管道。 名稱最多可以有 10 個字元。 它將在適用性規則和通訊流程中連接的應用程式中參考。 |
    | 伺服器位址       | 輸入電子郵件帳戶提供者的伺服器位址。 例如，`https://outlook.live.com` 提供者的伺服器位址為 imap-mail.outlook.com。 |
    | 伺服器連接埠          | 輸入電子郵件帳戶提供者使用的連接埠編號。 例如，`https://outlook.live.com` 提供者的伺服器連接埠為 993。 |
    | 使用者名稱祕密     | 輸入名稱包含電子郵件使用者帳戶識別碼的 Microsoft Azure Key Vault 秘密的名稱。 此秘密必須在 Key Vault 中建立並在您的服務環境中設定。 |
    | 使用者密碼祕密 | 輸入名稱包含電子郵件使用者帳戶密碼的 Key Vault 秘密的名稱。 |
    | 逾時              | 系統應等待回應的最大時間限制，以毫秒 (ms) 為單位。 預設值為 10,000 毫秒 (10 秒)。 |
    | 主資料夾          | 指定電子郵件匯入來源，或服務應處理的電子郵件源自的資料夾。 |
    | 封存資料夾       | 指定應儲存已處理電子郵件的資料夾。 如果不指定該資料夾，系統會自動建立。 |
    | 錯誤資料夾         | 指定處理失敗時系統應將電子郵件移動到的資料夾。 如果不指定該資料夾，系統會自動建立。 |
    | 訊息大小上限     | 輸入處理的單個訊息的最大大小 (以位元組為單位)。 預設值為 20,000,000 位元組。 |
    | 訊息數量上限   | 輸入處理的單個訊息的訊息數量上限。 如果您不想限制訊息數量，請將值設定為 **0** (零)。 |
    | 寄件者篩選器          | 輸入字串以按寄件者地址進行篩選。 只有寄件者地址與篩選器相符的電子郵件才會進行處理。 此為選填欄位。 要指定多個寄件者地址，請使用分號 (;) 作為分隔符。 |
    | 主旨篩選器       | 輸入字串以按主旨進行篩選。 只有主旨與篩選器相符的電子郵件才會進行處理。 此為選填欄位。 支援簡單的遮罩，如 **\*smth\*.ext**，其中的每個星號 (\*) 表示字元出現零次或多次。 |
    | 日期篩選器          | 指定一個日期以定義處理的郵件的最長期限 (以天為單位)。 此為選填欄位。 預設值為 30 日。 |
    | 處理模式      | <p>選擇以下選項之一以指定是否可以一起處理電子郵件中的所有附件，或者是否應單獨處理每個附件：</p><ul><li><b>按附件</b> – 將為電子郵件中的每個附件建立一個新的電子文件。 例如，如果一封電子郵件包含多個具有電子發票資料的文件，則每個文件都將視為系統中的新電子發票。</li><li><b>按電子郵件</b> – 一個附件將視為基本附件，系統將建立一張電子發票。 其他附件可做為支援文件。</li></ul> |

9. 在 **附件篩選器** 區段，新增檔案篩選資訊。 只有滿足定義篩選器的附件才會進行處理。 例如，**\*.xml** 將篩選具有 .xml 檔案副檔名的附件。 設定期間 Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 中將使用附件名稱。

    - 如果在上一步中將 **處理模式** 欄位設定為 **按電子郵件**，則可以在此處新增多個篩選器。 該名稱將標識特定文件。
    - 如果將 **處理模式** 欄位設定為 **按附件**，則只能新增一個篩選器。

10. 在 **適用性規則** 索引標籤，根據需要查看和更新條件。 **管道** 欄位的值必須等於您在步驟 8 **資料管道** 欄位中输入的值。
11. 選取 **儲存**，然後關閉此頁面。
