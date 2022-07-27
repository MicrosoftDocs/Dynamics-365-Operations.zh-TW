---
title: CHAR ER 函數
description: 本主題提供有關如何使用 CHAR 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: e422ccc406e919b2191f4bccb1ac8198bba84b09e9f01f6971876e2c6507d6d3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460284"
---
# <a name="char-er-function"></a>CHAR ER 函數

[!include [banner](../includes/banner.md)]

`CHAR` 函數回傳一個 *字串* 值，該值表示由指定 Unicode 編號參考的單個字元。

## <a name="syntax"></a>語法

```vb
CHAR (number)
```

## <a name="arguments"></a>引數

`number`：*整數*

對應於預期單個字元的數字。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

此函數回傳的字串取決於在父 **FILE** 格式元素中選取的編碼。 如需支援的編碼清單，請參閱[編碼類別](/dotnet/api/system.text.encoding)。

## <a name="example"></a>範例

`CHAR (255)` 會回傳 **"ÿ"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]