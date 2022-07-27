---
title: 變更處理作業的看板規則
description: 此過程著重在對指定看板的變更已使用看板規則。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13798e3521efacda896ca88a39faf36ac979d42c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448731"
---
# <a name="change-kanban-rules-for-a-process-job"></a>變更處理作業的看板規則

[!include [banner](../../includes/banner.md)]

此過程著重在對指定看板的變更已使用看板規則。 這對於平衡負載資源或在故障情況下很有用。 建立此程序的示範資料公司為 USMF。 此程序適用於在精益製造公司工作、負責價值流的計劃人員。


## <a name="copy-kanban-rule"></a>複製看板規則
1. 前往看板規則。
2. 在清單中，尋找並選擇所需紀錄。
    * 為產品 L0001 選取事件看板規則 000022。  
3. 按一下複製看板規則。
4. 按一下確定。

## <a name="change-kanban-rule"></a>變更看板規則
1. 關閉頁面。
2. 前往看板作業排程。
3. 在清單中，標記所選資料列。
    * 選取具有看板 000177 的明細。  
4. 按一下使用替代看板規則。
5. 按一下下一步。
6. 在看板規則欄位中，輸入或選取值。
    * 選取您稍早建立的看板規則。 即為具有最高的看板規則編號的看板規則。  
7. 按一下完成。
    * 現在看板作業正在使用另一個看板規則。 這對於平衡負載工作單元很有用。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]