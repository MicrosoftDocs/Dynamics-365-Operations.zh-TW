---
title: 廠商支付部分金額
description: 有時，您向廠商支付的款項可能少於發票金額。 本文介紹了處理這種情況的各種選項。
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd7b7092e0d0baf48a805bbb0cefb0eb77e49946c6dbc44c9f954781ca1259e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450840"
---
# <a name="vendor-payments-for-a-partial-amount"></a>廠商支付部分金額

[!include [banner](../includes/banner.md)]

有時，您向廠商支付的款項可能少於發票金額。 本文介紹了處理這種情況的各種選項。 您可以使用的選項取決於您的業務需求和設定。 

## <a name="cash-discount-amounts"></a>現金折扣金額

廠商可以為您在到期日之前提供現金折扣讓您支付發票。 例如，您輸入 100.00 的發票，如果發票在 10 天內支付，則指定 2% 的現金折扣。 到期日期限為 30 天。 如果付款建議使用現金折扣作為選取發票的標準，並且如果建議在現金折扣日期或之前運行，則選取發票進行付款，並建立 98.00 的付款。 手動建立的一次性付款也可以享有現金折扣。

## <a name="partial-payments-with-cash-discounts"></a>含現金折扣的部分付款
當您進行部分付款時，您可能計畫再進行部分付款以完全結算發票。 若要獲得部分付款的現金折扣，您必須將 **計算部分付款的現金折扣** 選項在 **應付帳款參數** 頁面上設定為 **是的**。 

例如，如果發票在開具後 10 天內付款，您將獲得 2% 的現金折扣。 100.00 過帳發票。 如果您在 10 天內支付 49.00，則在付款日記帳中輸入借方 49.00。 當您在 **結算未結交易** 頁面結算部分付款時，**1.00** 會出現在 **可獲得的現金折扣金額** 欄位中。 

> [!NOTE] 
> 如果您輸入部分付款並將完整的發票金額留在 **結算金額** 欄位中，**可獲得的現金折扣金額** 欄位會在您過帳交易時自動重新計算。

## <a name="credit-notes-with-cash-discounts"></a>有現金折扣的折讓單
您可能會退回發票上的某些項目並收到折讓單。 如果原始發票上有現金折扣，您可以減去折扣值並獲得正確的退款金額。 如果將 **計算折讓單的現金折扣** 選項在 **應付帳款參數** 頁面上設定為 **是的**，將自動為折讓單計算折扣。 

例如，如果發票在開具後 10 天內付款，您將獲得 2% 的現金折扣。 100.00 發票已過帳。 如果您退回貨物並收到折讓單，您可以輸入原始發票全部金額 100.00 的折讓單以及折讓憑證中定義的 2% 的現金折扣。  當您檢視 **結算交易** 頁面上的折讓單時，**98.00** 會出現在 **需結算的金額** 欄位，以及 **-2.00** 出現在 **現金折扣金額** 欄位。 折扣金額過帳到現金折扣科目。

## <a name="overpaymentunderpayment-amounts"></a>超額付款/過低付款金額
您可能會支付部分款項，但仍需結算的金額非常小。 例如，廠商發票為 1,000.00，而您支付了 999.90。 如果剩餘金額小於在 **應付帳款參數** 頁面上指定的超額付款或過低付款的金額，差額會自動過帳到超額付款/過低付款分類帳帳戶。


如需相關資訊，請參閱[廠商付款概覽](../cash-bank-management/tasks/vendor-payment-overview.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]