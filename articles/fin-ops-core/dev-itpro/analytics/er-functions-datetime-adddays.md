---
title: ADDDAYS ER 函數
description: 本主題提供有關如何使用 ADDDAYS 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/03/2019
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
ms.openlocfilehash: 8877bf5a1b6c06e1a25fa9ddaca9c3b039bd2e4d01f39eea9065125977f73e9a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460394"
---
# <a name="adddays-er-function"></a>ADDDAYS ER 函數

[!include [banner](../includes/banner.md)]

`ADDDAYS` 函數計算一個 *日期時間* 值，該值是指定開始日期之前或之後的指定天數。

## <a name="syntax"></a>語法

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>引數

`datetime`：*日期時間*

表示開始日期的日期/時間值。

`days`：*整數*

`datetime` 之前或之後的天數。

## <a name="return-values"></a>回傳值

*DateTime*

產生的日期/時間值。

## <a name="usage-notes"></a>使用方式說明

`days` 的正值會產生未來的日期。 負值產生過去的日期。

## <a name="example-1"></a>範例 1

`ADDDAYS (NOW(), 7)` 會回傳未來七天後的日期和時間。

## <a name="example-2"></a>範例 2

`ADDDAYS (NOW(), -3)` 會回傳過去三天後的日期和時間。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]