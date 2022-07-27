---
title: 邏輯類別中的 ER 函數清單
description: 本主題提供有關電子報告 (ER) 支援的邏輯函數的資訊。
author: NickSelin
ms.date: 02/11/2021
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
ms.openlocfilehash: 43cbecf80ff70dac058977932c3a0bb03662cd98a88c68407051bdc584609d84
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460170"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>邏輯類別中的 ER 函數清單

[!include [banner](../includes/banner.md)]

電子報告 (ER) 邏輯函數可用於處理邏輯值，以在單個運算式中執行多個比較或測試多個條件。 本主題提供了這些函數的摘要。

## <a name="list-of-supported-functions"></a>支援的函數清單

| 函數 | 描述 |
|----------|-------------|
| [和](er-functions-logical-and.md)                       | 如果所有指定條件都為真，則此函數回傳 **TRUE** 的 *布林值*。 否則，它會回傳 **FALSE** 的 *布林值*。 |
| [案例](er-functions-logical-case.md)                     | 此函數根據指定的替代選項計算指定運算式的值，並回傳等於指定運算式值的第一個選項的結果。 否則，如果預設結果被指定為被調用函數的最後一個參數且前面沒有選項，則它回傳一個可選的預設結果。 回傳的值可以是任何受支援的資料類型的值。 |
| [Contains](er-functions-logical-contains.md)             | 此函數確定指定的輸入是否包含指定的文字。 如果指定的輸入包含指定的文字，則回傳 *布林值* **TRUE**。 否則，它會回傳 **FALSE** 的 *布林值*。 |
| [EndsWith](er-functions-logical-endswith.md)             | 此函數確定指定輸入是否以指定文字結尾。 如果指定的輸入以指定的文字結尾，則回傳 *布林值* **TRUE**。 否則，它會回傳 **FALSE** 的 *布林值*。 |
| [If](er-functions-logical-if.md)                         | 如果滿足指定條件，此函數回傳第一個指定值。 否則，它回傳第二個指定值。 回傳的值可以是任何受支援的資料類型的值。 |
| [Not](er-functions-logical-not.md)                       | 此函數將指定條件的反轉邏輯值作為 *布林值* 回傳。 |
| [或](er-functions-logical-or.md)                         | 如果所有指定條件都為假，則此函數回傳 **FALSE** 的 *布林值*。 如果任何指定條件為真，則該函數回傳 *布林值* **TRUE**。 |
| [StartsWith](er-functions-logical-startswith.md)         | 此函數確定指定輸入是否以指定文字開頭。 如果指定輸入以指定文字開頭，則回傳 *布林值* **TRUE**。 否則，它會回傳 **FALSE** 的 *布林值*。 |
| [ValueIn](er-functions-logical-valuein.md)               | 此函數確定指定輸入是否與指定清單中指定項的任何值相符。 如果指定的輸入與對指定清單的至少一條記錄執行指定運算式的結果相符，則回傳 **True** 的 *布林值*。 否則，它會回傳 **FALSE** 的 *布林值*。 |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | 此函數確定 *Int64* 或 *Integer* 類型的指定輸入是否與指定清單中指定項的任何值匹配。 如果指定的輸入與對指定清單的至少一條記錄執行指定運算式的結果相符，則回傳 **True** 的 *布林值*。 否則，它會回傳 **FALSE** 的 *布林值*。 |


## <a name="additional-resources"></a>其他資源

[電子報告概觀](general-electronic-reporting.md)

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[電子報表公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]