---
title: EMPTYLIST ER 函數
description: 本主題提供有關如何使用 EMPTYLIST 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: fe2c72eddbb7f9227691ba29b19743c03aedfeb0d841e1a2466a159fa3afdf56
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460398"
---
# <a name="emptylist-er-function"></a>EMPTYLIST ER 函數

[!include [banner](../includes/banner.md)]

`EMPTYLIST` 函數透過使用指定的清單作為清單結構的來源來回傳空白 *記錄清單* 值。

## <a name="syntax"></a>語法

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="example"></a>範例

`EMPTYLIST (SPLIT ("abc", 1))` 回傳一個新的空白清單，該清單與使用的 `SPLIT` 函數回傳的清單具有相同的結構。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]