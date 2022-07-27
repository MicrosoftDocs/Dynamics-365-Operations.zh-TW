---
title: AND ER 函數
description: 本主題提供有關如何使用 AND 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 4d327f0f961a11fecdbc055ffbb1f3d8bc15bcfdd732e2565d0a5e9e2c0a31ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460479"
---
# <a name="and-er-function"></a>AND ER 函數

[!include [banner](../includes/banner.md)]

如果所有指定條件都為真，則 `AND` 函數會回傳的 *布林值* **TRUE**。 否則，它會回傳 **FALSE** 的 *布林值*。

## <a name="syntax"></a>語法

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>引數

`condition 1`：*布林值*

必須測試的有效條件式運算式。 此為必填引數。

`condition N`：*布林值*

必須測試的有效條件式運算式。 這些附加引數是可選的。

## <a name="return-values"></a>回傳值

*布林值*

產生的 *布林值* 值。

## <a name="usage-notes"></a>使用方式說明

在邏輯函數的引數中，您可以使用資料來源參考、數值和文字值、布林值、比較運算子和其他電子報表 (ER) 函數。 但是，必須將所有引數評估為 *布林值* **TRUE** 或 **FALSE**。

## <a name="example"></a>範例

`AND (1=1, "a"="a")` 會回傳 **TRUE**。

`AND (1=2, "a"="a")` 會回傳 **FALSE**。

## <a name="additional-resources"></a>其他資源

[邏輯函數](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]