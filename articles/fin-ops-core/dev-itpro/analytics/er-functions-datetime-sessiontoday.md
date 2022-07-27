---
title: SESSIONTODAY ER 函數
description: 本主題提供有關如何使用 SESSIONTODAY 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: caadfbe9d82c967b84abd362211a2ecec1bdd0481c7f3907816b7aec23883175
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460383"
---
# <a name="sessiontoday-er-function"></a>SESSIONTODAY ER 函數

[!include [banner](../includes/banner.md)]

`SESSIONTODAY` 函數回傳代表現行應用程式工作階段日期的 *日期* 值。

## <a name="syntax"></a>語法

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a>回傳值

*日期*

產生的日期值。

## <a name="example"></a>範例

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` 根據所選的德國文化和指定的格式，以字串 **「24-12-2015」** 的形式回傳現行的應用程式工作階段日期，即 2015 年 12 月 24 日。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]