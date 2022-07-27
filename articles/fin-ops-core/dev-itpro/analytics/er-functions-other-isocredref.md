---
title: ISOCREDREF ER 函數
description: 本主題提供有關如何使用 ISOCREDREF 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: e13b9bacc642917e6a520968630fc75fb30bc9dc3fd02b2d9aa3cfb2ceb33790
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460169"
---
# <a name="isocredref-er-function"></a>ISOCREDREF ER 函數

[!include [banner](../includes/banner.md)]

`ISOCREDREF` 函數根據指定發票編號的數字和字母符號回傳代表國際標準化組織 (ISO) 貸方參考的 *字串* 值。

## <a name="syntax"></a>語法

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>引數

`invoice number digits`：*字串*

代表發票編號數字的文字值。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

> [!NOTE] 
> 為了消除不符合 ISO 標準的字母表中的符號，`invoice number digits` 引數必須在傳遞給此函數之前進行翻譯。

## <a name="example"></a>範例

`ISOCredRef ("VEND-200002")` 會回傳 **"RF23VEND-200002"**。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]