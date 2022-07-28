---
title: FIRSTORNULL ER 函數
description: 本主題說明如何使用 FIRSTORNULL 電子報表 (ER) 函數
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 18c8f79d7d6306d9973c5a3f129b9cde38d05d58502a2c83ac89a2bd10aaaeab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460352"
---
# <a name="firstornull-er-function"></a>FIRSTORNULL ER 函數

[!include [banner](../includes/banner.md)]

`FIRSTORNULL` 函數將指定清單的第一個記錄回傳為 *容器 (記錄)* 值，前提是該記錄不為空白。 如果記錄為空，則此函數回傳 Null *容器 (記錄)* 值。

## <a name="syntax"></a>語法

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*容器 (記錄)*

產生的記錄值。

## <a name="example"></a>範例

運算式 `FIRSTORNULL(SPLIT("",1)).Value` 會回傳一個空白字串 (**「」**)。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]