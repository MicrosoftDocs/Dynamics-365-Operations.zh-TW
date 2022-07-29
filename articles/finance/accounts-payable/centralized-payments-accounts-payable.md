---
title: 應付帳款的集中付款
description: 包含多個法律實體的組織可以透過使用處理所有付款的單個法律實體來建立和管理付款。 因此，不必在多個法律實體中輸入相同的付款。 本主題提供的範例說明如何在各種環境中處理集中付款的過帳。
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df0d2178d1ebd3dcb154e2c4f7821a4007da55d4
ms.sourcegitcommit: 5033d42a2aac852916d726e40bd98a164d1a837d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2022
ms.locfileid: "8451629"
---
# <a name="centralized-payments-for-accounts-payable"></a>應付帳款的集中付款

[!include [banner](../includes/banner.md)]

包含多個法律實體的組織可以透過使用處理所有付款的單個法律實體來建立和管理付款。 因此，不必在多個法律實體中輸入相同的付款。 本主題提供的範例說明如何在各種環境中處理集中付款的過帳。

在集中付款組織中，有許多營業的法律實體，每個營業的法律實體都管理自己的廠商發票。 所有營業的法律實體的付款都是從稱作付款的法律實體的單個法律實體中產生的。 在結算過程中，會產生適用的應付和應收交易。 您可以指定組織中的哪個法律實體接收已實現收益或已實現損失交易，以及如何處理與跨公司付款相關的現金折扣交易。 在集中支付日記帳行上，**帳戶類型** 應設定為「廠商」。 **沖銷帳戶類型** 應設定為「銀行」或「分類帳」。 銀行帳戶應在目前公司中。 

以下範例說明如何在各種情況下處理過帳。 假設這些範例都採用以下設定：

-   法律實體是 Fabrikam、Fabrikam East 和 Fabrikam West。 從 Fabrikam 進行付款。
-   **公司間會計** 頁面上的 **過帳現金折扣** 欄位設定為 **發票法律實體**。
-   **公司間會計** 頁面上的 **過帳貨幣匯率損益** 欄位設定為 **發票法律實體**。
-   廠商 Fourth Coffee 在每個法律實體中設定為廠商。 來自不同法律實體的廠商被標識為同一廠商，因為他們共用相同的全球通訊錄識別碼。

| 目錄識別碼 | 廠商帳戶 | 姓名          | 法律實體  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Fourth Coffee | Fabrikam      |
| 1050         | 100            | Fourth Coffee | Fabrikam East |
| 1050         | 3004           | Fourth Coffee | Fabrikam West |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>範例 1：來自其他法律實體發票的廠商付款
Fabrikam East 有廠商帳戶 100 (Fourth Coffee) 的未結發票。 Fabrikam 輸入付款並將付款過帳到 Fabrikam 廠商帳戶 3004 (Fourth Coffee)。 使用未結發票結算付款。

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>在 Fabrikam East 中為廠商 100 過帳到發票

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 費用 (Fabrikam East)          | 600.00       |               |
| 應付帳款 (Fabrikam East) |              | 600.00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>在 Fabrikam 中為廠商 3004 產生並過帳付款

| 客戶                     | 借方金額 | 貸方金額 |
|-----------------------------|--------------|---------------|
| 應付帳款 (Fabrikam) | 600.00       |               |
| 現金 (Fabrikam)             |              | 600.00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 付款使用 Fabrikam East 發票結算

**Fabrikam 過帳**

| 客戶                           | 借方金額 | 貸方金額 |
|-----------------------------------|--------------|---------------|
| 從 Fabrikam East (Fabrikam) 的應收金額 | 600.00       |               |
| 應付帳款 (Fabrikam)       |              | 600.00        |

**Fabrikam East 過帳**

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 應付帳款 (Fabrikam East) | 600.00       |               |
| 向 Fabrikam (Fabrikam East) 的應付金額  |              | 600.00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>範例 2：來自具有現金折扣的其他法律實體發票的廠商付款
Fabrikam East 有廠商 100 (Fourth Coffee) 的未結發票。 發票有 20.00 現金折扣可用。 Fabrikam 為 Fabrikam 廠商 3004 (Fourth Coffee) 輸入並過帳 580.00 的付款。 付款使用未結 Fabrikam East 發票結算。 現金折扣過帳到發票的法律實體 Fabrikam East。

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>在 Fabrikam East 中為 Fabrikam East 廠商 100 過帳到發票

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 費用 (Fabrikam East)          | 600.00       |               |
| 應付帳款 (Fabrikam East) |              | 600.00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>在 Fabrikam 中為 Fabrikam 廠商 3004 產生並過帳付款

| 客戶                     | 借方金額 | 貸方金額 |
|-----------------------------|--------------|---------------|
| 應付帳款 (Fabrikam) | 580.00       |               |
| 現金 (Fabrikam)             |              | 580.00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 付款使用 Fabrikam East 發票結算

**Fabrikam 過帳**

| 客戶                           | 借方金額 | 貸方金額 |
|-----------------------------------|--------------|---------------|
| 從 Fabrikam East (Fabrikam) 的應收金額 | 580.00       |               |
| 應付帳款 (Fabrikam)       |              | 580.00        |

**Fabrikam East 過帳**

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 應付帳款 (Fabrikam East) | 580.00       |               |
| 向 Fabrikam (Fabrikam East) 的應付金額  |              | 580.00        |
| 應付帳款 (Fabrikam East) | 20.00        |               |
| 現金折扣 (Fabrikam East)    |              | 20.00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>範例 3：來自具有已實現匯損的其他法律實體發票的廠商付款
Fabrikam East 有廠商 100 (Fourth Coffee) 的未結發票。 Fabrikam 輸入並過帳 Fabrikam 廠商 3004 (Fourth Coffee) 的付款。 付款使用未結 Fabrikam East 發票結算。 結算過程中將產生匯率損失交易。

-   在發票日期的歐元 (EUR) 對美元 (USD) 的匯率：1.2062
-   在付款日期的歐元兌美元匯率：1.2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>在 Fabrikam East 中為 Fabrikam East 廠商 100 過帳到發票

| 客戶                          | 借方金額            | 貸方金額           |
|----------------------------------|-------------------------|-------------------------|
| 費用 (Fabrikam East)          | 600.00 EUR / 723.72 USD |                         |
| 應付帳款 (Fabrikam East) |                         | 600.00 EUR / 723.72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>在 Fabrikam 中為 Fabrikam 廠商 3004 產生並過帳付款

| 客戶                     | 借方金額            | 貸方金額           |
|-----------------------------|-------------------------|-------------------------|
| 應付帳款 (Fabrikam) | 600.00 EUR / 736.62 USD |                         |
| 現金 (Fabrikam)             |                         | 600.00 EUR / 736.62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 付款使用 Fabrikam East 發票結算

**Fabrikam 過帳**

| 客戶                           | 借方金額            | 貸方金額           |
|-----------------------------------|-------------------------|-------------------------|
| 從 Fabrikam East (Fabrikam) 的應收金額 | 600.00 EUR / 736.62 USD |                         |
| 應付帳款 (Fabrikam)       |                         | 600.00 EUR / 736.62 USD |
| 已實現損失 (Fabrikam)          | 0.00 EUR / 12.90 USD    |                         |
| 從 Fabrikam East (Fabrikam) 的應收金額 |                         | 0.00 EUR / 12.90 USD    |

**Fabrikam East 過帳**

| 客戶                          | 借方金額            | 貸方金額           |
|----------------------------------|-------------------------|-------------------------|
| 應付帳款 (Fabrikam East) | 600.00 EUR / 736.62 USD |                         |
| 向 Fabrikam (Fabrikam East) 的應付金額  |                         | 600.00 EUR / 736.62 USD |
| 向 Fabrikam (Fabrikam East) 的應付金額  | 0.00 EUR / 12.90 USD    |                         |
| 應付帳款 (Fabrikam East) |                         | 0.00 EUR / 12.90 USD    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>範例 4：來自具有現金折扣和已有匯率損失的其他法律實體發票的廠商付款
Fabrikam East 有廠商 100 (Fourth Coffee) 的未結發票。 發票有可用的現金折扣，並產生銷售稅交易。 Fabrikam 過帳 Fabrikam 廠商 3004 (Fourth Coffee) 的付款。 付款使用未結 Fabrikam East 發票結算。 結算過程中將產生匯率損失交易。 現金折扣過帳到發票的法律實體 (Fabrikam East)，且貨幣匯率損失過帳到付款的法律實體 (Fabrikam)。

-   在發票日期的歐元兌美元匯率：1.2062
-   在付款日期的歐元兌美元匯率：1.2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>過帳發票並在 Fabrikam East 中為廠商 100 產生稅務交易記錄

| 客戶                          | 借方金額            | 貸方金額           |
|----------------------------------|-------------------------|-------------------------|
| 費用 (Fabrikam East)          | 564.07 EUR / 680.38 USD |                         |
| 銷售稅 (Fabrikam East)        | 35.93 EUR / 43.34 USD   |                         |
| 應付帳款 (Fabrikam East) |                         | 600.00 EUR / 723.72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>在 Fabrikam 中為廠商 3004 產生並過帳付款

| 客戶                     | 借方金額            | 貸方金額           |
|-----------------------------|-------------------------|-------------------------|
| 應付帳款 (Fabrikam) | 588.72 EUR / 722.77 USD |                         |
| 現金 (Fabrikam East)        |                         | 588.72 EUR / 722.77 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 付款使用 Fabrikam East 發票結算

**Fabrikam 過帳**

| 客戶                           | 借方金額            | 貸方金額           |
|-----------------------------------|-------------------------|-------------------------|
| 從 Fabrikam East (Fabrikam) 的應收金額 | 588.72 EUR / 722.77 USD |                         |
| 應付帳款 (Fabrikam)       |                         | 588.72 EUR / 722.77 USD |
| 已實現損失 (Fabrikam)          | 0.00 EUR / 12.66 USD    |                         |
| 從 Fabrikam East (Fabrikam) 的應收金額 |                         | 0.00 EUR / 12.66 USD    |

**Fabrikam East 過帳**

| 客戶                          | 借方金額            | 貸方金額           |
|----------------------------------|-------------------------|-------------------------|
| 應付帳款 (Fabrikam East) | 588.72 EUR / 722.77 USD |                         |
| 向 Fabrikam (Fabrikam East) 的應付金額  |                         | 588.72 EUR / 722.77 USD |
| 向 Fabrikam (Fabrikam East) 的應付金額   | 0.00 EUR / 12.66 USD    |                         |
| 應付帳款 (Fabrikam East) |                         | 0.00 EUR / 12.66 USD    |
| 應付帳款 (Fabrikam East) | 11.28 EUR / 13.61 USD   |                         |
| 現金折扣 (Fabrikam East)    |                         | 11.28 EUR / 13.61 USD   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>範例 5：具有主要付款的廠商貸方通知單
Fabrikam 為廠商 3004 (Fourth Coffee) 產生 75.00 的付款。 使用 Fabrikam West 廠商 3004 的未結發票和 Fabrikam East 廠商 100 的未結貸方通知單結算付款。 該付款在 **結算交易** 頁面中選擇為主要付款。

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>發票為廠商 3004 過帳到 Fabrikam West

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 費用 (Fabrikam West)          | 100.00       |               |
| 應付帳款 (Fabrikam West) |              | 100.00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>貸方通知單為廠商 100 過帳到 Fabrikam East

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 應付帳款 (Fabrikam East) | 25.00        |               |
| 採購退貨 (Fabrikam East) |              | 25.00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>付款為廠商 3004 過帳到 Fabrikam

| 客戶                     | 借方金額 | 貸方金額 |
|-----------------------------|--------------|---------------|
| 應付帳款 (Fabrikam) | 75.00        |               |
| 現金 (Fabrikam)             |              | 75.00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam 付款使用 Fabrikam West 發票和 Fabrikam East 貸方通知單結算

**Fabrikam 過帳**

| 客戶                           | 借方金額 | 貸方金額 |
|-----------------------------------|--------------|---------------|
| 應付帳款 (Fabrikam)       | 25.00        |               |
| 向 Fabrikam (Fabrikam) 的應付金額   |              | 25.00         |
| 從 Fabrikam West (Fabrikam) 的應收金額 | 100.00       |               |
| 應付帳款 (Fabrikam)       |              | 100.00        |

**Fabrikam East 過帳**

| 客戶                           | 借方金額 | 貸方金額 |
|-----------------------------------|--------------|---------------|
| 從 Fabrikam (Fabrikam East) 的應收金額 | 25.00        |               |
| 應付帳款 (Fabrikam East)  |              | 25.00         |

**Fabrikam West 過帳**

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 應付帳款 (Fabrikam West) | 100.00       |               |
| 向 Fabrikam (Fabrikam West) 的應付金額  |              | 100.00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>範例 6：不具有主要付款的廠商貸方通知單
Fabrikam 為廠商 3004 (Fourth Coffee) 產生 75.00 的付款。 使用 Fabrikam West 廠商 3004 的未結發票和 Fabrikam East 廠商 100 的未結貸方通知單結算付款。 該付款在 **結算交易** 頁面中不選擇為主要付款。

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>發票為廠商 3004 過帳到 Fabrikam West

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 費用 (Fabrikam West)          | 100.00       |               |
| 應付帳款 (Fabrikam West) |              | 100.00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>貸方通知單為廠商 100 過帳到 Fabrikam East

| 客戶                          | 借方金額 | 貸方金額 |
|----------------------------------|--------------|---------------|
| 應付帳款 (Fabrikam East) | 25.00        |               |
| 採購退貨 (Fabrikam East) |              | 25.00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>付款為廠商 3004 過帳到 Fabrikam

| 客戶                     | 借方金額 | 貸方金額 |
|-----------------------------|--------------|---------------|
| 應付帳款 (Fabrikam) | 75.00        |               |
| 現金 (Fabrikam)             |              | 75.00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam 付款使用 Fabrikam West 發票和 Fabrikam East 貸方通知單結算

**Fabrikam 過帳**

| 客戶                           | 借方金額 | 貸方金額 |
|-----------------------------------|--------------|---------------|
| 從 Fabrikam West (Fabrikam) 的應收金額 | 75.00        |               |
| 應付帳款 (Fabrikam)       |              | 75.00         |

**Fabrikam East 過帳**

| 客戶                                | 借方金額 | 貸方金額 |
|----------------------------------------|--------------|---------------|
| 從 Fabrikam West (Fabrikam East) 的應收金額 | 25.00        |               |
| 應付帳款 (Fabrikam East)       |              | 25.00         |

**Fabrikam West 過帳**

| 客戶                              | 借方金額 | 貸方金額 |
|--------------------------------------|--------------|---------------|
| 應付帳款 (Fabrikam West)     | 75.00        |               |
| 向 Fabrikam (Fabrikam West) 的應付金額      |              | 75.00         |
| 應付帳款 (Fabrikam West)     | 25.00        |               |
| 向 Fabrikam East (Fabrikam West) 的應付金額 |              | 25.00         |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
