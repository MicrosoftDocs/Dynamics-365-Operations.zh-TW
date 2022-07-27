---
title: CURCREDREF ER 函數
description: 本主題提供有關如何使用 CURCREDREF 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: c90385c3bf64adfe80fa054e1eb78a6aa368c04eb1758a2e453669bb3d4b7214
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460466"
---
# <a name="curcredref-er-function"></a>CURCREDREF ER 函數

[!include [banner](../includes/banner.md)]

`CURCREDREF` 函數根據指定發票編號的數字回傳代表貸方參考的 *字串* 值。

## <a name="syntax"></a>語法

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a>引數

`invoice number digits`：*字串*

代表發票編號數字的文字值。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`CURCredRef ("VEND-200002")` 會回傳 **"2200002"**。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]