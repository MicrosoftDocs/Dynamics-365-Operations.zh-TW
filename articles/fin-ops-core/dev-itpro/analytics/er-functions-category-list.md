---
title: 清單類別中的 ER 函數清單
description: 本主題提供有關電子報表 (ER) 支援的清單函數的資訊。
author: NickSelin
ms.date: 04/01/2020
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
ms.openlocfilehash: 4f0d9f83a1750ff51d76716147f5d16e96c0fb415608256a5dcc7524a1f2bd2f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460171"
---
# <a name="list-of-er-functions-in-the-list-category"></a>清單類別中的 ER 函數清單

[!include [banner](../includes/banner.md)]

電子報表 (ER) 清單函數可用於從 *記錄清單* 和 *容器 (記錄)* 資料類型的資料來源中擷取資訊並進行操作。 本主題提供了這些函數的摘要。

## <a name="list-of-supported-functions"></a>支援的函數清單

| 函數 | 描述 |
|----------|-------------|
| [AllItems](er-functions-list-allitems.md)                 | 此函數作為記憶體式選取執行。 它回傳一個新的展平 *記錄清單* 值，該清單值包括表示與指定路徑相符的所有項目的記錄清單。 |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | 此函數作為連接的 SQL 查詢執行。 它回傳一個新的展平 *記錄清單* 值，該清單值包括表示與指定路徑相符的所有項目的記錄清單。 |
| [計數](er-functions-list-count.md)                       | 此函數回傳一個 *整數* 值，表示指定清單中的記錄數，如果清單不為空白。 如果清單為空白，此函數會回傳 **0** (零)。 |
| [EmptyList](er-functions-list-emptylist.md)               | 此函數透過使用指定的清單作為清單結構的來源來回傳空白 *記錄清單* 值。|
| [Enumerate](er-functions-list-enumerate.md)               | 此函數回傳一個新的 *記錄清單* 值，該值包含指定清單的列舉記錄。 |
| [篩選](er-functions-list-filter.md)                     | 此函數在查詢經更改後，會將指定的清單作為 *記錄清單* 值回傳，以便過濾指定的條件。 |
| [第一週](er-functions-list-first.md)                       | 此函數將指定清單的第一個記錄回傳為 *容器 (記錄)* 值，前提是該清單不為空白。 如果該清單為空白，此函數將引發異常。 |
| [FirstOrNull](er-functions-list-firstornull.md)           | 此函數將指定清單的第一個記錄回傳為 *容器 (記錄)* 值，前提是該記錄不為空白。 如果記錄為空，則此函數回傳 Null *容器 (記錄)* 值。 |
| [索引](er-functions-list-index.md)                       | 該函數回傳一個 *容器 (記錄)* 值，該值是透過使用指定清單中的指定數字索引選取的。 如果索引超出指定清單中記錄的範圍，則此函數將引發異常。 |
| [IsEmpty](er-functions-list-isempty.md)                   | 如果指定的清單不包含任何記錄，則此函數回傳 **True** 的 *布林值* 值。 否則，它會回傳 **FALSE** 的 *布林值*。 |
| [清單](er-functions-list-list.md)                         | 此函數回傳一個 *記錄清單* 值，該值包含從指定引數建立的新清單。|
| [ListDistinct](er-functions-list-listdistinct.md)         | 此函數計算指定運算式作為指定清單的每條記錄的選取器。 它回傳一個新的 *記錄清單* 值，其中包含每個唯一選取值的單個記錄。|
| [ListJoin](er-functions-list-listjoin.md)                 | 此函數回傳一個 *記錄清單* 值，表示從指定的引數建立的新加入清單。|
| [ListOfFields](er-functions-list-listoffields.md)         | 此函數回傳基於 *列舉* 或 *容器 (記錄)* 類型的指定引數的結構建立的 *記錄清單* 值。 |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | 此函數回傳一個僅包含指定清單的第一個記錄的 *記錄清單* 值。|
| [OrderBy](er-functions-list-orderby.md)                   | 此函數在根據指定引數排序後將指定清單作為 *記錄清單* 值回傳。 這些引數可以定義為運算式。 |
| [Reverse](er-functions-list-reverse.md)                   | 此函數將指定的清單回傳為反向排序順序的 *記錄清單* 值。 |
| [分割](er-functions-list-split.md)                       | 此函數將指定的輸入字串拆分為子字串並將結果回傳為新的 *記錄清單* 值。 |
| [SplitList](er-functions-list-splitlist.md)               | 此函數將指定清單拆分為子清單 (或批次)，每個子清單包含指定數量的記錄。 然後它將結果回傳為包含批次處理的新 *記錄清單* 值。 |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | 此函數將指定清單拆分為新的子清單 (批次) 清單。 每批中的記錄數是動態計算的。 然後該函數將結果回傳為包含批次處理的新 *記錄清單* 值。 |
| [StringJoin](er-functions-list-stringjoin.md)             | 此函數回傳一個 *字串* 值，由指定清單中的指定欄位的連接值組成。 這些值可以由指定的分隔符號分隔。 |
| [Where](er-functions-list-where.md)                       | 根據指定條件，此函數將指定的清單回傳為 *記錄清單* 值。 |

## <a name="additional-resources"></a>其他資源

[電子報表概觀](general-electronic-reporting.md)

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[電子報表公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]