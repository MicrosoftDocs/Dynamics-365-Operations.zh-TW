---
title: 建立銷售事件看板規則
description: 此程序著重於建立在銷售訂單建立期間觸發的看板規則所需的設定。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3cd2b579e542b9f905fc51b63f2120e5a5c883ae
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447933"
---
# <a name="create-a-sales-event-kanban-rule"></a>建立銷售事件看板規則

[!include [banner](../../includes/banner.md)]

此程序著重於建立在銷售訂單建立期間觸發的看板規則所需的設定。 事件看板規則補貨需求 (源自銷售訂單明細)。 建立此程序的示範資料公司為 USMF。 這適用於製程工程師或價值流經理，因為他們會準備新產品或調整後的產品的生產作業。




## <a name="create-a-new-kanban-rule"></a>創建新的看板規則
1. 前往看板規則。
2. 按一下新增。
3. 在補貨策略欄位中，選擇「事件」。
    * 選擇事件表示看板規則由事件觸發，例如建立銷售訂單明細。   這適用於每個看板應涵蓋特定需求的區域。  
4. 在第一個計劃活動欄位中，輸入或選擇一個值。
    * 選擇最終組件。  
5. 展開詳細資訊區段。
6. 在產品欄位中，輸入或選擇一個值。
    * 選擇 L0050。  

## <a name="define-an-event"></a>定義事件
1. 展開事件區段。
2. 在銷售事件欄位，選擇「自動」。
    * 透過選擇銷售事件自動，當銷售明細與產品和收貨地點相符時，將自動觸發此看板規則。 在此程序中，它是倉庫 13 上的產品 L0050。  
3. 將最小事件數量設定為「50」。
    * 最小事件數量為 50 的情況下，看板規則只會被數量為 50 或更多的事件觸發。  
4. 展開生產流程部分。
    * 請注意，收貨地點是倉庫 13。 這代表將為此位置觸發此看板規則。  
    * 在此範例中，倉庫 13 上數量為 50 或更多產品 L0050 的銷售明細將觸發此看板規則。  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>建立銷售明細以觸發事件看板規則
1. 前往所有銷售訂單。
    * 儲存看板規則時系統會顯示警告，這代表在建立銷售訂單期間將即時建立看板。  
2. 按一下新增。
3. 在客戶帳戶欄位中，輸入或選擇一個值。
    * 例如，選擇 US-003。  
4. 按一下確定。
5. 在項目編號欄位中輸入「L0050」。
6. 在站點欄位，輸入「1」。
    * 選擇站點 1，因為倉庫 13 位於站點 1。  
7. 在倉庫欄位中，輸入或選擇一個值。
    * 將倉庫設定為 13。  
8. 將數量設為「75」。
    * 輸入 50 或更大的數量，以觸發建立的看板規則。  

## <a name="verify-that-kanban-is-created"></a>驗證看板是否已建立
1. 按一下產品和供應。
2. 按一下查看需求追蹤樹。
    * 注意與銷售明細數量相同的看板已建立。 您也可以看到生產 L0050 所需的物料問題。 這是此程序的最後一個步驟。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]