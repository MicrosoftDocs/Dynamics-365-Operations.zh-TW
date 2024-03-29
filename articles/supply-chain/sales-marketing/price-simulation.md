---
title: 價格模擬
description: 本文提供有關報價的價格模擬的資訊。 在您承諾特定價格之前，價格模擬可幫助您在報價過程中評估扣除對未來銷售價格的影響。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationPriceSimulation, SalesQuotationsTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12254
ms.assetid: 92be7c85-73cf-4f77-833c-d37ce779a031
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a14e485d1e02247159e1d9eb1c5d81be37626216
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449316"
---
# <a name="price-simulation"></a>價格模擬

[!include [banner](../includes/banner.md)]

本文提供有關報價的價格模擬的資訊。 在您承諾特定價格之前，價格模擬可幫助您在報價過程中評估扣除對未來銷售價格的影響。

根據建議的新價格，報價的價格模擬會顯示新的總金額。 價格模擬還可以顯示在現有報價中建立的特定行的新金額。 您可以輸入價格模擬，然後稍後應用。 或者，您可以使用沒有價格模擬的原始報價，並在您與客戶一起完成銷售流程時進行更多更改。  

價格模擬不會改變報價中的價格。 如果價格模擬應用於整個報價，則會將其視為報價標頭上的特殊折扣。 如果價格模擬應用於特定品項，則會將其視為報價行上的特殊折扣。 應用價格模擬時，建立的報價行上的單位銷售價格不會改變。 反而，會應用與報價行的降價相對應的折扣百分比。 應用價格模擬時，單位銷售價格和折扣百分比會轉移到報價行或報價行標頭。  

>[注意！] 當您執行價格模擬時，僅使用當前銷售貨幣來建立模擬。 但是，當您檢視報價總計時，您會看到公司貨幣和銷售貨幣的組合。  

新增到報價行的額外項目可能會觸發行折扣或多行折扣。 它們還可能觸發總折扣，其會改變報價行和整個折扣的邊際貢獻和貢獻率。  

您可以執行多個價格模擬來追蹤價格調整對報價目標的影響。 藉由執行這些模擬，您可以調整報價的整體價格，或報價中一個或多個特定行的價格，然後應用最有可能幫助您完成交易的價格模擬。  

建立報價時，您可以設定提醒。 以下是使用提醒的一些方式：

-   它們可以讓您隨時了解組織中報價的狀態。
-   它們可以觸發對特定報價的檢閱，或者在超過折扣限制時通知您。

## <a name="price-simulation-and-discounts"></a>價格模擬和折扣
為保證正確計算折扣和價格，在您對有折扣的報價執行價格模擬時要小心。 由於所有價格模擬都被視為有效報價行或整個報價的特殊折扣，因此您必須追蹤折扣中的差異。

### <a name="types-of-discounts-in-trade-agreements"></a>貿易合約中的折扣類型

Supply Chain Management 中的貿易合約可以有四種類型的價格折扣。 可以為不同的項目、客戶或價格群組設定這些折扣，並且可以按日期限制它們。 為避免計算錯誤，您必須在執行價格模擬時考慮貿易合約。 以下是貿易合約中的四種折扣：

-   **銷售價格**–可以為項目指定單獨的銷售價格。 建立報價行時，程式會搜尋項目的正確銷售價格並將其轉移到報價行。 因此，具有這種折扣的貿易合約不會影響價格模擬。 報價行中使用的銷售價格反映了貿易合約。
-   **行折扣**–根據訂購的數量為項目指定特別折扣。 在執行價格模擬之前，通常會通過行折扣減少行金額。 因此，具有這種折扣的貿易合約會影響價格模擬。
-   **多行折扣**–如果合併數量超過您定義的限制，預先定義的訂購項目組合會觸發整個訂單的折扣。 在執行價格模擬之前，通常會通過行折扣減少行金額。 因此，具有這種折扣的貿易合約會影響價格模擬。
-   **總折扣**–如果合併數量超過您定義的限制，預先定義的訂購項目會觸發整個訂單的折扣。 總折扣由報價行產生。 但是，由於總折扣作為折扣應用於報價總額，因此會減少報價的總金額。 因此，具有這種折扣的貿易合約會影響價格模擬。

### <a name="quotation-lines-and-trade-agreements"></a>報價行和貿易合約

當您建立或調整報價行時，會自動計算行折扣。 根據貿易合約找到該項目的相關銷售價格。

## <a name="price-simulation-examples"></a>價格模擬範例
以下範例對報價標頭和單行項目使用價格模擬。

### <a name="price-simulation-for-quotation-headers"></a>報價標頭的價格模擬

您建立一個包含以下行的報價：

-   10 單位品項 BR-12（每單位成本價：USD 9.52，每單位銷售價格：USD 15.32）
-   12 單位品項 BR-14（每單位成本價：USD 7.48，每單位銷售價格：USD 13.75）

下表顯示報價明細。

|    &nbsp;                  | 計算                          | 結果   |
|----------------------------|--------------------------------------|----------|
| 銷售數量             | 10 單位 + 12 單位                  | 22 單位 |
| 銷售值以美元計         | (10 × 15.32) + (12 × 13.75)          | 318.20   |
| 成本值以美元計          | (10 × 9.52) + (12 × 7.48)            | 184.96   |
| 邊際貢獻以美元計 | 318.20 – 184.96                      | 133.24   |
| 貢獻率         | (\[318.20 – 184.96\] ÷ 318.20) × 100 | 41.87%   |

您執行價格模擬並對整個報價或報價標頭應用 15% 的總折扣。 下表顯示價格模擬執行後的新報價總額。

|     &nbsp;                                           | 計算                               | 結果   |
|------------------------------------------------------|-------------------------------------------|----------|
| 銷售數量                                       | 10 單位 + 12 單位                       | 22 單位 |
| 舊銷售值以美元計                               | (10 × 15.32) + (12 × 13.75)               | 318.20   |
| 舊成本值以美元計                                | (10 × 9.52) + (12 × 7.48)                 | 184.96   |
| 舊邊際貢獻以美元計                       | 318.20 – 184.96                           | 133.24   |
| 舊貢獻率                               | (\[318.20 – (10 × 9.52)\] ÷ 318.20) × 100 | 41.87%   |
| 15% 總折扣的價格模擬以美元計 | (15 × 318.2) ÷ 100                        | 47.73    |
| 新銷售值以美元計                               | 318.20 – 47.73                            | 270.47   |
| 新邊際貢獻以美元計                       | 270.47 – 184.96                           | 85.51    |
| 新貢獻率                               | \[(270.47 – 184.96) ÷ 270.47\] × 100      | 31.61%   |

### <a name="price-simulation-for-single-line-items"></a>單行項目的價格模擬

您建立一個包含以下行的報價：

-   10 單位品項 BR-12（每單位成本價：USD 9.52，每單位銷售價格：USD 15.32）
-   12 單位品項 BR-14（每單位成本價：USD 7.48，每單位銷售價格：USD 13.75）

下表顯示報價明細。

|      &nbsp;                          | 計算                          | 結果   |
|--------------------------------------|--------------------------------------|----------|
| 銷售數量                       | 10 單位 + 12 單位                  | 22 單位 |
| BR-12 的美元銷售值         | 10 × 15.32                           | 153.20   |
| BR-14 的美元銷售值         | 12 × 13.75                           | 165.00   |
| BR-12 的美元成本值          | 10 × 9.52                            | 95.20    |
| BR-14 的美元成本值          | 12 × 7.48                            | 89.76    |
| BR-12 的美元邊際貢獻 | 153.20 – 95.20                       | 58.00    |
| BR-14 的美元邊際貢獻 | 165.00 – 89.76                       | 75.24    |
| BR-12 的美元貢獻率  | \[(153.20 – 95.20) ÷ 153.20\] × 100  | 37.86    |
| BR-14 的美元貢獻率  | \[(165.00 – 89.76) ÷ 165.00\] × 100  | 45.60    |
| 總銷售值以美元計             | (10 × 15.32) + (12 × 13.75)          | 318.20   |
| 總成本值以美元計              | (10 × 9.52) + (12 × 7.48)            | 184.96   |
| 總邊際貢獻以美元計     | 318.20 – 184.96                      | 133.24   |
| 總貢獻率             | \[(318.20 – 184.96) ÷ 318.20\] × 100 | 41.87%   |

您執行價格模擬並對 BR-12 單位應用 10% 的總折扣。 下表顯示對單行項目執行價格模擬後的新報價總額。

|    &nbsp;                                         | 計算                             | 結果   |
|---------------------------------------------------|-----------------------------------------|----------|
| 銷售數量                                    | 10 單位 + 12 單位                     | 22 單位 |
| BR-12 的美元舊銷售值                  | 10 × 15.32                              | 153.20   |
| 對 BR-12的10% 折扣的價格模擬 | (10 × 153.2) ÷ 100                      | 15.32    |
| BR-12 的美元新銷售值                  | (10 × 15.32) – 15.32                    | 137.88   |
| BR-14 的美元銷售值                      | 12 × 13.75                              | 165.00   |
| BR-12 的美元成本值                       | 10 × 9.52                               | 95.20    |
| BR-14 的美元成本值                       | 12 × 7.48                               | 89.76    |
| BR-12 的美元新邊際貢獻          | 137.88 – 95.20                          | 42.68    |
| BR-14 的美元邊際貢獻              | 165.00 – 89.76                          | 75.24    |
| BR-12 的美元新貢獻率           | \[(137.88 – 95.20) ÷ 137.88\] × 100     | 30.95    |
| BR-14 的美元貢獻率               | \[(165.00 – 89.76) ÷ 165.00\] × 100     | 45.60    |
| 新總銷售值以美元計                      | \[(10 × 15.32) – 15.32\] + (12 × 13.75) | 302.88   |
| 總成本值以美元計                           | (10 × 9.52) + (12 × 7.48)               | 184.96   |
| 新總邊際貢獻以美元計              | 302.88 – 184.96                         | 117.92   |
| 新總貢獻率                      | \[(302.88 – 184.96) ÷ 302.88\] × 100    | 38.93%   |

價格模擬僅影響應用它的行並減少該行的總數。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]