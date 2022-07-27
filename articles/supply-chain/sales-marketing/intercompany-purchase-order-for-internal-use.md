---
title: 建立公司間訂購單的發票，以供內部使用
description: 本主題說明如何建立公司間訂購單的發票，以供內部使用
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
ms.openlocfilehash: 88a14ff962c5cf0cd1cff24b16cc7a62e9e1c8ce
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447741"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>建立公司間訂購單的發票，以供內部使用

[!include [banner](../../includes/banner.md)]

您可以為公司間的廠商建立公司間訂購單。 此功能會自動在公司間廠商建立公司間銷售訂單。

![公司間內部購買流程](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>建立公司間訂購單，以及對應的公司間銷售訂單

如圖所示，在法律實體 AAA 中執行下列步驟。

1. 選擇 **應付帳款** \> **採購訂單** \> **所有訂購單**。
1. 在 **所有訂購單** 清單頁面，為公司間廠商建立訂購單。 該欄位的值，會從廠商帳戶複製到訂購單。

    因為您使用的是公司間廠商，所以會在廠商對應的法律實體中，建立公司間銷售訂單。 公司間銷售訂單號碼，可以與公司間訂購單號碼相同，並且可以包括法律實體的識別碼。 所使用的號碼結構，是根據 **銷售訂單編號** 欄位中 **公司間** 頁面的選擇。 例如，如果您在法律實體 AAA 中建立訂購單 00029\_064，則法律實體 BBB 中的銷售訂單號碼為 AAA00029\_64。

    會出現訊息資訊，告知您已建立公司間訂購單和公司間銷售訂單。 該訊息會包括公司間銷售訂單編號，以供您參考。

1. 將明細項目新增至訂購單。 對應的明細項目，會自動新增至公司間銷售訂單中。 如果其他法律實體中的項目不存在，則會顯示訊息，並且您無法將該項目新增至訂購單中。 若要解決此問題，請切換至其他法律實體，並將該產品發佈給該法律實體。 該法律實體中的項目可用於新增至銷售訂單。 然後，切換返回至訂購單的法律實體，並繼續新增明細項目。
1. 當您完成訂購單的資訊輸入後，請確認。

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>處理公司間裝箱單和客戶發票

如圖所示，在法律實體 BBB 中執行下列步驟。

1. 前往 **應收帳款 \> 銷售訂單 \> 所有銷售訂單**。
1. 在 **所有銷售訂單** 清單頁面，選擇公司間銷售訂單。
1. 在動作窗格上，選擇 **挑選和包裝** 索引標籤，然後選擇 **裝箱單**。
1. 選擇 **過帳** 核取方塊。
1. 選擇 **確定**。 裝箱單已發佈至法律實體 BBB。
1. 在 **所有銷售訂單** 清單頁面，選擇公司間銷售訂單。
1. 在動作窗格上，選擇 **發票** 索引標籤，接著選擇 **發票**。
1. 選擇 **過帳** 核取方塊。
1. 選擇 **確定**。

    公司間銷售訂單的客戶發票，以發佈至法律實體 BBB。

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>處理公司間產品收據和廠商發票

如圖所示，在法律實體 AAA 中執行下列步驟。

1. 請前往 **應付帳款 \>採購單\> 所有採購單**。
1. 在 **所有訂購單** 清單頁面，選擇公司間訂購單。
1. 在動作窗格上，選擇 **接收**，接著選擇 **產品收據**。 已建立產品收據。 產品收據號碼與公司間裝箱單號碼相同。
1. 選擇 **過帳** 核取方塊。
1. 選擇 **確定**。
1. 在 **所有訂購單** 清單頁面，選擇公司間訂購單。
1. 在動作窗格上，選擇 **發票**，接著選擇 **發票**。 已建立廠商發票。 廠商發票號碼與公司間客戶發票號碼相同。
1. 完成廠商發票的輸入，然後將其發佈。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
