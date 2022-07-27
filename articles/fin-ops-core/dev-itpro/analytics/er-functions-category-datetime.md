---
title: 日期和時間類別中的 ER 函數清單
description: 本主題提供有關電子報表 (ER) 中支援的日期和時間函數的信息。
author: NickSelin
ms.date: 09/09/2021
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
ms.openlocfilehash: 0a0322e5490474e21ad91076ecc486f38a776e32
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2021
ms.locfileid: "8460173"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>日期和時間類別中的 ER 函數清單

[!include [banner](../includes/banner.md)]

電子報表 (ER) 日期和時間函數可用於從日期和時間值中提取信息，並對它們執行操作。 本主題提供了這些函數的摘要。

## <a name="list-of-supported-functions"></a>支援的函數清單

| 函數 | 描述 |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | 此函數回傳一個 *[日期時間](er-formula-supported-data-types-primitive.md#datetime)* 值，該值是指定開始日期之前或之後的指定天數。 |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | 此函數回傳一個 *日期時間* 值，該值從一個時區中的給定日期/時間值轉換為另一個時區中的日期/時間值。 |
| [DateFormat](er-functions-datetime-dateformat.md) | 此函數回傳一個 *[字串](er-formula-supported-data-types-primitive.md#string)* 值，該值將給定的日期值顯示為指定格式和可選指定區域性的文字。 |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | 此函數回傳一個 *字串* 值，該值將給定的日期/時間值顯示為指定格式和可選指定區域性的文字。 |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | 此函數回傳一個 *日期時間* 值，該值從指定格式和可選指定區域性的給定文字值轉換為日期/時間值。 |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | 此函數回傳一個 *日期時間* 值，該值從給定的日期值轉換為國際標準時間 (格林威治標準時間 \[GMT\]) 中的日期/時間值。 |
| [DateValue](er-functions-datetime-datevalue.md) | 此函數回傳一個 *[日期](er-formula-supported-data-types-primitive.md#date)* 值，該值從指定格式和可選指定區域性的給定文字值轉換為日期值。 |
| [DayOfYear](er-functions-datetime-dayofyear.md) | 此函數回傳一個 *[整數](er-formula-supported-data-types-primitive.md#integer)* 值，表示從 1 月 1 日到指定日期之間的天數。 |
| [Days](er-functions-datetime-days.md) | 此函數回傳一個 *整數* 值，該值表示一個指定日期和第二個指定日期之間的天數。 |
| [Now](er-functions-datetime-now.md) | 此函數回傳代表現行應用程式服務器日期和時間的 *日期時間* 值。 |
| [NullDate](er-functions-datetime-nulldate.md) | 此函數回傳代表 **Null** 日期 (1900 年 1 月 1 日) 的 *Date* 值。 |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | 此函數回傳一個 *日期時間* 值，該值表示國際標準時間的 **Null** 日期/時間值 (1900 年 1 月 1 日)。 |
| [SessionNow](er-functions-datetime-sessionnow.md) | 此函數回傳代表現行應用程式工作階段日期和時間的 *日期時間* 值。 |
| [SessionToday](er-functions-datetime-sessiontoday.md) | 此函數回傳代表現行應用程式工作階段日期的 *日期* 值。 |
| [今天](er-functions-datetime-today.md) | 此函數回傳代表現行應用程式伺服器日期的 *日期* 值。 |
| [WeekNum](er-functions-datetime-weeknum.md) | 此函數回傳一個 *整數* 值，表示一年中的第幾週。 |

## <a name="additional-resources"></a>其他資源

[電子報表概觀](general-electronic-reporting.md)

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[電子報表公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
