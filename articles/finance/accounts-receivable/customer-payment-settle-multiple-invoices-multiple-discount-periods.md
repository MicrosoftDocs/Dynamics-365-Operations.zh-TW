---
title: 使用一次付款來結算跨多個折扣期間的發票
description: 本主題顯示當每張發票符合現金折扣條件時如何支付多張發票。 本文中的案例重點介紹現金折扣執行方式如何因付款時間不同而有所不同。
author: ShivamPandey-msft
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c86423c9e3453d8be11e6bdbc3484647e26e9eeec59c9a2e888cc5a2b2b5592
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450735"
---
# <a name="use-one-payment-to-settle-invoices-that-span-multiple-discount-periods"></a>使用一次付款來結算跨多個折扣期間的發票

[!include [banner](../includes/banner.md)]

本主題顯示當每張發票符合現金折扣條件時如何支付多張發票。 本文中的案例重點介紹現金折扣執行方式如何因付款時間不同而有所不同。

Fabrikam 向客戶 4032 銷售商品。 如果發票在 14 天內支付，Fabrikam 便會提供 1% 的現金折扣。 Fabrikam 也提供部分付款的現金折扣。 結算參數位於 **應收帳款參數** 頁面。

## <a name="invoices"></a>發票
客戶 4032 有三張發票，總金額為 3,000.00：

-   在 5 月 15 日輸入 1,000.00 的發票 FTI-10040。 如果在 14 天內付款，則此發票付款可享受 1% 的現金折扣。
-   在 6 月 25 日輸入 1,000.00 的發票 FTI-10041。 如果在 14 天內付款，則此發票付款可享受 1% 的現金折扣。
-   在 6 月 25 日輸入 1,000.00 的發票 FTI-10042。 如果在 5 天內付款，此發票可享受 2% 的現金折扣，如果在 14 天內付款，則可享受 1% 的折扣。

## <a name="settle-all-invoices-on-june-29"></a>在 6 月 29 日結算所有發票
如果 Arnie 建立付款日記帳以在 6 月 29 日完全結算這些發票，則付款為 2,970.00。 所有折扣金額的總和為 30.00。 Arnie 為客戶 4032 建立付款，然後打開 **結算交易** 頁面。 在 **結算交易** 頁面，Arnie 將所有三個發票行標記為結算：

-   發票 FTI-10040 的付款為 1,000.00。 沒有提取現金折扣。
-   發票 FTI-10041 的付款為 990.00。 提取 1% 或 10.00 的現金折扣。
-   發票 FTI-10042 的付款為 980.00。 提取 2% 或 20.00 的現金折扣。

| 標記                     | 使用現金折扣 | 憑單   | 客戶 | 日期      | 到期日  | 發票 | 以交易貨幣扣款的金額 | 以交易貨幣入帳的金額 | 貨幣 | 結算金額 |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| 已選取                 | 標準            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1,000.00                             |                                       | 美元      | 1,000.00         |
| 已選取                 | 標準            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1,000.00                             |                                       | 美元      | 990.00           |
| 選擇並反白顯示 | 標準            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1,000.00                             |                                       | 美元      | 980.00           |

過帳付款後，客戶餘額為 0.00。

## <a name="settle-all-invoices-on-july-1"></a>在 7 月 1 日結算所有發票
如果 Arnie 建立付款日記帳以在 7 月 1 日完全結算這些發票，則付款為 2,980.00。 Arnie 為客戶 4032 建立付款，然後打開 **結算交易** 頁面。 在 **結算交易** 頁面，Arnie 將所有三個發票行標記為結算：

-   發票 FTI-10040 的付款為 1,000.00。 沒有提取現金折扣。
-   發票 FTI-10041 的付款為 990.00。 提取 1% 或 10.00 的現金折扣。
-   發票 FTI-10042 的付款為 990.00。 提取 1% 或 10.00 的現金折扣。 儘管 7 月 1 日在符合 2% 折扣條件的期間之後，但仍處於符合 1% 折扣條件的期間。

| 標記                     | 使用現金折扣 | 憑單   | 客戶 | 日期      | 到期日  | 發票 | 以交易貨幣扣款的金額 | 以交易貨幣入帳的金額 | 貨幣 | 結算金額 |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| 已選取                 | 標準            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1,000.00                             |                                       | 美元      | 1,000.00         |
| 已選取                 | 標準            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1,000.00                             |                                       | 美元      | 990.00           |
| 選擇並反白顯示 | 標準            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1,000.00                             |                                       | 美元      | 990.00           |

## <a name="partial-settlement-on-june-29"></a>6 月 29 日部分結算
客戶 4032 可以支付部分金額，例如每張發票的一半。 Arnie 為客戶 4032 建立付款，然後打開 **結算交易** 頁面。 在 **結算交易** 頁面，Arnie 將所有三個發票行標記為結算。 在每一行，Arnie 根據客戶提供的說明輸入要結算的金額。 當 Arnie 選擇一行時，Arnie 會看到該行的折扣金額以及所採用的現金折扣金額。 因為客戶支付了一半的發票，Arnie 會看到 FTI-10042 的 **現金折扣金額** 欄位中的值為 **20.00**，但 **提取的現金折扣** 欄位中的值為 **10.00**。 付款金額為 1,485.00。

| 標記                     | 使用現金折扣 | 憑單   | 客戶 | 日期      | 到期日  | 發票 | 以交易貨幣扣款的金額 | 以交易貨幣入帳的金額 | 貨幣 | 結算金額 |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| 已選取                 | 標準            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1,000.00                             |                                       | 美元      | 500.00           |
| 已選取                 | 標準            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1,000.00                             |                                       | 美元      | 495.00           |
| 選擇並反白顯示 | 標準            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1,000.00                             |                                       | 美元      | 490.00           |

Arnie 也可以在打開 **結算交易** 頁面前手動輸入付款金額 1,485.00。 如果 Arnie 手動輸入付款金額，然後標記全部三筆交易，但不調整每筆交易的 **要結算的金額** 欄位中的值，則 Arnie 會在關閉頁面時收到以下訊息：

> 標記的交易記錄的總金額與日記帳金額不符。 是否變更日記帳金額?

如果 Arnie 希望付款金額僅為 1,485.00，則點選 **否** 然後過帳日記帳。 交易結算如下：

1.  發票 FTI-10040 已完全結算為 1,000.00，因為它是在 5 月 15 日輸入的，並且是最早的發票。 沒有提取現金折扣。 付款交易的剩餘金額為 485.00。
2.  發票 FTI-10041 根本沒有結算。 發票 FTI-10041 和 FTI-10042 是在同一日期輸入的。 但是，發票 FTI-10041 可享受 1% 的折扣，發票 FTI-10042 可享受 2% 的折扣。 因為發票 FTI-10042 可獲得更好的折扣，剩餘的 485.00 使用發票 FTI-10042 結算。
3.  發票 FTI-10042 使用剩餘的 485.00 結算。 Fabrikam 提供部分折扣。 在這種情況下，折扣為 9.90 (= 485.00 ÷ 0.98 × 0.02)。 金額 (485.00) 除以 0.98，因為有 2% 的折扣 (因此，客戶支付發票的 98%)。 然後將結果乘以折扣百分比或 2%。 485.00 的付款加上 9.90 的折扣等於 494.90。 原始發票金額為 1,000.00。 因此，交易的餘額為 505.10 (= 1,000.00 – 494.90)。

Arnie 可以在 **客戶交易** 頁面上檢視此資訊。

| 憑單    | 交易類型 | 日期      | 發票 | 以交易貨幣扣款的金額 | 以交易貨幣入帳的金額 | 餘額  | 貨幣 |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | 發票          | 5/15/2015 | 10040   | 1,000.00                             |                                       | 0.00     | 美元      |
| FTI-10041  | 發票          | 6/25/2015 | 10041   | 1,000.00                             |                                       | 1,000.00 | 美元      |
| FTI-10042  | 發票          | 6/25/2015 | 10042   | 1,000.00                             |                                       | 505.10   | 美元      |
| ARP-10040  | 付款          | 6/29/2015 |         |                                      | 1,485.00                              | 0.00     | 美元      |
| DISC-10040 | 現金折扣    | 6/29/2015 |         |                                      | 9.90                                  | 0.00     | 美元      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]