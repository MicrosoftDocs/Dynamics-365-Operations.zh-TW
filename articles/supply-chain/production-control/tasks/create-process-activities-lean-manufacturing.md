---
title: 為精益製造創建流程活動
description: 為精益製造創建流程活動。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup, PlanActivityDetails, KanbanJobPickingListPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 214e54cc93379948e4c25b3b28d835bbbbd40b72
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448275"
---
# <a name="create-process-activities-for-lean-manufacturing"></a>為精益製造創建流程活動

[!include [banner](../../includes/banner.md)]

為精益製造創建流程活動。 

先決條件： 

1. 必須創建生產流程及尚未使用的版本。

2. 必須創建一個工作單元。


## <a name="find-the-production-flow-version"></a>尋找生產流程版本
1. 前往生產控制 > 設定 > 精益生產流程 > 生產流程。
2. 在清單中，尋找並選擇所需紀錄。
3. 在列表中，按一下所選行中的連結。

## <a name="create-a-new-activity"></a>建立新活動
1. 按一下活動。
    * 確保所選的生產流程中，有一個草稿版本，並選擇該版本。  
2. 按一下創建新計劃活動。
3. 按一下下一步。
4. 在名稱欄位中，輸入一個值。
5. 在名稱欄位中，輸入一個值。
    * 請注意，對於所有版本的生產流程，名稱都必須是唯一的。  
6. 在處理數量欄位中，輸入一個數字。
    * 請注意，無論作業處理多少數量，這是每個作業計算人工成本的最小數量。 如果作業數量與此數量有偏差，則會產生人工成本差異。  
7. 按一下下一步。

## <a name="select-the-work-cell"></a>選擇工作單元
1. 在工作單元欄位中，按一下下拉式按鈕開啟查詢。
2. 在列表中，按一下所選行中的連結。

## <a name="define-the-inventory-updates"></a>定義庫存更新
1. 選擇或清除更新現有收據核取方塊。
    * 如果更新現有數量 = 否，您可以定義接收半成品的活動 (活動未達到下一個 BOM 級別)。    您也可以選擇使用半成品。  

## <a name="define-the-picking-activities"></a>定義挑選活動
1. 按一下下一步。
2. 在清單中，標記所選資料列。
    * 已經為所選的工作單元中的所有輸入位置，創建預設挑選活動。  
3. 按一下新增。
    * 您可以為還沒暫存至工作單元輸入活動中特定產品，創建其他挑選活動。  
4. 在清單中，尋找並選擇所需紀錄。
5. 在項目編號欄位中，輸入一個值。
6. 在倉庫欄位中，按一下下拉式按鈕開啟查詢。
    * 使用此定義，活動中使用的所有材料，均會從預設輸入倉庫和位置中挑選，但在第二個挑選活動中定義的項目除外。 此項目將從不同的倉庫和位置挑選。  
7. 在清單中，尋找並選擇所需紀錄。
8. 在列表中，按一下所選行中的連結。
9. 選擇或清除登記報廢核取方塊。
10. 按一下下一步。

## <a name="define-the-activity-times"></a>定義活動次數
1. 在清單中，尋找並選擇所需紀錄。
    * 需要定義執行時間。 執行時間用於計算看板作業的成本和輸送量時間。 運行時間不用於計算產能負載和使用量，這是由生產流程版本任務衍伸的周期時間計算。  
2. 在時間欄位中，輸入一個數字。
3. 在單位欄位中，輸入一個值。
4. 選擇時間單位。
5. 在每個數量欄位中，輸入一個數字。
6. 在清單中，尋找並選擇所需紀錄。
    * 佇列時間為選填。  
7. 在時間欄位中，輸入一個數字。
8. 在單位欄位中，輸入一個值。
9. 選擇時間單位。
10. 在每個數量欄位中，輸入一個數字。
11. 按一下下一步。
12. 按一下完成。
13. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]