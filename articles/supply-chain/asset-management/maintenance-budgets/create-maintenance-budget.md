---
title: 建立維護預算
description: 本主題說明如何在資產管理中建立維護預算。
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a375eb7c208479615b2d5e7cf78168ffd7ac8b16c52c85a7ef5a41aa69c947d5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447279"
---
# <a name="create-maintenance-budgets"></a>建立維護預算

[!include [banner](../../includes/banner.md)]

 



維護預算用於提供預防性維護預期成本的概觀。 預算行是根據在預算期間，預期開始日期的維護計劃行計算的。

維護預算基於資產管理中使用的成本類型：**預防性**、**矯正措施**，和 **投資**。 投資維護的預算成本，包括預算期間內，具有更換日期和相關更換成本的活動性資產。 若過往的矯正措施發生日期，包含在計算預算的週期內，則會納入矯正措施維護預算當中。 在這種情況下，早期獲得的矯正措施成本，將會用於計算未來的維護預算。

## <a name="create-a-maintenance-budget"></a>建立一個維護預算

1. 選擇 **資產管理** \> **查詢** \> **維護預算** \> **預算**。
2. 選擇 **創建預算**。
3. 在 **維護預算** 欄位，輸入預算 ID。
4. 在 **描述** 欄位中，輸入描述。
4. 在 FastTab 的 **期間**，**起始日期** 和 **迄今為止** 欄位，輸入預算期間的開始和結束日期。
5. 若要從先前期間，根據實際成本來計算成本預算，以包括矯正措施預算，請在 **矯正措施日期** 欄位，輸入應納入成本計算期間的開始日期。
6. 根據預算所需的詳細程度，可在 FastTab 的 5 個 **群組依據** 設定相關選項。
7. 選擇 **確定**。
8. 選擇 **預算行** 打開 **維護預算行** 頁面，您可以在其中查看已為該期間創建的所有預算行。
9. 若要核准預算，請在 **維護預算** 頁面上，選擇 **核准**。 然後，在 **核准預算** 對話框中，選擇 **確定**。 您的姓名已輸入 **維護預算頁面** 上的 **經過核准** 欄位。

    > [!NOTE]
    > 核准維護預算後，您無法重新計算或調整 **維護預算行** 頁面上相關的行，除非您先移除核准。 若要移除核准的維護預算，請在 **維護預算** 頁面上，選擇 **核准**。 然後，在 **核准預算** 對話框中，選擇 **確定**。

![維護預算。](media/01-maintenance-budgets.png)

您還可以通過複製現有預算來創建新的維護預算。 在 **維護預算** 頁面上，選擇要複製的預算，然後選擇 **複製**。 此方式相當實用，例如，您已創建一個月的預算，並希望將其複製到其他月份。

> [!NOTE]
> 維護預算僅限於以維護計畫行的預算成本進行計算。 若要計算同一時期的實際成本，您可以在 **資產成本控制** 頁面中進行計算。 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]