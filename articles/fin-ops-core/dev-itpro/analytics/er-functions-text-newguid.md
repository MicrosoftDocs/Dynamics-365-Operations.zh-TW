---
title: NEWGUID ER 函數
description: 本主題提供有關如何使用 NEWGUID 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 5856a4d765f5136ecb11a34e0255c1ba88818f2c
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "8460586"
---
# <a name="newguid-er-function"></a>NEWGUID ER 函數

[!include [banner](../includes/banner.md)]

`NEWGUID` 函數產生一個新的全域唯一識別碼 (GUID) 並將其作為 *[GUID](er-formula-supported-data-types-primitive.md#guid)* 值回傳。

## <a name="syntax"></a>語法

```vb
NEWGUID ()
```

## <a name="return-values"></a>回傳值

*GUID*

產生的 GUID 值。

## <a name="example"></a>範例

`NEWGUID()` 總是回傳一個新的 *GUID* 值，例如 **3afcf7ff-af10-ec11-b6e6-000d3a13209e**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
