---
title: OR ER 函數
description: 本主題提供有關如何使用 OR 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: f6751c70599b5e3c05b9d1c69a95e82673b230210170cfead1e6a87c57d59c7f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460476"
---
# <a name="or-er-function"></a>OR ER 函數

[!include [banner](../includes/banner.md)]

如果所有指定條件均為假，則 `OR` 函數將回傳 *布林值* **FALSE**。 如果任何指定條件為真，則該函數回傳 *布林值* **TRUE**。

## <a name="syntax"></a>語法

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>引數

`condition 1`：*布林值*

必須測試的有效條件式運算式。 此為必填引數。

`condition N`：*布林值*

必須測試的有效條件式運算式。 這些附加引數是可選的。

## <a name="return-values"></a>回傳值

*布林值*

產生的 *布林值* 值。

## <a name="example"></a>範例

`OR (1=2, "a"="a")` 會回傳 **TRUE**。

## <a name="additional-resources"></a>其他資源

[邏輯函數](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]