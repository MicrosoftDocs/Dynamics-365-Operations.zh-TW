---
title: COLLECTEDLIST ER 函數
description: 本主題提供有關如何使用 COLLECTEDLIST 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 1b744a2bad1f463bcc8d278b48739208689f3529da91090e76d34871c534f873
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460189"
---
# <a name="collectedlist-er-function"></a>COLLECTEDLIST ER 函數

[!include [banner](../includes/banner.md)]

`COLLECTEDLIST` 函數一個 *記錄清單* 值，它包含格式元素的 **已收集資料索引鍵值** 屬性回傳的值清單，並在格式執行期間使用格式元素產生外發檔時收集，並且滿足指定條件。 每個條件都由一個索引鍵範圍和一個索引鍵值組成。

## <a name="syntax"></a>語法

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>引數

`condition 1 range`：*字串*

由已在電子報表 (ER) 格式組件的 **收集的資料索引鍵名稱** 屬性中設定的運算式回傳的值。 此引數是強制性的。

`condition 1 value`：*字串*

由已在電子報表 (ER) 格式組件的 **收集的資料索引鍵值** 屬性中設定的運算式回傳的值。 此引數是強制性的。

`condition N range`：*字串*

由已在電子報表 (ER) 格式組件的 **收集的資料索引鍵名稱** 屬性中設定的運算式回傳的值。 這些附加引數是可選的。

`condition N value`：*字串*

由已在電子報表 (ER) 格式組件的 **收集的資料索引鍵值** 屬性中設定的運算式回傳的值。 這些附加引數是可選的。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

可以為 **序列** 組件或 ER 格式的 **XML 元素** 組件設定 **收集的資料索引鍵名稱** 和 **收集的資料索引鍵值** 屬性，該組件位於打開 **收集輸出詳情** 選項的 **Common\\File** 組件下。

當現行 **Common\\File** 組件的 **收集輸出詳情** 選項關閉時，此函數回傳一個空白清單。

在 `condition range` 引數中，萬用字元 **「\*」** 可用於表示任意多個字元。

在 `condition value` 引數中，萬用字元 **「\*」** 可用於表示任意多個字元。

## <a name="example"></a>範例

如需如何使用此函數的相關信息，請參閱 **獲取/開發 IT 服務/解決方案組件** 業務流程的一部分 [ER 使用格式輸出的資料進行計數和求和](tasks/er-format-counting-summing-1.md)工作指南。

## <a name="additional-resources"></a>其他資源

[資料收集函數](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]