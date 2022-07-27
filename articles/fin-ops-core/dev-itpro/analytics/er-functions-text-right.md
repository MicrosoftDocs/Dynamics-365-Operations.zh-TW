---
title: RIGHT ER 函數
description: 本主題提供有關如何使用 RIGHT 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 45696d0498f712218126af8557521a2317d584eea5059ac3b588d3792d42495c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460154"
---
# <a name="right-er-function"></a>RIGHT ER 函數

[!include [banner](../includes/banner.md)]

`RIGHT` 函數回傳一個 *字串* 值，該值表示從指定字串的結尾開始的指定字元數。

## <a name="syntax"></a>語法

```vb
RIGHT (text, number)
```

## <a name="arguments"></a>引數

`text`：*字串*

表示原始文字的 *字串* 值。

`number`：*整數*

必須從原始文字末尾回傳的字元數。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`RIGHT ("Sample", 3)` 會回傳 **"ple"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]