---
title: 銀行擔保書交易
description: 本項程序詳盡解說銀行擔保書流程。
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 206050a2c60eaeff4776b534e3f366c6998f1756bf2734461fc10b9b83f4539a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450453"
---
# <a name="letter-of-guarantee-transaction"></a>銀行擔保書交易

[!include [banner](../../includes/banner.md)]

本項程序詳盡解說銀行擔保書流程。



完成這項程序之前須先完成下列任務：

- 設定銀行擔保書的銀行授信和過帳設定檔。

- 建立銀行擔保書的銀行授信協議。



此程序使用的是 USMF 示範公司。


## <a name="create-sales-order-with-letter-of-guarantee"></a>使用銀行擔保書建立銷售訂單
1. 前往 [應收帳款] > [訂單] > [所有銷售訂單]。
2. 點選新增。
3. 在客戶帳戶欄位中，輸入或選取一個值。
4. 展開一般專區。
5. 在網站欄位，輸入或選取一值。
6. 在清單中，點選已選取列的連結。
7. 在倉儲欄位，輸入或選取一值。
8. 在清單中，點選已選取列的連結。
9. 在銀行文件類型欄位，選取 '銀行擔保書'。
10. 點選確定。
11. 在商品號碼欄位中，輸入或選擇一個值。
12. 在 [單價] 欄位中，輸入一個數字。
13. 展開「行項細節」專區。
14. 點選交付索引標籤。
    * 注意：選取交付日期控制 = 無  
15. 在「要求的出貨日」欄位，輸入日期。
16. 在「確認的出貨日」欄位，輸入日期。

## <a name="process-letter-of-guarantee_request"></a>處理銀行擔保書申請。
1. 在動作窗格上，點選「管理」。
2. 點選銀行擔保書。
3. 在動作窗格上，點選銀行擔保書。
4. 點選申請，打開下拉式對話方塊。
5. 請在類型欄位中輸入或選取一值。
6. 在清單中，點選已選取列的連結。
7. 在值欄位中，輸入數字。
8. 在到期日欄位中，輸入日期和時間。
9. 點選確定。
10. 關閉頁面。

## <a name="process-letter-of-guarantee_submit-to-bank"></a>處理銀行擔保書並提交給銀行
1. 請前往現金和銀行管理 > 銀行擔保書 > 銀行擔保書。
2. 在清單中，尋找並選取所需的記錄。
3. 點選提交給銀行，打開下拉式對話方塊。
4. 在 [銀行帳戶] 欄位中，輸入或選擇一個值。
5. 在清單中，點選已選取列的連結。
6. 點選確定。

## <a name="process-letter-of-guarantee_receive-from-bank"></a>收到銀行的銀行擔保書與處理
1. 點選 [從銀行收取] 以打開下拉式對話方塊。
2. 在銀行編號欄位，輸入一值。
    * 驗證計算的保證金和費用欄位值。  
3. 點選確定。
4. 展開動作專區。
    * 驗證 '從銀行收取' 記錄。  
5. 按一下以開啟 [日記帳批次編號] 欄位中的連結。
6. 點選 [明細]。
    * 驗證日記帳分錄的過帳。  
7. 關閉頁面。

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>處理銀行擔保書及給予受益人
1. 前往 [應收帳款] > [訂單] > [所有銷售訂單]。
2. 在清單中，點選已選取列的連結。
3. 在動作窗格上，點選「管理」。
4. 點選銀行擔保書。
5. 在動作窗格上，點選銀行擔保書。
6. 點選給受益人，打開下拉式對話方塊。
7. 點選確定。
8. 請前往現金和銀行管理 > 銀行擔保書 > 銀行擔保書。
9. 在清單中，尋找並選取所需的記錄。
10. 點選給受益人，打開下拉式對話方塊。
11. 點選確定。
12. 展開動作專區。
    * 驗證 '給受益人' 記錄。  

## <a name="process-letter-of-guarantee_increase-value"></a>處理銀行擔保書並增加數值
1. 前往 [應收帳款] > [訂單] > [所有銷售訂單]。
2. 在清單中，點選已選取列的連結。
3. 在動作窗格上，點選「管理」。
4. 點選銀行擔保書。
5. 在動作窗格上，點選銀行擔保書。
6. 點選 [增加數值]，打開下拉式對話方塊。
7. 在預計新增值欄位，輸入數字。
8. 點選確定。
9. 請前往現金和銀行管理 > 銀行擔保書 > 銀行擔保書。
10. 在清單中，尋找並選取所需的記錄。
11. 點選 [增加數值]，打開下拉式對話方塊。
12. 點選確定。
13. 展開動作專區。
    * 驗證 '增加值' 記錄。  
14. 在清單中，尋找並選取所需的記錄。
15. 按一下以開啟 [日記帳批次編號] 欄位中的連結。
16. 點選 [明細]。
    * 驗證已過帳的日記帳分錄。  

## <a name="process-letter-of-guarantee_liquidate"></a>處理銀行擔保書和清算
1. 前往 [應收帳款] > [訂單] > [所有銷售訂單]。
2. 在清單中，點選已選取列的連結。
3. 在動作窗格上，點選「管理」。
4. 點選銀行擔保書。
5. 在動作窗格上，點選銀行擔保書。
6. 點選清算，打開下拉式對話方塊。
7. 點選確定。
8. 請前往現金和銀行管理 > 銀行擔保書 > 銀行擔保書。
9. 在清單中，尋找並選取所需的記錄。
10. 點選清算，打開下拉式對話方塊。
11. 點選確定。
12. 展開動作專區。
    * 驗證 '清算' 記錄。  
13. 在清單中，尋找並選取所需的記錄。
14. 按一下以開啟 [日記帳批次編號] 欄位中的連結。
15. 點選 [明細]。
    * 驗證已過帳的日記帳分錄。  
16. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]