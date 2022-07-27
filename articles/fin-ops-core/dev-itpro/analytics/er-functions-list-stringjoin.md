---
title: STRINGJOIN ER 函數
description: 本主題提供有關如何使用 STRINGJOIN 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 651cc261e6a33b1a824feb94afa767e439196e249bb13b0fc4886dc72bfdd184
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460481"
---
# <a name="stringjoin-er-function"></a>STRINGJOIN ER 函數

[!include [banner](../includes/banner.md)]

`STRINGJOIN` 函數回傳一個 *字串* 值，由指定清單中的指定欄位的連接值組成。 這些值可以由指定的分隔符號分隔。

## <a name="syntax"></a>語法

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`field`：*欄位*

指定清單中 *字串* 資料類型欄位的有效路徑。

`delimiter`：*字串*

用於分隔子字串的分隔符號。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

如果您輸入 `SPLIT("abc" , 1)` 作為資料來源 **DS**，運算式 `STRINGJOIN (DS, DS.Value, "-")` 則會回傳 **"a-b-c"**。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]