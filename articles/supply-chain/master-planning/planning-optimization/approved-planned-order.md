---
title: 檢視、管理和核准計劃訂單
description: 本主題說明如何在「規劃最佳化」中查看、管理和核准計劃訂單。
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 2d7daac5a33c77e1b49f689061a8dbcf17c3a1d3501461cf3abc0e9cac5121ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446634"
---
# <a name="view-manage-and-approve-planned-orders"></a>檢視、管理和核准計劃訂單

[!include [banner](../../includes/banner.md)]

本主題說明如何在「規劃最佳化」中查看、管理和核准計劃訂單。

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>檢視、管理計劃訂單

您可以在任何計劃訂單列表頁面上查看和管理計劃訂單。 根據您要處理的計劃訂單類型，請移至以下任一位置：

- 主計劃\>工作區\>主計劃
- 主計劃\>主計劃\>計劃訂單
- 產品控制\>生產訂單\>計劃生產訂單
- 採購和開源\>採購訂單\>計劃採購訂單
- 前往庫存管理 \> 入庫訂單 \> 計劃調撥
- 前往庫存管理 \> 出庫訂單 \> 計劃調撥

## <a name="view-and-edit-the-status-of-planned-orders"></a>查看和編輯計劃訂單的狀態

您可以使用每個計劃訂單的 **狀態** 欄位，輔助您追蹤進度或更改計劃訂單的處理方式。 下列 **狀態** 值可用：

- **未處理**–當計劃訂單從主計劃生成時，會被賦予此狀態。 具有此狀態的計劃訂單將在下一次計劃執行時被刪除。
- **完成** – 此狀態表示計劃訂單已完成。 如果您決定不確定計劃訂單，您可以手動將其狀態更改為 *完成*。 請注意，系統將 *未處理* 和 *完成* 狀態以同樣的方式。
- **已核准**–此狀態表示計劃訂單已核准確認。 如果您想要確定計劃訂單，您可以手動將其狀態更改為 *核准*。 如果您想保留對計劃訂單做的編輯，或者如果您打算確定計劃訂單，請將其狀態更改為 *已核准*。 狀態為 *已核准* 的計劃訂單，在主計劃中被認定是固定的和預期的供應。 因此，稍後主計劃執行時不會修改或刪除它們。 為實現此行為，在進行主計劃時，計劃邏輯從舊計劃版本複製狀態為 *已核准* 的計劃訂單到新計劃版本。 注意狀態為 *已核准* 的計劃訂單，僅在指定的主計劃中被認定是固定的和預期的供應。

若要更改單個計劃訂單的狀態，[請打開任何計劃訂單列表頁面](#view-planned-orders)，打開訂單，然後執行以下任一步驟：

- 在 **一般** 快速索引標籤，請更改 **狀態** 欄位的值。
- 在「動作窗格」上，在 **計劃訂單** 索引標籤上的 **處理** 群組中，選取 **更改狀態**。
- 在「動作窗格」上，選取 **核准** 將訂單標記為已核准。

若要同時更改多個計劃訂單的狀態，[請打開任何計劃訂單列表頁面](#view-planned-orders)，對您要更改的每個訂單，選取核取方塊，然後執行以下任一步驟：

- 在「動作窗格」上，在 **計劃訂單** 索引標籤上的 **處理** 群組中，選取 **更改狀態**。
- 在「動作窗格」上，選取 **核准** 將訂單標記為已核准。

## <a name="approve-planned-orders"></a>核准計劃訂單

在從計劃訂單建立確定訂單過程中，計劃訂單的核准是可選步驟。

下圖說明使用每個計劃訂單被指派的 **狀態** 值來實施核准工作流程的方法。 要實施核准流程，請手動調整每個計劃訂單的 **狀態** 值，如上節所述。

![計劃訂單流程](media/approved-planned-orders-1.png)

> [!TIP]
> 我們建議您核准任何修改後的計劃訂單。 否則，編輯將被忽略並被下一次計劃執行覆寫。

## <a name="additional-resources"></a>其他資源

- [確定計劃訂單](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
