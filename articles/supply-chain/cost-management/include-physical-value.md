---
title: 包括實物價值
description: 您會使用項目模型群組頁面的庫存模型 FastTab 上的「包括實物價值」核取方塊，來指定在計算項目的執行平均成本價格時，是否應考慮實體更新的交易。
author: AndersGirke
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 711c30376c4f1ecc5c1a747c675e6438a867c51ed066b6c15cdace6a071f7cfd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446991"
---
# <a name="include-physical-value"></a>包括實物價值

[!include [banner](../includes/banner.md)]

您會使用項目模型群組頁面的庫存模型 FastTab 上的「包括實物價值」核取方塊，來指定在計算項目的執行平均成本價格時，是否應考慮實體更新的交易。

**包括實物價值** 核取方塊具有以下值。

| 值    | 結果                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| 已選取 | 實體更新交易和財務更新交易都用於計算執行平均成本價格。 |
| 清除  | 僅財務更新交易都用於計算執行平均成本價格。                                     |

核取方塊的效果略有不同，視您使用的庫存模型而定。

-   如果您在使用 FIFO (先進先出)、LIFO (後進先出) 或 LIFO 日期庫存模型時選擇了 **包括實物價值** 核取方塊，庫存結算也會對實體更新的交易進行調整。
-   如果您不選擇 **包括實物價值** 核取方塊，在您使用這些庫存模型時，庫存結算僅會對財務更新的交易進行結算。
-   在您使用加權平均或加權平均日期庫存模型時，無論您是否選擇 **包括實物價值** 核取方塊，庫存結算都僅會結算財務更新的交易。

**範例 1** 您已選擇 **包括實物價值** 核取方塊並接收以下訂購單：

-   數量為 2 且成本價格為 10.00 美元的訂購單已更新裝箱單。
-   數量為 3 且成本價格為 12.00 美元的訂購單已更新發票。

在這種情況下，執行平均成本價將為 11.20 美元 = (2x10+3x12)/(2+3)，因為實體更新交易和財務更新交易都用於計算成本價。 

**範例 2** 您還沒有選擇 **包括實物價值** 核取方塊，且項目設定的成本價格為 10.00 美元。 

-   您會收到數量為 20 且成本價格為 12.00 美元的訂購單已更新裝箱單。

在銷售訂單已過帳時，過帳成本金額為 10.00 美元，因為執行平均成本價格不包括實際過帳的交易。 

> [!NOTE]
> 做為比較，如果您選擇了 **包括實物價值** 核取方塊，當銷售訂單過帳時，過帳成本金額將為 12.00 美元。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]