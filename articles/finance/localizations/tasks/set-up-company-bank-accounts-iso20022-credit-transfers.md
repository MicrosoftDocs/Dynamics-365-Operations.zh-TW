---
title: 設定 ISO20022 貸方轉帳公司銀行帳戶
description: 此程序顯示如何設定產生付款檔案所需的公司特定銀行帳戶資料。
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
ms.openlocfilehash: a3b3b5ce9d7e24b2b7d3f76e4d770968df897b546df507ba9e3bde5aeac91715
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450882"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>設定 ISO20022 貸方轉帳公司銀行帳戶

[!include [banner](../../includes/banner.md)]

此程序顯示如何設定產生付款檔案所需的公司特定銀行帳戶資料。 您設定產生 ISO 20022 貸方轉帳格式所需的資料，但根據格式的不同，可能還需要其他資料，例如：「公司識別碼」或「排序代碼」。 

用來建立此程序的示範資料公司為 DEMF。

這是五個用於說明使用電子申報設定的廠商付款流程之程序中的第二個。 此程序是 Dynamics 365 for Operations 版本 1611 中增加的功能。


## <a name="set-up-iban-and-swift-code"></a>設定 IBAN 和 SWIFT 代碼
1. 前往 [現金和銀行管理參數] > [銀行帳戶]。
2. 使用 [快速篩選條件] 以篩選含有「DEMF OPER」值的「銀行帳戶」。
3. 按一下 [DEMF OPER] 以開啟銀行帳戶詳細資料。
4. 按一下 [編輯]。
5. 展開 [額外識別] 區段。
6. 在 [IBAN] 欄位中，輸入「DE89370400440532013000」。
7. 在 [SWIFT 代碼] 欄位中，輸入「DEUTDEFF」。
    * 請注意，許多付款格式不需要 SWIFT\BIC，但是建議註冊銀行帳戶還是將其加入。  
8. 按一下 [儲存]。

## <a name="set-up-bank-account-for-the-legal-entity"></a>設定法律實體的銀行帳戶
1. 前往 [組織管理] > [組織] > [法律實體]。
2. 按一下 [編輯]。
3. 展開 [銀行帳戶資料] 區段。
4. 在 [銀行帳戶] 欄位中，輸入或選擇一個值。
5. 按一下 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]