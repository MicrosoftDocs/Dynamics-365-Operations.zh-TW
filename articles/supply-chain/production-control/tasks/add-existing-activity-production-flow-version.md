---
title: 將現有活動新增到生產流程版本
description: 建立新版本的生產流程時，您可以選擇將在舊版本建立的活動新增到新版本中。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f73274c6e102df3007793e027587793d87c4f83
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449202"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>將現有活動新增到生產流程版本

[!include [banner](../../includes/banner.md)]

建立新版本的生產流程時，您可以選擇將在舊版本建立的活動新增到新版本中。 此流程介紹如何為現有生產流程建立新版本，且無須複製活動。 在下一步，將現有活動新增到新版本中。 

此工作需要已建立版本和活動的生產流程。


## <a name="create-a-new-production-flow-version"></a>建立新的生產流程版本
1. 前往生產控制 > 設定 > 精益生產流程 > 生產流程。
2. 在清單中，尋找並選擇所需紀錄。
3. 在列表中，按一下所選行中的連結。
4. 按一下「編輯」。
5. 在清單中，標記所選資料列。
6. 在到期日欄位中，輸入日期和時間。
    * 請注意，在建立新的生產流程版本之前，請務必檢查活動版本的到期日和時間。 新建的版本會有一個有效的開始日期，且與選定版本的到期日相關聯。  
7. 按一下「新增」。
8. 在「從版本中複製」欄位中選取「否」。
    * 如果複製版本的大部分活動將被新活動替換，則選取「否」從空白版本開始。 手動將未更改的活動新增到活動表單中的「新增現有」功能。  
9. 在「重複看板規則」欄位中選取「否」。
    * 當沒有複製活動到新版本時，無法在建立新版本時複製看板規則。   相反，您稍後將在看板規則表單中使用建立替換看板功能，將舊生產流程版本的看板規則替換為使用新版本活動的看板規則。  
10. 按一下「確定」。
11. 在清單中，尋找並選擇所需紀錄。

## <a name="add-an-existing-activity"></a>新增現有活動
1. 按一下「活動」。
2. 按一下「新增現有」以打開下拉式對話方塊。
    * 查找並選取現有活動，新增到新生產流程版本。  請注意，該列表內為建立給此生產流程的所有活動，用於流程的所有舊版。  
3. 在活動欄位中，輸入或選取一個值。
4. 按一下「確定」。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]