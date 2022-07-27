---
title: 資料收集類別中的 ER 函數清單
description: 本主題提供有關電子報表 (ER) 中支援的資料收集函數的信息。
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 2046931732f2d1c1ca040c1c84d4b182c2214f2f44a5a90fceda49298445b743
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460172"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>資料收集類別中的 ER 函數清單

[!include [banner](../includes/banner.md)]

電子報表 (ER) 資料收集函數用於根據已經以 **文字** 或 **Xml** 格式產生的輸出資料，以正在執行的 ER 格式進行計數和求和。 此方法用於幫助提高執行的 ER 格式的效能、在產生的文件中輸入執行總計的值以及用於其他目的。 本主題提供了這些函數的摘要。

## <a name="list-of-supported-functions"></a>支援的函數清單

| 函數 | 描述 |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | 此函數回傳一個 *記錄清單* 值，該值包含格式元素的 **已收集資料索引鍵值** 屬性回傳的值清單，並在格式執行期間使用格式元素產生輸出文件時收集，並且滿足指定條件 . 每個條件都由一個索引鍵範圍和一個索引鍵值組成。 |
| [CountIF](er-functions-datacollection-countif.md) | 此函數回傳一個 *整數* 值，該值表示在格式執行期間使用格式元素產生輸出文件時收集的格式元素的數量，並且滿足指定條件。 該條件都由一個索引鍵範圍和一個索引鍵值組成。 |
| [CountIFs](er-functions-datacollection-countifs.md) | 此函數回傳一個 *整數* 值，該值表示在格式執行期間使用格式元素產生輸出文件時收集的格式元素的數量，並且滿足指定條件。 每個條件都由一個索引鍵範圍和一個索引鍵值組成。 |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | 此函數回傳一個 *字串* 值，該值表示現行 ER 格式元素的名稱。 |
| [SumIF](er-functions-datacollection-sumif.md) | 此函數回傳一個 *實數* 值，該值表示在格式執行期間使用格式元素產生輸出文件時由格式元素的繫結回傳並收集的值的總和，並且滿足指定的條件。 該條件都由一個索引鍵範圍和一個索引鍵值組成。 |
| [SumIFs](er-functions-datacollection-sumifs.md) | 此函數回傳一個 *實數* 值，該值表示在格式執行期間使用格式元素產生輸出文件時由格式元素的繫結回傳並收集的值的總和，並且滿足指定的條件。 每個條件都由一個索引鍵範圍和一個索引鍵值組成。 |

## <a name="additional-resources"></a>其他資源

[電子報表概觀](general-electronic-reporting.md)

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[電子報表公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]