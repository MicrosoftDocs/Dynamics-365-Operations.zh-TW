---
title: 主規劃首頁
description: 總體規劃可以讓公司決定和平衡未來所需的原材料和產能需求，以滿足公司目標。
author: ChristianRytt
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7dd25fdd1549fb2fddff57dc2d9cf8762cfd6823
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2021
ms.locfileid: "8447369"
---
# <a name="master-planning-home-page"></a>主規劃首頁

[!include [banner](../includes/banner.md)]

總體規劃的核心，是讓公司決定和平衡未來所需的原材料和產能需求，以滿足公司目標。 總體規劃會評估下列內容：

- 目前有哪些可用的原材料和產能？
- 完成生產需要哪些原材料和產能？ 例如，完成生產之前必須製造、購買、轉移或留作安全庫存的需求。

總體規劃會使用這些資訊，進行需求計算並產生計劃訂單。

三個主要的規劃過程是：

- **總體規劃** - 總體規劃計算淨需求。 根據目前的實際訂單，使公司能夠在短期、日常的基礎上控制庫存補貨。 另一個描述詞彙是 *淨需求計劃*。 如需詳細資訊，請參閱[主計劃概觀](master-plans.md)。

- **預測規劃** - 預測規劃計算總需求。 根據未來的專案 (或預測)，使公司能夠對材料和產能進行長期規劃。 如需詳細資訊，請參閱[需求預測概觀](introduction-demand-forecasting.md)。

- **公司間總體規劃** - 公司間總體規劃計算法人實體之間的淨需求。 建立公司之間的需求和供應的連結，不僅是為短期、明確的需求和供應，同時也是為長期的、計劃的 (尚未確定的) 需求和供應。 如需詳細資訊，請參閱[公司間規劃](planning-optimization/Intercompany-planning.md)。

公司可以變更計劃的輸出。 公司可以執行重新產生、淨變更或是兩者。 重新產生規劃會更新所有需求，而淨變更規劃，僅更新自上次執行以來具有新需求項目的規劃。

總排程通常涉及短期規劃，可能是一星期到六個月不等。 總體規劃模組決定能滿足目前需求 (淨需求) 的供應 (材料) 和產能 (資源) 需求。 在多數公司中，這被擴展為包括待接收產品中最長的累積交貨時間。

## <a name="learning-map"></a>學習地圖

下列學習地圖，顯示總體規劃模組架構的主要概念和任務。 按一下[快速連結](#quick-links)中的連結部分，以瞭解如何使用該模組。

[![總體規劃學習地圖。](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>快速連結

- [主計劃概觀](master-plans.md)  
- [產生受限方案](./tasks/constrained-plan.md)
- [為副產品建立材料規劃](./tasks/create-material-plan-co-products.md)
- [主規劃和多站點功能概觀](master-plan-multisite-functionality.md)
- [建立公司間規劃](./tasks/create-intercompany-plan.md)
- [需求預測概觀](introduction-demand-forecasting.md)
- [預測縮減參數](reduction-keys.md)

## <a name="additional-resources"></a>其他資源

### <a name="roadmaps"></a>藍圖

前往 [Microsoft Dynamics 365 發展藍圖](https://roadmap.dynamics.com/)檢視已發佈的新功能及開發中的新功能。

### <a name="blogs"></a>部落格

您可以在 [Dynamics AX 製造研發團隊部落格](/archive/blogs/axmfg/)和 [Dynamics AX 研發團隊的 Supply Chain Management 部落格](https://blogs.msdn.microsoft.com/dynamicsaxscm)中找到有關總體規劃與其他解決方案的意見、新聞和其他資訊。

### <a name="task-guides"></a>工作指南

將以工作指南的方式提供額外協助。 若要存取工作指南，請按一下任何頁面上的 **說明** 按鈕。

### <a name="webinars"></a>網路研討會

[將 Azure 機器學習用於需求預測](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)

### <a name="tech-conference-recordings"></a>技術會議錄製內容

- [擴展需求預測功能](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
- [總體規劃 - 針對效能進行疑難排解的秘訣和訣竅](https://youtu.be/7v8BPmEs9Dg)
- [MRP 效能微調](https://youtu.be/RLXybx20B5o)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]