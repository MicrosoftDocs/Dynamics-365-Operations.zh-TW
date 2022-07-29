---
title: 匯出信用證
description: 此項程序經歷匯出信用狀的流程。
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87bcf161e385b66ad725fc0fd915368ed3120a1573d780bebfb48ff73cce7847
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450687"
---
# <a name="export-letter-of-credit"></a>匯出信用證

[!include [banner](../../includes/banner.md)]

此項程序經歷匯出信用狀的流程。

信用狀是銀行簽發的協議，其中銀行確保代表買方保證付款，前提是符合買賣雙方之間的協議條款。



在此程序之前運行“設置銀行設施和過帳配置文件”程序和“信用證_創建銀行設施協議”程序。 必須選擇 USMF 演示公司才能成功運行此過程。




## <a name="create-sales-order-for-export-letter-of-credit"></a>為出口信用證創建銷售訂單
1. 前往 [應收帳款] > [訂單] > [所有銷售訂單]。
2. 點選新增。
3. 在 [客戶帳戶] 欄位中，按一下下拉式按鈕開啟查詢。
4. 在清單中，尋找並選取所需的記錄。
5. 在清單中，點選已選取列的連結。
6. 展開或摺疊 [一般] 區段。
7. 在站點欄位中，按一下下拉式按鈕開啟查詢。
    * 選擇存放要發出的項目的站點。  
8. 在清單中，點選已選取列的連結。
9. 在倉庫欄位中，按一下下拉式按鈕開啟查詢。
    * 選擇存放要發出的物料倉庫。  
10. 在清單中，點選已選取列的連結。
    * 注意：銀行文件類型欄位應選取「信用狀」值。  
11. 在銀行文件類型欄位，選取「信用狀」。
12. 展開或摺疊交貨區段。
    * 注意：選取交付日期控制 = 無。  
13. 在要求收件日期欄位，輸入日期。
14. 點選確定。
15. 在 [品項編號] 欄位中，按一下下拉式按鈕開啟查詢。
    * 選擇要發行/出售的所需項目。  
16. 在清單中，尋找並選取所需的記錄。
17. 在清單中，點選已選取列的連結。
18. 在 [單價] 欄位中，輸入一個數字。
19. 展開或摺疊 [行詳細資料] 區段。
20. 點選交付索引標籤。
21. 在「要求的出貨日」欄位，輸入日期。
22. 在「確認的出貨日」欄位，輸入日期。
23. 在動作窗格上，點選「管理」。
24. 點擊信用狀。
25. 在銀行文件編號欄位，輸入一值。
26. 在到期日欄位中，輸入日期和時間。
27. 展開或摺疊銀行詳細資料區段。
28. 按一下欄位中的下拉式按鈕以開啟查詢。
29. 在清單中，點選已選取列的連結。
30. 按一下廣告銀行欄位中的下拉式按鈕以開啟查詢。
31. 在清單中，尋找並選取所需的記錄。
32. 在清單中，點選已選取列的連結。
33. 點選擷取銷售訂單出貨。
34. 點擊簽發銀行單據。
35. 關閉頁面。

## <a name="post-packing-slip"></a>過帳裝箱單據
1. 在動作窗格上按一下揀貨並裝箱。
2. 按一下過帳裝箱單。
3. 展開或摺疊參數區段。
4. 在數量欄位中，選取 [全部]。
5. 展開或摺疊 [設定] 區段。
6. 在裝箱單日期欄位，輸入日期。
7. 選擇裝運編號。
8. 在清單中，點選已選取列的連結。
9. 點選確定。
10. 點選確定。

## <a name="post-sales-invoice"></a>過帳銷售發票
1. 在動作窗格上點選發票。
2. 點選發票。
3. 展開或摺疊概覽區段。
4. 選擇裝運編號。
5. 在清單中，點選已選取列的連結。
6. 展開或摺疊 [設定] 區段。
7. 在發票日期欄位，輸入日期。
8. 點選確定。
9. 點選確定。

## <a name="shipment-document-submitted-status"></a>裝運文件提交狀態
1. 在動作窗格上，點選「管理」。
2. 點擊信用狀。
3. 展開或摺疊行區段。
    * 注意：「提交的文件」欄位應設定為「是」。  

## <a name="verify-export-letter-of-credit"></a>驗證出口信用證
1. 前往現金和銀行管理 > 信用狀 > 出口信用狀和進口託收。
2. 在清單中，尋找並選取所需的記錄。
3. 在清單中，點選已選取列的連結。
    * 驗證出口信用證的裝運狀態是否為「已開票」。  

## <a name="customer-payment"></a>客戶付款
1. 前往 [應收帳款] > [付款] > [付款日記帳]。
2. 點選新增。
3. 在清單中，標示選取的列。
4. 在名稱欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，點選已選取列的連結。
6. 點選行項。
7. 在日期欄位輸入日期。
8. 在 [科目] 欄位中，指定所需值。
9. 點擊結算。
10. 選擇總計標題上的複選方塊。
    * 注意：將顯示字段設置為「信用狀」。  
11. 在清單中，尋找並選取所需的記錄。
12. 選取或清除核取方塊。
13. 點選確定。
14. 點選付款索引標籤。
    * 驗證銀行文件編號和發貨編號詳細資訊  
15. 點選過帳。

## <a name="verify-export-letter-of-credit-after-payment"></a>付款後驗證出口信用證
1. 前往現金和銀行管理 > 信用狀 > 出口信用狀和進口託收。
2. 在清單中，尋找並選取所需的記錄。
3. 在清單中，點選已選取列的連結。
    * 驗證發貨狀態 = 已收到付款且餘額 = 0.00。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]