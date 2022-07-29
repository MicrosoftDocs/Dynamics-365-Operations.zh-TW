---
title: 設定 ISO20022 直接借記公司銀行帳戶
description: 此工作透過設定所需的公司特定銀行帳戶資料，以產生客戶付款檔案。
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0f8ac369bb6b9a7a0f21c23aaddab2601ae3f8f37e2427cbb10b5509a7a2f23
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450720"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>設定 ISO20022 直接借記公司銀行帳戶

[!include [banner](../../includes/banner.md)]

此工作透過設定所需的公司特定銀行帳戶資料，以產生客戶付款檔案。 此程序使用 ISO 20022 直接借記格式作為範例。 其他格式可能需要更多設定資料，例如：「公司識別碼」或「排序代碼」。



用於建立此工作的示範資料公司是 DEMF。



這是五個用於示範使用電子申報設定的客戶付款流程之程序中的第二個。


## <a name="set-up-the-iban-and-swift-codes"></a>設定 IBAN 和 SWIFT 代碼
1. 前往 [現金和銀行管理參數] > [銀行帳戶]。
2. 使用 [快速篩選條件] 以篩選含有「DEMF OPER」值的「銀行帳戶」。
3. 在清單中，點選已選取列的連結。
    * 例如，按一下「DEMF OPER」開啟銀行帳戶詳細資料。  
4. 按一下 [編輯]。
5. 展開或摺疊「額外識別」區段。
6. 在 [IBAN] 欄位中，輸入一個值。
    * 例如，輸入「DE89370400440532013000」。  
7. 在 [SWIFT 代碼] 欄位中，輸入一個值。
    * 例如，輸入「DEUTDEFF」。    請注意，許多付款格式不需要 SWIFT\BIC，但是建議註冊銀行帳戶還是將其加入。  
8. 按一下 [儲存]。

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>設定法律實體的銀行帳戶
1. 前往 [組織管理] > [組織] > [法律實體]。
2. 按一下 [編輯]。
3. 展開或摺疊 [銀行帳戶資料] 區段。
4. 在 [銀行帳戶] 欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，點選已選取列的連結。
    * 例如，選擇「DEMF OPER」銀行帳戶。  
6. 按一下 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]