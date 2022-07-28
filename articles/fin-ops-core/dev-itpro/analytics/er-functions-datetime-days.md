---
title: DAYS ER 函數
description: 本主題提供有關如何使用 DAYS 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 19e363e7bc8b8ad898244702ad6ba14bcf490f5ca2381b006a35dc0ed9309d49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460389"
---
# <a name="days-er-function"></a>DAYS ER 函數

[!include [banner](../includes/banner.md)]

`DAYS` 函數回傳一個 *整數* 值，該值表示一個指定日期和第二個指定日期之間的天數。

## <a name="syntax"></a>語法

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>引數

`date 1`：*日期*

一個日期值，表示計算天數的開始日期。

`date 2`：*日期*

一個日期值，表示計算天數的結束日期。

## <a name="return-values"></a>回傳值

*整數*

產生的數值。

## <a name="usage-notes"></a>使用方式說明

`DAYS` 函數在第一個日期晚於第二個日期時回傳正值，當第一個日期等於第二個日期時回傳 **0** (零)，當第一個日期早於第二個日期時回傳負值日期。

## <a name="example"></a>範例

`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` 會回傳 **-1**。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]