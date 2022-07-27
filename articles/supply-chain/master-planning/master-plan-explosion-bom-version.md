---
title: BOM 版本的擴展
description: 本文章說明涉及物料清單 (BOM) 版本擴展的主計劃方案。
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be4dfc85ad7ab01df9a95a394896873e2d649e12
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448788"
---
# <a name="explosion-of-a-bom-version"></a>BOM 版本的擴展

[!include [banner](../includes/banner.md)]

本文章說明涉及物料清單 (BOM) 版本擴展的主計劃方案。

物料清單 (BOM) 版本的需求擴展會在特定位置 (也可能在特定倉庫) 對每個 BOM 行項目建立需求。 在特定位置的 BOM 中，可以為每個 BOM 行定義一個特定倉庫。 此外，對於每個 BOM 行，物料的維度設定會決定是否需要倉庫。 然後，每個 BOM 行項目的最終需求會成為額外需求擴展的起點。 此總體規劃情境涉及以下條件：

-   位置維度是強制性的，並且必須輸入需求交易。
-   位置維度是一致的。 因此，較低層級需求的位置與初始需求交易的位置相同。

下列圖示顯示主計劃需求擴展的過程。 ![使用 BOM 版本的需求擴展。](./media/multisitedemandexplosionscenariousingbomversion.gif)

## <a name="additional-resources"></a>其他資源

[確定 BOM 版本](master-plan-bom-version-determined.md)

[主規劃和多站點功能概觀](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]