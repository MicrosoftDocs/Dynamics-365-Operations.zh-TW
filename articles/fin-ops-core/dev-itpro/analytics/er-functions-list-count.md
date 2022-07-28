---
title: COUNT ER 函數
description: 本主題提供有關如何使用 COUNT 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 0fc122dafd6be90d090ba3b79a8c2eccab74d77441f82db71cb5e08d13d13518
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460399"
---
# <a name="count-er-function"></a>COUNT ER 函數

[!include [banner](../includes/banner.md)]

`COUNT` 函數回傳一個 *整數* 值，表示指定清單中的記錄數，如果清單不為空白。 如果清單為空白，此函數會回傳 **0** (零)。

## <a name="syntax"></a>語法

```vb
COUNT (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*整數*

產生的數值。

## <a name="example"></a>範例

`COUNT (SPLIT("abcd" , 3))` 回傳 **2**，因為此範例中使用的 `SPLIT` 函數建立了一個包含兩條記錄的清單。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]