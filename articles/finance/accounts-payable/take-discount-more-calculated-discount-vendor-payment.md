---
title: 為廠商付款收取超過計算的折扣
description: 本文將引導您了解一個案例，現金折扣的金額大於發票上最初可用的折扣。 如果組織與廠商達成協議在發票上支付較少的金額，則可能會發生這種情況。
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52e18e75cfad34829dc78486d2b78b8e4211bb948bc5ddd0be85552bd914010b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450357"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a>為廠商付款收取超過計算的折扣

[!include [banner](../includes/banner.md)]

本文將引導您了解一個案例，現金折扣的金額大於發票上最初可用的折扣。 如果組織與廠商達成協議在發票上支付較少的金額，則可能會發生這種情況。 

如果發票在 7 天內支付，廠商 3051 便會提供 Fabrikam 4% 的現金折扣。 6 月 29 日，April 輸入發票金額為 1,000.00。 廠商讓 April 獲得 60.00 的折扣，而非可用於發票的預設折扣 40.00。 April 使用應付帳款付款日記帳記錄一次性付款。 她輸入廠商進行付款，然後開啟 **結算交易** 頁面。 她標記發票，並將 **現金折扣金額** 欄位中的值變更為 **60.00**。

| 標記     | 使用現金折扣 | 憑單   | 客戶 | 日期      | 到期日  | 發票 | 以交易貨幣計價的金額 | 貨幣 | 結算金額 |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| 已選取 | 標準            | Inv-10040 | 3051    | 6/29/2015 | 7/29/2015 | 10040   | 1,000.00                       | 美元      | 940.00           |

折扣資訊顯示在 **結算交易** 頁面底部。

| 欄位                        | 值     |
|------------------------------|-----------|
| 現金折扣日期           | 7/12/2015 |
| 現金折扣金額         | 60.00     |
| 使用現金折扣            | 標準    |
| 享有的現金折扣          | 0.00      |
| 現金折扣金額 | 60.00     |

April 過帳付款日記帳。 使用 940.00 的付款和 60.00 的折扣完全結算發票。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]