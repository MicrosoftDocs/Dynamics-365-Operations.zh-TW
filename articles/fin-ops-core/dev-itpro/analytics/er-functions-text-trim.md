---
title: TRIM ER 函數
description: 本主題提供有關如何使用 TRIM 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 816f6d6623bb778c9186d294c9b67db7edddd671
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/01/2022
ms.locfileid: "8460230"
---
# <a name="trim-er-function"></a>TRIM ER 函數

[!include [banner](../includes/banner.md)]

`TRIM` 函數在製表符、回車、換行和換頁字元被單個空格字元替換後，在前導和尾隨空格被截斷後，在單詞之間的多個空格被替換後，將指定的文字字串作為 *字串值* 回傳刪除。

## <a name="syntax"></a>語法

```vb
TRIM (text)
```

## <a name="arguments"></a>引數

`text`：*字串*

*字串* 類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

在某些情況下，您可能希望截斷前導空格和尾隨空格，但希望保留指定文字的格式。 例如，當此文字表示可以在多行文字方塊中輸入的地址並且可以包含換行和回車格式時。 在這種情況下，請使用以下運算式：`REPLACE(text,"^[ \t]+|[ \t]+$","", true)` 其中 `text` 是參考指定文字字串的引數。

## <a name="example-1"></a>範例 1

`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` 會回傳 **「樣本文字」**。

## <a name="example-2"></a>範例 2

``TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` 會回傳 **「樣本文字」**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)

[REPLACE ER 函數](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
