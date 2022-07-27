---
title: ROUND ER 函數
description: 本主題提供有關如何使用 ROUND 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 10/21/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0c28ba2faebf117aa008106f8a77f79af8f4de3122df858825aa15a6dae3616
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460472"
---
# <a name="round-er-function"></a>ROUND ER 函數

[!include [banner](../includes/banner.md)]

`ROUND` 函數在四捨五入到指定的小數位數後將指定的數字作為 *實數* 值回傳。

## <a name="syntax"></a>語法

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>引數

`number`：*實數*

必須四捨五入的數值。

`decimals`：*整數*

表示小數位數的數值。

## <a name="return-values"></a>回傳值

*真實*

產生的數值。

## <a name="usage-notes"></a>使用方式說明

如果 `decimals` 參數的值大於 0 (零)，則指定的數字將四捨五入到小數位數。

如果 `decimals` 參數的值為 **0** (零)，則指定的數字會四捨五入到最接近的偶數整數。

如果 `decimals` 參數的值小於 0 (零)，則指定的數字將舍入到小數點左側。

## <a name="example-1"></a>範例 1

`ROUND (1200.767, 2)`四捨五入到小數點後兩位並回傳 **1200.77**。

## <a name="example-2"></a>範例 2

`ROUND (1200.767, -3)`四捨五入到最接近的 1,000 的倍數並回傳 **1000**。

## <a name="example-3"></a>範例 3

`ROUND (1200.5, 0)` 舍入到最接近的偶數並回傳 **1200**，而 `ROUND (1201.5, 0)` 執行相同的操作並回傳 **1202**。

## <a name="additional-resources"></a>其他資源

[數學函數](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]