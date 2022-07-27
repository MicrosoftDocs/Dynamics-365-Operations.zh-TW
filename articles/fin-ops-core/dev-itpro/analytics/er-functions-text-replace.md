---
title: REPLACE ER 函數
description: 本主題提供有關如何使用 REPLACE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: e7bee3ed0531df64e813423f7280a62fd2afe77432ae05c1fb21264578c9e4ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460542"
---
# <a name="replace-er-function"></a>REPLACE ER 函數

[!include [banner](../includes/banner.md)]

`REPLACE` 函數將指定文字字串的全部或部分替換為另一個字串後，將其作為 *字串* 值回傳。

## <a name="syntax"></a>語法

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>引數

`text`：*字串*

*字串* 類型的資料來源的有效路徑。

`pattern`：*字串*

如果 `regular expression flag` 引數為 **FALSE**，則此引數包含必須替換的文字。

如果 `regular expression flag` 引數為 **TRUE**，則此引數包含一個定義搜尋模式和替換文字的規則運算式。

`replacement`：*字串*

如果 `regular expression flag` 引數為 **FALSE**，則此引數包含要用作替換的文字。

如果 `regular expression flag` 引數為 **TRUE**，則不使用此引數。

`regular expression flag`：*布林值*

指示是否使用規則運算式進行替換的 *布爾值*。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

如果 `regular expression flag` 引數為 **TRUE**，則此函數在透過應用由 `pattern` 引數指定的規則運算式更改後回傳指定的字串。 規則運算式用於尋找必須替換的字元。

如果 `regular expression flag` 引數為 **FALSE**，則在 `pattern` 引數中定義的字元集被 `replacement` 參數的字元替換後，此函數回傳指定的字串。 

## <a name="example-1"></a>範例 1

`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)`套用刪除所有非數字元號的規則運算式，並回傳 **「19234564971」**。 

## <a name="example-2"></a>範例 2

`REPLACE ("abcdef", "cd", "GH", false)` 用字串 **"GH"** 替換模式 **"cd"** 並回傳 **"abGHef"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]