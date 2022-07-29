---
title: 發票比對和公司間採購訂單
description: 公司間貿易交易涉及的採購法人實體可能設定使用應付帳款發票比對。 此時必須先符合公司間貿易和應付帳款發票比對的過帳要求，才能過帳公司間廠商發票。
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: twheeloc
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e884e96e1275f9162b642bbe48c2d891c6434002
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451560"
---
# <a name="invoice-matching-and-intercompany-purchase-orders"></a>發票比對和公司間採購訂單

[!include [banner](../includes/banner.md)]

公司間貿易交易涉及的採購法人實體可能設定使用應付帳款發票比對。 當 **應付帳款參數** 頁面的 **過帳有差額發票** 欄位設定為 **需要核准** 時，將執行發票比對驗證。 此時必須先符合公司間貿易和應付帳款發票比對的過帳要求，才能過帳公司間廠商發票。

本主題的範例使用下列設定進行公司間貿易：
-   Fabrikam Purchase 是購買法人實體。
-   Fabrikam Sales 是銷售法人實體。
-   Fabrikam Sales 存在 Customer 4020。
-   Fabrikam Purchase 存在廠商 3024。
-   在 Fabrikam Purchase 中，廠商 3024 已指明公司間資訊。 Fabrikam Sales 被指明為客戶公司，而客戶 4020 被指明為呼應 Fabrikam Purchase 法人實體的客戶帳號。
-   在 Fabrikam Sales 中，客戶 4020 已指明公司間資訊。 Fabrikam Purchase 被指明為廠商公司，而廠商 3024 被指明為呼應 Fabrikam Sales 法人實體的廠商帳號。

這些範例使用下列設定比對 Fabrikam Purchase 的應付帳款發票：
-   在 **應付帳款參數** 頁面上，選取 **啟用發票比對驗證** 選項。
-   **應付帳款參數** 頁面上的 **過帳有差額發票** 選項設定為 **需要核准**。
-   法人實體的價格容差佔比為 2%。

## <a name="example-price-matching-and-intercompany-trade"></a>範例：價格比對和公司間貿易
公司間廠商發票與公司間客戶發票淨額必須相等。 此項要求優先於任何適用的發票比對核准或價格容差佔比。 例如，您按照下列步驟。
1.  在 Fabrikam Purchase 中，為客戶 4020 建立銷售訂單 SO888。 Fabrikam Purchase 中廠商 3024 自動建立公司間採購訂單 ICPO222，而 Fabrikam Sales 中自動建立銷售訂單 ICSO888。
2.  在 Fabrikam Sales 中，登記品項已收到並張貼裝箱單。 ICSO888 狀態更改為已交付。 ICPO222 狀態更改為已收到。
3.  在 Fabrikam Sales 中，更新 ICSO888 的發票。 單價 0.45，並且已更新 100 件品項。
4.  在 Fabrikam Purhcase 中，建立 ICPO222 的發票。 您不小心把淨價從 45.00 更改為 54.00。 顯示圖示指出價格超過 2% 的允許價格容差。
5.  在 **發票比對細節** 頁面上，選取此選項核准過帳有比對差異的項目。 在 **廠商發票** 頁面上，點選 **確定**。 如果廠發票不是公司間廠商發票，過帳會成功。 不過，因為您使用公司間廠商發票，所以過帳不成功。 公司間貿易方面，公司間銷售訂單上的發票總額必須等於呼應公司間採購訂單上的發票總額。 為了解決此問題，您必須藉由將淨價改回預設金額 45.00 來改正發票上的淨價。

## <a name="example-quantity-matching-with-intercompany-trade"></a>範例：公司間貿易的數量比對
公司間訂購單和公司間銷售訂單上的數量必須相等。 此項要求優先於任何適用的發票比對核准。 本範例使用下列額外設定進行公司間貿易：
-   在 Fabrikam Purchase 中，廠商 3024 的採購訂單動作政策設定為自動過帳原始客戶發票和公司間廠商發票。

本範例使用下列額外設定比對 Fabrikam Purchase 的應付帳款發票：
-   在 **品項模型群組** 頁面上，品項 B-R14 使用的模型群組，選取 **收件要求** 選項。
-   B-R14 品項的現貨數量 0 (零)。

例如，您按照下列步驟。
1.  在 Fabrikam Purchase 中，為客戶 4020 建立銷售訂單 SO999。 訂單包含一行品項：100 件電池 (B-R14 品項)，單價 1.00。 Fabrikam Purchase 中廠商 3024 自動建立公司間採購訂單 ICPO333，而 Fabrikam Sales 中自動建立銷售訂單 ICSO999。
2.  在 Fabrikam Sales 中執行 ICSO999 的發票更新。 過帳不成功，因為該品項庫存用盡且尚未收到。 因此無法更新財務資訊。
3.  在 Fabrikam Sales 中，登記品項已收到並張貼 ICSO999 的裝箱單。 ICPO333 的產品收據會自動過帳到 Fabrikam 購買。 在 Fabrikam Purchase 中，B-R14 品項的收件數量更改為 100。
4.  在 Fabrikam Sales 中執行 ICSO999 的發票更新。 兩個法人實體的過帳成功。 在 Fabrikam Purchase 中，B-R14 品項的購買數量更改為 100。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
