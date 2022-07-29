---
title: 未計算稅款或稅額為零
description: 本主題提供的資料可在稅額為 0 (零) 或未計算稅款時，協助疑難排解。
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 45aa5931b5d958dd32bd165b414957fa7b366d077cef67621221ce19b56b67d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450786"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>未計算稅款或稅額為零

[!include [banner](../includes/banner.md)]

交易的明細金額可能不為 0 (零)，但未計算稅款或計算出的稅額為 0 的情況。 若要解決此問題，請根據需要按照以下各部分中的步驟操作。

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>驗證交易是否正確選擇稅籍代碼

如果交易未選擇正確的稅籍代碼，或者未選擇任何稅籍代碼，將不會計算稅款。 請按照以下步驟驗證交易是否正確選擇稅籍代碼。 

1. 在交易明細的 **明細詳細資料** FastTab 中，在 **設定** 索引標籤的 **銷售稅** 區段，驗證是否在 **品項銷售稅群組** 和 **銷售稅群組** 欄位中選擇正確的稅金群組。 如果未選擇正確的稅金群組，則進行選擇。

    [![品項銷售稅群組和銷售稅群組欄位。](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. 前往 **稅** \> **間接稅** \> **銷售稅** \> **銷售稅群組**。
3. 選擇合適的銷售稅群組，然後在 **設定** FastTab 中，記下 **銷售稅代碼** 欄位中的稅籍代碼。

    [![銷售稅群組頁面。](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. 前往 **稅** \> **間接稅** \> **銷售稅** \> **品項銷售稅群組**。
5. 選擇合適的品項銷售稅群組，然後在 **設定** FastTab，驗證 **銷售稅代碼** 欄位中的稅籍代碼與銷售稅群組的稅籍代碼是否相符。

    [![品項銷售稅群組頁面。](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. 如果稅籍代碼不相符，更新其中一個群組的銷售稅代碼。

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>驗證所選稅籍代碼非免稅並且具有正確的稅率值

如果稅籍代碼是免稅，或者稅率為 0 (零)，則稅款計算結果將為 0。 請按照以下步驟確認所選的稅籍代碼是否免稅，並驗證是否對其應用正確的稅率。

1. 前往 **稅** \> **間接稅** \> **銷售稅** \> **銷售稅群組**。
2. 選擇合適的銷售稅群組，然後在 **設定** FastTab 中，確認 **免稅** 核取方塊是否已清除。 如果已選取，請清除。

    [![銷售稅群組頁面上的免稅核取方塊。](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. 前往 **稅務** \> **間接稅** \> **銷售稅** \> **銷售稅代碼**。
4. 選擇合適的銷售稅代碼，然後驗證 **值** 欄位不是 0 (零)。 如果為 0，請更新該欄位以將其設定為正確的稅率。

    [![銷售稅代碼值頁面上的值欄位。](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>確認零是否是正確的稅額

在某些情況下，稅額為 0 (零) 是正確的。 請按照以下步驟確認 0 是否是您交易的正確稅額。

1. 前往 **總帳**\>**分類帳設定**\>**總分類帳參數**。
2. 在 **銷售稅** 索引標籤中，在 **計算方法** 欄位內驗證已選擇 **總計**。

    [![總帳參數頁面上的計算方法欄位。](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. 前往 **稅務** \> **間接稅** \> **銷售稅** \> **銷售稅代碼**。
4. 選擇合適的銷售稅代碼，選擇 **計算**\> **邊際基數**，並驗證邊際基數設定為 **發票餘額的淨額** 或 **包括其他銷售稅金額的發票總計**。 如需更多資料，請參閱[包括其他銷售稅金額的發票總計](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts)。
5. 如果在步驟 2 和 4 中已設定正確值，則確認交易的總金額是否為 0 (零)。 如果總金額為 0，則稅額為 0 是預期結果。 因為稅款計算是根據發票餘額的總金額計算的，而且該金額不是逐行計算的，所以稅額 0 將在稅款計算後分配給每一行。

## <a name="determine-whether-customization-exists"></a>確認是否存在自訂

如果您已完成前幾部分中的步驟，但仍未發現問題，請確認是否存在自訂。 如果自訂不存在，請建立 Microsoft 服務要求以獲得更多支援。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
