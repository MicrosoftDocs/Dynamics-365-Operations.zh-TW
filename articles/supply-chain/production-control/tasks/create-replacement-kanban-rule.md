---
title: 建立取代看板規則
description: 此程序重點是使用特定日期的新看板規則，取代現有的看板規則。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2db44c1b43a6dc5e0ab37a7756c4eecaab468e15
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448272"
---
# <a name="create-a-replacement-kanban-rule"></a>建立取代看板規則

[!include [banner](../../includes/banner.md)]

此程序重點是使用特定日期的新看板規則，取代現有的看板規則。 當要需要協調和安排生產流程或補貨規則的變更時，這會很有幫助。 創建此程序的示範資料公司為 USMF。 此程序適用於製程工程師或價值流經理，當他們會為變更後的生產流程，或是新的補充規則準備生產。 此任務將看板規則 000022 替換為新規則，並將新規則的最大數量從 48 增加到 100。


## <a name="select-a-kanban-rule-to-replace"></a>選擇一個要替換的看板規則
1. 前往看板規則。
2. 在清單中，尋找並選擇所需紀錄。
    * 選擇看板規則 000022。  

## <a name="create-a-replacement-kanban-rule"></a>建立取代看板規則
1. 按一下取代看板規則。
2. 在生效日期欄位中，輸入日期和時間。
    * 選擇未來的日期，例如：從現在起一周。 這是新看板規則生效並替換舊看板規則的日期和時間。  
    * 如果看板規則變更了生產流程中的路徑，則可以選擇另一個活動。  在此程序中，我們將保持活動不變。  
3. 按一下確定。
    * 請注意，以創建一個新的看板規則，以替換看板規則 000022。  
    * 生效日期是根據您替換看板規則時選擇的日期設定。  
4. 在清單中，尋找並選擇所需紀錄。
    * 選擇替換的看板規則 000022。  
    * 請注意，被替換的看板規則具有與到期日期相同的日期，因為這是它將到期的日期。  
5. 在清單中，選擇第 1 列。
    * 選擇列表頂部新的看板規則。 此看板規則具有最高的看板規則編號。  
6. 在列表中，按一下所選行中的連結。
    * 按一下看板規則編號，以打開看板規則。  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>修改替換看板規則的最大數量
1. 將最大數量設定為「100」。
    * 展開數量 FastTab 以查看最大數量欄位。 將最大數量變更為 100，以允許處理多達 100 個看板。    這是此工作的最後一個步驟。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]