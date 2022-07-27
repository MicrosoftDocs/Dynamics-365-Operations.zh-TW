---
title: IF ER 函數
description: 本主題提供有關如何使用 IF 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 8bd0a7181b441a0a00163b31d4f1116c8bad0705a7f3b52a2985f1b31ecdb28b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460478"
---
# <a name="if-er-function"></a>IF ER 函數

[!include [banner](../includes/banner.md)]

如果滿足指定條件，`IF` 函數回傳第一個指定值。 否則，它回傳第二個指定值。 回傳的值可以是任何受支援的資料類型的值。

## <a name="syntax"></a>語法

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>引數

`condition`：*布林值*

必須測試的有效條件式運算式。

`first value`：*任何受支援的資料類型*

滿足條件時回傳的結果。

`second value`：*任何受支援的資料類型*

不滿足條件時回傳的結果。

## <a name="return-values"></a>回傳值

*任何受支援的資料類型*

任何受支援的資料類型的結果值。

## <a name="usage-notes"></a>使用方式說明

`first value` 和 `second value` 參數必須使用相同的資料類型指定。 如果設定值的資料類型不相符，則會在設計階段引發異常。

如果第一個值和第二個值是 *容器 (記錄)* 或 *記錄清單* 資料類型的值，則結果只有兩個值中都存在的欄位。

## <a name="example"></a>範例

`IF (1=2, "condition is met", "condition is not met")` 會回傳字串 **「條件不滿足」**。

## <a name="additional-resources"></a>其他資源

[邏輯函數](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]