---
title: 應收帳款的集中付款
description: 包含多個法律實體的組織可以透過使用處理所有付款的單個法律實體來建立和管理付款。 因此，不必在多個法律實體中輸入相同的交易。 本文提供的範例說明如何在各種環境中處理集中付款的過帳。
author: ShivamPandey-msft
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5dfa3965cc22c0c3bcf31ae076afb586e12d158ef66464ce933b509aaf9a521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450237"
---
# <a name="centralized-payments-for-accounts-receivable"></a>應收帳款的集中付款

[!include [banner](../includes/banner.md)]

包含多個法律實體的組織可以透過使用處理所有付款的單個法律實體來建立和管理付款。 因此，不必在多個法律實體中輸入相同的交易。 本文提供的範例說明如何在各種環境中處理集中付款的過帳。

包含多個法律實體的組織可以透過使用處理所有付款的法律實體來建立和管理付款。 因此，不必在多個法律實體中輸入相同的交易。 此外，該組織還節省了時間，因為針對集中付款、付款方案、結算以及編輯未結和已結交易的流程都得到了簡化。 

在集中付款組織中，有許多營業的法律實體，每個營業的法律實體都管理自己的發票應收資訊。 所有營業的法律實體的付款都是從稱作付款的法律實體的單個法律實體接收的。 在結算過程中，會產生適用的應付和應收交易。 您可以指定組織中的哪個法律實體接收已實現收益或已實現損失交易，以及如何處理與集中式付款相關的現金折扣交易。 在集中支付日記帳行上，**帳戶類型** 應設定為「客戶」。 **沖銷帳戶類型** 應設定為「銀行」或「分類帳」。 銀行帳戶應在目前公司中。 

以下範例說明如何在各種情況下處理過帳。 假設這些範例都採用以下設定：

-   法律實體是 Fabrikam、Fabrikam East 和 Fabrikam West。 客戶付款輸入 Fabrikam。
-   **公司間會計** 頁面上的 **過帳現金折扣** 欄位設定為 **發票法律實體**。
-   **公司間會計** 頁面上的 **過帳貨幣匯率損益** 欄位設定為 **發票法律實體**。
-   客戶 Northwind Traders 在每個法律實體中設定為客戶。 來自不同法律實體的客戶被標識為同一客戶，因為他們共用相同的全球通訊錄識別碼。

| 通訊錄識別碼 | 客戶帳戶 | 姓名              | 法律實體  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4000             | Northwind Traders | Fabrikam      |
| 4050            | 4000             | Northwind Traders | Fabrikam East |
| 4050            | 10000            | Northwind Traders | Fabrikam West |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>範例 1：來自其他法律實體發票的客戶付款
Fabrikam 收到 Fabrikam 客戶帳戶 4000 (Northwind Traders) 的 600.00 付款。 使用 Fabrikam East 中客戶帳戶 4000 的未結發票結算付款。

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>在 Fabrikam East 中為客戶 4000 過帳到發票

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam East) | 600.00       |               |
| 銷售 (Fabrikam East)               |              | 600.00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>在 Fabrikam 中接收並過帳客戶 4000 的付款

| 客戶                        | 借方金額 | 貸方金額 |
|--------------------------------|--------------|---------------|
| 現金 (Fabrikam)                | 600.00       |               |
| 應收帳款 (Fabrikam) |              | 600.00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 付款使用 Fabrikam East 發票結算

**Fabrikam 過帳**

| 客戶                         | 借方金額 | 貸方金額 |
|---------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam)  | 600.00       |               |
| 向 Fabrikam (Fabrikam) 的應付金額 |              | 600.00        |

**Fabrikam East 過帳**

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 從 Fabrikam (Fabrikam East) 的應收金額   | 600.00       |               |
| 應收帳款 (Fabrikam East) |              | 600.00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>範例 2：來自具有現金折扣的其他法律實體發票的客戶付款
Fabrikam 收到 Fabrikam 客戶 4000 (Northwind Traders) 的 580.00 付款。 Fabrikam East 有客戶 4000 的未結發票。 發票有 20.00 現金折扣可用。 付款使用未結 Fabrikam East 發票結算。 現金折扣過帳到發票的法律實體 Fabrikam East。

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>在 Fabrikam East 中為 Fabrikam East 客戶 4000 過帳發票

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam East) | 580.00       |               |
| 銷售 (Fabrikam East)               |              | 580.00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>在 Fabrikam 中接收並過帳 Fabrikam 客戶 4000 的付款

| 客戶                        | 借方金額 | 貸方金額 |
|--------------------------------|--------------|---------------|
| 現金 (Fabrikam)                | 600.00       |               |
| 應收帳款 (Fabrikam) |              | 600.00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 付款使用 Fabrikam East 發票結算

**Fabrikam 過帳**

| 客戶                         | 借方金額 | 貸方金額 |
|---------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam)  | 580.00       |               |
| 向 Fabrikam (Fabrikam) 的應付金額 |              | 580.00        |

**Fabrikam East 過帳**

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 從 Fabrikam (Fabrikam East) 的應收金額   | 580.00       |               |
| 應收帳款 (Fabrikam East) |              | 580.00        |
| 現金折扣 (Fabrikam East)       | 20.00        |               |
| 應收帳款 (Fabrikam East) |              | 20.00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>範例 3：來自具有已實現匯率收益的其他法律實體發票的客戶付款
Fabrikam 收到 Fabrikam 客戶 4000 (Northwind Traders) 的 600.00 歐元 (EUR) 的付款。 使用 Fabrikam East 中客戶 4000 的未結發票結算付款。 結算過程中將產生匯率收益交易。

-   在發票日期的歐元 (EUR) 對美元 (USD) 的匯率：1.2062
-   在付款日期的歐元兌美元匯率：1.2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>在 Fabrikam East 中為 Fabrikam East 客戶 4000 過帳發票

| 客戶                             | 借方金額            | 貸方金額           |
|-------------------------------------|-------------------------|-------------------------|
| 應收帳款 (Fabrikam East) | 600.00 EUR / 723.72 USD |                         |
| 銷售 (Fabrikam East)               |                         | 600.00 EUR / 723.72 USD |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>在 Fabrikam 中接收並過帳 Fabrikam 客戶 4000 的付款

| 客戶                        | 借方金額            | 貸方金額           |
|--------------------------------|-------------------------|-------------------------|
| 現金 (Fabrikam)                | 600.00 EUR / 736.62 USD |                         |
| 應收帳款 (Fabrikam) |                         | 600.00 EUR / 736.62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 付款使用 Fabrikam East 發票結算

**Fabrikam 過帳**

| 客戶                         | 借方金額            | 貸方金額           |
|---------------------------------|-------------------------|-------------------------|
| 應收帳款 (Fabrikam)  | 600.00 EUR / 736.62 USD |                         |
| 向 Fabrikam (Fabrikam) 的應付金額 |                         | 600.00 EUR / 736.62 USD |
| 向 Fabrikam (Fabrikam) 的應付金額 | 0.00 EUR / 12.90 USD    |                         |
| 已實現收益 (Fabrikam)        |                         | 0.00 EUR / 12.90 USD    |

**Fabrikam East 過帳**

| 客戶                             | 借方金額            | 貸方金額           |
|-------------------------------------|-------------------------|-------------------------|
| 從 Fabrikam (Fabrikam East) 的應收金額   | 600.00 EUR / 736.62 USD |                         |
| 應收帳款 (Fabrikam East) |                         | 600.00 EUR / 736.62 USD |
| 應收帳款 (Fabrikam East) | 0.00 EUR / 12.90 USD    |                         |
| 從 Fabrikam (Fabrikam East) 的應收金額   |                         | 0.00 EUR / 12.90 USD    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>範例 4：來自具有現金折扣和已有匯率收益的其他法律實體發票的客戶付款
Fabrikam 為 Fabrikam 客戶 4000 (Northwind Traders) 過帳支付 Fabrikam East 的未結發票。 發票有可用的現金折扣，並產生銷售稅交易。 付款使用未結 Fabrikam East 發票結算。 結算過程中將產生匯率收益交易。 現金折扣過帳到發票的法律實體 (Fabrikam East)，且貨幣匯率收益過帳到付款的法律實體 (Fabrikam)。

-   在發票日期的歐元兌美元匯率：1.2062
-   在付款日期的歐元兌美元匯率：1.2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>過帳普通發票，並在 Fabrikam East 中為客戶 4000 產生稅務交易記錄

| 客戶                             | 借方金額            | 貸方金額           |
|-------------------------------------|-------------------------|-------------------------|
| 應收帳款 (Fabrikam East) | 638.22 EUR / 769.82 USD |                         |
| 銷售 (Fabrikam East)               |                         | 600.00 EUR / 723.72 USD |
| 銷售稅 (Fabrikam East)           |                         | 38.22 EUR / 46.10 USD   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>在 Fabrikam 中接收並過帳客戶 4000 的付款

| 客戶                        | 借方金額            | 貸方金額           |
|--------------------------------|-------------------------|-------------------------|
| 現金 (Fabrikam)                | 626.22 EUR / 768.81 USD |                         |
| 應收帳款 (Fabrikam) |                         | 626.22 EUR / 768.81 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 付款使用 Fabrikam East 發票結算

**Fabrikam 過帳**

| 客戶                         | 借方金額            | 貸方金額           |
|---------------------------------|-------------------------|-------------------------|
| 應收帳款 (Fabrikam)  | 626.22 EUR / 768.81 USD |                         |
| 向 Fabrikam (Fabrikam) 的應付金額 |                         | 626.22 EUR / 768.81 USD |
| 向 Fabrikam (Fabrikam) 的應付金額 | 0.00 EUR / 13.46 USD    |                         |
| 已實現收益 (Fabrikam)        |                         | 0.00 EUR / 13.46 USD    |

**Fabrikam East 過帳**

| 客戶                             | 借方金額            | 貸方金額           |
|-------------------------------------|-------------------------|-------------------------|
| 從 Fabrikam (Fabrikam East) 的應收金額   | 626.22 EUR / 768.81 USD |                         |
| 應收帳款 (Fabrikam East) |                         | 626.22 EUR / 768.81 USD |
| 應收帳款 (Fabrikam East)  | 0.00 EUR / 13.46 USD    |                         |
| 從 Fabrikam (Fabrikam East) 的應收金額   |                         | 0.00 EUR / 13.46 USD    |
| 現金折扣 (Fabrikam East)       | 12.00 EUR / 14.47 USD   |                         |
| 應收帳款 (Fabrikam East) |                         | 12.00 EUR / 14.47 USD   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>範例 5：具有主要付款的客戶貸方通知單
Fabrikam 從客戶 4000 (Northwind Traders) 收到 75.00 付款。 使用 Fabrikam West 客戶 10000 的未結發票和 Fabrikam East 客戶 4000 的未結貸方通知單結算付款。 該付款在 **結算交易** 頁面中選擇為主要付款。

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>發票為客戶 10000 過帳到 Fabrikam West

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam West) | 100.00       |               |
| 銷售 (Fabrikam West)               |              | 100.00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>貸方通知單為客戶 4000 過帳到 Fabrikam East

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 銷售退貨 (Fabrikam East)       | 25.00        |               |
| 應收帳款 (Fabrikam East) |              | 25.00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>客戶 4000 的付款已過帳到 Fabrikam

| 客戶                        | 借方金額 | 貸方金額 |
|--------------------------------|--------------|---------------|
| 現金 (Fabrikam)                | 75.00        |               |
| 應收帳款 (Fabrikam) |              | 75.00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam 付款使用 Fabrikam West 發票和 Fabrikam East 貸方通知單結算

**Fabrikam 過帳**

| 客戶                           | 借方金額 | 貸方金額 |
|-----------------------------------|--------------|---------------|
| 從 Fabrikam East (Fabrikam) 的應收金額 | 25.00        |               |
| 應收帳款 (Fabrikam)    |              | 25.00         |
| 應收帳款 (Fabrikam)    | 100.00       |               |
| 向 Fabrikam West (Fabrikam) 的應付金額   |              | 100.00        |

**Fabrikam East 過帳**

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam East) | 25.00        |               |
| 向 Fabrikam (Fabrikam East) 的應付金額     |              | 25.00         |

**Fabrikam West 過帳**

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 從 Fabrikam (Fabrikam West) 的應收金額   | 100.00       |               |
| 應收帳款 (Fabrikam West) |              | 100.00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>範例 6：不具有主要付款的客戶貸方通知單
Fabrikam 從客戶 4000 (Northwind Traders) 收到 75.00 付款。 使用 Fabrikam West 客戶 10000 的未結發票和 Fabrikam East 客戶 4000 的未結貸方通知單結算付款。 該付款在 **結算交易** 頁面中不選擇為主要付款。

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>發票為客戶 10000 過帳到 Fabrikam West

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam West) | 100.00       |               |
| 銷售 (Fabrikam West)               |              | 100.00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>貸方通知單為客戶 4000 過帳到 Fabrikam East

| 客戶                             | 借方金額 | 貸方金額 |
|-------------------------------------|--------------|---------------|
| 銷售退貨 (Fabrikam East)       | 25.00        |               |
| 應收帳款 (Fabrikam East) |              | 25.00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>客戶 4000 的付款已過帳到 Fabrikam

| 客戶                        | 借方金額 | 貸方金額 |
|--------------------------------|--------------|---------------|
| 現金 (Fabrikam)                | 75.00        |               |
| 應收帳款 (Fabrikam) |              | 75.00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam 付款使用 Fabrikam West 發票和 Fabrikam East 貸方通知單結算

**Fabrikam 過帳**

| 客戶                         | 借方金額 | 貸方金額 |
|---------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam)  | 75.00        |               |
| 向 Fabrikam West (Fabrikam) 的應付金額 |              | 75.00         |

**Fabrikam East 過帳**

| 客戶                              | 借方金額 | 貸方金額 |
|--------------------------------------|--------------|---------------|
| 應收帳款 (Fabrikam East)  | 25.00        |               |
| 向 Fabrikam West (Fabrikam East) 的應付金額 |              | 25.00         |

**Fabrikam West 過帳**

| 客戶                                | 借方金額 | 貸方金額 |
|----------------------------------------|--------------|---------------|
| 從 Fabrikam (Fabrikam West) 的應收金額      | 75.00        |               |
| 應收帳款 (Fabrikam West)    |              | 75.00         |
| 從 Fabrikam East (Fabrikam West) 的應收金額 | 25.00        |               |
| 應收帳款 (Fabrikam West)    |              | 25.00         |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]