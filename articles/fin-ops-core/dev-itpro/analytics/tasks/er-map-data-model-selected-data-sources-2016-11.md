---
title: ER 將資料模型對應到選定的資料來源
description: 本主題介紹如何將電子報表 (ER) 資料模型對應到選定的 Microsoft Dynamics 365 Finance 資料來源。
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60c20f6616d406bdd1ccdf42ac62eb4c1c5d27040f32469fa6dd370c41830450
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460236"
---
# <a name="er-map-data-model-to-selected-data-sources"></a>ER 將資料模型對應到選定的資料來源

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何將電子報表 (ER) 資料模型對應到選定的資料來源。 此模型對應稍後將用作格式設定中的資料來源，用於管理電子支付文件。 在此範例中，您將樣本公司 Litware, Inc. 的資料模型對應到資料來源。 若要完成這些步驟，您必須先完成「為模型對應選取資料來源」程序中的步驟。


## <a name="open-er-configurations-tree"></a>打開 ER 設定樹狀結構
1. 進入組織管理 > 工作區 > 電子報表。
2. 點選設定。

## <a name="select-created-model-mapping"></a>選取建立的模型對應
1. 在樹狀結構中，選取「付款 (簡化模型)」。
    * 確保模型設定「付款 (簡化模型)」已預先建立。 否則，現在停止並在完成工作指南「使用所選領域的資料模型建立新設定」後回傳。  
2. 點選模型設計工具。
3. 點選將模型對應到資料來源。
4. 選取「CT 對應」記錄。
    * CT 對應  

## <a name="bind-created-data-sources-to-data-model-elements"></a>將建立的資料來源繫結到資料模型元素
1. 點選設計工具。
2. 在樹狀結構中，選取「處理日期和時間(ProcessingDateTime)」。
3. 在樹狀結構中，選取「處理日期(ProcessingDateTime)」。
4. 點選繫結。
5. 在樹狀結構中，選取「付款訊息識別(MessageIdentification)」。
6. 在樹狀結構中，展開「Transactions」。
7. 在樹狀結構中，選取「Transactions\Journal batch number(JournalNum)」。
8. 點選繫結。
9. 在樹狀結構中，選取「付款」。
10. 在樹狀結構中，選取「Transactions」。
11. 點選繫結。
12. 在樹狀結構中，展開「Payments= Transactions」。
13. 在樹狀結構中，展開「Payments= Transactions\Creditor」。
14. 在樹狀結構中，展開「Payments= Transactions\Creditor\Account」。
15. 在樹狀結構中，選取「Payments= Transactions\Creditor\Account\Currency code(Currency)」。
16. 在樹狀結構中，展開「Transactions\vendBankAccountInTransactionCompany()」。
17. 在樹狀結構中，選取「Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)」。
18. 點選繫結。
19. 在樹狀結構中，選取「Payments= Transactions\Creditor\Account\IBAN code(IBAN)」。
20. 在樹狀結構中，選取「Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)」。
21. 點選繫結。
22. 在樹狀結構中，選取「Payments= Transactions\Creditor\Account\Number」。
23. 在樹狀結構中，選取「Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)」。
24. 點選繫結。
25. 在樹狀結構中，展開「Payments= Transactions\Creditor\Agent」。
26. 在樹狀結構中，選取「Payments= Transactions\Creditor\Agent\Name」。
27. 在樹狀結構中，選取「Transactions\vendBankAccountInTransactionCompany()\Name」。
28. 點選繫結。
29. 在樹狀結構中，選取「Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)」。
30. 在樹狀結構中，選取「Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)」。
31. 點選繫結。
32. 在樹狀結構中，選取「Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)」。
33. 在樹狀結構中，選取「Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)」。
34. 點選繫結。
35. 在樹狀結構中，選取「Payments= Transactions\Creditor\Name」。
36. 在樹狀結構中，展開或摺疊「Transactions\findVendTable()」。
37. 在樹狀結構中，選取「Transactions\findVendTable()\name()」。
38. 點選繫結。
39. 在樹狀結構中，選取「Payments= Transactions\Currency code(Currency)」。
40. 在樹狀結構中，展開「Transactions\>Relations」。
41. 在樹狀結構中，展開「Transactions\>Relations\Currency table(Currency)」。
42. 在樹狀結構中，選取「Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)」。
43. 點選繫結。
44. 在樹狀結構中，展開「Payments= Transactions\Debtor」。
45. 在樹狀結構中，展開「Payments= Transactions\Debtor\Account」。
46. 在樹狀結構中，選取「Payments= Transactions\Debtor\Account\Currency code(Currency)」。
47. 在樹狀結構中，選取「Bank Account(BankAccount)」。
48. 在樹狀結構中，展開「Bank Account(BankAccount)」。
49. 在樹狀結構中，選取「Bank Account(BankAccount)\Currency(CurrencyCode)」。
50. 點選繫結。
51. 在樹狀結構中，選取「Bank Account(BankAccount)\IBAN'」。
52. 在樹狀結構中，選取「Payments= Transactions\Debtor\Account\IBAN code(IBAN)」。
53. 點選繫結。
54. 在樹狀結構中，選取「Payments= Transactions\Debtor\Account\Number」。
55. 在樹狀結構中，選取「Bank Account(BankAccount)\Bank account number(AccountNum)」。
56. 點選繫結。
57. 在樹狀結構中，展開「Payments= Transactions\Debtor\Agent」。
58. 在樹狀結構中，選取「Payments= Transactions\Debtor\Agent\Name」。
59. 在樹狀結構中，選取「Bank Account(BankAccount)\Name」。
60. 點選繫結。
61. 在樹狀結構中，選取「Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)」。
62. 在樹狀結構中，選取「Bank Account(BankAccount)\Routing number(RegistrationNum)」。
63. 點選繫結。
64. 在樹狀結構中，選取「Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)」。
65. 在樹狀結構中，選取「Bank Account(BankAccount)\SWIFT code(SWIFTNo)」。
66. 點選繫結。
67. 在樹狀結構中，選取「Payments= Transactions\Debtor\Name」。
68. 在樹狀結構中，選取「Company information(Company)」。
69. 在樹狀結構中，展開「Company information(Company)」。
70. 在樹狀結構中，選取「Company information(Company)\Name」。
71. 點選繫結。
72. 在樹狀結構中，選取「Payments= Transactions\Description」。
73. 在樹狀結構中，選取「Transactions\Description(Txt)」。
74. 點選繫結。
75. 在樹狀結構中，選取「Payments= Transactions\End to end Identification code(End2EndID)」。
76. 在樹狀結構中，選取「Transactions\$EndToEndID」。
77. 點選繫結。
78. 在樹狀結構中，選取「Payments= Transactions\Instructed amount(InstructedAmount)」。
79. 在樹狀結構中，選取「Transactions\$Amount」。
80. 點選繫結。
81. 在樹狀結構中，選取「Payments= Transactions\Transaction date(TransactionDate)」。
82. 在樹狀結構中，選取「Transactions\Date(TransDate)」。
83. 點選繫結。

## <a name="validate-created-mapping"></a>驗證建立的對應
1. 點選「驗證」。
    * 驗證新對應以確保所有繫結都正常。  
2. 點選箭頭以展開或摺疊錯誤清單部分。
3. 點選儲存。
4. 關閉頁面。
5. 關閉頁面。
6. 關閉頁面。

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>更改現行版本模型設定的狀態
1. 點選更改狀態。
    * 將設計模型設定的狀態從草稿更改為已完成，以使其可用於付款格式設計。  
2. 點選完成。
    * 選取 [完成]。  
3. 在描述欄位中，輸入一個值。
    * 例如，「版本 1」。  
4. 點選確定。
5. 選取現行設定的完整版本。
    * 請注意，建立的設定儲存為已完成的版本 1。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]