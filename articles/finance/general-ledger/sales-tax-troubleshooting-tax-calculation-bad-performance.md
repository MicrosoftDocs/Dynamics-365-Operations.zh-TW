---
title: 稅款計算性能影響交易
description: 本主題提供與稅款計算性能及其對交易的影響相關的疑難排解資料。
author: shtao
ms.date: 04/07/2021
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
ms.openlocfilehash: da19a83945450c2d35f95be2241b84e407860fe7808ff83934686ca2e00859bc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450516"
---
# <a name="tax-calculation-performance-affects-transactions"></a>稅款計算性能影響交易

[!include [banner](../includes/banner.md)]

有時，交易會受到稅款計算存在的性能問題之影響。 若要解決此問題，請根據需要按照以下各部分中的步驟操作。

## <a name="review-the-transaction-line-count"></a>查看交易明細計數

確認交易是否有很多行 (例如：多於幾百行)。 如果沒有，請繼續下一部分。 如果交易確實有幾百行，則延遲稅款計算。 如需更多資料，請參閱[在日記帳上啟用延遲稅款計算](enable-delayed-tax-calculation.md)。 

接下來，您可以確定是否滿足以下任一條件：

- 有來自大型檔案的匯入交易。
- 多個工作階段同時處理同一個交易稅款計算。
- 交易有多行明細，視圖會即時更新。 例如，更改明細欄位時，會即時更新 **普通日記帳** 頁面上的 **計算銷售稅金額** 欄位。

   [![日記帳憑單頁面中計算得出的銷售稅金額欄位。](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

如果滿足這些條件的任何一個，則延遲稅款計算。

## <a name="review-the-call-stack"></a>查看呼叫堆疊

查看呼叫堆疊，以確認是否多次呼叫稅款計算。 如果不是，請繼續下一部分。 如果呼叫堆疊被多次呼叫，請按照以下步驟幫助減少稅款計算次數。

1. 如果日記帳已考慮交易，則延遲稅款計算。 如需更多資料，請參閱[在日記帳上啟用延遲稅款計算](enable-delayed-tax-calculation.md)。
2. 如果交易是訂購單，應用程式版本比 10.0.15 新，可以透過啟用 **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch** 的小眾測試將稅款計算延遲到最終計算。

## <a name="review-the-call-stack-timeline"></a>查看呼叫堆疊時間表

查看呼叫堆疊時間表，以確認是否存在以下問題。 如果存在，啟用 **TaxUncommittedDoIsolateScopeFlighting** 的小眾測試來解決問題。

- 交易將導致系統停止回應，直到工作階段結束。 因此，交易無法計算稅款結果。 下圖顯示您收到的「工作階段結束」訊息框。

    [![工作階段結束訊息。](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- **TaxUncommitted** 方法會比其他方法花費更多時間。 例如，在下圖中，**TaxUncommitted::updateTaxUncommitted()** 方法需要 43,347.42 秒，而其他方法則需要 0.09 秒。

    [![方法持續時間。](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>自訂和呼叫稅款計算

當您自訂時，請勿在每一行的 **insert()** 或 **update()** 方法中呼叫稅款計算。 應在交易等級呼叫稅款計算。

## <a name="determine-whether-customization-exists"></a>確認是否存在自訂

如果您已完成前幾部分中的步驟，但仍未發現問題，請確認是否存在自訂。 如果自訂不存在，請建立 Microsoft 服務要求以獲得更多支援。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
