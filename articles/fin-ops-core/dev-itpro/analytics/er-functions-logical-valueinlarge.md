---
title: VALUEINLARGE ER 函數
description: 本主題提供有關如何使用 VALUEINLARGE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 08/17/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 57b2246631b31cce10d086da29e76b729059a64aa6a3c2d8cf864dd70085dbfd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460474"
---
# <a name="valueinlarge-er-function"></a>VALUEINLARGE ER 函數

[!include [banner](../includes/banner.md)]

`VALUEINLARGE` 函數確定 *Int64* 或 *Integer* 類型的指定輸入是否與指定清單中指定項的任何值相符。 如果指定的輸入與對指定清單的至少一條記錄執行指定運算式的結果相符，該函數則會回傳 **True** 的 *布林值*。 否則，它會回傳 **FALSE** 的 *布林值*。 若要了解與 `VALUEIN` 函數的不同處，請參閱本主題後面的[使用方式說明](#usage_note)章節。

## <a name="syntax"></a>語法

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a>引數

`input`：*欄位*

*記錄清單* 類型的資料來源項目的有效路徑。 此項目的值將符合。

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`list item expression`：*運算式*

一個有效的條件運算式，它指向或包含應用於相符的指定清單的單個欄位。

## <a name="return-values"></a>回傳值

*布林值*

產生的 *布林值* 值。

## <a name=""></a><a name="usage_note">使用方式說明</a>

當指定的輸入代表一個 *Int64* 或 *Integer* 類型的資料來源項目，對它的調用可以直接翻譯成 SQL 陳述式，指定的清單被轉換為一個臨時 SQL 表，透過執行單一 `EXISTS JOIN` 查詢在資料庫中進行比對。 否則，此函數會以[`VALUEIN`](er-functions-logical-valuein.md)函數運作。

當指定的輸入表示設計為 *Int64* 和 *Integer* 類型以外的項的資料來源項目時，在設計階段會發生錯誤，通知您 `VALUEINLARGE` 函數不適用於設定的 ER 運算式。

當執行 `VALUEINLARGE` 函數運算式並且在此執行範圍內使用了多個臨時表時，會發生執行階段錯誤。

## <a name="example"></a>範例

您在模型對應中定義以下資料來源：

- *資料表記錄* 類型的 **In** 資料來源。
    - 此資料來源指的是 **Intrastat** 資料表。
    - 將 **跨公司** 選項設定為 **否**。
- *導出欄位* 類型的 **InMemory** 資料來源。
    - 此資料來源包含運算式 `WHERE (In, In.Port <> "")`。
- *導出欄位* 類型的 **InFiltered** 資料來源。
    - 此資料來源包含運算式 `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`。

當資料來源 **InFiltered** 在公司 **DEMF** 的背景下被調用時，在應用程式資料庫中建立一個新的臨時表，在記憶體中收集的記錄識別碼清單被插入到這個表中，並產生以下 SQL 陳述式來回傳 **Intrastat** 表中的過濾記錄。

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a>其他資源

[邏輯函數](er-functions-category-logical.md)

[VALUEIN 函數](er-functions-logical-valuein.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]