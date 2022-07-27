---
title: NUMBERVALUE ER 函數
description: 本主題提供有關如何使用 NUMBERVALUE 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: bcb76310a53c86b68f18085e203d11f405b16946a25fe1be67e649f83335d1f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460191"
---
# <a name="numbervalue-er-function"></a>NUMBERVALUE ER 函數

[!include [banner](../includes/banner.md)]

`NUMBERVALUE` 函數回傳一個從指定的 *字串* 值轉換而來的 *實數* 值。 在轉換過程中，會考慮指定的小數和數字分組分隔符號。

## <a name="syntax"></a>語法

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>引數

`text`：*字串*

必須轉換為 *實數* 數字的文字值。

`decimal separator`：字串

小數分隔符號。 它用於分隔十進位數的整數和小數部分。

`digit grouping separator`：*字串*

數字分組分隔符號。 它用作千位分隔符號。

## <a name="return-values"></a>回傳值

*真實*

產生的數值。

## <a name="example"></a>範例

`NUMBERVALUE( "1 234,56", ",", " ")` 會回傳 **1234.56**。

## <a name="additional-resources"></a>其他資源

[類型轉換函數](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]