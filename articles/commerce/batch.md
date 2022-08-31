---
title: 改善批次追蹤項目的處理
description: 本文章介紹 Microsoft Dynamics 365 Commerce 中對帳單過帳過程中已改善的批次追蹤項目處理功能。
author: josaw1
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 736ab8dd21f04d7119cca6d53bfeb5e408b8cbd2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881870"
---
# <a name="improved-handling-of-batch-tracked-items"></a>改善批次追蹤項目的處理

[!include [banner](includes/banner.md)]

本文章介紹 Microsoft Dynamics 365 Commerce 中對帳單過帳過程中已改善的批次追蹤項目處理功能。

在 Dynamics 365 Commerce 銷售點 (POS) 中，無法在銷售時為批次追蹤項目擷取批次號碼。 但是，對於當透過客戶訂單或對帳單過帳在 Commerce Headquarters 內將銷售過帳時的特定設定，Commerce 預期批次追蹤項目存在有效的批次號碼，並將在開票過程中使用。

如果產品有可用的有效批次號碼，則來自對帳單過帳的客戶訂單開票流程和銷售訂單開票流程都會使用它們。 如果產品沒有可用的有效批次號碼，則客戶訂單開票流程無法過帳，並且 POS 使用者會收到錯誤消息。 即使已為產品啟用負庫存，對帳單過帳也會進入錯誤狀態。

對 Commerce 的改進有助於確保在為批次追蹤項目啟用負庫存時，如果庫存為 0 (零) 或批次號碼不可用，不會阻止透過對帳單過帳的客戶訂單開票和銷售訂單開票。 當批次號碼不可用時，改進的功能會使用銷售明細的預設批次識別碼。

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>定義用於客戶訂單的預設批次識別碼

要定義用於客戶訂單的預設批次識別碼，請執行以下步驟。

1. 在 Commerce Headquarters，前往 **Retail 和 Commerce \> Headquarters 設定 \> 參數 \> Commerce 參數**。
1. 在 **客戶訂單** 索引標籤上的 **訂單** FastTab 上，在 **預設批次識別碼** 欄位中輸入一個值。

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>定義透過對帳單過帳的銷售訂單開票所用的預設批次別碼

要定義透過對帳單過帳的銷售訂單開票所用的預設批次別碼，請執行以下步驟。

1. 在 Commerce Headquarters，前往 **Retail 和 Commerce \> Headquarters 設定 \> 參數 \> Commerce 參數**。
1. 在 **過帳** 索引標籤上的 **庫存更新** FastTab 上，在 **預設批次識別碼** 欄位中輸入一個值。

> [!NOTE]
> - 預設批次識別碼功能僅在為特定商店倉庫和品項啟用進階倉儲時可用。 在未來的版本中，預設批次識別碼功能也將在未啟用進階倉庫管理的案例中受到支援。
> - Commerce 版本 10.0.5 中引入了在對張單過帳過程中對非進階倉庫管理案例的改進處理批次追蹤項目的支援。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
