---
title: 建立客戶直接借記授權
description: 本工作指南示範如何建立直接借記授權並用於發票上。
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51fea2b9a0f25b078abc3ca83ee02c585eaf465128bebba0234ffadb030ef42a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450417"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>建立客戶直接借記授權

[!include [banner](../../includes/banner.md)]

本工作指南示範如何建立直接借記授權並用於發票上。


## <a name="create-a-bank-account"></a>建立銀行帳戶
1. 在 **瀏覽窗格** 中，前往 **模組 > 應收帳款 > 客戶 > 所有客戶**。
2. 請在清單中，選取報表。 例如，選擇 US-001
3. 在 [動作窗格] 上按一下 **客戶**。
4. 按一下 **銀行帳戶**。
5. 點選 **新增**。
6. 在 **銀行帳戶** 欄位中，輸入一個值。
7. 在 **名稱** 欄位中，輸入一個值。
8. 在 **IBAN** 欄位中，輸入一個值。
9. 請在 **貨幣** 欄位中輸入一值。
10. 點選 **儲存**。
11. 關閉頁面。
12. 在 **瀏覽窗格** 中，前往 **模組 > 現金和銀行管理 > 銀行帳戶 > 銀行帳戶**。
13. 在清單中，尋找並選取所需的記錄。
14. 在清單中，點選已選取列的連結。
15. 點選 **編輯**。
16. 展開 **其他識別碼** fastTab。
17. 在 **直接借記識別碼** 欄位中，輸入一個值。
18. 在 **IBAN** 欄位中，輸入一個值。
19. 關閉頁面。
20. 關閉頁面。

## <a name="define-the-electronic-payment-method"></a>定義電子付款方式
1. 在 **瀏覽窗格** 中，進入 **模組 > 應收帳款 > 付款設定 > 付款方式**。
2. 點選 **新增**。
3. 在 **付款方式** 欄位，輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
5. 在 **付款類型** 欄位中，輸入 [電子支付]。 直接借記授權付款方式的付款類型必須是 [電子付款]。
6. 在 **需要授權** 欄位中選取 [是]。
7. 關閉頁面。

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>將直接借記授權新增至客戶。
1. 在 **瀏覽窗格** 中，前往 **模組 > 應收帳款 > 客戶 > 所有客戶**。
2. 請在清單中，選取報表。 例如，選擇 US-001
3. 點選 **編輯**。
4. 展開 **付款預設** fastTab。
5. 在 **付款方式** 欄位中，輸入或選取一個值。
6. 展開 **付款預設** fastTab。
7. 展開 **直接借記授權** fastTab。
8. 選點 **新增**。
9. 在 **銀行帳戶** 欄位中，輸入或選擇一個值。
10. 在 **貸方銀行帳戶** 欄位中，輸入或選擇一個值。
11. 在 **付款頻率** 欄位中，輸入您希望為此授權處理的付款數量。
12. 點選 **確定**。
13. 點選 **列印**。
14. 點選 **授權報告**。
15. 關閉頁面。
16. 點選 **編輯**。
17. 在 **簽章日期** 欄位中，輸入日期。
18. 點選 **是**。
19. 輸入簽署授權的位置。
20. 點選 **確定**。
21. 關閉頁面。

## <a name="create-a-free-text-invoice-with-mandate"></a>建立包含授權的普通發票
1. 在 **瀏覽窗格** 中，前往 **模組 > 應收帳款 > 發票 > 所有普通發票**。
2. 點選 **新增**。
3. 選擇您已新增授權的客戶。
4. 在 **直接借記授權識別碼** 欄位，輸入或選擇一個值。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]