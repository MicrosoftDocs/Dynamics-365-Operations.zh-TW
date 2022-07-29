---
title: 手動折舊
description: 本文概述手動折舊方法。
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5b62bbdd5d745bc9d0745cc6fa6d6e8034a61e3
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451077"
---
# <a name="manual-depreciation"></a>手動折舊

[!include [banner](../includes/banner.md)]

本文概述手動折舊方法。

當您在 **折舊設定檔** 頁面的 **方法** 欄位選取 **手動** 設定固定資產折舊設定檔，已經指派給折舊設定檔的固定資產折舊會按您按日曆年制輸入的每個間隔佔比判定。 您設定佔比的間隔會根據您在 **折舊設定檔** 頁，**一般** FastTab 上的 **期間頻率** 的選取值過帳。 以下是您可以選取的值：

- 每年
- 每月
- 每季
- 每半年
- 每日

待您選取週期頻率後，點選 **手動期程**，並為每個過帳間隔設定佔比。 手動期程和過帳間隔共同定義折舊金額，如本文稍候範例所示。 手動折舊始終按取得價格的佔比計算。 以手動折舊而言，您在折舊間隔輸入的佔比不見得非得加到 100%。 手動折舊是一種靈活的折舊方法，往往用來在 **帳冊** 頁定義異常折舊設定檔，例如用於特殊用途 (例如稅賦) 的非定期折舊。

## <a name="examples"></a>範例
取得價格：11,000.00 預期報廢值：1,000.00 下表顯示您在 **固定資產折舊設定檔期程** 頁設定的問隔和佔比。

| 間隔數字 | 佔比 |
|-----------------|------------|
| 1               | 10.00      |
| 2               | 50.00      |
| 3               | 8.00       |

下表顯示如何計算每個間隔的折舊。

|  間隔數字 | 該年折舊金額的計算 | 期末帳面淨值 |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1                | (11,000 – 1,000) × 10% = 1,000                | 10,000 (11,000 – 1,000)                   |
| 2                | (11,000 – 1,000) × 50% = 5,000                | 5,000 (10,000 – 5,000)                    |
| 3                | (11,000 – 1,000) × 8% = 800                   | 4,200 (5,000 – 800)                       |

如果您在 **週期頻率** 欄位選取 **按月**，您等於設定 12 個手動期程間隔。 下表顯示前兩個間隔的折舊金額。

| 間隔 | 折舊金額            |
|----------|--------------------------------|
| 一月  | (11,000 – 1,000) × 10% = 1,000 |
| 二月 | (11,000 – 1,000) × 50% = 5,000 |

如果您在 *<strong><em>週期頻率</em>* 欄位</strong>選取<strong>半年</strong>，您等於設定兩個手動期程間隔。 下表顯示那兩個間隔的折舊金額。

| 間隔    | 折舊金額            |
|-------------|--------------------------------|
| 六月 30 日     | (11,000 – 1,000) × 10% = 1,000 |
| 十二月 31 日 | (11,000 – 1,000) × 50% = 5,000 |

所有間隔的總佔比不必非得 100。 不過，如果 **固定資產折舊設定檔基程** 頁的 **應計佔比** 欄位值不是 **100**，您會收到訊息。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]