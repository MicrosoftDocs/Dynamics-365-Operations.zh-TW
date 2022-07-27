---
title: UPPER ER 函數
description: 本主題提供有關如何使用 UPPER 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 3742f490fb87d156e3b3dcebabdcebb85ab76f5d0afd9a60806497d32e5746e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460397"
---
# <a name="upper-er-function"></a>UPPER ER 函數

[!include [banner](../includes/banner.md)]

`UPPER` 函數將指定的文字字串轉換為大寫字母後作為 *字串* 值回傳。

## <a name="syntax"></a>語法

```vb
UPPER (text )
```

## <a name="arguments"></a>引數

`text`：*字串*

*字串* 類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`UPPER ("Sample")` 會回傳 **"SAMPLE"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]