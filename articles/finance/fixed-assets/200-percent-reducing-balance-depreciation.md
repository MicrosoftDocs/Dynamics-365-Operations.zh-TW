---
title: 200% 餘額遞減折舊法
description: 本主題概述了 200% 餘額遞減折舊法。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52a199489ffe42bc7b2d21e85b18dcd0bf35c165
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451236"
---
# <a name="200-percent-reducing-balance-depreciation"></a>200% 餘額遞減折舊法

[!include [banner](../includes/banner.md)]

本主題概述了 200% 餘額遞減折舊法。

如果設定固定資產折舊設定檔並在 **折舊設定檔** 頁面的 **方法** 欄位中選擇 **200% 餘額遞減法**，則已指派此折舊設定檔的固定資產將在每個折舊期間按相同的百分比進行折舊。 該百分比是根據資產的使用年限計算的。 例如，如果資產的使用年限為五年，則百分比按 40% (200% ÷ 5) 計算。 

這種方法也稱為雙倍餘額遞減折舊法。

若要設定 200% 餘額遞減折舊法，您還必須在 **折舊設定檔** 頁面的 **折舊年份** 欄位和 **時間頻率** 欄位中選擇選項。 **期間頻率** 欄位中提供的選項因 **折舊年份** 欄位中所選的值而異。

## <a name="select-a-depreciation-year"></a>選擇折舊年份
您可以選擇 **折舊設定檔** 頁面 **折舊年份** 欄位內的 **行事曆** 或 **財務**。 預設值為 **行事曆**。 

您的選擇會決定 **週期頻率** 欄位開放使用的選項。 此欄位定義整個日曆年的折舊應計過帳日期和金額。

### <a name="calendar"></a>行事曆

您可以保留 **折舊年份** 欄位中的預設值，即 **行事曆**。 

**行事曆** 選項在每年的 1 月 1 日更新折舊基價。 通常，折舊是帳面淨值減去殘值。 在本主題後文的範例中，折舊基價是計算行中第一個運算式中的分子。 

若您選擇 **行事曆** 為折舊年份，則 **週期頻率** 欄位會提供以下選項: 

-   **每年** 在 12 月 31 日過帳金額。
-   **每月** 每月底過帳每月金額。
-   **每季** 在日曆年每一季末 (3 月 31 日、6 月 30 日、9 月 30 日和 12 月 31 日) 過帳一季金額。
-   **每半年** 是在行事曆半年末 (6 月 30 日和 12 月 31 日) 過帳半年金額。
-   **每日** 使用每日一筆交易的日常折舊方法進行過帳折舊金額。

### <a name="fiscal"></a>會計

如果在 **折舊** 年份欄位中選擇 **會計**，200% 餘額遞減折舊法是根據用於帳簿中指定的會計行事曆或在 **分類帳** 頁面上選擇的會計行事曆的會計年度進行計算。 會計行事曆是在 **會計行事曆** 頁面上設定的。 

例如，對於 7 月 1 日至隔年 6 月 30 日的會計年度，折舊計算從 7 月 1 日開始。 會計年度可以長於或短於 12 個月。 每個期間都可以調整折舊。 下一會計年度的長度由 **會計日曆** 頁面上的期間設定決定。 

如果選擇 **會計** 作為折舊年份，則 **期間頻率** 欄位中提供以下選項：

-   **每年** 將會計年度計算的折舊總額在會計年度的最後一天以一筆金額過帳。
-   **會計期間** 將過帳為會計年度計算的折舊總額。 此金額應計入在 **會計行事曆** 頁上定義的會計期間。

## <a name="example-of-200-reducing-balance-depreciation"></a>200% 餘額遞減折舊法範例

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| 購置成本               | 11,000 |
| 殘值                  | 1, 000 |
| 折舊基價              | 10,000 |
| 服務年限             | 5      |
| 每年折舊百分比 | 40%    |

200% 餘額遞減折舊法將 200% 除以使用年限年限。 用此百分比將乘以資產的帳面淨值，以確定當年折舊金額。

| 期間 | 該年折舊金額的計算 | 帳面價值             | 年末帳面淨值 |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| 第 1 年 | (11,000 – 1,000) × 40% = 4,000                | 11,000 – 4,000 = 7,000 | 11,000 – 1,000 – 4,000 = 6,000        |
| 第 2 年 | 6,000 × 40% = 2,400                           | 7,000 – 2,400 = 4,600  | 6,000 – 2,400 = 3,600                 |
| 第 3 年 | 3,600 × 40% = 1,440                           | 4,600 – 1,440 = 3,160  | 3,600 – 1,440 = 2,160                 |

> [!NOTE] 
> 通常，當使用 200% 餘額遞減折舊法計算的金額小於使用直線法計算的金額時，剩餘年限將轉換為直線法。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
