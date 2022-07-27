---
title: 定義 ER 模型對應並為其選取資料來源
description: 本主題描述系統管理員或電子報表開發人員如何為電子報表資料模型選取資料來源。
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69fb025b273aca6a0cf7733732f2849686eaa470ded6804a10b793cff9837562
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460268"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a>定義 ER 模型對應並為其選取資料來源

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何為電子報表 (ER) 資料模型選取資料來源。 資料來源將在設計階段繫結到所選資料模型的各個組件，並在執行階段將業務資料填入到該資料模型中。 在此範例中，您將為已為樣本公司 Litware, Inc. 建立的現有資料模型選取資料來源。若要完成這些步驟，您必須先完成「建立新資料模型」程序中的步驟。


## <a name="open-the-electronic-reporting-configurations-tree"></a>開啟電子報表設定樹狀結構
1. 進入組織管理 > 工作區 > 電子報表。
2. 點選報表設定。

## <a name="insert-a-new-model-mapping"></a>插入新模型對應
1. 在樹狀結構中，選取「付款 (簡化模型)」。
2. 點選設計工具。
3. 點選將模型對應到資料來源。
4. 點選「新增」。
    * 這將建立一個將資料模型對應到資料來源的新記錄。 在此範例中，您將資料模型對應到所需支付類型的資料來源：貸方轉帳。     可以為特定資料模型設計多個對應。 例如，您可以為不同類型的付款建立對應，例如直接借記或貸方轉帳。 在本例中，您將為貸方轉帳建立一個對應。  
5. 在名稱欄位，輸入「CT mapping」。
    * CT 對應  
6. 在描述欄位中，輸入「Payment model mapping CT」。
    * 付款模式對應 CT  
7. 在定義欄位，輸入「CustomerCreditTransferInitiation」。
    * CustomerCreditTransferInitiation  
8. 解決更改定義。
9. 點選儲存。

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>定義現行模型對應所需的資料來源
1. 點選設計工具。
2. 在樹狀結構中，選取「Dynamics 365 for Operations\資料表記錄」。
3. 點選新增根。
    * 輸入此資料來源以存取付款交易。  
4. 在名稱欄位，輸入「Transaction」。
    * 交易  
5. 在標籤欄位中，輸入「Transactions」。
    * 交易  
6. 在幫助欄位中，輸入「Ledger journal lines」。
    * 分類帳日記帳明細  
7. 在詢問查詢欄位中選取是。
    * 選取是。  
8. 在資料表欄位，輸入「LedgerJournalTrans」。
    * LedgerJournalTrans  
9. 點選確定。
    * 選取 LedgerJournalTrans 表作為現行資料模型的資料來源。  
10. 在樹狀結構中，選取「函數\匯出欄位」。
11. 選點新增。
    * 點選新增以新增新的匯出欄位。  
12. 在名稱欄位，輸入「$EndToEndID」。
    * $EndToEndID  
13. 點選編輯公式。
14. 在樹狀結構中，選取「字串\連接」。
15. 點選新增函數。
16. 在樹狀結構中，展開「Transactions」。
17. 在樹狀結構中，選取「Transactions\Voucher」。
18. 點選新增資料來源。
19. 在公式欄位中，輸入「CONCATENATE(Transactions.Voucher, "-", 」。
    * 在公式末尾輸入 [ , "-", ]。  
20. 在樹狀結構中，選取「String\TEXT」。
21. 點選新增函數。
22. 在樹狀結構中，選取「Transactions\Record-ID(RecId)」。
23. 點選新增資料來源。
24. 在公式欄位中，輸入「CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))」。
    * 在公式末尾輸入 [))]。  
25. 點選儲存。
    * 確保沒有為建立的公式發現錯誤。 請參閱公式編輯器控制項下方的 ERRORS 索引標籤。  
26. 關閉頁面。
27. 點選確定。
    * 將匯出欄位新增到此資料來源。  
28. 選點新增。
    * 點選新增以新增新的匯出欄位。  
29. 在名稱欄位，輸入「$Amount」。
    * $Amount  
30. 點選編輯公式。
31. 在樹狀結構中，展開「Transactions」。
32. 在樹狀結構中，選取「Transactions\Debit(AmountCurDebit)」。
33. 點選新增資料來源。
34. 在公式欄位中，輸入「Transactions.AmountCurDebit - 」。
    * 在公式末尾輸入 [ - ]。  
35. 在樹狀結構中，選取「Transactions\Credit(AmountCurCredit)」。
36. 點選新增資料來源。
37. 點選儲存。
38. 關閉頁面。
39. 點選確定。
    * 這會將 $Amount 匯出欄位新增到現行資料模型的選定資料來源。  
40. 在樹狀結構中，選取「Transactions\$Amount」。
41. 在樹狀結構中，展開「Transactions」。
42. 在樹狀結構中，展開或摺疊「Transactions\$Amount」。
43. 在樹狀結構中，展開或摺疊「Transactions」。
44. 在樹狀結構中，選取「Dynamics 365 for Operations\資料表記錄」。
45. 點選新增根。
    * 輸入此資料來源以存取公司的銀行帳戶詳情。  
46. 在名稱欄位，輸入「BankAccount」。
    * BankAccount  
47. 在標籤欄位中，輸入「Bank Account」。
    * 銀行帳戶  
48. 在幫助欄位中，輸入「Bank Account」。
    * 銀行帳戶  
49. 在詢問查詢欄位中選取是。
    * 選取是。  
50. 在資料表欄位，輸入「BankAccountTable」。
    * BankAccountTable  
51. 點選確定。
    * 選取 BankAccountTable 表作為現行資料模型的資料來源。  
52. 點選新增根。
    * 輸入此資料來源以存取公司的要求。  
53. 在名稱欄位，輸入「Company」。
    * 公司  
54. 在標籤欄位中，輸入一個值。
    * 公司資訊  
55. 在幫助欄位中，輸入「Company information」。
    * 公司資訊  
56. 在詢問查詢欄位中選取是。
    * 選取是。  
57. 在資料表欄位，輸入「CompanyInfo」。
    * CompanyInfo  
58. 點選確定。
    * 選取 CompanyInfo 表作為現行資料模型的資料來源。  
59. 在樹狀結構中，選取「函數\匯出欄位」。
60. 點選新增根。
    * 插入匯出欄位作為新資料來源。  
61. 在名稱欄位中，輸入「ProcessingDateTime」。
    * ProcessingDateTime  
62. 在標籤欄位中，輸入「處理日期和時間」。
    * 處理日期和時間  
63. 點選編輯公式。
64. 在樹狀結構中，選取「Date/time\SESSIONNOW」。
65. 點選新增函數。
66. 點選儲存。
67. 關閉頁面。
68. 點選確定。
    * 新增 ProcessingDateTime 匯出欄位作為現行資料模型的資料來源。  
69. 點選儲存。
70. 關閉頁面。
71. 關閉頁面。
72. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]