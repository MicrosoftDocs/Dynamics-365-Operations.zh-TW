---
title: 交貨排程
description: 當您對單一銷售訂單、銷售報價或採購單使用多個交貨時，交貨排程可讓您追蹤訂單明細數量。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b50558c5da71351082d36276a3185e1f91543f2b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448620"
---
# <a name="delivery-schedules"></a>交貨排程

[!include [banner](../includes/banner.md)]

當您對單一銷售訂單、銷售報價或採購單使用多個交貨時，交貨排程可讓您追蹤訂單明細數量。

當訂單或報價明細上的總數量必須分多次裝運交貨時，請使用交貨排程。 單一裝運會依交貨明細表示。 兩則以上則交貨明細會構成一個交貨排程。 交貨明細可有不同交貨日期、數量、交貨模式和儲存維度，例如站點和倉庫。  

**交貨排程範例**

| 項目                              | 值                                    |
|-----------------------------------|------------------------------------------|
| 總訂單 (原始訂單明細) | 600 張椅子                               |
| 要求的交貨排程       | 每月 100 張椅子                     |
| 要求的交貨時間範圍 | 6 個月，每個月的第一天 |

在這種情況下，客戶要求在六個月內分批交貨 600 張椅子，每批 100 張椅子。 如要追蹤交貨要求，您可以建立交貨排程。 在交貨排程頁面上，您會建立六個單獨的交貨明細。 每個交貨明細包含 100 張椅子，並指明這 100 張椅子的交貨日期。 在這種情況下，每個明細會連續六個月，在每月的第一天被沖銷。  

建立交貨排程時，原始訂單明細的類型會自動變更為 **具有多個交貨的訂單明細**。 此類型的明細稱為商業明細，並用圖示標記。 交貨明細由不同的圖示進行標記。 如果您變更交貨明細上的數量，商業明細將更新為交貨排程的總數量。 如果貿易合約定義了訂單的總折扣，則交貨排程可確保您的訂單有資格取得總訂單折扣，即使訂單被拆分為單獨的交貨也一樣。  

具有交貨排程的訂單，將依據交貨明細進行處理。 處理包括裝箱單的過帳、產品收據和發票開立。  

具有交貨排程的訂單和報價單之文件列印輸出僅會顯示交貨明細。 它們不會顯示原始明細 (商業明細)。 **注意：** 此外，在您執行這些動作時，系統僅會顯示交貨明細：

-   張貼
-   複製頁面
-   瀏覽清單頁面和報告

在您確認銷售報價時，產生的銷售訂單會顯示整個交貨排程，甚至是具有多個交貨的訂單明細。 此外，整個交貨排程會顯示在所有主要頁面上，例如銷售訂單、銷售報價和採購訂單。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]