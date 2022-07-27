---
title: ER 使用格式設定為付款產生電子文件
description: 本主題介紹如何使用新的電子報表 (ER) 格式設定來產生用於處理付款的電子文件。
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05295ff36ffd194b3f50fcdd9d7528c787c80f39104f46f9c51890a75a852735
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460258"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>ER 使用格式設定為付款產生電子文件

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何使用新的電子報表 (ER) 格式設定來產生用於處理付款的電子文件。 這些步驟可以在 GBSI 樣本公司中執行。

要完成這些步驟，您必須先完成「使用付款文件格式建立設定」程序中的步驟。


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>更改電子付款方式的設定
1. 進入應付帳款 > 付款安裝 > 付款方式。
2. 如果需要，切換檔案格式部分來展開它。
3. 使用快速篩選器尋找記錄。 例如，使用值為「電子」的付款方式欄位進行過濾。
4. 點選編輯。
5. 將一般電子報表欄位設定為是。
    * 選取是以使用常用電子報表模式產生付款檔案。  
6. 在名稱欄位中，點選下拉式按鈕開啟查詢。
7. 選取 BACS (UK fictitious) 格式設定。
8. 點選儲存。
9. 關閉頁面。

## <a name="test-the-format-of-generated-payment-files"></a>測試產生的付款檔案的格式
1. 進入應付帳款 > 付款 > 付款日記帳。
2. 點選新增。
3. 在清單中，標示選取的列。
4. 在名稱欄位中，點選下拉式按鈕開啟查詢。
5. 在清單中，點選所選資料列中的連結。
    * 選取 VendPay。  
6. 點選儲存。
7. 點選明細。
8. 在公司欄位中，輸入「DEMF」。
    * DEMF  
9. 在帳戶欄位中，指定值「DE-01001」。
    * DE-01001  
10. 在描述欄位中輸入「付款」。
    * 付款  
11. 在借方欄位中，輸入數字。
    * 1000  
12. 點選付款索引標籤。
13. 在付款方式欄位中，點選下拉式按鈕以打開查詢。
14. 在清單中，尋找並選取所需的記錄。
    * 選取電子值。  
15. 在清單中，點選所選資料列中的連結。
16. 點選儲存。
17. 點選產生付款。
18. 在付款方式欄位中，點選下拉式按鈕以打開查詢。
19. 在清單中，尋找並選取所需的記錄。
    * 選取電子值。  
20. 在清單中，點選所選資料列中的連結。
    * 選取電子值。  
21. 在檔案名稱欄位中，輸入一個值。
    * 例如，輸入「payments」。  
22. 在銀行帳戶欄位中，點選下拉式按鈕開啟查詢。
23. 在清單中，點選所選資料列中的連結。
    * 選取值 GBSI OPER。  
24. 點選確定。
25. 點選確定。
    * 以 XML 格式分析建立的付款檔案。 將其與設計的文件配置和定義的付款交易屬性進行比較。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]