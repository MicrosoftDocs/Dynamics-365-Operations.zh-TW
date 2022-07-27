---
title: 將看板數量計算原則新增到看板規則
description: 此流程著重在建立看板數量計算原則並將其新增到看板規則，優化看板大小和數量。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a844d455b1e583f234ddc47280f5cac8ee0ab852
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449199"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>將看板數量計算原則新增到看板規則

[!include [banner](../../includes/banner.md)]

此流程著重在建立看板數量計算原則並將其新增到看板規則，優化看板大小和數量。 建立此程序的示範資料公司為 USMF。 此流程供價值流經理使用。 在建立計算看板數量建議流程之前，此流程是其先決條件。 


## <a name="create-a-kanban-quantity-calculation-policy"></a>建立看板數量計算原則
1. 請前往生產控制 > 定期工作 > 看板數量計算 > 看板數量計算原則。
2. 按一下 「新增」。
3. 在名稱欄位中，輸入一個值。
    * 例如，輸入 Speaker2016。  
4. 在主計劃欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，尋找並選擇所需紀錄。
    * 選取 StaticPlan 來計算需求。  
6. 在列表中，按一下所選行中的連結。
7. 按一下「儲存」。
8. 在「最小看板數量」欄位，輸入「1」。
    * 這是看板數量計算中包含的額外看板數量。  
9. 將安全係數設定為「1」。
    * 這是用於計算額外安全庫存數量的係數。  
10. 在「前置天數」欄位中，輸入「30」。
    * 這是需求計算時，在看板數量計算日期之前需包含的天數。  
11. 在「後置天數」欄位中，輸入「30」。
    * 這是需求計算時，在看板數量計算日期之後需包含的天數。  用於計算的公式與實際值一起顯示。 例如，看板數量 = ((平均每日需求 x 提前期 x 2.00) / 每個承辦單位的產品數量) + 1  
12. 關閉頁面。

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>將看板數量計算原則新增到看板規則
1. 前往產品資訊管理 > 精益製造 > 看板規則。
2. 在清單中，尋找並選擇所需紀錄。
    * 為此流程選取看板規則 000020。  
3. 在列表中，按一下所選行中的連結。
4. 切換看板數量計算原則區段的擴充。
5. 按一下「新增」。
    * 新增在上一個子工作中剛建立的看板數量計算原則。  
6. 在清單中，標記所選資料列。
7. 在名稱欄位中，按一下下拉式按鈕開啟查詢。
8. 在列表中，按一下所選行中的連結。
    * 選取在上一個子工作中剛建立的原則 Speaker2016。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]