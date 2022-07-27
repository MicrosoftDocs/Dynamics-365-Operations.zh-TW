---
title: 篩選公司間訂單以避免同步 Orders 和 OrderLines
description: 本主題說明如何篩選公司間訂單，以使 Orders 和 OrderLines 實體不同步。
author: negudava
ms.date: 11/09/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: negudava
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 8575f38ca23ef245947a41c35846983604662ef2
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460550"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>篩選公司間訂單以避免同步 Orders 和 OrderLines

[!include [banner](../../includes/banner.md)]

您可以篩選公司間訂單，以便不會同步 **Orders** 和 **OrderLines** 表。 在某些情況下，客戶業務開發應用程式中不需要公司間訂單詳情。

每個標準 Dataverse 表都透過參考 **IntercompanyOrder** 欄進行擴展，並且修改了雙重寫入對應，以便它們參考篩選器中的附加資料欄。 因此，公司間訂單不再同步。 此過程有助於防止客戶業務開發應用程式中出現不必要的資料。

1. 透過新增對 **IntercompanyOrder** 欄的參考來擴展 **CDS 銷售訂單標題** 表。 此欄僅在公司間訂單上填入。 在 **SalesTable** 表中可以使用 **IntercompanyOrder** 欄。

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="將暫存對應到 CDS 銷售訂單標題的目標頁面。":::

2. 擴展 **CDS 銷售訂單標題** 後，對應中的 **IntercompanyOrder** 欄可用。 套用以 `INTERCOMPANYORDER == ""` 作為查詢字串的篩選器。

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="CDS 銷售訂單標題的編輯查詢對話方塊。":::

3. 透過新增對 **IntercompanyInventTransId** 欄的參考來擴展 **CDS 銷售訂單明細** 表。 此欄僅在公司間訂單上填入。 在 **SalesLine** 表中可以使用 **InterCompanyInventTransId** 欄。

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="將暫存對應到 CDS 銷售訂單明細的目標頁面。":::

4. 擴展 **CDS 銷售訂單明細** 後，對應中的 **IntercompanyInventTransId** 欄可用。 套用以 `INTERCOMPANYINVENTTRANSID == ""` 作為查詢字串的篩選器。

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="CDS 銷售訂單明細的編輯查詢對話方塊。":::

5. 重複步驟 1 和 2 以擴展 **銷售發票抬頭 V2** 表並新增篩選器查詢。 在這種情況下，使用 `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` 作為篩選器的查詢字串。

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="將暫存對應到銷售發票抬頭 V2 的目標頁面。":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="銷售發票抬頭 V2 的編輯查詢對話方塊。":::

6. 重複步驟 3 和 4 以擴展 **銷售發票明細 V2** 表並新增篩選器查詢。 在這種情況下，使用 `INTERCOMPANYINVENTTRANSID == ""` 作為篩選器的查詢字串。

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="銷售發票明細 V2 的編輯查詢對話方塊。":::

7. **報價單** 表沒有公司間關係。 如果有人為您的一位內部公司客戶建立報價單，您可以使用 **CustGroup** 欄將所有這些客戶歸入一個客戶組。 您可以透過新增 **CustGroup** 欄來擴展標題和明細，然後進行篩選以使該組不包括在內。

    :::image type="content" source="media/filter-cust-group.png" alt-text="將暫存對應到 CDS 銷售報價單標題的目標頁面。":::

8. 擴展 **報價** 後，套用一個篩選器，將 `CUSTGROUP != "<company>"` 作為查詢字串。

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="CDS 銷售報價單標題的編輯查詢對話方塊。":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]