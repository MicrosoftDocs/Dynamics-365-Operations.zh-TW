---
title: TRANSLATE ER 函數
description: 本主題提供有關如何使用 TRANSLATE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: 0b43c1edb2a26ebe01e8d5cf69e1ff377c6c8bf84e889b6bb3d1828d3dc84b53
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460291"
---
# <a name="translate-er-function"></a>TRANSLATE ER 函數

[!include [banner](../includes/banner.md)]

`TRANSLATE` 函數回傳一個 *字串* 值，該值包含將指定文字替換為另一個提供的字元集的字元的結果。

## <a name="syntax"></a>語法

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>引數

`text`：*字串*

*字串* 類型的資料來源的有效路徑。

`pattern`：*字串*

必須替換的文字。

`replacement`：*字串*

用作替換的文字。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

`TRANSLATE` 函數一次替換一個字元。 該函數將 `text` 引數的第一個字元替換為 `pattern` 引數的第一個字元，然後是第二個字元，並遵循相同的流程直到完成。 當 `text` 和 `pattern` 引數中的字元匹配時，它會被 `replacement` 引數中的字元替換，該字元與 `pattern` 引數中的字元位於相同位置。 如果一個字元在 `pattern` 引數中出現多次，則使用對應於該字元第一次出現的 `replacement` 引數對應。

## <a name="example-1"></a>範例 1

`TRANSLATE ("abcdef", "cd", "GH")` 將指定的 **「abcdef」** 文字的 **「c」** 字元替換為 `replacement` 文字的 **「G」** 字元，原因如下：
-   **「c」** 字元出現在 `pattern` 文字中的第一個位置。
-   `replacement` 文字的第一個位置包含 **「G」** 字元。

## <a name="example-2"></a>範例 2

`TRANSLATE ("abcdef", "ccd", "GH")` 會回傳 **「abGdef」**。

## <a name="example-3"></a>範例 3

`TRANSLATE ("abccba", "abc", "123")` 會回傳 **"123321"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]