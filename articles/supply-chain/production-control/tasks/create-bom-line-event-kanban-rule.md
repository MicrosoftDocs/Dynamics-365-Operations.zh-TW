---
title: 建立 BOM 細項事件看板規則
description: 此工作著重於建立事件看板規則所需的設定，以確保在混合精實和經典生產環境中為生產 BOM 細項提供供應。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14cef6279b756ff71872747dfb1ca9e5c8cd8fcc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448782"
---
# <a name="create-a-bom-line-event-kanban-rule"></a>建立 BOM 細項事件看板規則

[!include [banner](../../includes/banner.md)]

此工作著重於建立事件看板規則所需的設定，以確保在混合精實和經典生產環境中為生產 BOM 細項提供供應。 用於創建此工作的示範資料公司是 USMF。 此工作適用於製程工程師或價值流經理，因為他們會準備新產品或調整後的產品的生產作業。


## <a name="create-a-new-kanban-rule"></a>創建新的看板規則
1. 前往生產控制 > 定期工作 > 看板數量計算 > 看板規則。
2. 按一下新增。
3. 在類型欄位中，選擇「提取」。
    * 提取類型是用於建立轉移看板。  
4. 在補貨策略欄位中，選擇「事件」。
    * 選擇事件策略來建立以事件為基礎的看板轉移。 稍後在工作指南中，我們將透過預估生產訂單來進行觸發。  
5. 在第一個計劃活動欄位中，輸入或選擇一個值。
    * 輸入或選擇 ReplenishSpeakerComponents。 此轉移活動具有接收 (輸出) 倉庫和位置 12，這代表該物料將移動到倉庫 12 中的位置 12。  
6. 展開詳細資訊區段。
7. 在產品欄位中，輸入或選擇 M0001。
8. 展開事件區段。
9. 在 BOM 細項事件欄位，選擇「自動」。
    * 將 BOM 細項事件欄為設定為自動，看板將自動建立以滿足生產訂單 BOM 細項的物料需求。  
10. 關閉頁面。

## <a name="create-and-modify-a-new-production-order"></a>建立並修改新的生產訂單
1. 移至 [生產控制] > [生產訂單] > [所有生產訂單]。
2. 按一下新增生產訂單。
3. 在品項編號欄位中，輸入或選擇一個值。
    * 輸入或選擇「L0001」。 我們使用項目 L0001，因為項目 M0001 包含在項目 L0001 的 BOM 中。  
4. 按一下建立。
5. 在清單中，按一下 L0001 列中的連結
6. 按一下 BOM。
7. 在列表中，按一下所選行中的連結。
8. 按一下編輯。
9. 在細項類型欄位中，選擇「掛鉤供應」。
    * 選擇掛鉤供應以觸發看板的供應建立。  
10. 在資源耗用欄位中選擇否。
    * 清除資源耗用核取方塊，可讓我們變更倉庫。  
11. 展開庫存維度區段。
12. 在倉庫欄位，輸入「12」。
    * 倉庫設為 12，因為這是提取活動的輸出倉庫。  
13. 在位置欄位，輸入「12」。
    * 位置設為 12，因為這是提取活動的輸出位置。  
14. 關閉頁面。
15. 關閉頁面。

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>預估生產訂單並檢視建立的看板
1. 按一下估計。
    * 估計生產訂單將觸發相關看板的建立以供應物料 M0001。  
2. 按一下確定。
3. 關閉頁面。
4. 關閉頁面。
5. 前往產品資訊管理 > 精益製造 > 看板規則。
6. 在列表中，按一下所選行中的連結。
    * 選擇為物料 M0001 建立的事件看板規則。  
7. 展開看板區段。
8. 在清單中，標記所選資料列。
    * 注意為估計生產訂單供應 M0001 而建立的看板。  
    * 這是最後一步！  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]