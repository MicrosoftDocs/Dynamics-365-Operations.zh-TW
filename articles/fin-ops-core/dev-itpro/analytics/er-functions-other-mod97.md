---
title: MOD_97 ER 函數
description: 本主題提供有關如何使用 MOD_97 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: edc29cac14014929e0672183be1c5db44fe6b5afe9543cd00942a95c79ec8897
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460152"
---
# <a name="mod_97-er-function"></a>MOD_97 ER 函數

[!include [banner](../includes/banner.md)]

`MOD_97` 函數根據指定發票編號的數字回傳一個 *字串* 值，該值將貸方參考表示為 MOD97 運算式。

## <a name="syntax"></a>語法

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a>引數

`invoice number digits`：*字串*

代表發票編號數字的文字值。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`MOD_97 ("VEND-200002")` 會回傳 **"20000285"**。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]