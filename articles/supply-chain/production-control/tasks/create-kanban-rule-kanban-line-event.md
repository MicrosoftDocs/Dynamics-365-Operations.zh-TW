---
title: 使用看板行事件創建看板規則
description: 此程序通過使用看板行事件，設置提取流程活動的觸發器，以創建看板規則。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7aaf959db0f0a136fc615f9a57ec787ef6cf2ad
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449184"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>使用看板行事件創建看板規則

[!include [banner](../../includes/banner.md)]

此程序通過使用看板行事件，設置提取流程活動的觸發器，以創建看板規則。 看板規則由看板流程活動觸發，每個數量等於或大於 25。 用於創建此工作的示範資料公司是 USMF。 此工作適用於製程工程師或價值流經理，因為他們會於精益環境中，為新產品或是調整後的產品的準備生產。


## <a name="create-a-kanban-rule"></a>創建看板規則
1. 前往產品資訊管理 > 精益製造 > 看板規則。
2. 按一下新增。
3. 在補貨策略欄位中，選擇「事件」。
    * 直接根據需求生成看板。 設定根據訂單生產情況定義的規則。  
4. 在第一個計劃活動欄位中，輸入或選擇一個值。
    * 輸入或選擇 SpeakerAssemblyAndPolish。 製作看板規則的第一個活動，就是生產流程中的處理活動。 當您選擇活動時，活動的有效日期將復製到看板規則的有效日期。  
5. 展開詳細資訊區段。
6. 在產品欄位中，輸入「L0001」。
7. 展開事件區段。
8. 在看板行事件欄位，選擇「自動」。
    * 這會根據需求生成事件看板。  該欄位用於配置看板規則，以補充下游流程活動中所需的材料。 當您選擇自動時，會根據需求創建事件看板。 如果您希望在同一天執行生產，則建議使用此設定。  
9. 將最小事件數量設定為「25」。
    * 當需求數量等於或大於該欄位時，會生成事件看板。 如果您希望在一台機器上生產的訂單數量少於此欄位，而在另一台機器上生產的訂單數量多於此欄位，這將非常實用。  
10. 按一下儲存。

## <a name="create-sales-order-and-trigger-kanban-chain"></a>創建銷售訂單和看板鏈觸發程序
1. 前往銷售和行銷 > 銷售訂單 > 所有銷售訂單。
2. 按一下新增。
3. 在客戶帳戶欄位中，輸入或選擇一個值。
    * 選擇客戶帳戶 US-003，Forest Wholesales。  
4. 按一下確定。
5. 在品項編號欄位中輸入「L0001」。
    * L0001 是您為其創建看板規則的項目。  
6. 將數量設為「27」。
    * 因為 27 高於看板規則上的最小數量 25，這將觸發事件看板。  
7. 在站點欄位，輸入「1」。
8. 在倉庫欄位中，輸入或選擇一個值。
    * 選擇倉庫 13。  
9. 按一下儲存。

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>查看看板規則生成的看板
1. 前往產品資訊管理 > 精益製造 > 看板規則。
2. 在清單中，尋找並選擇所需紀錄。
3. 展開看板區段。
    * 請注意，已創建 27 的看板，以根據已創建的看板規則處理活動。  
    * 這是最後一步。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]