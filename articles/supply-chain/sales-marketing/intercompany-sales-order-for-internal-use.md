---
title: 建立公司間銷售訂單的發票，以供內部使用
description: 本主題說明如何建立公司間銷售訂單，以供內部使用
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0718a1560ec42df2a0a12e8b81484aa3be46d2d8
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447732"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>建立公司間銷售訂單的發票，以供內部使用

[!include [banner](../../includes/banner.md)]

通常，公司間銷售訂單，會根據公司間訂購單自動建立。 您也可以手動建立公司間銷售訂單，然後在公司間客戶的法律實體中，產生公司間訂購單。

![公司間內部銷售流程](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>手動建立公司間銷售訂單

如圖所示，在法律實體 B 中執行下列步驟。

1. 前往 **應收帳款 \> 銷售訂單 \> 所有銷售訂單**。
1. 在動作窗格上，選擇 **銷售訂單** 以建立銷售訂單。
1. 在 **建立銷售訂單** 頁面上，選擇一個客戶帳戶。 在 **一般** FastTab 上，確保已選取 **公司間** 核取方塊。 這表示，所選的客戶是公司間客戶。
1. 輸入或修改資訊，選擇 **確定**，然後照常完成訂單行。

    從公司間銷售訂單標題，將 **交貨地址** 欄位值，複製到公司間訂購單標題。 從公司間銷售訂單行，將 **品項編號** 欄位，包括產品尺寸，以及 **交貨日期** 和 **貨幣代碼** 欄位值，複製到公司間訂購單行。

1. 在訂單標題中，選擇 **公司間**，檢視相關的公司間訂購單。
1. 在訂單行上，選擇 **公司間**，檢視相關的公司間交易，現有庫存的資訊。

> [!TIP]
> 您可以在 **公司間訂單** 頁面上，檢視公司間銷售訂單。

> [!NOTE]
> 當您與公司間合作時，我們建議您清空 **應收帳款參數** 頁面上的 **開立發票後刪除訂單** 核取方塊。 否則，相關訂購單將被刪除。 我們也建議您清空 **應付帳款參數** 頁面上的 **開立發票後刪除訂購單** 核取方塊。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
