---
title: WEEKNUM ER 函數
description: 本主題提供有關如何使用 WEEKNUM 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 37e62b32896e2030b3322a89ac4acdd6c18d5e3c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460589"
---
# <a name="weeknum-er-function"></a>WEEKNUM ER 函數

[!include [banner](../includes/banner.md)]

`WEEKNUM` 函數回傳一個 *[整數](er-formula-supported-data-types-primitive.md#integer)* 值，該值表示包含指定 *[日期](er-formula-supported-data-types-primitive.md#date)* 值的一年中的第幾週。 該計算基於定義日曆週和一週第一天的文化相關規則。

## <a name="syntax"></a>語法

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">引數</a>

`date`：*日期*

一個日期值，表示用於計算一年中第幾週的日期。

`culture`*[字串](er-formula-supported-data-types-primitive.md#string)*

用於計算的文化。 您可以使用受 .NET [標準](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0)支援的文化代碼。

## <a name="return-values"></a>回傳值

*整數*

產生的數值。

## <a name="usage-notes"></a>使用方式說明

如果該標準已被執行階段提供區域設定的國家或地區採用，則根據 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 標準計算一年中的星期幾。 否則，計算基於國家/地區特定的國家標準。

如果在執行階段提供了不受支援的[文化](#arguments)代碼作為 `WEEKNUM` 函數的引數，則會引發異常。 如果提供空白字串作為文化代碼，則使用英語國家/地區中性日曆來計算週數。

## <a name="examples"></a>範例

`WEEKNUM (DATEVALUE ("01-01-2020", "de"))` 會回傳 **1**。

`WEEKNUM (DATEVALUE ("01-01-2021", "de"))` 會回傳 **53**。

`WEEKNUM (DATEVALUE ("01-01-2022", "de"))` 會回傳 **52**。

`WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` 會回傳 **21**。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
