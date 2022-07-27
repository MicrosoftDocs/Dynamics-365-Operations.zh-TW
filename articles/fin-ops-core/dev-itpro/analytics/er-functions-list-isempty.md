---
title: ISEMPTY ER 函數
description: 本主題提供有關如何使用 ISEMPTY 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 41d1f773e3fc2f076dbe3d826d14a364548d6656c95c03e54eb36345c004fecd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460349"
---
# <a name="isempty-er-function"></a>ISEMPTY ER 函數

[!include [banner](../includes/banner.md)]

如果指定的清單不包含任何記錄，則 `ISEMPTY` 函數將回傳 *布林值* **TRUE**。 否則，它會回傳 **FALSE** 的 *布林值*。

## <a name="syntax"></a>語法

```vb
ISEMPTY (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*布林值*

產生的 *布林值* 值。

## <a name="example-1"></a>範例 1

如果輸入 *匯出欄位* 類型的資料來源 **DS**，它包含運算式 `SPLIT ("A|B|C", "|")`，運算式 `ISEMPTY(DS)` 會回傳 **FALSE**。

## <a name="example-2"></a>範例 2

運算式 `ISEMPTY (SPLIT ("",1))` 會回傳 **TRUE**。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]