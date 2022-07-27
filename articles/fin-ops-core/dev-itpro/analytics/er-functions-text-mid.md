---
title: MID ER 函數
description: 本主題提供有關如何使用 MID 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 33a8d02e937b3d88d98cac96ae28a30345ccffb23be37d7add67f721dfb9cc70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460491"
---
# <a name="mid-er-function"></a>MID ER 函數

[!include [banner](../includes/banner.md)]

`MID` 函數回傳一個 *字串* 值，該值表示指定字串中的指定字元數，從指定位置開始。

## <a name="syntax"></a>語法

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>引數

`text`：*字串*

*字串* 值，它指定要從中回傳字元的文字。

`starting position`：*整數*

*整數* 值，它指定必須從指定文字回傳的第一個字元的位置。

`number of characters`：*整數*

*整數* 值，它指定必須回傳的字元數，從指定的起始位置開始。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

如果 `starting position` 引數的值小於 0 (零)，則回傳的字元從指定字串中的第一個位置開始計數。

如果 `starting position` 引數值超過指定字串的長度，則回傳一個空白字串。

## <a name="example"></a>範例

`MID ("Sample", 2, 3)` 會回傳 **「amp」**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]