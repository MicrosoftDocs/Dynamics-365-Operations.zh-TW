---
title: LISTOFFIRSTITEM ER 函數
description: 本主題提供有關如何使用 LISTOFFIRSTITEM 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: e0497a4ee2c44efd4ee8d1551440bd2984ebb0cff9980206b058670a16928986
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460345"
---
# <a name="listoffirstitem-er-function"></a>LISTOFFIRSTITEM ER 函數

[!include [banner](../includes/banner.md)]

`LISTOFFIRSTITEM` 函數回傳一個僅包含指定清單的第一個記錄的 *記錄清單* 值。

## <a name="syntax"></a>語法

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="example"></a>範例

運算式 `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` 會回傳文字值 **「A」**。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]