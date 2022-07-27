---
title: 為製造建立固定數量的看板規則
description: 此程序聚焦於建立固定製造看板規則的必要設定，可觸發精實環境工作單元的調撥活動。
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
ms.openlocfilehash: 16299427a8a6c74e43d7f0eb3ecb3edf4a8f08f0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448953"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>為製造建立固定數量的看板規則

[!include [banner](../../includes/banner.md)]

此程序聚焦於建立固定製造看板規則的必要設定，可觸發精實環境工作單元的調撥活動。 建立此程序的示範資料公司為 USMF。 此程序適用於製程工程師或價值流經理，因為他們會準備新產品或調整後的產品的生產作業。


## <a name="create-new-kanban-rule"></a>建立新的看板規則
1. 前往看板規則。
2. 按一下新增。
    * 請注意，預設類型為製造，補貨原則為固定。 您不必變更這些參數。  
3. 在第一個計劃活動欄位中，輸入或選擇一個值。
    * 這是以此看板規則建立的看板將執行的活動。  選擇「SpeakerTestAndPackaging」。  
4. 展開詳細資訊區段。
5. 在產品欄位中，輸入或選擇一個值。
    * 選擇 L0050。  
6. 在測量單位欄位中，輸入或選擇一個值。
    * 選擇分鐘。  
7. 在前置時間欄位中，輸入一個數字。
    * 輸入 5。  

## <a name="set-quantities"></a>設定數量
1. 展開數量區段。
2. 將預設數量設為「10」。
    * 這是每個看板會轉移的數量。  
3. 選擇產品數量差異核取方塊。
    * 在此，預設數量差異範圍內的所選看板都會完成。  若要完成 8 至 12 個看板，請將兩個差異值都設為 2。  
4. 將差異下限設為「2」。
    * 如此完成數量最少為 10 - 2 = 8  
5. 將差異上限設為「2」。
    * 如此完成數量最多為 10 + 2 = 12  
6. 在固定看板數量欄位中，輸入一個數字。
    * 這是應為使用中的看板數量。 以此範例而言，這 5 個看板每個都會處理 10 項產品。  
7. 在警示邊界下限欄位中，輸入「2」。
    * 可追蹤應位於目的地的完整看板的最低數量。 例如，可用於掌握整體看板數量。  
8. 在警示邊界上限欄位中，輸入「4」。
    * 可追蹤應位於目的地的完整看板的最高數量。 例如，可用於掌握整體看板數量。  
9. 在自動計劃數量欄位中，輸入「1」。
    * 設為 1，代表每個看板都會自動計劃。   若輸入 3，則 3 個空看板準備計劃前，都不會計劃看板。 這對於工作分組非常實用，並避免過多的設定作業。  

## <a name="create-kanbans"></a>建立看板
1. 展開看板區段。
2. 按一下儲存。
    * 須先儲存看板規則，才能建立看板。  
3. 按一下新增。
    * 請注意，由於此建議的「新看板數量」為 5，因此沒有使用中看板。 此數量等於「固定看板數量」。  
4. 按一下建立。
    * 如此將建立 5 個看板。  
    * 請注意，此製造看板規則會建立 5 個看板，每個會處理 10 項產品。 這是此程序的最後一個步驟。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]