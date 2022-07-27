---
title: VALUE ER 函數
description: 本主題提供有關如何使用 VALUE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 04d3320276bc1e23436bd9baa7a84da36314d6c3bf7f84694aa2e01e31230a0b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460190"
---
# <a name="value-er-function"></a>VALUE ER 函數

[!include [banner](../includes/banner.md)]

`VALUE` 函數回傳一個從指定字串轉換而來的 *實數* 值。

## <a name="syntax"></a>語法

```vb
VALUE (text)
```

## <a name="arguments"></a>引數

`text`：*字串*

必須轉換為數字值的字串值。

## <a name="return-values"></a>回傳值

*真實*

產生的數值。

## <a name="usage-notes"></a>使用方式說明

逗號和點字元 (.) 被視為小數分隔符號，前導連字元號 (-) 用作負號。 如果指定的字串包含其他非數字字元，則會在執行階段引發異常。

## <a name="example-1"></a>範例 1

`VALUE ("1 234,56")` 引發異常。

## <a name="example-2"></a>範例 2

`VALUE ("1234,56")` 會回傳 **1234.56**。

## <a name="additional-resources"></a>其他資源

[類型轉換函數](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]