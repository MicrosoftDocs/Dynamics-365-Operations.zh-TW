---
title: SUMIF ER 函數
description: 本主題提供有關如何使用 SUMIF 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 04/27/2020
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
ms.openlocfilehash: 8721e0115ab3c5ebe3071fe0b9ca5a80db766b0878d886b186f3f3d39f4a6397
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460396"
---
# <a name="sumif-er-function"></a>SUMIF ER 函數

[!include [banner](../includes/banner.md)]

`SUMIF` 函數回傳一個 *實數* 值，該值表示由格式元素的繫結回傳的值和當格式元素在格式運行期間產生輸出文件時收集的值之和，並滿足指定條件。 該條件都由一個索引鍵範圍和一個索引鍵值組成。

## <a name="syntax"></a>語法

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a>引數

`key name for summing`：*字串*

由電子報告格式 (ER) 格式組件的 **收集資料索引鍵名稱** 屬性設定的運算式回傳的值，必須將繫結值用於求和目的。

**收集的資料索引鍵值** 屬性可以設定為位於 **Common\\File** 組件下的 ER 格式的 **序列** 組件或 **XML 元素** 組件，其中 **收集輸出詳情** 選項已打開。

## <a name="return-values"></a>回傳值

*真實*

產生的數值。

## <a name="usage-notes"></a>使用方式說明

當現行 **Common\\File** 組件的 **收集輸出詳情** 選項關閉時，此函數回傳 **0** (零) 值。

在 `condition range` 引數中，萬用字元 **"\*"** 可用於表示任意多個字元。

在 `condition value` 引數中，萬用字元 **"\*"** 可用於表示任意多個字元。

## <a name="example"></a>範例

如需如何使用此函數的相關信息，請參閱 **獲取/開發 IT 服務/解決方案組件** 業務流程的一部分 [ER 使用格式輸出的資料進行計數和求和](tasks/er-format-counting-summing-1.md)工作指南。

如需有關使用此函數的相關信息和範例，請參閱[遞延執行 ER 格式的序列元素](er-defer-sequence-element.md#Example)和[遞延執行 ER 格式的 XML 元素](er-defer-xml-element.md#Example)。

## <a name="additional-resources"></a>其他資源

[資料收集函數](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]