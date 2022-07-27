---
title: 使用最低庫存活動創建看板規則
description: 此程序重點在於使用最低庫存事件，來創建看板規則所需的設定，以確保特定產品在特定位置中始終有庫存。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd7e02a8a3bf62606c680dad91d46658775138df
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447930"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a>使用最低庫存活動創建看板規則

[!include [banner](../../includes/banner.md)]

此程序重點在於使用最低庫存事件，來創建看板規則所需的設定，以確保特定產品在特定位置中始終有庫存。 當庫存等級低於 200 件以下時，會建立看板規則以轉移物料至該位置。 透過執行需求追蹤事件處理，可以創建所需的看板。 用於創建此工作的示範資料公司是 USMF。 此工作適用於製程工程師或價值流經理，因為他們會於精益環境中，為新產品或是調整後的產品的準備生產。


## <a name="create-a-new-kanban-rule"></a>創建新的看板規則
1. 前往產品資訊管理 > 精益製造 > 看板規則。
2. 按一下新增。
3. 在類型欄位中，選擇「提取」。
    * 此類型將用於創建轉移看板。  
4. 在補貨策略欄位中，選擇「事件」。
    * 事件策略用來基於事件創建轉移看板。 在程序的稍後部分，您將通過使用庫存補貨來觸發轉移看板。  
5. 在第一個計劃活動欄位中，輸入或選擇一個值。
    * 輸入或選擇 ReplenishSpeakerComponents。 此轉移活動收貨 (輸出) 倉庫和位置 12，這意味著物料將移動到 12 倉庫中的 12 位置。  
6. 展開詳細資訊區段。
7. 在產品欄位中，輸入或選擇一個值。
    * 選擇 M0007。  
8. 展開事件區段。
9. 在庫存補貨事件欄位中，選擇「批次」。
    * 這可以在需求追蹤事件處理的過程中，建立看板，已滿足相關位置的物料需求。  

## <a name="set-the-minimum-quantity-for-the-item"></a>設置項目的最低數量
1. 按一下，以跟隨產品欄位中的連結。
2. 按一下，以跟隨項目編號欄位中的連結。
3. 展開產品圖片 FactBox。
4. 在動作窗格上，按一下計畫。
5. 按一下項目涵蓋。
6. 按一下新增。
7. 在清單中，標記所選資料列。
8. 在倉庫欄位中，輸入或選擇一個值。
    * 將倉庫設定為 12。  
9. 將最低值設定為「200」。

## <a name="run-the-batch-event-creation-job"></a>執行批次處理事件創建作業
1. 前往生產控制 > 定期任務 > 看板作業批處理 > 需求追蹤事件處理。
2. 按一下確定。
3. 前往產品資訊管理 > 精益製造 > 看板規則。
4. 在列表中，按一下所選行中的連結。
    * 選擇您之前創建的看板規則。  
5. 展開看板區段。
    * 請注意，已創建一個看板來將所需物料轉移到倉庫 12。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]