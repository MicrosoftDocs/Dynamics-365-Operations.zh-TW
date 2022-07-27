---
title: CONCATENATE ER 函數
description: 本主題提供有關如何使用 CONCATENATE 電子報表 (ER) 函數的信息
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 1507e1b8a31ed45e7c540e4e2ff31b79e8de3b866ffbace9de17d7b3e169e877
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460180"
---
# <a name="concatenate-er-function"></a>CONCATENATE ER 函數

[!include [banner](../includes/banner.md)]

`CONCATENATE` 函數將所有指定的文字字串作為字串值在它們連接成一個 *字串* 後回傳。

## <a name="syntax"></a>語法

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>引數

`text 1`：*字串*

對 *字串* 資料類型的資料來源的參考。 此為必填引數。

`text N`：*字串*

對 *字串* 資料類型的資料來源的參考。 這些附加引數是可選的。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`CONCATENATE ("abc", "def")` 會回傳 **「abcdef」**。

## <a name="usage-notes"></a>使用方式說明

運算式 `"abc" & "def"` 還會回傳 **"abcdef"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]