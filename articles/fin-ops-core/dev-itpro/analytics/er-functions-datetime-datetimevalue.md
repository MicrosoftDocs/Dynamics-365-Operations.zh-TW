---
title: DATETIMEVALUE ER 函數
description: 本主題提供有關如何使用 DATETIMEVALUE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 09/08/2021
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
ms.openlocfilehash: 7a9da0b9461926b1033d6a97b37d4b43a86d8dad
ms.sourcegitcommit: e7eeca05d738e9e46d6185d1ba349836ebafc1a4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2021
ms.locfileid: "8460164"
---
# <a name="datetimevalue-er-function"></a>DATETIMEVALUE ER 函數

[!include [banner](../includes/banner.md)]

`DATETIMEVALUE` 函數回傳一個 *[日期時間](er-formula-supported-data-types-primitive.md#datetime)* 值，該值從指定格式和可選指定[文化](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)的給定文字值轉換為日期/時間值。 如需支援格式的相關信息，請參閱[標準](/dotnet/standard/base-types/standard-date-and-time-format-strings)和[自訂](/dotnet/standard/base-types/custom-date-and-time-format-strings)。

## <a name="syntax-1"></a>語法 1

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>語法 2

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>引數

`text`*[字串](er-formula-supported-data-types-primitive.md#string)*

表示要格式化的值的文字。

`format`：*字串*

給定文字的格式。 如需支援格式的相關信息，請參閱[標準](/dotnet/standard/base-types/standard-date-and-time-format-strings)和[自訂](/dotnet/standard/base-types/custom-date-and-time-format-strings)。

`culture`：*字串*

用於格式化給定文字的區域性。 如需支援的文化的相關信息，請參閱[文化](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)。

## <a name="return-values"></a>回傳值

*DateTime*

產生的日期/時間值。

## <a name="usage-notes"></a>使用方式說明

當文化沒有被定義為被調用函數的參數時，`culture` 的值由調用內容定義。 例如，如果為設定為使用德國文化的 **FILE** 元素使用電子報表 (ER) 格式中的語法 1 調用 `DATETIMEVALUE` 函數，則將使用德國文化完成轉換。 預設的 `culture` 值為 **EN-US**。

## <a name="example-1"></a>範例 1

`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` 根據指定的自訂格式和預設應用程式的 **EN-US** 文化回傳 **2016 年 12 月 21 日 2:55:00 AM**。

## <a name="example-2"></a>範例 2

`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` 根據指定的自訂格式和區域性回傳 **2016 年 12 月 21 日 2:55:00 AM**。

然而，`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` 引發異常以通知使用者指定的字串未被識別為指定區域性的有效日期/時間。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
