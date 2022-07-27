---
title: 更新維護預算
description: 本主題說明如何在資產管理中更新維護預算。
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 87c054cb96d56e40e35ee44142396f59d61395263ff41232423f6c7911478b0d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446736"
---
# <a name="update-maintenance-budgets"></a>更新維護預算

[!include [banner](../../includes/banner.md)]

 

**維護預算行** 頁面顯示已經為 **維護預算** 頁面中選擇的預算建立的所有預算行。 (有關詳細資訊，請參閱[建立維護預算](create-maintenance-budget.md)。) 您可以重新計算和調整維護預算行，直到維護預算獲得核准。 預算期間過後，且成本已在資產管理中過帳後，還可以使用實際成本更新預算行。

## <a name="recalculate-a-maintenance-budget"></a>重新計算維護預算

您可以在 **維護預算行** 頁面中重新計算維護預算。 重新計算維護預算時，將刪除現有預算行，並進行新計算。

1. 在 **維護預算行** 頁面上，選擇 **重新計算**。
2. 在 **重新計算預算** 對話方塊中，對新計算進行必要的變更，然後選擇 **確定**。

根據您設定的值建立新的預算行。

## <a name="adjust-budget-lines"></a>調整預算行

您可以調整與預算成本相關的所選行，而不是重新計算整個維護預算。

1. 在 **維護預算行** 頁面上，選擇要為其更新預算成本的行。
2. 選擇 **調整**。
3. 若要對所選行新增金額，請選擇 **新增成本** 核取方塊，然後在 **增加值** 欄位中輸入值。
4. 若要將所選預算行的預算成本乘以係數，請選擇 **相乘成本** 核取方塊，然後在 **相乘值** 欄位輸入系數。

    例如，如果在 **相乘值** 欄位中輸入 **1.2**，則所選行的預算成本增加 20%。 如果輸入 **0.7**，則所選行的預算成本減少 30%。

5. 選取 **確定**。

所選預算行將根據步驟 3 或 4 中設定的值進行更新。

## <a name="update-actual-costs"></a>更新實際成本

預算行的日期過後，且成本已在資產管理中過帳後，可以更新維護預算的實際成本。

1. 在 **維護預算行** 頁面，選擇 **更新成本**。
2. 在 **計算實際成本** 對話方塊，選擇 **確定**。

如果實際成本已過帳，預算行上的 **實際成本** 欄位會更新。 如果在建立預算後建立了新的資產類型，且如果已經對為其建立了工作訂單且為其過帳了關聯的成本的資產使用了這些資產類型，則可能會產生新的預算行。 新的預算行僅顯示實際成本，因為沒有為它們計算預算成本。

> [!NOTE]
> 若要查看拆分為預防成本、糾正成本和投資成本的實際成本概觀，您可以在 **資產成本控制** 頁面中為相同期間執行計算。 

## <a name="manually-add-budget-lines"></a>手動新增預算行

在 **維護預算行** 頁面，您可以選擇 **新增** 手動新增預算行，然後在行上進行選擇。 這種方法也許能在以下情況派上用場：

- 您知道某些資產的整修目前處於計劃階段，但尚未在資產管理中建立相關工作。 但是，您希望將這些作業的預算成本包含在維護預算中。
- 在建立維護預算後已建立了新的資產或資產類型，但尚未針對這些資產或資產類型設定維護計劃。 但是，您希望將這些資產類型的預算成本包含在維護預算中。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]