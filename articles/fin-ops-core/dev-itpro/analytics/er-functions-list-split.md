---
title: SPLIT ER 函數
description: 本主題提供有關如何使用 SPLIT 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 4a42b0c7cfa2a8d3dcb7448224c9e88a48276f7d8cdbcce484383a778b8275a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460341"
---
# <a name="split-er-function"></a>SPLIT ER 函數

[!include [banner](../includes/banner.md)]

`SPLIT` 函數將指定的輸入字串拆分為子字串並將結果回傳為新的 *記錄清單* 值。

## <a name="syntax-1"></a>語法 1

```vb
SPLIT (input, length)
```

此語法用於將指定的輸入字串拆分為子字串，每個子字串具有指定的長度。

## <a name="syntax-2"></a>語法 2

```vb
SPLIT (input, delimiter)
```

此語法用於根據指定的分隔符號將指定的輸入字串拆分為子字串。

## <a name="arguments"></a>引數

`input`：*字串*

要分割的文字。

`length`：*整數*

單個子字串的最大長度。

`delimiter`：*字串*

用於分隔子字串的分隔符號。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

回傳的清單的記錄結構由 *字串* 類型的 **值** 欄位組成。 回傳的清單的每條記錄都包含該欄位中產生的子字串。

如果 `delimiter` 引數為空白，則回傳的新清單由一條具有 *字串* 類型的 **值** 欄位的記錄組成。 此欄位包含輸入文字。

如果 `input` 引數為空白，則回傳一個新的空白清單。 如果 `input` 或 `delimiter` 引數未指定 (Null)，則會引發應用程式異常。

## <a name="example-1"></a>範例 1

`SPLIT ("abcd", 3)`` 會回傳一個新清單，該清單由兩個具有 *字串* 類型的 **值** 欄位的記錄組成。 第一條記錄中的 **值** 欄位包含文字 **「abc」**，第二條記錄中的 **值** 欄位包含文字 **「d」**。

## <a name="example-2"></a>範例 2

`SPLIT ("XAb aBy", "aB")`` 會回傳一個新清單，該清單由三個具有 *字串* 類型的 **值** 欄位的記錄組成。 第一條記錄中的 **值** 欄位包含文字 **「X」**，第二條記錄中的 **值** 欄位包含文字 **「&nbsp;」**，第三條記錄中的 **值** 欄位包含文字 **「y」**。 

## <a name="example-3"></a>範例 3

您可以使用 [INDEX](er-functions-list-index.md) 函數存取指定輸入字串的各個元素。 如果輸入 **匯出欄位** 類型的 **MyList** 資料來源並為其設定 `SPLIT("abc", 1)` 運算式，則運算式 `INDEX(MyList,2).Value` 會回傳文字 **「b」**。

## <a name="example-4"></a>範例 4

[ENUMERATE](er-functions-list-enumerate.md) 函數也可以幫您存取指定輸入字串的各個元素。 如果先輸入 **匯出欄位** 類型的 **MyList** 資料來源並為其設定 `SPLIT("abc", 1)` 運算式，然後輸入 **匯出欄位** 類型的 **EnumeratedList** 資料來源並為其設定 `ENUMERATE(MyList)` 運算式，運算式 `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` 會回傳文字 **「b」**。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
