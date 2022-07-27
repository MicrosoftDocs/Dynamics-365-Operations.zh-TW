---
title: 建立活動關係 - 後續者
description: 精實生產流程中的活動流程會透過活動關係記錄下來。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8cee0c75de1fee24cfb6df018de62ece102c96cc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449190"
---
# <a name="create-activity-relation---successor"></a>建立活動關係 - 後續者

[!include [banner](../../includes/banner.md)]

精實生產流程中的活動流程會透過活動關係記錄下來。 此記錄會顯示如何建立活動關係。

先決條件：

- 草稿模式下的生產流程和版本。 

- 在生產流程中已建立兩個相互跟隨但不相關的活動。


## <a name="find-the-production-flow-version"></a>尋找生產流程版本 
1. 前往生產控制 > 設定 > 精益生產流程 > 生產流程。
2. 在清單中，尋找並選擇所需紀錄。
3. 在列表中，按一下所選行中的連結。
4. 在清單中，標記所選資料列。
5. 在清單中，選擇一個草稿版本。
    * 活動關係可以新增到生產流程的草稿或使用中版本中。  

## <a name="open-the-activity-overview"></a>打開活動概觀
1. 按一下活動。
    * 請注意，該表單顯示了分配給您正在使用的生產流程版本之生產流程所有活動。  

## <a name="add-a-successor"></a>新增後續者
1. 按一下新增後續者。
2. 在活動欄位中，按一下下拉式按鈕開啟查詢。
3. 在清單中，尋找並選擇所需紀錄。
4. 在列表中，按一下所選行中的連結。
5. 選擇限制核取方塊。
6. 在限制值欄位中，輸入一個數字。
    * 限制時間是在先行者的計劃結束 (到期日和時間) 和後續者的計劃開始之間要計劃的時間。  
7. 在單位欄位中，輸入一個值。
8. 在週期比率欄位中，輸入一個數字。
    * 如果兩個活動以相同的產距執行，則週期比率應為 1。 如果先行者以後續者的雙倍速度執行，則比率應為 2。   週期比率是用於計算生產流程活動的個別週期。  
9. 按一下確定。
10. 關閉頁面。
11. 按一下 GridPanel 索引標籤。
12. 關閉頁面。
13. 重新整理頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]