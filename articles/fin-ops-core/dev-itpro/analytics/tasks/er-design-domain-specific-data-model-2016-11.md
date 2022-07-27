---
title: ER 設計領域特定資料模型
description: 本主題描述如何建立包含電子付款文件資料模型的新電子報表 (ER) 設定。
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16d76d243779f83646f14418a12c9c895fdf043451d82bd7062289be6cd8014a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460265"
---
# <a name="er-design-domain-specific-data-model"></a>ER 設計領域特定資料模型

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何建立包含電子付款文件資料模型的新電子報表 (ER) 設定。 此資料模型稍後將在您建立付款文件格式時用作資料來源。

在此範例中，您將為樣本公司 Litware, Inc. 建立一個設定。這些步驟可以在任何公司中執行，因為 ER 設定在公司之間共用。 若要完成這些步驟，您必須先完成「建立設定提供者並將其標記為有效」程序中的步驟。

1. 進入組織管理 > 工作區 > 電子報表。

    選取樣本公司「Litware, Inc.」的設定提供者 如果您沒有看到此設定提供者，則必須先完成「建立設定提供者並將其標記為有效」程序中的步驟。  
    
2. 點選報表設定。

    您將建立一個設定，其中包含電付款文件的資料模型。 當您為付款文件建立格式時，此資料模型將在稍後用作資料來源。  

## <a name="create-a-new-data-model-configuration"></a>建立新的資料模型設定
1. 點選建立設定即可打開下拉式對話方塊。
2. 在名稱欄位，輸入「Payments (simplified model)」。
3. 在描述欄位中，輸入「Payment model configuration」。

    有效設定提供者會自動在此處輸入。 此提供者將能夠維護此設定。 其他提供者可以使用此設定，但無法維護它。  

4. 點選「建立設定」按鈕，完成設定建立工作

## <a name="create-a-data-model"></a>建立資料模型
您正在為選定的設定建立一個新的資料模型。 此設定版本的狀態為草稿。  
1. 點選設計工具。

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a>定義參與付款流程的一方的結構
1. 按一下新增以開啟下拉式對話方塊。
2. 在名稱欄位，輸入「Party」。
3. 選點新增。
4. 按一下新增以開啟下拉式對話方塊。
5. 在名稱欄位，輸入「Name」。
6. 在項目類型欄位中，選取「字串」。
7. 選點新增。
8. 在尋找欄位，輸入「Party」。
9. 點選尋找上一頁。

## <a name="define-the-bank-structure-for-this-model"></a>定義此模型的銀行結構
1. 按一下新增以開啟下拉式對話方塊。
2. 在名稱欄位，輸入「Agent」。
3. 在項目類型欄位中，選取「記錄」。
4. 選點新增。
5. 在描述欄位中，輸入「Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).」。

    金融機構 (例如，銀行) 為當事人 (債務人/債權人) 的帳戶提供服務。  

6. 按一下新增以開啟下拉式對話方塊。
7. 在名稱欄位，輸入「Name」。 
8. 在項目類型欄位中，選取「字串」。
9. 選點新增。
10. 按一下新增以開啟下拉式對話方塊。
11. 在名稱欄位，輸入「SWIFT」。
12. 選點新增。
13. 在描述欄位中，輸入「Bank identification code」。 
14. 按一下新增以開啟下拉式對話方塊。
15. 在名稱欄位，輸入「RoutingNumber」。
16. 選點新增。
17. 在描述欄位中，輸入「Routing number」。
18. 點選尋找上一頁。

## <a name="define-the-bank-account-structure-for-this-model"></a>定義此模型的帳戶結構
1. 按一下新增以開啟下拉式對話方塊。
2. 在名稱欄位，輸入「Account」。 
3. 在項目類型欄位中，選取「記錄」。
4. 選點新增。
5. 在描述欄位中，輸入「Identification of an account of a party in a financial institution (for instance, a bank).」。

    金融機構 (例如銀行) 中一方的帳戶識別資訊。  

6. 按一下新增以開啟下拉式對話方塊。
7. 在名稱欄位，輸入「Currency」。 
8. 在項目類型欄位中，選取「字串」。
9. 選點新增。
10. 在描述欄位中，輸入「Currency code」。
11. 按一下新增以開啟下拉式對話方塊。
12. 在名稱欄位，輸入「Number」。 
13. 選點新增。
14. 按一下新增以開啟下拉式對話方塊。
15. 在名稱欄位，輸入「IBAN」。 
16. 選點新增。
17. 在描述欄位中，輸入「International bank account number」。

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a>定義貸方轉帳付款類型的付款訊息結構
1. 按一下新增以開啟下拉式對話方塊。
2. 在作為欄位的新節點中，輸入「Model root」。
3. 在名稱欄位，輸入「CustomerCreditTransferInitiation」。
4. 選點新增。
5. 在尋找欄位，輸入「CustomerCreditTransferInitiation」。 
6. 點選尋找上一頁。
7. 按一下新增以開啟下拉式對話方塊。
8. 在名稱欄位中，輸入「MessageIdentification」。 
9. 選點新增。
10. 在描述欄位中，輸入「The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.」。

    指示方指派 (並發送給下一方) 以識別訊息的點對點參考。  

11. 按一下新增以開啟下拉式對話方塊。
12. 在名稱欄位中，輸入「ProcessingDateTime」。
13. 在項目類型欄位中，選取「日期時間」。
14. 選點新增。
15. 在描述欄位中，輸入「Date and time at which the payment message was created.」。 
16. 按一下新增以開啟下拉式對話方塊。

    定義此模型的付款交易結構。  

17. 在名稱欄位，輸入「Payments」。
18. 在項目類型欄位中，選取「記錄清單」。
19. 選點新增。
20. 在描述欄位中，輸入「Payment lines of the current message」。
21. 按一下新增以開啟下拉式對話方塊。
22. 在名稱欄位，輸入「Creditor」。 
23. 在項目類型欄位中，選取「記錄」。
24. 選點新增。
25. 在描述欄位中，輸入「Party to which an amount of money is due.」。 
26. 點選切換項目參考。
27. 在尋找欄位，輸入「Party」。
28. 下一步點選尋找。
29. 按一下確定。
30. 在尋找欄位，輸入「Payments」。
31. 下一步點選尋找。
32. 按一下新增以開啟下拉式對話方塊。
33. 在名稱欄位，輸入「Debtor」。 
34. 選點新增。
35. 在描述欄位中，輸入「Party that owes an amount of money to the (ultimate) creditor.」。
36. 點選切換項目參考。
37. 在尋找欄位，輸入「Party」。
38. 下一步點選尋找。
39. 按一下確定。
40. 下一步點選尋找。
41. 按一下新增以開啟下拉式對話方塊。
42. 在名稱欄位，輸入「Description」。
43. 在項目類型欄位中，選取「字串」。
44. 選點新增。
45. 按一下新增以開啟下拉式對話方塊。
46. 在名稱欄位，輸入「Currency」。
47. 選點新增。
48. 在描述欄位中，輸入「Currency code」。
49. 按一下新增以開啟下拉式對話方塊。
50. 在名稱欄位，輸入「TransactionDate」。 
51. 在項目類型欄位中，選取「日期」。
52. 選點新增。
53. 在描述欄位中，輸入「Transaction date」。 
54. 按一下新增以開啟下拉式對話方塊。
55. 在名稱欄位，輸入「InstructedAmount」。  
56. 在項目類型欄位中，選取「實數」。
57. 選點新增。
58. 在描述欄位中，輸入「The amount of money to be moved between the debtor and creditor, before deduction of charges. The amount should be expressed in the currency as ordered by the initiating party.」。

    扣除費用之前，在債務人和債權人之間轉移的金額。 該金額應以發起方訂購的貨幣表示。  

59. 按一下新增以開啟下拉式對話方塊。
60. 在名稱欄位，輸入「End2EndID」。 
61. 在項目類型欄位中，選取「字串」。
62. 選點新增。
63. 在描述欄位中，輸入「The unique identification assigned by the initiating party. This identification is passed on, unchanged, throughout the entire end-to-end chain.」。 
64. 在名稱欄位，輸入「PaymentModel」。

    PaymentModel 名稱與付款表單的預定義介面一致。  

65. 點選儲存。
66. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
