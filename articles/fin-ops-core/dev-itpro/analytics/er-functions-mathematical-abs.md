---
title: ABS ER 函數
description: 本主題提供有關如何使用 ABS 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: db12ddddb087556414e81d646c4c87d273a77c133e49152091452d0731916e93
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460160"
---
# <a name="abs-er-function"></a>ABS ER 函數

[!include [banner](../includes/banner.md)]

`ABS` 函數將指定數字的絕對值 (模組) 作為 *實數* 值回傳。 換句話說，它回傳沒有符號的數字。

## <a name="syntax"></a>語法

```vb
ABS (number)
```

## <a name="arguments"></a>引數

`number`：*實數*

您想要取模的數值。

## <a name="return-values"></a>回傳值

*真實*

產生的數值。

## <a name="example"></a>範例

`ABS (-1)` 會回傳 **1**。

## <a name="additional-resources"></a>其他資源

[數學函數](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]