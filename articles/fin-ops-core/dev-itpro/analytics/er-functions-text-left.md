---
title: LEFT ER 函數
description: 本主題提供有關如何使用 LEFT 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: 5d0056dbe46b20432aacb35a971895b987fdbf1b8ebc0d2679bb1e52eb3c4cc2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460486"
---
# <a name="left-er-function"></a>LEFT ER 函數

[!include [banner](../includes/banner.md)]

`LEFT` 函數回傳一個 *字串* 值，該值表示從指定字串的開頭開始的指定字元數。

## <a name="syntax"></a>語法

```vb
LEFT (text, number)
```

## <a name="arguments"></a>引數

`text`：*字串*

表示原始文字的 *字串* 值。

`number`：*整數*

必須從原始文字的開頭回傳的字元數。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`LEFT ("Sample", 3)` 會回傳 **"Sam"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]