---
title: NUMBERFORMAT ER 函數
description: 本主題提供有關如何使用 NUMBERFORMAT 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 0208796382bd6564539ebbe3d902cc41dedce235adafefe1126961774cdb2076
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460179"
---
# <a name="numberformat-er-function"></a>NUMBERFORMAT ER 函數

[!include [banner](../includes/banner.md)]

`NUMBERFORMAT` 函數回傳一個 *字串* 值，該值以指定的格式和可選的指定[文化](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)呈現指定的數字。 如需支援格式的相關信息，請參閱[標準](/dotnet/standard/base-types/standard-numeric-format-strings)和[自訂](/dotnet/standard/base-types/custom-numeric-format-strings)。

## <a name="syntax-1"></a>語法 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>語法 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>引數

`number`：*整數* 或 *實數*

一個數值，指定必須格式化的數字。

`format`：*字串*

表示格式的 *字串* 值。

`culture`：*字串*

一個 *字串* 值，表示用於格式化的文化。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

如果文化未定義為被調用函數的參數，則運行此函數的內容將確定用於格式化數字的文化。

## <a name="example-1"></a>範例 1

對於 **EN-US** 文化，`NUMBERFORMAT (0.45, "p")` 回傳 **"45.00 %"**，而 `NUMBERFORMAT (10.45, "#")` 回傳 **"10"**。

## <a name="example-2"></a>範例 2

`NUMBERFORMAT (10/3, "F2", "de")` 回傳 **3,33**，而 `NUMBERFORMAT (10/3, "F2", "en-us")` 回傳 **3.33**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]