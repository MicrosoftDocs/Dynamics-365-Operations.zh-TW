---
title: 合併公司的貨幣重估
description: 本主題介紹如何在合併公司中重估貨幣。
author: roschlom
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: roschlom
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4f2d4e1340e6ed986a1a079a7e88fea3bbe6e1d6af8aee99837adbfe03c39f1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450144"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a>合併公司的貨幣重估

[!include [banner](../includes/banner.md)]

當您將資料從一種記帳貨幣合併到另一種記帳貨幣時，如果匯率發生變化，您仍必須執行貨幣重估，以便正確重估帳戶餘額。 最初合併資料時，使用 **貨幣換算** 索引標籤以在合併過程中選擇要轉換的初始匯率。 輸入新匯率後（例如，下個月），您必須重新評估帳戶餘額。 然後根據新的匯率和日期相應地更新未實現收益或損失。 以下範例說明了在此過程中建立的會計分錄。

## <a name="company-setup"></a>公司設定
-   **來源/營運公司 (USMF)** – 美元 (USD) 用作會計和報表貨幣。
-   **合併的公司 (CON)** – 歐元 (EUR) 用作會計和報表貨幣。
    -   **已實現收益** – 分類帳科目 801500
    -   **已實現損失** – 分類帳科目 801600
    -   **未實現收益** – 分類帳科目 801600
    -   **未實現損失** – 分類帳科目 801400

## <a name="original-transactions"></a>原始交易
### <a name="cash-receipt-transactions-in-usmf"></a>USMF 中的現金收據交易

| 日期       | 分類帳科目               | 貨幣 | 金額 |
|------------|------------------------------|----------|--------|
| 10/11/2015 | 110110 - 現金                | 美元      | 500    |
| 10/11/2015 | 130100 – 應收帳款 | 美元      | -500   |

## <a name="exchange-rates"></a>匯率

| 開始貨幣 | 結束貨幣 | 開始日期 | 匯率 |
|---------------|-------------|------------|---------------|
| 歐元           | 美元         | 10/1/2015  | 200           |
| 歐元           | 美元         | 11/1/2015  | 150           |
| 歐元           | 美元         | 12/1/2012  | 100           |

## <a name="perform-the-consolidation-for-october-2015"></a>執行合併 (2015 年 10 月)
### <a name="balances-in-the-consolidation-company"></a>合併公司的餘額

| 分類帳科目 | 貨幣 | 金額 | 計算    |
|----------------|----------|--------|----------------|
| 110110         | 歐元      | 250    | 500 美元 × 50%  |
| 130100         | 歐元      | -250   | -500 美元 × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a>執行科目貨幣重估 (2015 年 10 月 1 日至 2015 年 11 月 30 日)
### <a name="balances-in-the-consolidation-company"></a>合併公司的餘額

| 分類帳科目 | 貨幣 | 金額  | 計算                        |
|----------------|----------|---------|------------------------------------|
| 110110         | 歐元      | 333.33  | 原始金額為 500 × 66.6667%  |
| 130100         | 歐元      | -333.33 | 原始金額為 -500 × 66.6667% |
| 801400         | 歐元      | 83.33   | 333.33 – 250                       |
| 801600         | 歐元      | -83.33  | -333.33 – (-250)                   |

您將看到報表貨幣金額的其他交易。

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a>執行科目貨幣重估 (2015 年 10 月 1 日至 2015 年 12 月 31 日)
### <a name="balances-in-the-consolidation-company"></a>合併公司的餘額

| 分類帳科目 | 貨幣 | 金額  | 計算                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | 歐元      | 500.00  | 原始金額為 500 × 1                           |
| 130100         | 歐元      | -500.00 | 原始金額為 -500 × 1                          |
| 801400         | 歐元      | 250     | 500 – 333.33 = 166.67 166.67 + 83.33 = 250           |
| 801600         | 歐元      | -250    | -500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]