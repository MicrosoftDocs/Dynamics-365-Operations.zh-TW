---
title: ROUNDDOWN ER 函數
description: 本主題提供有關如何使用 ROUNDDOWN 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 77186dc4d607f419149e4001a7404afba9e80fc7ec2528b840261a329a1e7872
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460471"
---
# <a name="rounddown-er-function"></a>ROUNDDOWN ER 函數

[!include [banner](../includes/banner.md)]

`ROUNDDOWN` 函數將指定的數字無條件捨去到指定的小數位數後作為 *實數* 值回傳。

## <a name="syntax"></a>語法

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>引數

`number`：*實數*

必須無條件捨去的數值。

`decimals`：*整數*

表示小數位數的數值。

## <a name="return-values"></a>回傳值

*真實*

產生的數值。

## <a name="usage-notes"></a>使用方式說明

此函數的行為類似於 [ROUND](er-functions-mathematical-round.md)，但它總是將指定的數字無條件捨去 (朝零)。

## <a name="example-1"></a>範例 1

`ROUNDDOWN (1200.767, 2)` 無條件捨去到小數點後兩位並回傳 **1200.76**。 

## <a name="example-2"></a>範例 2

`ROUNDDOWN (1700.767, -3)` 無條件捨去到最接近的 1,000 的倍數並回傳 **1000**。

## <a name="additional-resources"></a>其他資源

[數學函數](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]