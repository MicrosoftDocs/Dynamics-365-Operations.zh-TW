---
title: CASE ER 函數
description: 本主題提供有關如何使用 CASE 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 97f5e821a635d5d31092a7b27f7ae3c2e603462186449bab5856955371a7f613
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460480"
---
# <a name="case-er-function"></a>CASE ER 函數

[!include [banner](../includes/banner.md)]

`CASE` 函數根據指定的替代選項計算指定運算式的值，並回傳等於指定運算式值的第一個選項的結果。 否則，如果預設結果被指定為被調用函數的最後一個參數且前面沒有選項，則它回傳一個可選的預設結果。 回傳的值可以是任何受支援的資料類型的值。

## <a name="syntax"></a>語法

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>引數

`expression`：*原始資料類型* (布林值、數字或文字)

回傳原始資料類型值的有效運算式。

`option 1`：*原始資料類型* (布林值、數字或文字)

一個有效的運算式，它回傳與被調用函數的 `expression` 引數相同的原始資料類型的值。 此為必填引數。

`result 1`：*任何受支援的資料類型*

與上述選項對應的回傳結果。 此為必填引數。

`option N`：*原始資料類型* (布林值、數字或文字)

一個有效的運算式，它回傳與被調用函數的 `expression` 引數相同的原始資料類型的值。 此引數為選取性選項。

`result N`：*任何受支援的資料類型*

與上述選項對應的回傳結果。 此引數為選取性選項。

`default result`：*任何受支援的資料類型*

不相符時應回傳的結果。 此引數為選取性選項。

## <a name="return-values"></a>回傳值

*任何受支援的資料類型*

任何受支援的資料類型的結果值。

## <a name="usage-notes"></a>使用方式說明

如果沒有相符且未定義可選的預設結果，則在執行階段引發異常。

必須使用相同的資料類型指定所有結果。 如果設定結果的資料類型不相符，則會在設計階段引發異常。

如果第一個結果值和第 *N* 個結果值是 *容器 (記錄)* 或 *記錄清單* 資料類型的值，則結果只有兩個值中都存在的欄位。

## <a name="example"></a>範例

如果現行應用程式工作階段日期在 10 月和 12 月之間，`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` 將回傳字串 **「WINTER」**。 否則，它回傳一個空白字串。

## <a name="additional-resources"></a>其他資源

[邏輯函數](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]