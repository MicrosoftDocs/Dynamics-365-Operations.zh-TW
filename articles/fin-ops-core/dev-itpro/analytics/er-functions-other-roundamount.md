---
title: ROUNDAMOUNT ER 函數
description: 本主題提供有關如何使用 ROUNDAMOUNT 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 1b05c6024d9eeecfe74022df10d793055a026d5a159e9c011f37708f6a4e6e0d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460151"
---
# <a name="roundamount-er-function"></a>ROUNDAMOUNT ER 函數

[!include [banner](../includes/banner.md)]

`ROUNDAMOUNT` 函數回傳一個 *實數* 值，作為根據指定進位規則將指定數字進位到另一個數字的最接近倍數的結果。

## <a name="syntax"></a>語法

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>引數

`number`：*Int* 或 *實數*

必須四捨五入的數值。

`decimals`：*Int* 或 *實數*

`number` 參數的值必須四捨五入為整數倍的數字。

`round rule`：*列舉值*

定義進位規則的 **RoundOffType** 列舉的列舉值。 此列舉提供以下值：

- 普通 (普通)
- 無條件捨去 (RoundDown)
- 無條件進位 (RoundUp)

## <a name="return-values"></a>回傳值

*實數*

產生的數值是 `decimals` 參數指定的值的倍數，並且最接近 `number` 參數指定的值。

## <a name="usage-notes"></a>使用方式說明

當 `number` 參數為零時，此函數始終回傳零。

當 `decimals` 參數為零時，此函數將四捨五入到預設整數值。 當 `round rule` 參數設定為 **RoundOffType.Ordinary** 時，預設四捨五入值為 **0.01**。 否則，預設四捨五入值為 **1.0**。

當 `round rule` 參數設定為 **RoundOffType.Ordinary** 時，此函數會四捨五入到最接近的整數額。

當 `round rule` 參數設定為 **RoundOffType.RoundDown** 時，此函數向零四捨五入到最接近的整數額。

當 `round rule` 參數設定為 **RoundOffType.RoundUp** 時，此函數會從零四捨五入到最接近的整數額。

當 `round rule` 參數設定為 **RoundOffType.Ordinary** 時，此函數的行為類似於 [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel 函數和 [ROUND](../dev-ref/xpp-math-run-time-functions.md#round) X++ 函數。

## <a name="remarks"></a>備註

若要將數值四捨五入到指定的小數位數，請使用 [ROUND](er-functions-mathematical-round.md) 函數。

## <a name="example"></a>範例

如果 **model.RoundOff** 參數設定為 **RoundOffType.Ordinary**，`ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 回傳 7.35。 

如果 **model.RoundOff** 參數設定為 **RoundOffType.RoundDown**，`ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 回傳 7.35。 

如果 **model.RoundOff** 參數設定為 **RoundOffType.RoundUp**，`ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 回傳 8.4。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)

[數學函數](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]