---
title: 定義精益作業計畫群組
description: 定義精益作業計畫群組後，即可在看板排程中將產品分組與區分。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9d16c0d3192773c32c8dcc57a430607c6b60f97
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448722"
---
# <a name="define-lean-schedule-groups"></a>定義精益作業計畫群組

[!include [banner](../../includes/banner.md)]

定義精益作業計畫群組後，即可在看板排程中將產品分組與區分。 此分組可做為公司的一般關聯，或特定工作單元的關聯。 每個群組都會指派顏色代碼，在看板排程清單頁面中展現視覺效果。 建立此程序的示範資料公司為 USMF。


## <a name="define-lean-scheduling-group"></a>定義精益作業計畫群組
1. 移至產品資訊管理 > 精益製造 > 精益作業計畫群組。
2. 按一下新增。
3. 在計畫群組欄位中，輸入一個值。
    * 計畫群組可定義為全域群組或專屬特定工作單元。 在此簡單的範例中，我們定義全域群組，工作單元則保持空白。 此群組設定會套用至沒有特定計畫群組的所有工作單元。  
4. 從色彩選項中選擇一個顏色。
    * 此顏色會用於突顯看板排程清單頁面或看板流程板上的作業。  
5. 在清單中，標記所選資料列。
6. 在列表中，按一下所選行中的連結。

## <a name="associate-product"></a>與產品建立關聯
1. 與特定產品建立關聯
    * 將產品與精益作業計畫群組建立關聯有兩種方式：以特定產品 (項目關係類型 = 項目) 或以項目分配索引鍵的一部分 (項目關係類型 = 群組) 來建立關聯。    
2. 在項目關係類型欄位中，選擇項目
3. 在項目編號欄位中，輸入一個值。
4. 在輸送量比率欄位中，輸入一個數字。
    * 預設輸送量比率為 1，代表相關產品消耗的產能與生產流程處理活動指定的產能完全一樣。 輸送量比率 > 1 代表資源消耗較多，輸送量比率 < 1 代表資源消耗較少。 此比率可用於計算成本與看板作業耗用量。  

## <a name="associate-item-allocation-key"></a>與項目分配索引鍵建立關聯
1. 與項目分配索引鍵建立關聯
    * 使用項目關係類型群組，新增項目分配索引鍵的關聯。   請注意，以此流程而言，您需要預測資料內定義的項目分配索引鍵。  
2. 在項目關係類型欄位中，選擇群組
3. 在項目分配索引鍵欄位中，按一下下拉式按鈕開啟查詢。
4. 在列表中，按一下所選行中的連結。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]