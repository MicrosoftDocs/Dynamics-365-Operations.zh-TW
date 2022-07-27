---
title: 將 Dynamics 365 Commerce 定價引擎與 Dynamics 365 Sales 結合使用
description: 本主題介紹如何使用 Microsoft Dynamics 365 Commerce 定價引擎在 Dynamics 365 Sales 中建立銷售報價單。
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c3f1527e5f37bebba57661ca86b1a3aae7e62da0
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2021
ms.locfileid: "8460548"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>將 Dynamics 365 Commerce 定價引擎與 Dynamics 365 Sales 結合使用

[!include [banner](../../includes/banner.md)]

本主題介紹如何使用 Microsoft Dynamics 365 Commerce 定價引擎在 Dynamics 365 Sales 中建立銷售報價單。

Dynamics 365 Commerce 定價引擎支援大多數企業對消費者 (B2C) 定價方案，例如商店級定價、基於附屬機構和基於忠誠度的定價、混合搭配折扣、數量折扣和閾值折扣。 定價引擎使用複雜的規則來確定給定報價或訂單的最佳價格。

當您使用[雙重寫入](./dual-write-overview.md)時，您有三個選項可以滿足您的定價需求。 您可以使用來自 Dynamics 365 Sales 中的價目表、Dynamics 365 Supply Chain Management 中的定價引擎或 Dynamics 365 Commerce 中的定價引擎的靜態定價。 在這些選項中，Commerce 定價引擎最適合 B2C 案例。

## <a name="use-the-commerce-pricing-engine-in-sales"></a>在 Sales 中使用 Commerce 定價引擎

> [!NOTE]
> 目前，Commerce 定價引擎只能用於 Sales 中的報價單建立。 銷售訂單與 Commerce 定價引擎的整合尚不可用。

當使用者在 Sales 中發起報價時，雙重寫入架構會將報價詳情複製到 Commerce。 對現有報價行的任何更改或 Sales 中任何新新增的報價行都會複製到 Commerce。 當使用者想要使用 Commerce 定價引擎對報價進行定價時，他們可以選取 **報價** 以根據 Commerce 定價引擎更新報價的價格。 然後在 Sales 和 Commerce 中自動更新價格。

## <a name="prerequisites"></a>先決條件

- 在您可以在 Sales 中使用 Commerce 定價引擎之前，您必須按照[雙重寫入中的潛在客戶到現金流程](./dual-write-prospect-to-cash.md)。
- 您必須按照以下步驟關閉手動輸入的貿易協議評估：

    1. 在您的 Commerce 環境中，進入 **應收帳款\>設定\>應收帳款參數**。
    1. 在 **價格** 索引標籤的 **貿易協定評估** FastTab 上，清除 **手動輸入** 核取方塊。

## <a name="additional-resources"></a>其他資源

[雙重寫入中的從潛在客戶到現金流程](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]