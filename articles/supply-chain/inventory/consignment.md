---
title: 設定寄售
description: 本主題說明如何使用入庫寄售庫存流程。
author: yufeihuang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchTablePart, PurchVendorPortalConfirmedOrders, DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4a1b96d18048a1ae6e380374f32d2bfa2270ae24
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449037"
---
# <a name="set-up-consignment"></a>設定寄售

[!include [banner](../includes/banner.md)]

本主題說明如何使用入庫寄售庫存流程。

寄售庫存是由廠商擁有但儲存在您站點的庫存。 當您準備好消耗或使用庫存時，您將接管庫存的所有權。 本主題包含如何在不建立總帳交易的情況下實際接收廠商擁有的現有庫存、如何啟動可以實際保留廠商所擁有庫存的生產流程的資訊。 以及如何變更原材料的所有權，以便能將消耗作為生產訂單處理的一部分進行處理。 還有一些關於廠商如何使用廠商協作介面監控其庫存消耗的資訊。

## <a name="overview-of-the-consignment-process"></a>寄售流程概觀

在此範例案例中，USMF 公司與廠商 US-104 簽訂了原材料 M9211CI 的寄售合約。

1. 寄售補貨訂單由 USMF 的某位員工根據預期需求手動建立。 為廠商 US-104 建立訂單，並為項目 MS9211CI 新增一行。
1. 廠商會收到有關預期交付的通知。 可能以底下三種方式之一發生：
    - 在 USMF 工作的人將訂單資訊寄給廠商。
    - 廠商可以使用廠商共同作業介面監控預期的現有庫存。
    - 在 USMF 工作的人會篩選 **現有庫存** 頁面，僅顯示廠商 US-104 的記錄，其中收貨狀態為 **已訂購**，然後將此資訊寄給廠商。
1. 庫存從 US-104 交付給 USMF。
1. 物料到達 USMF 時，將使用產品收據更新寄售補貨訂單。 僅記錄廠商擁有庫存的實際數量。 沒有建立總帳交易，因為庫存仍歸廠商所有。
1. 廠商使用 **現有寄售庫存** 頁面監控實際現有庫存的更新。
1. 現在實際庫存為現有，生產流程保留廠商擁有的庫存，並開始進行將耗用原材料 M9211CI 的成品生產訂單。
1. 將在今天的生產中耗用之保留原材料的擁有者從 US-104 改為 USMF。 這是使用庫存所有權變更日記帳完成的。 此流程建立訂購單，其中 **來源** 欄位設為 **寄售**。
1. 廠商在 **從寄售庫存中收到的產品** 頁面監控耗用 (所有權變更)，並根據兩家公司之間的合約開立發票。
1. 生產流程透過生產揀料單耗用原材料。 實際保留會自動更新，以反映現有庫存歸 USMF 所有。
1. US-104 的發票依據處理庫存所有權變更日記帳時自動產生的訂購單進行處理。 向廠商 US-104 支付已耗用庫存的款項。

USMF 執行額外的定期流程：

- 使用轉移日記帳處理廠商擁有的庫存在不同倉庫之間的實體移動。
- 現有的實體庫存使用 **項目清點** 日記帳更新。 如果廠商有權限這樣做，也可以使用盤點來更新現有庫存。

廠商 US-104 可以使用 **現有寄售庫存** 頁面監控更新。

## <a name="consignment-replenishment-orders"></a>寄售補貨訂單

寄售補貨訂單是一種文件，用於透過建立訂購的庫存交易，請求和追蹤廠商打算在特定日期間隔內交付之產品的庫存數量。 通常這將基於特定產品的預測和實際需求。 將根據寄售補貨訂單接收的庫存，仍歸廠商所有。 僅記錄與實物接收更新相關之產品的擁有情況，因此不會發生總帳交易更新。

**擁有者** 維度用於區隔哪些庫存由廠商擁有，以及哪些由接收法律實體擁有的相關資訊。 只要寄售補貨訂單明細的全部數量尚未收到或取消，明細就會有 **未結訂單** 狀態。 全部數量已收到或取消時，狀態將改為 **已完成**。 可以使用登記流程和產品收貨更新流程，記錄與寄售補貨訂單相關的實際現有庫存。 登記可以作為項目到達流程的一部分，也可以透過手動更新訂單明細來完成。 使用產品收貨更新流程時，會在產品收貨日記帳進行記錄，可用於向廠商確認收貨。

[![寄售補貨訂單。](./media/consignment-replenishment-order.png)](./media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>庫存所有權變更日記帳

**庫存所有權變更** 日記帳用於記錄將寄售庫存的所有權從廠商更改為耗用的法律實體。 預期不會為日記帳建立庫存交易。 如同任何庫存日記帳，它必須以庫存日記帳名稱識別。 這些名稱建立於 **庫存日記帳名稱** 頁面，而且 **日記帳類型** 必須設為 **所有權變更**。

只會建立與已過帳日記帳相關的庫存交易。 日記帳過帳時：

- 廠商擁有的庫存使用 **所有權變更** 參考及 **已售出** 狀態來發佈。
- 現有庫存由耗用的法律實體使用訂購單上的產品收貨更新庫存交易接收。 這會將訂單的狀態設為 **已收到**。 用於寄售的採購訂單，**來源** 欄位設為 **寄售**。

訂單建立後，無法更新寄售訂購單明細上的數量。

[![庫存所有權變更日記帳。](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>寄售流程中的廠商共同作業

如果您的廠商使用廠商共同作業介面，他們可以使用它來監控您站點的庫存耗用。 廠商共同作業介面有與入庫寄售流程相關的三個頁面：

- **訂購單** **耗用寄售庫存** - 顯示與寄售流程中所有權變更相關的詳細訂購單資訊。
- **從寄售庫存中收到的產品** - 顯示有關在所有權變更過程中更新產品收貨之品項和數量的資訊。
- **現有寄售庫存** - 顯示有關其預計交付之寄售物品的資訊，以及在客戶站點實際提供的物品。

更多有關設定廠商以使用廠商共同作業的資訊，請參閱[廠商入口網站使用者安全性](../procurement/configure-security-vendor-portal-users.md)。

## <a name="inventory-owners"></a>庫存擁有者

為了記錄實體入庫寄售庫存，您需要定義廠商擁有者。 這是在 **庫存擁有者** 頁面進行。 當您選擇 **廠商帳戶** 時，這會產生 **名稱** 和 **擁有者** 欄位的預設值。 **擁有者** 欄位中的值將對廠商可見，因此如果您的廠商帳戶名稱不容易被外部人員識別，您可能需要更改。 可以編輯 **擁有者** 欄位，但僅能在您儲存 **庫存擁有者** 記錄之前進行。 **名稱** 欄位填入與廠商帳戶相關方的名稱，並且無法更改。

[![庫存擁有者。](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>追蹤維度群組

將在寄售流程中使用的品項，必須與 **追蹤維度群組** 相關聯，其中 **擁有者** 維度設為 **使用中**。 擁有者維度的 **實體庫存** 和 **財務庫存** 選項恆為選擇。 **依維度劃分的覆蓋範圍計劃** 恆不選擇。

[![追蹤維度群組。](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
