---
title: DAYOFYEAR ER 函數
description: 本主題提供有關如何使用 DAYOFYEAR 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: ab252b6194267836ba9e1d85f3b96fb100c9f598c783bd9c849c6490c2e54e21
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460165"
---
# <a name="dayofyear-er-function"></a>DAYOFYEAR ER 函數

[!include [banner](../includes/banner.md)]

`DAYOFYEAR` 函數回傳一個 *整數* 值，表示從 1 月 1 日到指定日期之間的天數。

## <a name="syntax"></a>語法

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>引數

`date`：*日期*

一個日期值，表示用於計算天數的日期。

## <a name="return-values"></a>回傳值

*整數*

產生的數值。

## <a name="example-1"></a>範例 1

`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` 會回傳 **61**。

## <a name="example-2"></a>範例 2

`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` 會回傳 **1**。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]