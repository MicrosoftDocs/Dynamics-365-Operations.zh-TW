---
title: GETCURRENTCOMPANY ER 函數
description: 本主題提供有關如何使用 GETCURRENTCOMPANY 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: c74ffaf1ee134da8d962e054656301d5e99827ff53f560f5d93f9dcb51819c13
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460161"
---
# <a name="getcurrentcompany-er-function"></a>GETCURRENTCOMPANY ER 函數

[!include [banner](../includes/banner.md)]

`GETCURRENTCOMPANY` 函數回傳一個 *字串* 值，該值表示使用者現行登入的法律實體 (公司) 的代碼。

## <a name="syntax"></a>語法

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`GETCURRENTCOMPANY ()` 為登入到 **Contoso Entertainment System USA** 公司的使用者回傳 **USMF**。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]