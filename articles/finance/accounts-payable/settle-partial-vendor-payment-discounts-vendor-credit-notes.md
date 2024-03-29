---
title: 結算其貸項通知單有折扣的部分廠商付款
description: 本文將引導您完成根據發票結算貸項通知單的案例。
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 553150a59d132bb1d8b563e03456995cbc8d2be5f36bab0c1fe6b8bbbf77dce1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450375"
---
# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-credit-notes"></a>結算其貸項通知單有折扣的部分廠商付款

[!include [banner](../includes/banner.md)]

本文將引導您完成根據發票結算貸項通知單的案例。

Fabrikam 的廠商對貸項通知單提供現金折扣。 如果在 14 天內支付發票款項，廠商 3050 便會提供 Fabrikam 1% 的現金折扣。

## <a name="invoice-and-credit-memo"></a>發票與貸項通知單
在 6 月 29 日，April 為廠商 3050 建立面額為 1,000.00 的發票。 7 月 2 日，她建立一張面額為 200.00 的貸項通知單。 在 **廠商** 頁面上，April 開啟 **結算交易** 頁面。 她可以使用 **結算交易** 頁面來標記貸項通知單和發票進行結算。 在貸項通知單上計算 2.00 的折扣。 因此，貸項通知單的總值減少到 198.00。

| 標記                     | 使用現金折扣 | 憑單   | 客戶 | 日期      | 到期日  | 發票 | 以交易貨幣計價的金額 | 貨幣 | 結算金額 |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| 已選取                 | 標準            | Inv-10070 | 3050    | 6/29/2015 | 7/29/2015 | 10070   | -1,000.00                      | 美元      | -990.00          |
| 選擇並反白顯示 | 標準            | CR-10070  | 3050    | 7/2/2015  | 7/29/2015 |         | 200.00                         | 美元      | 198.00           |

貸項通知單的折扣資訊會顯示在 **結算未結交易** 頁面底部。

| 欄位                        | 值     |
|------------------------------|-----------|
| 現金折扣日期           | 7/13/2015 |
| 現金折扣金額         | 2.00      |
| 使用現金折扣            | 標準    |
| 享有的現金折扣          | 0.00      |
| 現金折扣金額 | 2.00      |

April 按一下 **過帳**。 然後她檢閱完成的結算。 April 看到已套用面額為 198.00 的貸項通知單，並採用 2.00 的折扣。 因此，總計為 200.00。

| 標記                     | 使用現金折扣 | 憑單   | 客戶 | 日期      | 到期日  | 發票  | 以交易貨幣計價的金額 | 貨幣 | 結算金額 |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| 選擇並反白顯示 | 標準            | Inv-10070 | 3050    | 6/29/2015 | 7/29/2015 | 10070    | -1,000.00                      | 美元      | -200.00          |
| 已選取                 | 標準            | CR-10070  | 3050    | 7/2/2015  | 7/29/2015 | CR-10070 | 200.00                         | 美元      | 198.00           |

April 可以在 **廠商交易** 頁面上檢閱廠商交易，方法是在 **所有廠商** 頁面上選取廠商，然後在 \[動作\] 窗格上按一下 **交易**。 在此頁面上，April 看到發票的餘額為 -800.00。 她還看到 198.00 的貸項通知單與 2.00 的折扣。

| 憑單    | 交易類型 | 日期      | 發票 | 以交易貨幣扣款的金額 | 以交易貨幣入帳的金額 | 餘額 | 貨幣 |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | 發票          | 6/29/2015 | 10070   |                                      | 1,000.00                              | -800.00 | 美元      |
| Inv-10071  |                  | 7/2/2015  | CR10071 | 200.00                               |                                       | 0.00    | 美元      |
| DISC-10071 |  現金折扣   | 7/2/2015  |         | 2.00                                 |                                       | 0.00    | 美元      |
| DISC-10071 |  現金折扣   | 7/2/2015  |         |                                      | 2.00                                  | 0.00    | 美元      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]