---
title: DATEFORMAT ER 函數
description: 本主題提供有關如何使用 DATEFORMAT 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 4a6c113f5f8147cbeaab103e86a44d4c66272c13
ms.sourcegitcommit: e7eeca05d738e9e46d6185d1ba349836ebafc1a4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2021
ms.locfileid: "8460177"
---
# <a name="dateformat-er-function"></a>DATEFORMAT ER 函數

[!include [banner](../includes/banner.md)]

`DATEFORMAT` 函數回傳一個 *[字串](er-formula-supported-data-types-primitive.md#string)* 值，它將給定的日期值顯示為指定格式和可選指定[文化](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)的文字。 如需支援格式的相關信息，請參閱[標準](/dotnet/standard/base-types/standard-date-and-time-format-strings)和[自訂](/dotnet/standard/base-types/custom-date-and-time-format-strings)。

## <a name="syntax-1"></a>語法 1

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a>語法 2

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a>引數

`date`：*[日期](er-formula-supported-data-types-primitive.md#date)*

表示要格式化的日期的日期值。

`format`：*字串*

輸出字串的格式。 如需支援格式的相關信息，請參閱[標準](/dotnet/standard/base-types/standard-date-and-time-format-strings)和[自訂](/dotnet/standard/base-types/custom-date-and-time-format-strings)。

> [!NOTE]
> 當您使用標準格式或自訂格式時，格式字串區分大小寫。 例如，[標準](/dotnet/standard/base-types/standard-date-and-time-format-strings)「d」格式說明符使用短日期模式回傳日期，而標準「D」格式說明符使用長日期模式回傳日期。 此外，[自訂](/dotnet/standard/base-types/custom-date-and-time-format-strings)「M」格式指定元回傳從 1 到 12 的月份，而自訂「m」格式指定元回傳從 0 到 59 的分鐘。

`culture`：*字串*

用於格式化的文化。 如需支援的文化的相關信息，請參閱[文化](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)。

## <a name="return-values"></a>回傳值

*字串*

產生的字串值。

## <a name="usage-notes"></a>使用方式說明

如果文化沒有被定義為被調用函數的參數，那麼 `culture` 的值由調用內容定義。 例如，如果為設定為使用德國文化的 **FILE** 元素使用電子報表 (ER) 格式中的語法 1 調用 `DATEFORMAT` 函數，則將使用德國文化完成轉換。 預設的 `culture` 值為 **EN-US**。

## <a name="example-1"></a>範例 1

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` 根據指定的自訂格式回傳現行應用程式伺服器日期 2015 年 12 月 24 日，作為字串 **「24-12-2015」**。

## <a name="example-2"></a>範例 2

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` 根據所選的德國文化和指定的格式，以字串 **「24-12-2015」** 的形式回傳現行的應用程式工作階段日期，即 2015 年 12 月 24 日。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
