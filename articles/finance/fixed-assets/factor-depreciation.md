---
title: 係數折舊
description: 本文概述係數折舊方法。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aab5ab518f2806e1b27f352e354dc9280fd27def
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451059"
---
# <a name="factor-depreciation"></a>係數折舊

[!include [banner](../includes/banner.md)]

本文概述係數折舊方法。

係數是用於折舊資產的百分比。 當您設置固定資產折舊配置文件並選擇 **係數** 在裡面 **方法** 場上 **折舊配置文件** 頁面，您可以設置累進、離題或直線折舊。

-   在累進折舊中，折舊金額會在每個折舊期增加。
-   在離題折舊中，每個期間的折舊金額隨著時間的推移而減少。
-   在直線折舊中，每個期間的折舊都是相同的。

以下規則和示例說明瞭如何為每種類型的折舊設置係數。 

> [!NOTE] 
> 當您選擇 **係數** 在裡面 **方法** 場 **係數** 領域和 **間隔** 欄位顯示。

## <a name="progressive-depreciation"></a>累進折舊
**係數** 欄位中的值大於 **50**。

### <a name="example"></a>範例

收購價 10 萬，係數 70，使用年限 10 年，1 月 1 日開始折舊。 折舊金額和賬面淨值金額僅在使用年限的前六年顯示。

| 年 | 期間      | 折舊金額 | 帳面淨值金額 |
|------|-------------|---------------------|-----------------------|
| 1    | 12 月 31 日 | 307.69              | 99,692.31             |
| 2    | 12 月 31 日 | 1,447.21            | 98,245.10             |
| 3    | 12 月 31 日 | 3,104.50            | 95,140.60             |
| 4    | 12 月 31 日 | 5,150.21            | 89,990.39             |
| 5    | 12 月 31 日 | 7,522.95            | 82,467.44             |
| 6    | 12 月 31 日 | 10,184.06           | 72,283.38             |

## <a name="digressive-depreciation"></a>遞減折舊
中的值 **係數** 欄位小於 **50**.

### <a name="example"></a>範例 

收購價 10 萬，係數 20，使用年限 10 年，1 月 1 日開始折舊。 折舊金額和賬面淨值金額僅在使用年限的前六年顯示。

| 年 | 期間      | 折舊金額 | 帳面淨值金額 |
|------|-------------|---------------------|-----------------------|
| 1    | 12 月 31 日 | 56,080.43           | 43,919.57             |
| 2    | 12 月 31 日 | 10,665.70           | 33,253.87             |
| 3    | 12 月 31 日 | 7,156.22            | 26,097.65             |
| 4    | 12 月 31 日 | 5,538.06            | 20,559.59             |
| 5    | 12 月 31 日 | 4,579.89            | 15,979.70             |
| 6    | 12 月 31 日 | 3,937.36            | 12,042.34             |

## <a name="straight-line-depreciation"></a>直線法折舊
中的值 **係數** 欄位等於 **50**. 在這種情況下，每個期間的折舊都是相同的，您應該考慮在其他欄位中指定的值的含義，如中所述[直線使用壽命折舊](straight-line-service-life-depreciation.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
