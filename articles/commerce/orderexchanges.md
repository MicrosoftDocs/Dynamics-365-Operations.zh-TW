---
title: 在退貨單上設定及處理換貨
description: 本文章說明如何在 Dynamics 365 Commerce 中設定退換貨。
author: josaw1
ms.date: 07/28/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f33c674e4110b4e45ac58e499a65da2509b00046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845784"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>在退貨單上設定及處理換貨

[!include [banner](includes/banner.md)]

舊版 Dynamics 365 Commerce 是使用總部的退貨單文件來處理客戶訂單的退貨事宜。 不過，退貨單文件僅可用來處理要退回的產品。 退貨單明細上會將退回產品數量以負數表示。 反之，銷售訂單數量則由正數表示。 不過，退貨單文件不支援正數的數量。 基於此限制，舊版應用程式不支援使用退貨單文件進行產品更換的案例。

不過，目前已新增支援在退貨單上進行換貨的案例功能。 Commerce 現在使用銷售訂單文件 (而不是退貨單文件) 來處理這類交易。

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>設定 Commerce 以支援在退貨單上進行換貨

> [!NOTE]
> Commerce 10.0.20 版及更新版本提供了名為 POS 統一退貨處理體驗的新功能。 如果啟用此功能，則不需要以下設定步驟。 **以銷售訂單形式處理退貨** 已成為永久設定，而無法變更。

按照下列步驟設定系統，以支援在退貨單上進行換貨 (如果您未啟用 **POS 統一退貨處理體驗** 功能的話)。

1. 移至 **Retail 和 Commerce \> 總部設定 \> 參數 \> Commerce 參數**。 在 **客戶訂單** FastTab 上，將 **以銷售訂單形式處理退貨** 選項設為 **是**。
2. 執行 **全域設定分配排程** 工作 (**1110**)。

## <a name="make-an-exchange"></a>辦理換貨

按照上一節所述設定系統後，銷售點 (POS) 使用者仍可如舊版應用程式一般選取銷售訂單或銷售發票來處理退貨。 不過，當退貨品項新增到購物車後，使用者就能夠將新的銷售明細新增到購物車。

針對這些新的銷售明細，使用者必須定義所有必要屬性以處理客戶訂單明細。 這些屬性包括交貨方法和履行位置。 交易的到期付款金額是退貨單明細和銷售訂單明細的淨額。 交易付款後，退貨單即會以銷售訂單文件形式在總部過帳，而系統會立即針對退貨明細開立發票。

為了讓購物車的各種金額更加一目了然，我們為購物車新增了三個全新金額欄位。 您可以使用畫面設計工具，在 POS 使用者介面 (UI) 中顯示這些新欄位。

- **扣除訂金** - 使用者在客戶訂單取貨時已扣除的交易訂金金額。 如果沒有任何訂金覆寫，並且設定 10% 訂金，則此欄位中的金額為客戶訂單總金額的 90%。
- **執行金額** - 在建立或編輯客戶訂單時，或在客戶訂單換貨期間，交付模式設定為 **執行** 時的明細總金額。 此欄位中的金額包括稅金與費用。
- **退貨金額** - 在客戶訂單換貨期間具有負數數量的明細總金額。 此欄位中的金額包括稅金與費用。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
