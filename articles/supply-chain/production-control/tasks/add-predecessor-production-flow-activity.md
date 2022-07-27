---
title: 將前置活動新增到生產流程活動
description: 在生產流程版本中，所有活動都必須按順序排列。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc1aa742013faeeb545d746f9715c639a5b66b9b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448785"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>將前置活動新增到生產流程活動

[!include [banner](../../includes/banner.md)]

在生產流程版本中，所有活動都必須按順序排列。 一個活動可以有一個或多個前置活動或後繼活動。 

此流程顯示如何將前置活動與活動相關聯。 

要執行此工作，您需要一個具有草稿版本的生產流程，其中至少有兩個可以連接的活動。 

若要瞭解更多，請閱讀白皮書「精益製造中的生產流程和活動」。


## <a name="find-the-production-flow-and-version"></a>尋找生產流程和版本
1. 前往生產控制 > 設定 > 精益生產流程 > 生產流程。
2. 在清單中，尋找並選擇所需紀錄。
3. 在列表中，按一下所選行中的連結。
4. 在清單中，尋找並選擇所需紀錄。
5. 按一下「活動」。

## <a name="select-an-activity-and-add-a-predecessor"></a>選擇一個活動並新增一個前置活動
1. 在清單中，尋找並選擇所需紀錄。
2. 按一下新增前置活動。
3. 在活動欄位中，輸入或選取一個值。
4. 在週期比率欄位中，輸入一個數字。
    * 活動關係的預設週期時間比率為 1。 這假設兩個活動以相同的速度或產距時間執行。 如果前置活動以較高的速度 (較低的產距時間) 運行，則該比率應小於 1，如果前置活動以較慢的速度 (較高的產距時間) 運行，則週期比率應大於 1。  
5. 按一下「確定」。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]