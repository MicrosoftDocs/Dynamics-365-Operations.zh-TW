---
title: 類型轉換類別中的 ER 函數清單
description: 本主題提供有關電子報表 (ER) 中支援的轉換函數的資訊。
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
ms.openlocfilehash: a6d678c2a38039285bd835abcbbaf13ec00298c0660c62e7496a5d7405db8f61
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460193"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>類型轉換類別中的 ER 函數清單

[!include [banner](../includes/banner.md)]

電子報表 (ER) 類型轉換函數可用於在類型之間轉換值。 本主題提供了這些函數的摘要。

## <a name="type-conversion-functions"></a>類型轉換函數

| 函數 | 描述 |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | 此函數回傳一個表示指定字串的 *Int64* 值。 |
| [IntValue](er-functions-conversion-intvalue.md)       | 此函數回傳一個表示指定字串的 *Int* 值。 |
| [NumberValue](er-functions-conversion-numbervalue.md) | 此函數回傳一個從指定的 *字串* 值轉換而來的 *實數* 值。 在轉換過程中，會考慮指定的小數和數字分組分隔符號。 |
| [值](er-functions-conversion-value.md)             | 此函數回傳一個從指定的 *字串* 值轉換而來的 *實數* 值。 |

## <a name="type-conversion-functions-in-the-container-category"></a>容器類中的類型轉換函數

下表描述了[容器](er-functions-category-container.md)類中的類型轉換函數。

| 函數 | 描述 |
|----------|-------------|
| [Base64StringToContainer](er-functions-container-base64stringtocontainer.md) | 該函數將 *字串* 類型的指定輸入轉換為 *容器* 類型的資料項。 |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>日期和時間類中的類型轉換函數

下表描述了[日期和時間](er-functions-category-datetime.md)類別中的類型轉換函數。

| 函數 | 描述 |
|----------|-------------|
| [DateTimeValue](er-functions-datetime-datetimevalue.md)   | 此函數回傳一個 *日期時間* 值，該值從指定格式和可選指定區域性的給定 *字串* 值轉換為日期/時間值。 |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | 此函數回傳一個 *日期時間* 值，該值從給定的 *日期* 值轉換為國際標準時間 (格林威治標準時間 \[GMT\]) 的日期/時間值。 |
| [DateValue](er-functions-datetime-datevalue.md)           | 此函數回傳一個 *日期* 值，該值從指定格式和可選指定區域性的給定 *字串* 值轉換為日期值。 |

## <a name="type-conversion-functions-in-the-list-category"></a>清單類中的類型轉換函數

下表描述了[清單類別](er-functions-category-list.md)類中的類型轉換函數。

| 函數 | 描述 |
|----------|-------------|
| [清單](er-functions-list-list.md)                 | 此函數回傳一個 *記錄清單* 值作為一個新清單，該清單是從 *容器 (記錄)* 類型的指定參數建立的。 |
| [ListOfFields](er-functions-list-listoffields.md) | 此函數回傳基於 *列舉* 或 *容器 (記錄)* 類型的給定參數的結構建立的 *記錄清單* 值。 |
| [分割](er-functions-list-split.md)               | 此函數將指定的 *字串* 值拆分為子字串，並將結果作為新的 *記錄清單* 值回傳。 |
| [StringJoin](er-functions-list-stringjoin.md)     | 此函數回傳一個 *字串* 值，由指定 *記錄清單* 值中的指定欄位的連接值組成。 這些值可以由指定的分隔符號分隔。 |

## <a name="type-conversion-functions-in-the-text-category"></a>文字類中的類型轉換函數

下表描述了[文字類別](er-functions-category-text.md)類中的類型轉換函數。

| 函數 | 描述 |
|----------|-------------|
| [Char](er-functions-text-char.md)                 | 此函數回傳一個 *字串* 值，該值表示由指定 Unicode 編號參考的單個字元。 |
| [GuidValue](er-functions-text-guidvalue.md)       | 該函數將 *字串* 類型的指定輸入轉換為 *GUID* 類型的資料項。 |
| [NumberFormat](er-functions-text-numberformat.md) | 此函數回傳一個 *字串* 值，該值表示以指定格式和可選指定區域性表示的指定數字。 |
| [QrCode](er-functions-text-qrcode.md)             | 此函數回傳一個 *容器* 值，該值以二進位格式顯示指定字串的快速回應碼 (QR 碼) 影像。 |
| [文字](er-functions-text-text.md)                 | 此函數回傳一個 *字串* 值，該值表示指定數字在轉換為根據現行應用程式實體的伺服器區域設定格式化的文字字串後。 |

## <a name="additional-resources"></a>其他資源

[電子報表概觀](general-electronic-reporting.md)

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[電子報表公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]