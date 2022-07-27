---
title: POWER ER 函數
description: 本主題提供有關如何使用 POWER 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 6955d2787b2a9be6d38fe10165a9d5ef8310b108e3a9772709d9d1ff51712424
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460473"
---
# <a name="power-er-function"></a>POWER ER 函數

[!include [banner](../includes/banner.md)]

`POWER` 函數回傳一個 *實數* 值，該值表示將指定正數提高到指定冪的結果。

## <a name="syntax"></a>語法

```vb
POWER (number, power)
```

## <a name="arguments"></a>引數

`number`：*實數* 或 *整數*

必須提高到指定冪的數值。

`power`：*實數* 或 *整數*

表示特定冪的數值。

## <a name="return-values"></a>回傳值

*真實*

產生的數值。

## <a name="example-1"></a>範例 1

`POWER (10, 2)` 會回傳 **100**。

## <a name="example-2"></a>範例 2

`POWER (4, 0.5)` 會回傳 **2**。

## <a name="additional-resources"></a>其他資源

[數學函數](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]