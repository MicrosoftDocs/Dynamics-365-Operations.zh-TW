---
title: 維護已計劃訂單
description: 本主題提供有關如何管理計劃訂單的資訊。 它描述如何更新計劃訂單的狀態、進行確認，以及篩選與選取的計劃訂單具有相同狀態的計劃訂單。
author: ChristianRytt
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4ec4e50d37403107b31117912423b8bbc8ebb35
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448836"
---
# <a name="maintain-planned-orders"></a>維護已計劃訂單

[!include [banner](../includes/banner.md)]

本主題提供有關如何管理計劃訂單的資訊。 它描述如何更新計劃訂單的狀態、進行確認，以及篩選與選取的計劃訂單具有相同狀態的計劃訂單。

您可以從 **主計劃** 工作區、**計劃訂單** 清單，或 **計劃生產訂單**、**計劃訂購單**，和 **計劃轉移** 清單來管理已計劃的訂單。 

## <a name="planned-order-status"></a>已計劃訂單狀態
您可以使用 **狀態** 欄位以幫助追蹤您的進度。 以下是使用的值：

-   當計劃訂單從主計劃產生時，計劃訂單會被賦予 **未處理** 狀態。
-   如果您決定不確定計劃訂單，您可以其狀態更改為 **完成**。
-   如果您想要確認計劃訂單，您可以手動將狀態變更為 **已核准**。 主計畫會豁免具有 **已核准** 狀態的計劃訂單，因此在之後的主計劃執行期間，該計劃訂單不會被修改或刪除。 為此，在主計劃期間，計劃邏輯會將 **已核准** 的計劃訂單從舊計劃版本複製到新計劃版本。

## <a name="firming-planned-orders"></a>確認計劃訂單 
透過確認計劃訂單，建立真正的訂單。 這些也被稱為 *已發佈* 或 *未結訂單*。 在確認計劃訂單後，將其移至相關模組的訂單區段。

您可以從 **計劃訂單** 頁面選取兩個確認選項：

-   **確認** – 這將確認一個或多個選取的計劃訂單。
-   **確認全部** – 這將確認篩選條件中的所有計劃訂單。 若使用 **確認全部**，則您不必選擇計劃訂單，篩選條件內的所有計劃訂單都將被確認。 如果您要確認大量的計劃訂單，則此選項會很實用。

> [!NOTE]
> 您可以在 **計劃訂單表單 > 檢視 > 確認歷程記錄** 下的 **確認歷程記錄** 中追蹤已確認的計劃訂單。

## <a name="parallelize-firming"></a>並行確認
如果您打算同時確認多個訂單，則並行化執行可以縮短執行時間或提高效能。 當使用 **確認** 或 **確認全部** 確認多個計劃訂單時，則此選項可用。 可以使用以下參數：

-   **並行確認** – 如果為 **是**，則確認過程將與 **執行緒數** 定義的執行緒數量並行。
-   **執行緒數** – 控制用於並行確認過程的執行緒數。 僅在 **並行確認** 設為 **是** 的時候，該參數才會顯示。

> [!NOTE]
> 只有在您選擇了一個以上的計劃訂單進行確認時，**並行確認** 的選項才會顯示。

## <a name="additional-resources"></a>其他資源

[主計劃概觀](master-plans.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]