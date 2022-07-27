---
title: FIRST ER 函數
description: 本主題提供有關如何使用 FIRST 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: f108676c2ff8801fddc0a72be3f75d212582efe6b5d96f7515354739eb446532
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460355"
---
# <a name="first-er-function"></a>FIRST ER 函數

[!include [banner](../includes/banner.md)]

`FIRST` 函數將指定清單的第一個記錄回傳為 *容器 (記錄)* 值，前提是該清單不為空白。 如果該清單為空白，此函數將引發異常。

## <a name="syntax"></a>語法

```vb
FIRST (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*容器 (記錄)*

產生的記錄值。

## <a name="example-1"></a>範例 1

運算式 `FIRST(SPLIT("ABC",1)).Value` 會回傳文字值 **「A」**。

## <a name="example-2"></a>範例 2

運算式 `FIRST(SPLIT("",1)).Value` 在執行階段引發異常。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]