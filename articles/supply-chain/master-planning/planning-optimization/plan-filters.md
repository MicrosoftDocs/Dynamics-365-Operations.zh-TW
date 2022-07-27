---
title: 將篩選條件套用至計劃
description: 本主題說明在使用規劃最佳化功能時如何對計劃使用篩選條件。
author: ChristianRytt
ms.date: 01/08/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 3612dd45a3f4b8c3597c81962a66c21ed14fb206
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2021
ms.locfileid: "8449409"
---
# <a name="apply-filters-to-a-plan"></a>將篩選條件套用至計劃

[!include [banner](../../includes/banner.md)]

使用規劃最佳化功能時，您可以將篩選條件套用至計劃。 **計劃篩選條件** 將一律於總規劃執行期間套用。 當您想要將計劃限制為特定的項目群組，並確保未包含其他項目作為所產生總規劃的一部分時，**計劃篩選條件** 很有用。

如果套用 **計劃篩選條件**，且在總規劃執行期間也會套用執行階段篩選條件，則在規劃執行中只會包含兩個篩選條件的交集。

使用規劃最佳化期間，可從 **總規劃** 中存取 **計劃篩選條件**。

## <a name="example-scenario"></a>範例案例

設定一個規劃篩選條件，其中包含項目 A、B 和 C。接著針對相同的計劃執行總規劃執行，但套用不同的執行階段篩選條件：

- **包含項目 D 的執行階段篩選條件：** 未規劃任何項目，因為規劃篩選條件與執行階段篩選條件之間沒有交集。
- **包含項目 A 和 D 的執行階段篩選條件：** 只有項目 A 包含在規劃執行中，因為項目 D 不是計劃篩選條件的一部分。
- **包含項目 B 的執行階段篩選條件：** 只有項目 B 包含在規劃執行中，且保留項目 A 的先前規劃輸出。
- **包含所有項目的執行篩選條件 (空白篩選條件)：** 項目 A、B 和 C 會包含在計劃執行中，且會覆寫項目 A 和 B 的先前規劃輸出。

> [!NOTE]
> 如果您在 **總規劃參數** 頁面上對選為 **目前動態總計劃** 的計劃設定計劃篩選條件，則動態總計劃功能將限於已篩選的項目。 例如，如果為不屬於計劃篩選條件的項目更新淨需求，將不會產生任何結果。

## <a name="related-resources"></a>相關資源

[規劃最佳化概觀](planning-optimization-overview.md)

[開始使用規劃最佳化](get-started.md)

[規劃最佳化適合度分析](planning-optimization-fit-analysis.md)

[檢視計劃歷程與規劃日誌](plan-history-logs.md)

[取消規劃作業](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
