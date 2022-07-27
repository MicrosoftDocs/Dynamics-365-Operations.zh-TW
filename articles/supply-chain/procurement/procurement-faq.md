---
title: 採購常見問題集
description: 本主題提供有關 Supply Chain Management 的採購功能常見問題集 (FAQ) 的解答。
author: Henrikan
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 99d44f2409d8207ed7a0fb1fc92a99de42240e86
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448986"
---
# <a name="procurement-faq"></a>採購常見問題集

[!include [banner](../includes/banner.md)]

本主題提供有關 Supply Chain Management 的採購功能常見問題集 (FAQ) 的解答。

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>我是否可以只顯示我建立的採購訂單？

此功能目前不可用。

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>我可以保留庫存並根據採購訂單上登記的庫存建立交易嗎？

### <a name="issue-description"></a>問題描述

即使當品項在採購訂單上為 *已登記* 狀態，您仍可以保留庫存。 換句話說，您可以針對已登記的庫存建立交易。

### <a name="reproduce-the-issue"></a>重現該問題

以下程序顯示重現該問題的一種方法。

1. 建立訂購單。
2. 登記採購訂單行。
3. 請注意，您可以針對已登記的庫存產生保留或交易。

### <a name="issue-resolution"></a>問題解決方法

透過行為設計。 預期狀況是所登記品項的實體已抵達倉庫或庫存，因此可供保留。

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>我可以找到取消採購訂單的使用者嗎？

只有當採購訂單受變更管理影響時，才會追蹤此資訊。 如果您使用變更管理，您便可以查看誰已提交變更 (取消)，以及誰核准了變更。

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>為什麼我不能將採購合約連結到現有採購訂單？

建立採購訂單時，採購合約必須與採購訂單相關聯。 否則，採購訂單行無法與採購合約行相關聯。

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>什麼檢查會觸發「更新手動輸入的價格與折扣或更新外部文件」訊息？

當您變更出貨日期時，您可能會收到一則訊息指出「更新手動輸入的價格與折扣或更新外部文件」。 您會收到此訊息是因為，如果出貨日期變更，可能會觸發不同的貿易或銷售合約並導致價格變化。 出貨日期的變更也會影響倉庫排程和其他相關資訊。

每當任何日期或某些其他參數變更時，都會觸發此訊息。 此訊息的目的是確保您瞭解價格會因為這些改變而發生變化。

此訊息是貿易合約評估 (TAE) 提示。 如需完整說明，請參閱[貿易合約評估政策](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper)。

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>為什麼我不能為具有以類別為基礎品項的採購訂單行過帳多個發票？

如果您要過帳發票，數量是必填的。 因此，如果某一行項其全部數量僅開具部分金額的發票，您將無法為剩餘金額開具另一張發票。
