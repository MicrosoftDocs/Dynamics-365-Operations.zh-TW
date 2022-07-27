---
title: NOT ER 函數
description: 本主題提供有關如何使用 NOT 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 094c60157d3ac4091fb02b24dcc00dddba2397abe87510952371a779eb3a2f4a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460477"
---
# <a name="not-er-function"></a>NOT ER 函數

[!include [banner](../includes/banner.md)]

`NOT` 函數將指定條件的反轉邏輯值作為 *布林值* 回傳。

## <a name="syntax"></a>語法

```vb
NOT (condition)
```

## <a name="arguments"></a>引數

`condition`：*布林值*

必須撤銷的有效條件運算式。

## <a name="return-values"></a>回傳值

*布林值*

產生的 *布林值* 值。

## <a name="example"></a>範例

`NOT (TRUE)` 會回傳 **FALSE**。

## <a name="additional-resources"></a>其他資源

[邏輯函數](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]