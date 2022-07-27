---
title: PADLEFT ER 函數
description: 本主題提供有關如何使用 PADLEFT 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: a45333b8160a42063de8000ab27ea23136eb75ee7b55162b4602a5f3c52550de
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460304"
---
# <a name="padleft-er-function"></a>PADLEFT ER 函數

[!include [banner](../includes/banner.md)]

`PADLEFT` 函數回傳一個指定長度的 *字串* 值，其中指定字串的開頭用指定字元填入。

## <a name="syntax"></a>語法

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>引數

`text`：*字串*

表示原始文字的 *字串* 值。

`length`：*整數*

*整數* 值，表示填入字串中的最終字元數。

`padding chars`：*字串*

用於填入的字元。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`PADLEFT ("1234", 10, "`&nbsp;`")` 會回傳文字字串 **「&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234」**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]