---
title: 為多個活動創建看板規則
description: 此步驟說明如何創建包含生產流中多個活動的看板規則。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f55034f4f0557023ce0c659c1e8258214cf8bfa3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448194"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>為多個活動創建看板規則

[!include [banner](../../includes/banner.md)]

此步驟說明如何創建包含生產流中多個活動的看板規則。 用於創建此工作的示範資料公司是 USMF。 此工作適用於製程工程師或價值流經理，因為他們會於精益環境中，為新產品或是調整後的產品的準備生產。


## <a name="create-a-new-kanban-rule"></a>創建新的看板規則
1. 前往產品資訊管理 > 精益製造 > 看板規則。
2. 按一下新增。
3. 在補貨策略欄位中，選擇「排程」。
4. 在第一個計劃活動欄位中，輸入或選擇一個值。
    * 選擇 SpeakerAssemblyAndPolish。  
5. 選擇多個活動核取方塊。
    * 目的是在看板規則中包含不止一項活動。 當您選擇最後一個計劃活動時，您會在生產流程中選擇一條路徑。  
6. 在最後一個計劃活動欄位中，輸入或選擇一個值。
    * 選擇 SpeakerTestAndPackaging。 在您選擇值後，會自動打開一個頁面。 選擇看板流程 SpeakerAssemblyAndPolish > SpeakerTestAndPackaging。 按一下確定。  
7. 展開詳細資訊區段。
8. 在產品欄位中，輸入或選擇一個值。
    * 選則項目 L0006。  

## <a name="create-kanban-and-view-jobs"></a>創建看板並查看作業
1. 展開看板區段。
2. 按一下新增。
3. 在新看板的數量欄位中，輸入「1」。
    * 如此將建立 1 個看板。  
4. 將產品數量設為「3」。
    * 看板將處理 3 個產品。  
5. 在截止日期/時間欄位中，輸入日期和時間。
    * 您可以輸入今天。  
6. 按一下建立。
7. 按一下詳細資料。
    * 請注意，看板有兩個來自生產流程的處理作業。 第一個是 SpeakerAssemblyAndPolish，第二個是 SpeakerTestAndPackaging。  
    * 這是最後一步！  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]