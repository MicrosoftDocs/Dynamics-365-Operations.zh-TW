---
title: 建立提取看板規則
description: 此程序說明在精益環境中轉移物料的提取看板規則建立所需的設定。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba30e9d09e9eeb0cd7428aafc1195d6b7e7caaa4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448728"
---
# <a name="create-a-withdrawal-kanban-rule"></a>建立提取看板規則

[!include [banner](../../includes/banner.md)]

此程序說明在精益環境中轉移物料的提取看板規則建立所需的設定。 建立此程序的示範資料公司為 USMF。 此程序適用於製程工程師或價值流經理，因為他們會準備新物料或調整後的物料的補貨作業。


## <a name="create-new-kanban-rule"></a>建立新的看板規則
1. 前往看板規則。
2. 按一下新增。
3. 在類型欄位中，選擇「提取」。
    * 提取類型會用於轉移物料或商品的看板規則。  
4. 在第一個計劃活動欄位中，輸入或選擇一個值。
    * 選擇 ReplenishSpeakerComponents。   設定此活動是為了將組件從倉庫 11、位置 11 移動至倉庫 12 和位置 12。  
5. 在產品欄位中，輸入或選擇一個值。
    * 選擇 M0007。  
6. 在前置時間欄位中，輸入一個數字。
    * 例如：60。  
7. 在測量單位欄位中，輸入或選擇一個值。
    * 例如：分鐘。  

## <a name="set-quantities-for-kanban"></a>設定看板數量
1. 將預設數量設為「5」。
    * 這是每個看板會轉移的數量。  
2. 在固定看板數量欄位中，輸入「2」。
    * 這是應為使用中的看板數量。 以此範例而言，這 2 個看板每個都會轉移 5 項產品。  
3. 在警示邊界下限欄位中，輸入「1」。
    * 可追蹤應位於目的地的完整看板的最低數量。 例如，可用於掌握整體看板數量。  
4. 在警示邊界上限欄位中，輸入「2」。
    * 可追蹤應位於目的地的完整看板的最高數量。 例如，可用於掌握整體看板數量。  

## <a name="create-kanbans"></a>建立看板
1. 按一下儲存。
    * 須先儲存看板規則，才能建立看板。  
2. 按一下新增。
    * 請注意，由於此建議的「新看板數量」為 2，相當於「固定看板數量」，因此沒有使用中看板。  
3. 按一下建立。
    * 如此將建立兩個看板。  
    * 請注意，此提取看板規則會建立 2 個看板，每個會處理 5 項產品。  這是此程序的最後一個步驟。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]