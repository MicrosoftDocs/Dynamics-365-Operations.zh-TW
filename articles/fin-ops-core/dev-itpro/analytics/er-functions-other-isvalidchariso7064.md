---
title: ISVALIDCHARACTERISO7064 ER 函數
description: 本主題提供有關如何使用 ISVALIDCHARACTERISO7064 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 884fbf7371ea9d9ac931655f8b11ec1e13c83a46aaa831c96f5d558209205e09
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460168"
---
# <a name="isvalidcharacteriso7064-er-function"></a>ISVALIDCHARACTERISO7064 ER 函數

[!include [banner](../includes/banner.md)]

如果指定的字串表示有效的國際銀行帳號 (IBAN)，則 `ISVALIDCHARACTERISO7064` 函數將回傳 *布林值* **TRUE**。 否則，它會回傳 **FALSE** 的 *布林值*。

## <a name="syntax"></a>語法

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>引數

`text`：*字串*

代表 IBAN 的文字值。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` 會回傳 **TRUE**。 

`ISVALIDCHARACTERISO7064 ("AT61")` 會回傳 **FALSE**。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]