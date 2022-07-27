---
title: VALUEIN ER 函數
description: 本主題提供有關如何使用 VALUEIN 電子報表 (ER) 函數的資訊。
author: NickSelin
ms.date: 12/14/2021
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
ms.openlocfilehash: efa811df360b2ca38eb59bac849e70041405fa81
ms.sourcegitcommit: b1c758ec4abfcf3bf9e50f18c1102d4a9c1316d0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2021
ms.locfileid: "8460475"
---
# <a name="valuein-er-function"></a>VALUEIN ER 函數

[!include [banner](../includes/banner.md)]

`VALUEIN` 函數確定指定輸入是否符合指定清單中指定項的任何值。 如果指定的輸入與對指定清單的至少一條記錄執行指定運算式的結果相符，則回傳 **True** 的 *布林值*。 否則，它會回傳 **FALSE** 的 *布林值*。

## <a name="syntax"></a>語法

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>引數

`input`：*欄位*

*記錄清單* 類型的資料來源項目的有效路徑。 此項目的值將符合。

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

`list item expression`：*布林值*

一個有效的條件運算式，它指向或包含應用於相符的指定清單的單個欄位。

## <a name="return-values"></a>回傳值

*布林值*

產生的 *布林值* 值。

## <a name="usage-notes"></a>使用方式說明

一般來說，`VALUEIN` 函數被翻譯成一組 **OR** 條件。 如果 **OR** 條件清單很大並且可能超出 SQL 語句的最大總長度，請考慮使用 [`VALUEINLARGE`](er-functions-logical-valueinlarge.md) 函數。

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

在某些情況下，可以使用 `EXISTS JOIN` 運算子將其轉換為資料庫 SQL 陳述式。

> [!NOTE]
> `VALUEIN` 函數回傳的值是[不同用途](er-functions-list-filter.md#usage-notes)，取決於該函數是用於指定 [`FILTER`](er-functions-list-filter.md) 函數還是 [`WHERE`](er-functions-list-where.md) 函數的選取標準。

## <a name="example-1"></a>範例 1

在您的模型對應中，您定義 *導出欄位* 類型的 **清單** 資料來源。 此資料來源包含運算式 `SPLIT ("a,b,c", ",")`。

調用資料來源時，如果已將其設定為 `VALUEIN ("B", List, List.Value)` 運算式，則回傳 **TRUE**。 在這種情況下，`VALUEIN` 函數被轉換為以下一組條件：`(("B" = "a") or ("B" = "b") or ("B" = "c"))`，其中 `("B" = "b")` 等於 **TRUE**。

調用資料來源時，如果已設定為 `VALUEIN ("B", List, LEFT(List.Value, 0))` 運算式，則回傳 **False**。 在這種情況下，`VALUEIN` 函數被轉換為以下條件：`("B" = "")`，它不等於 **True**。

此類條件的文字中的字元數上限為 32,768 個字元。 因此，您不應建立在執行階段可能超過此限制的資料來源。 如果超出限制，應用程式將停止執行，並引發異常。 例如，如果資料來源設定為 `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`，並且 **List1** 和 **List2** 清單包含大量記錄，就會出現這種情況。

在某些情況下，`VALUEIN` 函數透過使用 `EXISTS JOIN` 運算子轉換為資料庫陳述式。 當使用 [`FILTER`](er-functions-list-filter.md) 函數並滿足以下條件時，會發生此行為：

- 對於參考記錄清單的 `VALUEIN` 函數的資料來源，**ASK FOR QUERY** 選項已關閉。 在執行階段不會向此資料來源套用其他條件。
- 沒有為參考記錄清單的 `VALUEIN` 函數的資料來源設定巢狀運算式。
- `VALUEIN` 函數的清單項是指指定資料來源的欄位，而不是該資料來源的運算式或方法。

考慮使用此選項而不是本範例前面描述的 [`WHERE`](er-functions-list-where.md) 函數。

## <a name="example-2"></a>範例 2

您在模型對應中定義以下資料來源：

- *資料表記錄* 類型的 **In** 資料來源。 此資料來源指的是 Intrastat 資料表。
- *資料表記錄* 類型的 **Port** 資料來源。 此資料來源指的是 IntrastatPort 資料表。

當調用設定為 `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` 運算式的資料來源時，會產生以下 SQL 陳述式回傳 Intrastat 表的過濾記錄。

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

對於 **dataAreaId** 欄位，使用 `IN` 運算子產生最終的 SQL 陳述式。

## <a name="example-3"></a>範例 3

您在模型對應中定義以下資料來源：

- *導出欄位* 類型的 **Le** 資料來源。 此資料來源包含運算式 `SPLIT ("DEMF,GBSI,USMF", ",")`。
- *資料表記錄* 類型的 **In** 資料來源。 此資料來源參考 Intrastat 表，並為此打開了 **跨公司** 選項。

當調用已設定為 `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` 運算式的資料來源時，最終的 SQL 陳述式包含以下條件。

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>其他資源

[邏輯函數](er-functions-category-logical.md)

[VALUEINLARGE 函數](er-functions-logical-valueinlarge.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
