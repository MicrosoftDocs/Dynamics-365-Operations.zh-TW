---
title: 為精益製造建立調撥活動
description: 為精益製造建立調撥活動。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eee0fd510639f2dad78fecb6395c0e31154db6b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448074"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>為精益製造建立調撥活動

[!include [banner](../../includes/banner.md)]

為精益製造建立調撥活動。 

先決條件： 

1. 必須創建生產流程及尚未使用的版本。

2. 必須建立倉庫和位置的出發地與目的地。 或者，也可建立補貨或補貨工作單元。


## <a name="find-the-production-flow-version"></a>尋找生產流程版本
1. 前往生產控制 > 設定 > 精益生產流程 > 生產流程。
2. 在清單中，尋找並選擇所需紀錄。
    * 請注意，生產流程必須有草稿狀態的版本。  
3. 在列表中，按一下所選行中的連結。

## <a name="create-a-new-activity"></a>建立新活動
1. 按一下活動。
    * 確保所選的生產流程中，有一個草稿版本，並選擇該版本。  
2. 按一下創建新計劃活動。
3. 按一下下一步。
4. 在名稱欄位中，輸入一個值。
5. 在活動類型欄位中，選擇「調撥」。
6. 在處理數量欄位中，輸入一個數字。
7. 按一下下一步。

## <a name="select-the-work-cells"></a>選擇工作單元
1. 在補貨欄位中，按一下下拉式按鈕開啟查詢。
    * 若要將工作單元輸出位置當作調撥活動的出發地位置，請選擇工作單元。 補貨工作單元也可採取相同操作，藉此設定調撥活動的目標位置。  
2. 在列表中，按一下所選行中的連結。

## <a name="define-the-inventory-updates"></a>定義庫存更新
1. 在產品類型欄位中，選擇一個選項。
    * 請注意，調撥不會改變產品類型。 您可調撥成品或半成品 (在生產流程的兩個活動間調撥，或是在看板流程的兩個活動間調撥)。     調撥成品時，您可選擇揀貨或收貨是否算是庫存交易。  

## <a name="define-the-transfer-locations"></a>定義調撥位置
1. 按一下下一步。
2. 在倉庫欄位中，按一下下拉式按鈕開啟查詢。
3. 在清單中，尋找並選擇所需紀錄。
4. 在列表中，按一下所選行中的連結。
5. 在位置欄位中，按一下下拉式按鈕以開啟查詢。
6. 在列表中，按一下所選行中的連結。
7. 在運貨人欄位中，選擇「貨運公司」。
    * 選項包括：貨運公司 - 經營貨運倉庫的組織，收件者 - 經營收貨倉庫的組織，承運業者 - 第三方廠商。 若經營組織為廠商，則調撥活動需要分包合約。  
8. 按一下下一步。

## <a name="define-the-activity-times"></a>定義活動次數
1. 在清單中，尋找並選擇所需紀錄。
    * 需要定義執行時間。 執行時間用於計算看板作業的成本和輸送時間。 運行時間不用於計算產能負載和使用量，這是由生產流程版本任務衍伸的週期時間計算。  
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