---
title: 自訂憑證和密碼
description: 本主題說明如何在電子開票中設定自訂憑證和密碼。
author: dkalyuzh
ms.date: 02/07/2022
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
ms.openlocfilehash: 1325cad95e9a6dc470691f5f168439fccaaa78e1
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451716"
---
# <a name="customer-certificates-and-secrets"></a>自訂憑證和密碼

[!include [banner](../includes/banner.md)]

如果你在 Regulatory Configuration Service (RCS) 中已有 Microsoft Azure Key Vault 參考，您可以建立對 Key Vault 憑證和密碼的參考。 如果您還沒有 Key Vault 參考，請參閱[服務環境](e-invoicing-service-environments.md)了解有關如何建立此參考的資訊。

## <a name="create-certificates-and-secrets"></a>建立憑證和密碼

若要建立和設定憑證和密碼，請執行以下步驟。

1. 登入您的 RCS 帳戶。
2. 在 **全球化功能** 工作區的 **環境** 區段中，選擇 **電子開票** 圖格。
3. 在 **環境設定** 頁面的動作窗格上，選擇 **服務環境**。
4. 在 **服務環境** 頁面的動作窗格上，選擇 **Key Vaul 參數**。
5. 在 **Key Vault 參數** 頁面，選擇一個 Key Vault 參考，然後在 **憑證** 區段選擇 **新增**。
6. 在 **名稱** 欄位中，輸入 Key Vault 憑證或密碼的名稱。 有關詳細資訊，請參閱[在 Azure 入口網站中建立 Azure 儲存體帳戶](e-invoicing-create-azure-storage-account-azure-portal.md)。
7. 在 **描述** 欄位中，輸入描述。
8. 如果您要參考儲存在金鑰保存庫中的憑證，請在 **類型** 欄位，選擇 **憑證**。 如果您要參考儲存在金鑰保存庫中的密碼，請選擇 **密碼**。
9. 選擇 **儲存**。

> [!NOTE]
> 在某些情況下，您必須使用具有 .cer 副檔名的公用憑證。 但是，Key Vault 不支援將此類型的憑證作為 Key Vault 憑證匯入和儲存。 在這些情況下，您應該將 .cer 檔案儲存為 Base-64 編碼的 X.509 (.CER) 字串。 然後，在 Key Vault 密碼中，儲存出現在檔案中 **開始憑證** 行和 **結束憑證** 行之間的字串。 在服務環境中，您仍應建立對 Key Vault 記錄的參考並設定 **類型** 欄位設定為 **憑證**。

## <a name="create-a-chain-of-certificates"></a>建立憑證鏈

如果您的國家/地區特定發票需要一系列憑證來套用數位簽章或建立安全 (安全通訊端層 \[SSL\]) 連接到外部 Web 服務，請建立憑證鏈，憑證按以下順序排列：

1. 根憑證
2. 中間憑證
3. 最終使用者憑證

根憑證主管機構 (CA) 是受信任的憑證來源。 中間 CA 憑證是將最終使用者憑證鏈接到根 CA 憑證的橋樑。

若要建立和設定憑證鏈，請執行以下步驟。

1. 在 **Key Vault 參數** 頁面，在動作窗格上，選擇 **憑證鏈**。
2. 選擇 **新增** 以建立憑證鏈。
3. 在 **名稱** 欄位中，輸入憑證鏈的名稱。
4. 在 **描述** 欄位中，輸入描述。
5. 在 **憑證** 區段中，選擇 **新增** 將憑證新增到憑證鏈中。
6. 使用 **向上** 或 **向下** 按鈕變更憑證在憑證鏈中的位置。 將 CA 根憑證放在清單頂部，將最終使用者憑證放在底端。
7. 選擇 **儲存**。

您可以根據需要在 RCS 中建立任意數量的 Key Vault 參考。 請記住，儲存共用存取簽章 (SAS) 權杖的金鑰用於將指定的服務環境連結到 Key Vault 參考。 您可以參考儲存在金鑰保存庫中的 Key Vault 憑證和密碼，該金鑰保存庫還包含您在設定服務環境時使用的儲存 SAS 權杖的密碼。
