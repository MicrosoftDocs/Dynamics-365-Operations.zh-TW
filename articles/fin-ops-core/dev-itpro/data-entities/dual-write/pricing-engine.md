---
title: 與 Supply Chain Management 定價引擎按需同步
description: 本主題介紹如何在 Microsoft Dynamics 365 Sales 的 Microsoft Dynamics 365 Supply Chain Management 中使用定價引擎。
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6b0cc8f403be866ff00b89a33f6c59089c987bb0
ms.sourcegitcommit: 9c19898e1f41495f804c7f07e2636b53a098c4c1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2022
ms.locfileid: "8460519"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>與 Supply Chain Management 定價引擎按需同步

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management 包括一個處理貿易協議、價目表、客戶忠誠度計劃、促銷和折扣的定價引擎。 定價引擎使用複雜的規則來確定給定報價或訂單的最佳價格。 使用雙重寫入時，您可以在 Microsoft Dynamics 365 Sales 的 **報價單** 和 **訂單** 頁面上使用靜態定價或 Supply Chain Management 中的定價引擎。

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>在 Sales 中使用 Supply Chain Management 中的定價引擎

1. 在 Sales 中，進入 **銷售\>訂單**。
1. 選取 **新建** 建立新的訂購單，或在 **我的訂單** 清單選取現有訂單。
1. 新增新的訂單明細。
1. 如果您要建立新訂單，請選取動作窗格上的 **價格訂單**。 如果您要更新現有訂單，請選取動作窗格上的 **重新計算**。
1. 以下資料欄會自動填入：

    - 明細金額
    - 折扣 %
    - 折扣
    - 運費前金額
    - 運費金額
    - 總稅金
    - 總金額

> [!NOTE]
> 建立報價單時也適用類似的過程。

## <a name="how-it-works"></a>運作方式

當您在 Sales 中建立訂單時，該訂單會立即使用您在 Sales 中輸入的值同步到 Supply Chain Management。 當您在 Sales 中選取 **價格訂單** 或 **報價**，Supply Chain Management 根據 Supply Chain Management 中定義的貿易協議規則計算每個訂單行的價格和總訂單。 然後將新計算的值同步回 Sales。

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>在 Supply Chain Management 中設定貿易協議評估選項

您可以將 Supply Chain Management 設定為在計算在 Sales 中建立的訂單的價格時尊重或忽略貿易協議。 按照以下步驟動作安裝此選項。

1. 登入您的 Supply Chain Management 環境。
1. 前往 **應收帳款\>設定\>應收帳款參數**。
1. 在 **價格** 索引標籤，在 **貿易協定評估** FastTab，根據需要新增或刪除 **手動輸入** 原則的資料列。 此原則的存在與否會控制 Supply Chain Management 定價引擎是否會自動否決在 Sales 中輸入的銷售價格。

    - 如果 **手動輸入** 原則 *不* 存在於 **貿易協定評估** 設定，Supply Chain Management 則是價格主資料。 當使用者選取 Sales 動作窗格中的 **價格訂單** 或 **報價**，調用 Supply Chain Management 定價引擎，並覆寫在 Sales 中輸入的銷售價格，除非它等於在 Supply Chain Management 中計算的銷售價格。
    - 如果 **手動輸入** 原則 *存在* 於 **貿易協定評估** 設定，Sales 則是價格主資料。 當使用者在 Sales 中的動作窗格上選取 **價格訂單** 或 **報價** 時，防止在銷售中輸入的銷售價格被自動覆寫。
    - 銷售中的 **單價** 和/或 **折扣** 值為 *0* (零) 的訂單明細和報價行被視為特殊情況。 如果相關貿易協議價格可用，Supply Chain Management 將 *一律* 將其套用於這些欄位，而不管 **貿易協議評估** 設定如何。

    如需每種情況的範例，請參閱以下情境。

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>範例情境 1：沒有手動輸入選項的貿易協議評估

在這種情況下，Supply Chain Management 中的 **貿易協議評估** 設定 *不* 包括 **手動輸入** 原則。 銷售使用者在 Sales 中輸入具有非零銷售價格的訂單明細，並且在 Supply Chain Management 中沒有為項目定義銷售價格。

1. 在 Sales 中，使用者建立一個訂單明細，其 **單價** 為 1 美元 (USD)。
1. 訂單行以 1 美元的銷售價格同步到 Supply Chain Management。
1. 在 Sales 中，使用者選取動作窗格上的 **價格訂單**。
1. Supply Chain Management 搜尋相關價格和折扣，然後計算總計。 由於該項目在 Supply Chain Management 中沒有銷售價格，因此計算會更新該行，使其具有 0 美元的銷售價格。
1. 該行的新銷售價格將同步回 Sales。
1. 結果是銷售中的訂單行，其銷售價格為 0 美元。

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>範例情境 2：含有手動輸入選項的貿易協議評估

在這種情況下，Supply Chain Management 中的 **貿易協議評估** 設定 *有* 包括 **手動輸入** 原則。 Sales 使用者在銷售中輸入具有非零銷售價格的訂單明細。 Supply Chain Management 包括一個貿易協議，該協議為訂購的商品設定了 2 美元的銷售價格。

1. 在 Sales 中，使用者為 **單價** 為 1 美元的商品建立訂單明細。
1. 訂單行以 1 美元的銷售價格同步到 Supply Chain Management。
1. 在 Sales 中，使用者選取動作窗格上的 **價格訂單**。
1. 由於 Supply Chain Management 中的 **貿易協議評估** 設定包括 **手動輸入** 策略，因此銷售價格不會更改，即使適用的貿易協議指定了另一個銷售價格。
1. Sales 和 Supply Chain Management 中的銷售價格保持不變。

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>範例情境 3：Sales 中銷售價格為零的項目的貿易協議評估

在這種情況下，Supply Chain Management 中的 **貿易協議評估** 設定 *有* 包括 **手動輸入** 原則。 Sales 使用者在 Sales 中輸入銷售價格為 0 (零) 的訂單明細。 Supply Chain Management 包括一個貿易協議，該協議為訂購的商品設定了 2 美元的銷售價格。

1. 在 Sales 中，使用者建立一個訂單明細，其 **單價** 為 0 美元，**明細折扣** 值為 0 美元。
1. 訂單行以 0 美元的銷售價格同步到 Supply Chain Management。
1. 因為它收到一個銷售價格為 0 (零) 的訂單明細，即使 **手動輸入** 選項已啟用，Supply Chain Management 將其稱為定價引擎。 定價引擎回傳由貿易協議確定的 2 美元的銷售價格，並更新 Supply Chain Management 中的訂單明細。
1. 更新的銷售價格尚未同步到銷售中的訂單明細。
1. 在 Sales 中，使用者選取動作窗格上的 **價格訂單**。
1. Supply Chain Management 中的訂單明細保持其銷售價格 2 美元，現在已同步回 Sales。 因此，Sales 中訂單明細的 **單價** 值從 0 美元更新為 2 美元。
1. 在 Sales 中，使用者輸入新的 **明細折扣** 值 0.50 美金。 Sales 現在計算出該明細的 **擴展金額** 值為 1.50 美元。
1. 訂單明細以 0.50 美元的 **明細折扣** 同步到 Supply Chain Management。
1. 在 Sales 中，使用者選取動作窗格上的 **價格訂單**。
1. 銷售中的訂單明細沒有價格或折扣變化。

## <a name="limitations"></a>限制

填入 Sales 中的資料欄時，適用以下限制：

- Supply Chain Management 中的費用設定和費用指派不會在 Sales 中複製。
- 定價不考慮在 Supply Chain Management 的銷售訂單行頁面的 **零售通路** 欄中指定的特殊零售定價。
- 不考慮在 Supply Chain Management 的 **貿易津貼管理** 部分中定義的折扣。
- 定價不考慮銷售協議。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
