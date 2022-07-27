---
title: 雙重寫入中的庫存可用性
description: 本主題提供有關如何在雙重寫入中檢查庫存可用性的資訊。
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 989ba6cd26d6e48c24db856fa9bb0bd5d2bae80e
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460490"
---
# <a name="inventory-availability-in-dual-write"></a>雙重寫入中的庫存可用性

[!include [banner](../../includes/banner.md)]

透過使用庫存可用性，您可以在將產品新增到 Microsoft Dynamics 365 Sales 的 **報價單**、**訂單** 或 **發票** 頁面之前檢查您的庫存。 例如，您檢查庫存並確定履行日期是[從潛在客戶到現金](dual-write-prospect-to-cash.md)流程中的一項關鍵工作。

如果您沒有足夠的庫存，您可以根據預計的庫存收貨和問題估算交貨日期。 您還可以查看產品的可承諾量 (ATP) 資訊，您可以在其中找到預定義時界中的 ATP 數量。

## <a name="on-hand-inventory"></a>現有庫存

在 Dynamics 365 Sales 中，新的 **現有庫存** 按鈕已新增到 **報價單**、**訂單** 和 **發票** 頁面的標題中。 當您選取此按鈕時，將出現一個對話方塊，您可以在其中指定要檢查現有庫存的公司和產品。 此對話方塊顯示與[現有庫存](../../../../supply-chain/inventory/tasks/check-availability-stock.md)相同的資訊。

該對話方塊從 Dynamics 365 Supply Chain Management 回傳庫存資訊。 此資訊包括以下數量：

- 現有數量
- 保留現有數量
- 現有數量
- 訂購數量
- 訂購數量
- 保留的訂購數量
- 總體可用數量

## <a name="atp-information"></a>ATP 資訊

在銷售中，新的 **ATP 資訊** 按鈕已新增到 **報價單**、**訂單** 和 **發票** 頁面上的訂單項。 選取此按鈕時，會出現一個對話方塊，您可以在其中指定公司、產品、庫存地點、庫存倉庫和訂單數量。 此對話方塊具有與[訂單承諾](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations)中描述的相同的設定。

該對話方塊回傳來自 Supply Chain Management 的 ATP 資訊。 此資訊包括以下數量：

- ATP 數量
- 收據數量
- 簽發數量
- 現有數量

## <a name="how-it-works"></a>運作方式

當您在 **報價單**、**訂單** 或 **發票** 頁面上選取 **現有庫存** 按鈕時，將對 **現有庫存** API 進行即時雙重寫入調用。 API 計算給定產品的現有庫存。 結果儲存在 **InventCDSInventoryOnHandRequestEntity** 和 **InventCDSInventoryOnHandEntryEntity** 表，然後透過雙重寫入寫入 Dataverse。 若要使用此函數，您需要執行以下雙重寫入對應。 執行地圖時跳過初始同步。

- CDS 庫存現有分錄 (msdyn_inventoryonhandentries)
- CDS 庫存現有請求 (msdyn_inventoryonhandrequests)

## <a name="templates"></a>範本

以下範本可用於公開現有庫存資料。

財務和營運應用程式 | Customer Engagement 應用程式     | 描述
---|---|---
[CDS 現有庫存分錄](mapping-reference.md#145) | msdyn_inventoryonhandentries |
[CDS 現有庫存要求](mapping-reference.md#147) | msdyn_inventoryonhandrequests |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
