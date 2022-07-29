---
title: 預算計劃資料分配
description: 本主題介紹 Microsoft Dynamics 365 Finance 中可用的分配方法以及如何使用它們。
author: panolte
ms.date: 03/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6011c4c005a26720fd57caca0075483404f41b4
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451017"
---
# <a name="budget-planning-data-allocation"></a>預算計劃資料分配

[!include [banner](../includes/banner.md)]

本主題介紹 Microsoft Dynamics 365 Finance 中可用的分配方法以及如何使用它們。  

您可以透過多種方式分配預算計劃中的資料，以準確描述預計金額。

## <a name="allocation-methods"></a>分配方法
三種分配方法 (跨期間分配、分配到維度和使用分類帳分配規則) 可以建立根據同一預算計劃中的行的預算計劃行。 其他三種方法 (彙總、分發和從預算計劃複製) 可以在其他預算計劃中建立預算計劃行。 對於全部六種分配方法，您可以指定目標方案。 目標方案可以與來源方案相同，也可以與來源方案不同。 此外，您可以指定是否將新行附加到預算計劃或替換預算計劃中的目前行。

> [!NOTE] 
> 應該使用唯一方案進行彙總，該方案不同於先前在上層計劃中執行的分發或其他修改的方案。  

[![分配到跨期間分配方法。](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**跨期間分配** – 期間分配類別用於跨目標方案中的期間分配來源預算計劃方案中的預算計劃行。 根據期間分配類別中定義的百分比和日期，將來源金額分配給目標方案中的多個行。         

[![分配到維度分配方法。](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**分配給維度** – 根據所選預算分配期限中定義的百分比和財務維度，將預算計劃行從來源預算計劃方案分配到目標方案中的一個或多個行。           

![匯總圖表。](./media/aggregatechart-300x230.png)
**匯總** – 預算計劃行從關聯 (下層) 預算計劃中的來源預算計劃方案彙總到上層預算計劃中的目標方案。 此方法使在組織中較低等級準備的預算金額可以在較高等級進行合併。          

[![分發圖表。](./media/distributechart-300x230.png)](./media/distributechart.png)
**分發** – 根據關聯計劃的組織單位的財務維度，預算計劃行從上層預算計劃中的來源預算計劃方案分發到關聯 (下層) 預算計劃中的目標方案。 此方法使在組織中較高等級準備的預算金額進行分散以實現更在地化審核。           

[![分類帳分配規則。](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**使用分類帳分配規則** – 根據選擇的分類帳分配規則，將預算計劃行從來源預算計劃方案分配到目標方案。 

[![從預算計劃複製。](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**從預算計劃複製** – 與分發分配方法一樣，預算計劃行將根據相關預算計劃中的行在目標中建立。 但是，對於此方法，來源預算計劃不必是上層計劃，而是可以位於預算計劃階層中的任何更高等級。 如果合併金額最初在更高等級進行預算，並且必須轉移到組織的較低等級進行詳細審查和調整，然後才能獲得上層核准，則此分配方法會很實用。          

## <a name="using-allocation-methods-in-a-budget-plan"></a>在預算計劃中使用分配方法
要在預算計劃頁面上執行分配，請選擇要分配的行，然後點擊 **分配預算**。

[![分配預算按鈕。](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

接下來，選擇分配方法。 然後根據您選擇的方法設定其餘欄位。 這些欄位包括預算計劃資料的來源和目標以及一個選項，此選項可讓您在建立目標金額時將來源乘以指定的係數，以簡化大量調整。 您還可以設定 **附加到計劃** 選項。 選擇 **否** 替換現有的預算計劃行，或選擇 **是** 保留現有預算計劃行並為分配的金額新增行。

## <a name="automating-allocations-during-a-workflow"></a>在工作流程中自動分配
這種強大的功能可讓分配作為預算計劃工作流程的一部分自動執行。 隨著預算計劃透過其工作流程，自動化工作可以在指定的預算計劃階段叫用分配。 

要設定自動分配，您必須先在 **預算計劃設定** 頁面上建立分配計劃。 分配計劃定義了執行自動分配時將使用的分配方法，以及各種分配選項的值 (請參見上一節中的說明)。 

接下來，在 **預算計劃設定** 頁面上建立階段分配。 階段分配將分配計劃指派給預算計劃工作流程和階段。 

最後，在所需的工作流程階段為預算計劃階段分配新增自動化工作。 在以下範例中，已將兩個預算計劃階段分配 (以紅色標出) 插入到工作流程中。

[![預算編製階段分配。](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
