---
title: 固定資產折舊慣例
description: 本主題說明固定資產的折舊慣例。
author: moaamer
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 823f8826e297a01c3658ceb8e82e6f9902d7a359
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451230"
---
# <a name="fixed-asset-depreciation-conventions"></a>固定資產折舊慣例

[!include [banner](../includes/banner.md)]

本主題說明固定資產的折舊慣例。 折舊慣例用來判定採購兩年固定資產時，計算兩個年度折舊的時機點和方式及處置的年份。

可以將折舊慣例指派給固定資產群組帳冊的設定。 若要查看或指派折舊慣例，請在固定資產的設定區選取 **固定資產** 群組。 請選取 **帳冊** 按鈕。 此時指派的折舊慣例會在建立固定資產帳冊時當成預設值。 折舊慣例也可以在個別固定資產帳冊設定。 為此，請在固定資產設定區選取 **帳冊**，然後選取 **固定資產群組** 按鈕。

| 折舊慣例   | 描述 |
|---------------------------|-------------|
| 無                      | 資產開始在<strong>投入使用</strong>日期當天貶值。 |
| 半年                 | 您對財產進行折舊的第一年和最後一年都會扣除半年的折舊。 恢復期間每隔一年就會扣除一整年的折舊。 |
| 整個月                | 當月任何時間是<strong>投入使用</strong>日期的資產會開始在該月第一天貶值。 基於折舊目的，資產在上個月的最後一天視同已報廢。 不考慮它們報廢當月的特定日。 |
| 季中               | 若要計算財產投入使用當年的折舊扣除額，請將全年折舊乘以財產投入使用當季的百分比，如下表所示。<table><thead><tr><th>季</th><th>百分比</th></tr></thead><tbody><tr><td>第一個</td><td>87.5</td></tr><tr><td>第二個</td><td>62.5</td></tr><tr><td>第三個</td><td>37.5</td></tr><tr><td>第四個</td><td>12.5</td></tr></tbody></table>處置資產的當季 (或完全折舊的當季) 進行半季折舊。 |
| 月中 (每月第 1 天)  | 前半個月有<strong>投入使用</strong>日期 (第 1 天到第 15 天) 的資產開始在<strong>投入使用</strong>日期當月的第一天開始貶值。 後半個月有<strong>投入使用</strong>日期 (第 16 天到月底) 的資產開始在<strong>投入使用</strong>日期後隔月的第一天開始貶值。 基於折舊目的，前半個月 (第 1 天到第 15 天) 報廢的資產被視為已在上個月的最後一天報廢。 基於折舊目的，後半個月 (第 16 天到月底) 報廢的資產被視為已在報廢月的最後一天報廢。 |
| 月中 (每月第 15 天) | 若要計算您讓財產投入使用時的折舊扣除額，請將全年折舊乘以分數。 此分數的分子 (上端數字) 是該財產投入使用之當年度全月數目加上 1/2 或 (0.5)。 分母 (下端數字) 則為 12。 如果您在恢復期結束前處置財產，請使用相同方法計算處置年度的折舊扣除額。 |
| 半年 (年度開始) | 前半年有<strong>投入使用</strong>日期的資產會開始在當年度第一天 (全年) 貶值。 後半年有<strong>投入使用</strong>日期的資產會開始在當年度中間點貶值。 |
| 半年 (下一年)     | 前半年有<strong>投入使用</strong>日期的資產會開始在當年度第一天 (全年) 貶值。 後半年有<strong>投入使用</strong>日期的資產會開始在隔年第一天貶值。 基於折舊目的，前半年報廢的資產被視為已在去年最後一天報廢。 本年度過帳的任何折舊都必須沖銷或調出。基於折舊目的，後半年報廢的資產會被視為已在報廢年度的最後一天報廢。 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
