---
title: 設定 ISO20022 直接借記的客戶和公司銀行帳戶
description: 此工作透過設定所需的客戶銀行帳戶和客戶直接借記授權，以產生客戶付款檔案 (如 ISO20022 直接借記)。
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595e89faa1e24ca937d399994e15ce53e3f5308b1c6fd7f43e4e831e70c15ad8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450351"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>設定 ISO20022 直接借記的客戶和公司銀行帳戶

[!include [banner](../../includes/banner.md)]

此工作透過設定所需的客戶銀行帳戶和客戶直接借記授權，以產生客戶付款檔案 (如 ISO20022 直接借記)。 根據設定的客戶付款格式，客戶或客戶銀行帳戶可能需要此程序中未包含的其他資料。 

此工作是使用示範資料公司 DEMF 所建立的，該公司的法律實體主要地址位於德國。



這是五個用於示範使用電子申報設定的客戶付款流程之程序中的第四個。


## <a name="set-up-a-customer-bank-account"></a>設定客戶銀行帳戶
1. 前往 [應收帳款] > [客戶] > [所有客戶]。
2. 使用快速篩選條件尋找記錄。 例如，使用值為「DE-010」的 [帳戶] 欄位篩選。
3. 在清單中，點選已選取列的連結。
4. 在「動作窗格」上按一下 [客戶]。
5. 按一下 [銀行帳戶]。
6. 按一下 [新建]。
7. 在 [銀行帳戶] 欄位中，輸入一個值。
8. 在名稱欄位中，輸入一個值。
    * 例如，輸入「EUR 銀行」。  
9. 在 [銀行群組] 欄位中，輸入或選擇一個值。
10. 在 [IBAN] 欄位中，輸入一個值。
    * 例如，輸入「DE36200400000628808808」。  
11. 在 [SWIFT 代碼] 欄位中，輸入一個值。
    * 例如，輸入「COBADEFFXXX」。  請注意，許多付款格式不需要 SWIFT\BIC，但是建議註冊銀行帳戶還是將其加入。  
12. 按一下 [儲存]。
13. 關閉頁面。
14. 按一下 [編輯]。
15. 展開 [付款預設] 區段。
16. 在 [銀行帳戶] 欄位中，輸入或選擇一個值。

## <a name="add-a-direct-debit-mandate"></a>新增直接借記授權
1. 展開 [直接借記授權] 區段。
2. 按一下 [新增]。
3. 在 [貸方銀行帳戶] 欄位中，輸入或選擇一個值。
    * 例如，選擇「DEMF OPER」。  
4. 在 [簽章日期] 欄位中，輸入日期。
5. 按一下 [是] 以確認日期更新。
6. 在 [簽章位置] 欄位中，輸入或選取一個值。
7. 在 [付款預期值] 欄位中，輸入一個數字。
8. 按一下 [確定]。
9. 按一下 [儲存]。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]