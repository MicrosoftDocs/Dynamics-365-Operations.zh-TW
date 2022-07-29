---
title: 服務環境
description: 本主題提供有關電子開票服務環境的資訊並說明如何設定它們。
author: dkalyuzh
ms.date: 02/28/2022
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
ms.openlocfilehash: a8a135098f71e1413cd20ff8ad4003f090ae3407
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451707"
---
# <a name="service-environments"></a>服務環境

[!include [banner](../includes/banner.md)]

服務環境是為支援全球化功能和在電子開票服務中處理的相應文件而建立的邏輯分區。 必須在服務環境級別設定安全性密碼和數位憑證以及存取權限 (治理)。

您可以根據需要建立任意數量的服務環境。 您建立的所有服務環境都是相互獨立的。 作為最佳做法，建議您至少建立兩個服務環境：

- 一種是用於主要開發和驗證目的的環境。 此環境通常是使用者驗收測試 (UAT) 環境。
- 一種是用於生產目的的環境。 該環境通常是生產環境。

這種類型的分區有助於確保電子發票流程在投入生產之前在沙箱中得到驗證和自訂。

必須在 Regulatory Configuration Service (RCS) 中建立和維護服務環境。 然後，服務環境準備就緒後，必須將其發佈到電子開票服務。 發佈流程將服務環境的參數從 RCS 執行個體發送到電子開票服務。

如果您在建立新服務環境或調整現有服務環境 (例如，透過新增或刪除使用者或 Microsoft Azure Key Vault 密碼) 後未完成發佈流程，變更將無效。 Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 只能存取已發佈的環境。

## <a name="service-environment-statuses"></a>服務環境狀態

服務環境可以透過其狀態進行管理。 您可以在 **服務環境** 頁面上查看環境的狀態。 可以使用以下狀態：

- **未發表** – 環境已建立，但尚未發佈。
- **已發佈** – 環境已發佈到電子發票服務。
- **已變更** – 已發佈環境的屬性已變更，但尚未發佈變更。

## <a name="users"></a>使用者

每個服務環境必須列出可以從 Finance 或 Supply Chain Management 連接到電子開票的使用者。

## <a name="applications"></a>應用程式

在某些情況下，Finance 或 Supply Chain Management 以外的應用程式可能必須連接到電子開票服務，才能提交電子文件以進行進一步處理，或擷取諸如文件提交狀態之類的資訊。 在這些情況下，應在應用程式清單中定義應用程式。 這樣，應用程式就可以存取電子開票服務。 該應用程式還必須在 Azure Active Directory(Azure AD) 中註冊為應用程式，且必須使用物件識別碼來加以識別。 

由於 Microsoft 要求對可連接到電子開票服務的應用程式進行高級別的安全控制，因此您必須透過 <DGXRegulatoryservicesengineering@service.microsoft.com> 連絡 Microsoft，並提供應用程式的以下詳細資訊：

- Azure AD 租用戶識別碼
- Microsoft Dynamics Lifecycle Services (LCS) 環境識別碼
- 應用程式識別碼 (用戶端識別碼)
- 物件識別碼
- 應用程式的理由和高級描述

Microsoft 將評估該要求並將應用程式註冊到安全性註冊表中，以確保它可以使用電子發票進行作業。

## <a name="number-sequences"></a>編號規則

如果您的方案需要編號規則 (例如，在檔案名稱中)，您可以使用為特定環境定義的編號規則，但可以跨全球化功能或特定全球化功能使用。 定義好編號規則後，您可以在變數和處理管道中使用它。 要追蹤其使用情況，請在 **編號規則** 頁面，尋找 **使用中** 參數的 **目前** 值。

### <a name="working-with-number-sequences"></a>使用編號規則
在 **編號規則** 頁面： 

- 選取 **新建** 建立編號規則。 然後輸入名稱和描述。 
- 選擇 **刪除** 以刪除不再使用的編號規則。
- 無須在在動作窗格上選擇 **發佈** 來發佈對編號規則的變更。 更新會自動完成。

## <a name="create-a-key-vault-reference"></a>建立 Key Vault 參考

1. 登入您的 RCS 帳戶。
2. 在 **全球化功能** 工作區的 **環境** 區段中，選擇 **電子開票** 圖格。
3. 在 **環境設定** 頁面的動作窗格上，選擇 **服務環境**。
4. 在 **服務環境** 頁面的動作窗格上，選擇 **Key Vaul 參數**。
5. 在 **Key Vault 參數** 頁面，選擇 **新增** 以建立 Key Vault 參考。
6. 在 **名稱** 欄位中輸入 Key Vault 參考的名稱。
7. 在 **描述** 欄位中，輸入描述。
8. 在 **Key Vault URI** 欄位中，貼上來自金鑰保存庫 (`https://<your key vault>.vault.azure.net/`) 的 Key Vault URI。 有關詳細資訊，請參閱[在 Azure 入口網站中建立 Azure Key Vault](e-invoicing-create-azure-key-vault-azure-portal.md)。
9. 選擇 **儲存**。
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>為儲存體帳戶密碼權杖建立密碼

1. 在 **Key Vault 參數** 頁面，選擇在上一個程序中建立的 Key Vault 參考，然後在 **憑證** 區段選擇 **新增**。
2. 在 **名稱** 欄位中，輸入儲存體帳戶密碼的名稱。 此名稱應與儲存體共用存取簽章 (SAS) 權杖的 Key Vault 密碼的名稱相符。 有關詳細資訊，請參閱[在 Azure 入口網站中建立 Azure 儲存體帳戶](e-invoicing-create-azure-storage-account-azure-portal.md)。 
3. 在 **描述** 欄位中，輸入描述。
4. 在 **類型** 欄位中，選取 **密碼**。
5. 選擇 **儲存**。
    
## <a name="create-a-service-environment"></a>建立服務環境

1. 在 **服務環境** 頁面，選擇 **新增** 以建立服務環境。
2. 在 **名稱** 欄位中輸入電子開票環境的名稱。
3. 在 **描述** 欄位中，輸入描述。
4. 在 **儲存體 SAS 權杖密碼** 欄位中，選擇必須用於對儲存體帳戶的存取權進行驗證的儲存體帳戶密碼的名稱。
5. 在 **使用者** 區段，選擇 **新增** 以新增允許透過環境提交電子發票並連接到儲存體帳戶的使用者。
6. 在 **使用者識別碼** 欄位，輸入使用者的別名。 
7. 在 **電子郵件** 欄位中，輸入使用者的電子郵件地址。
8. 選擇 **儲存**。
9. 在動作窗格上，選擇 **發佈** 將環境發佈到電子開票服務。 驗證 **狀態** 欄位的值是否已變更為 **已發佈**。
