---
title: 進階銀行對帳設定流程
description: 進階銀行對帳功能可讓您在 Microsoft Dynamics 365 Finance 中匯入電子銀行對帳單，並與銀行交易自動對帳。 本文將說明對帳的設定流程。
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42c86a120403d8d87d62c76d56993decca7f6cdafaeb67c7afec29da0bf8f18f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450597"
---
# <a name="advanced-bank-reconciliation-setup-process"></a>進階銀行對帳設定流程

[!include [banner](../includes/banner.md)]

進階銀行對帳功能可讓您在 Microsoft Dynamics 365 Finance 中匯入電子銀行對帳單，並與銀行交易自動對帳。 本文將說明對帳的設定流程。  

在使用進階銀行對帳功能之前，必須設定許多部分。 更多有關設定銀行對帳單匯入的資訊，請參閱[設定進階銀行對帳匯入流程](set-up-advanced-bank-reconciliation-import-process.md)。  對帳流程的設定要求詳述如下。

## <a name="transaction-codes"></a>交易代碼
交易代碼可用作銀行對帳比對規則的一部分。 交易代碼將有助於僅比對 Finance 和您的銀行對帳單之間相同類型的交易。 為了進行這種類型的比對，您必須先從 Finance 定義用於銀行交易的交易類型，然後將這些類型對應到您的銀行使用的對帳單交易代碼。 銀行交易的交易類型在 **銀行交易類型** 頁面中定義。 這也是定義要用於與該交易類型關聯的過帳的主科目。 

定義銀行交易代碼後，將其對應到電子銀行對帳單中使用的交易代碼。 這個對應流程是使用 **交易代碼對應** 頁面執行。 每個銀行帳戶分別完成交易代碼對應。

## <a name="matching-rules-and-matching-rule-sets"></a>比對規則和比對規則集
比對規則可讓您定義財務銀行交易和銀行對帳單交易之間自動對帳的條件。 比對規則的設定是在 **對帳比對規則** 頁面執行。 更多資訊，請參閱[設定銀行對帳比對規則](set-up-bank-reconciliation-matching-rules.md)。 

比對規則集用於定義在銀行對帳流程中按順序執行的一組比對規則。  比對規則集在 **對帳比對規則集** 頁面中設定。

## <a name="cash-and-bank-management-parameters"></a>現金和銀行管理參數
在 **現金和銀行管理參數** 頁面中有許多特定於進階銀行對帳流程的參數。  **顯示借方/貸方對帳單行金額** 變更 **銀行對帳單** 頁面上金額的檢視表。 如果選擇此選項，銀行對帳單交易金額將顯示在單獨的借方和貸方欄中。 如果未選擇此選項，銀行對帳單交易金額將顯示在單個金額欄中，並帶有相應的符號。 

在參數頁面上設定的驗證選項會覆寫在比對規則上設定的選擇。 例如，您不能手動或自動比對在參數頁面上設定的日期差異以外的文件。 此外，如果選擇 **驗證交易類型對應** 選項時，必須在財務銀行交易和銀行對帳單交易之間對應交易類型，以便手動或自動比對交易。 

您還必須在 **現金和銀行管理參數** 頁面設定必要的編號規則。  在 **編號規則** 索引標籤，為下載 **識別碼、對帳單識別碼、對帳識別碼和銀行對帳** 參考設定編號規則。

## <a name="bank-account-reconciliation-options"></a>銀行帳戶對帳選項
您必須先為銀行帳戶啟用進階銀行對帳。 啟用進階銀行對帳功能後，**銀行帳戶** 頁面將提供許多其他可用選項。 

**使用銀行對帳單作為電子支付確認** 功能將銀行對帳功能與電子支付狀態相整合。 啟用此功能後，將為設定為 **已發送** 的電子支付狀態自動建立銀行單據。 此外，電子支付的狀態將在比對、對帳和過帳付款後，從 **已發送** 更新為 **已接收**。 

**報表中的銀行帳戶名稱** 欄位是用於您的電子銀行對帳單上的銀行帳戶的名稱。 當從可能包含多個銀行帳戶資訊的報表中確定要為銀行帳戶匯入哪些交易時，將使用此名稱。 

**匯入後對帳** 選項將自動驗證銀行對帳單，建立新的銀行對帳和工作表，並執行預設比對規則集。 此功能使流程自動化，直到必須手動比對交易為止。 匯入時將預設使用銀行帳戶上的設定。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]