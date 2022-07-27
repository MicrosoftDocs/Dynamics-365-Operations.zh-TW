---
title: 檢查公司間訂單價格差異
description: 本主題將說明如何檢查公司間訂單價格差異
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f9a0ba4980f8acf56d84dc865094b405b7402ad5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447720"
---
# <a name="check-intercompany-order-price-discrepancies"></a>檢查公司間訂單價格差異

[!include [banner](../../includes/banner.md)]

您可以使用此程序檢查公司間訂單的價格差異。

1. 依序前往 **採購 \> 定期 \> 清理 \> 檢查公司間訂單價格差異**。
1. 如有需要，可以設定批次處理作業，然後選擇 **確定**，即可檢查公司間銷售訂單和訂購單的價格和折扣。 否則請選擇 **取消** 以關閉頁面而不執行檢查。

    > [!TIP]
    > 如有任何同步問題或價格問題，系統會在顯示的資訊訊息中列出。 您可以列印資訊訊息做為參考。

1. 在資訊訊息上選擇相關明細，即可開啟目前法律實體中的訂單。 選擇 **公司間**，然後選擇 **公司間訂購單** 或 **公司間銷售訂單**，即可開啟相關法律實體中的訂單。

    > [!NOTE]
    > 若要允許更新公司間訂單：
    >
    > 1. 前往 **應收帳款 \> 客戶 \> 所有客戶**。
    > 1. 在動作窗格上，選擇 **一般** 索引標籤，然後選擇 **公司間**。
    > 1. 在 **公司間** 頁面上，選擇 **訂購單政策** 或 **銷售訂單政策**。
    > 1. 同時在兩個區域中選擇 **允許編輯價格** 和 **允許編輯折扣**。

1. 開啟要保留價格的相關公司間訂單。
1. 更改每個訂單明細的 **單價** 欄位，然後再改回原始值。 更改明細的 **折扣** 欄位再改回原始值，然後更改相關 **採購費用** 或 **銷售費用** 欄位再改回原始值。 來回更改值會同步處理此公司間訂單明細與參照的公司間訂單明細的價格、折扣和費用，使雙方的值自動保持一致。

    > [!NOTE]
    > 只有在公司間銷售訂單尚未開立發票時，此同步作業才有效。 如果公司間銷售訂單已開立發票、過帳並建立客戶發票日記帳，則必須直接變更公司間訂購單明細，方法是將價格、折扣和費用設為公司間客戶發票日記帳上的價格、折扣和費用。 如果不這樣做，則無法對內部公司採購訂單開立發票並過帳，因為訂單總額將不相符。

1. 重複此程序，直到所有公司間訂購單和銷售訂單同步。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
