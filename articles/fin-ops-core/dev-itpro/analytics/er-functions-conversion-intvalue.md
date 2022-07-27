---
title: INTVALUE ER 函數
description: 本主題提供有關如何使用 INTVALUE 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 5d54543a6f9878feb3482c1c1e6c1f1f468718489fbc46aded84a5a84bdfb04e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460192"
---
# <a name="intvalue-er-function"></a>INTVALUE ER 函數

[!include [banner](../includes/banner.md)]

`INTVALUE` 函數回傳一個表示指定字串的 *Int* 值。

## <a name="syntax-1"></a>語法 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>語法 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>引數

`text`：*字串*

必須轉換為 *Int* 數字的文字值。

`number`：*實數* 或 *整數*

必須轉換為 *Int* 數字的數字 *實數* 或 *整數* 值。

## <a name="return-values"></a>回傳值

*Int*

產生的數值。

## <a name="usage-notes"></a>使用方式說明

任何小數位都會被截斷。

## <a name="example-1"></a>範例 1

`INTVALUE ("100.77")` 會回傳 *Int* 值 **100**。

## <a name="example-2"></a>範例 2

`INTVALUE (-100.77)` 會回傳 *Int* 值 **-100**。

## <a name="additional-resources"></a>其他資源

[類型轉換函數](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]