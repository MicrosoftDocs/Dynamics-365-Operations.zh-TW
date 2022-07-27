---
title: WHERE ER 函數
description: 本主題提供有關如何使用 WHERE 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: dd021381e04e8794a5668041dbd71e5c981577a19141581fdde078a9d5801f49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460482"
---
# <a name="where-er-function"></a>WHERE ER 函數

[!include [banner](../includes/banner.md)]

根據指定條件，`WHERE` 函數將指定的清單回傳為 *記錄清單* 值。

## <a name="syntax"></a>語法

```vb
WHERE (list, condition)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`condition`：*布林值*

一個有效的條件運算式，用於過濾指定清單的記錄。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

此函數與 [FILTER](er-functions-list-filter.md) 函數不同，因為指定的條件適用於記憶體中存在的 *記錄清單* 類型的任何電子報表 (ER) 資料來源。

如果為此函數設定的參數 (`list` 和 `condition`)允許將此請求轉換為直接 SQL 調用，則會在設計階段引發警告訊息。 此訊息通知使用者，如果使用 [FILTER](er-functions-list-filter.md) 函數而不是 `WHERE`，則效能可能會提高。

## <a name="example-1"></a>範例 1

如果 **廠商** 設定為參考 VendTable 表的 ER 資料來源，則運算式 `WHERE (Vendors, Vendors.VendGroup = "40")` 回傳僅屬於廠商組 40 的廠商的清單。

## <a name="example-2"></a>範例 2

如果輸入 *導出欄位* 類型的資料來源 **DS**，並且它包含運算式 `SPLIT ("A|B|C", "|")`，則運算式 `WHERE( DS, DS.Value = "B")` 回傳僅包含一條記錄的清單，該記錄在 **值** 欄位中包含文字 **「B」**。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]