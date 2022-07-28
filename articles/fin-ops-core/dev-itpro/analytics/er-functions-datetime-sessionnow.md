---
title: SESSIONNOW ER 函數
description: 本主題提供有關如何使用 SESSIONNOW 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: fc532a96c7e52e6a12877ae88d1a6183829a1282d43c7df52dd90e536a7e3d75
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460386"
---
# <a name="sessionnow-er-function"></a>SESSIONNOW ER 函數

[!include [banner](../includes/banner.md)]

`SESSIONNOW` 函數回傳代表現行應用程式工作階段日期和時間的 *日期時間* 值。

## <a name="syntax"></a>語法

```vb
SESSIONNOW ()
```

## <a name="return-values"></a>回傳值

*DateTime*

產生的日期/時間值。

## <a name="example"></a>範例

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` 根據所選的德國文化和指定的格式，將現行應用程式工作階段日期/時間值 (2015 年 12 月 24 日) 回傳為 **「24.12.2015」**。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]