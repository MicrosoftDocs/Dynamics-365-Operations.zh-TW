---
title: 規劃最佳化概觀
description: 本主題概述規劃最佳化功能。
author: ChristianRytt
ms.date: 10/31/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 49da88be9faff8f327f8079245b3c07db79308e6
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449706"
---
# <a name="planning-optimization-overview"></a>規劃最佳化概觀

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management的規劃最佳化增益集讓總規劃計算能夠在 Dynamics 365 Supply Chain Management以及相關的 SQL 資料庫外部進行。 與該規劃最佳化功能相關的優點包括在總規劃執行期間提高效能，並對 SQL 資料庫的影響降至最低。 即使在辦公期間也可以快速進行規劃執行，以便規劃員可以立即處理需求或參數的變化。

要使用規劃最佳化，您必須從您的 Microsoft Dynamics Lifecycle Services (LCS) 的項目中安裝規劃最佳化增益集，然後開啟 Supply Chain Management 中的計劃最佳化功能。 有關詳細資訊，請參閱[開始使用規劃最佳化](get-started.md)。

下圖顯示了在辦公時間執行規劃最佳化的優勢。

![在辦公時間執行規劃最佳化的優勢。](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>提高效能

計劃最佳化可用於涉及長期總規劃的情況。 它專為涉及龐大資料量的快速計算而設計。 因為它是作為超大規模的多租戶服務所建立的，所以多個執行個體可以同時協同工作來計算規劃。 此外，規劃服務會從您的系統中移除總規劃的負載，並和會最大限度地減少伺服器負載的資料流一起使用。

規劃最佳化能幫助您實現以下目標：

- 透過更短的執行階段提高規劃效能。
- 減少總規劃執行期間對其他程序的影響。
- 進行更頻繁的規劃執行。 （您不僅限於每日執行。）
- 相信未來的業務增長不會使規劃系統過載。

## <a name="architecture-and-data-flow"></a>架構和資料流

從 LCS 安裝規劃最佳化增益集時，將建立與規劃最佳化服務的安全連接。 該服務與相關的 Supply Chain Management 執行個體位於相同的資料中心國家或地區。 設定規劃最佳化後，在執行總規劃時，主資料和交易資料會從 Supply Chain Management 發送到規劃最佳化服務。

如果解除安裝規劃最佳化增益集，則規劃最佳化服務中的所有相關資料將會被移除。

### <a name="high-level-data-flow-for-regeneration-runs"></a>重新產生執行的高階資料流

1. Supply Chain Management 客戶端發送信號，要求從規劃最佳化規劃執行。
2. 規劃最佳化透過整合連接器要求所需資料。
3. SQL 資料庫透過連接器將有關設定、主資料和交易資料的要求資訊發送到規劃最佳化。 該連接器在 Supply Chain Management 和規劃最佳化服務之間轉換資訊。
4. 規劃最佳化服務將與計劃相關的資料保存在記憶體內並進行所需的計算。
5. 規劃結果透過連接器發送到Supply Chain Management 資料庫。 該結果包括計劃訂單和需求追蹤資訊等資訊。 規劃最佳化發送信號至 Supply Chain Management，以表示規劃執行已完成。 它還發送任何相關訊息和警告。

下圖顯示了資料流。

![重新產生執行的資料流。](media/PlanningOptimization2.png)

## <a name="related-resources"></a>相關資源

[開始使用規劃最佳化](get-started.md)

[規劃最佳化適合度分析](planning-optimization-fit-analysis.md)

[檢視計劃歷程與規劃日誌](plan-history-logs.md)

[將篩選條件套用至計劃](plan-filters.md)

[取消規劃作業](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]