---
title: 追蹤品項或原材料
description: 此程序會展示如何使用品項追蹤來識別品項或原材料已使用或正在使用的位置。
author: yufeihuang
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c01cabf32542798f70720ab0db7d055fc54cf345
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448845"
---
# <a name="trace-an-item-or-raw-material"></a>追蹤品項或原材料

[!include [banner](../../includes/banner.md)]

此程序會展示如何使用品項追蹤來識別品項或原材料已使用或正在使用的位置。 透過此程序，您可以識別一個品項，將其追溯到源頭，然後透過成品的生產和銷售進行追溯。 該程序可用於調查受影響的客戶、受影響的銷售訂單等。 在示範資料公司 USP2 中可以使用此程序。


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>使用已知的批號追溯品項
1. 在 **功能窗格** 中，前往 **模組 > 庫存管理 > 查詢和報告 > 追蹤維度 > 品項追蹤**。
2. 在 **品項編號** 欄位中，選擇「P9100」。
3. 在列表中，按一下所選行中的連結。
4. 在裡面 **正向或逆向** 欄位中，選擇「逆向」。
5. 在裡面 **批號** 欄位中，選擇「as-12-344-01」。
6. 在列表中，按一下所選行中的連結。
7. 按一下 **確定**。

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>識別一個品項，正向追踪並進行分析

樹狀結構的頂部節點代表所選品項和批次的現有數量。 您必須展開樹狀結構的節點，以找到應該執行正向追蹤的品項。   
1. 在樹狀結構中，展開「下方描述的節點，然後選擇最後一個節點」。
    
    展開：'P9100 / 1 / 10 / as-12-344-01 ● 2 桶 ● 7.00 gal \P9100 ● 揀貨 ● 銷售訂單 000072 ● 2015 年 12 月 22 日 ● -1 桶 ● -4.00 gal ● 站點=1，倉庫=10，批號=as-12-344-01 \P9100 ● 生產 B-000050 ● 12/9/2015 ● 7 桶 ● 27.00 加侖 ● 站點=1，倉庫=10，批號=as-12-344-01 ● 聯產品：P9101'，然後選擇該節點。     
2. 在樹狀結構中，展開「下方描述的節點，然後選擇該節點」。
    
    從剛剛選擇的節點開始，展開 'M9103 ● 生產線 B-000050 ● 12/9/2015 ● -160.00 lb ● Size=70, Color=OK, Site=1, Warehouse=10, Batch number=App01 ' 然後選擇該節點。  
3. 點擊 **從節點追蹤**。
4. 按一下 **正向**。
5. 在 **動作窗格** 上，按一下 **追蹤**。
    
    有幾個追蹤選項可提供有關受您正在追蹤的品項影響的客戶的資訊，以及與已發貨和尚未發貨的品項相關的銷售訂單。   
6. 點擊 **顧客**。
7. 關閉頁面。
8. 在 **動作窗格** 上，按一下 **追蹤**。
9. 按一下 **運送銷售訂單**。
10. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]