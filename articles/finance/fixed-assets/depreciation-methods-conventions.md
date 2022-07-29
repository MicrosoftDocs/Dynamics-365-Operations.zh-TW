---
title: 折舊方法和慣例
description: 本文概述了 Microsoft Dynamics 365 Finance 支援的折舊慣例和折舊方法。
author: moaamer
ms.date: 12/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f0f3b8be86225fd68df9b099e5c8e13a220a213
ms.sourcegitcommit: a5861c2fef4071e130208ad20e26cb3a42a45cf1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2021
ms.locfileid: "8451311"
---
# <a name="depreciation-methods-and-conventions"></a>折舊方法和慣例

[!include [banner](../includes/banner.md)]

本文概述了支援的折舊慣例和折舊方法。

您可以選擇各種折舊方法和慣例。 這些方法的目的是將固定資產的折舊價值分攤到各會計期間。 固定資產的可折舊價值是購置價格減去殘值 (如果有)。 

如果您在使用折舊慣例並修改資產的最後折舊開始日期，這會導致跳過某些折舊，則上一年的折舊可能高於或低於預期。 折舊根據受上次折舊執行日期修改影響的折舊期數進行調整。

例如，如果您在三年後使用半年折舊慣例，則折舊通常在三年半發生。 如果您在三年半的期間中變更最後折舊開始日期，則折舊的最後一年會移出受影響的期間外。 如果您將日期移動三個月，則去年將有九個月的折舊價值，而正常情況下是有六個月的折舊價值。

您可以從以下折舊慣例中進行選擇。


-   半年
-   整個月
-   季中
-   月中 (每月第 1 天)
-   月中 (每月第 15 天)
-   半年 (年度開始)
-   半年 (下一年)

您可以從以下折舊方法中進行選擇。
-   直線法使用年限
-   餘額遞減法
-   手動
-   係數
-   消耗
-   直線法 (剩餘年限)
-   200% 餘額遞減法
-   175% 餘額遞減法
-   150% 餘額遞減法
-   125% 餘額遞減法





## <a name="additional-resources"></a>其他資源

[固定資產折舊](fixed-asset-depreciation.md)

[直線法使用年限折舊](Straight-line-service-life-depreciation.md)

[餘額遞減折舊法](reduce-balance-depreciation.md)

[手動折舊](manual-depreciation.md)

[要素折舊](factor-depreciation.md)

[消耗折舊](consumption-depreciation.md)

[直線年限剩餘折舊](straight-line-life-remaining-depreciation.md)

[125% 餘額遞減折舊法](125-percent-reducing-balance-depreciation.md)

[150% 餘額遞減折舊法](150-percent-reducing-balance-depreciation.md)

[175% 餘額遞減折舊法](175-percent-reducing-balance-depreciation.md)

[200% 餘額遞減折舊法](200-percent-reducing-balance-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
