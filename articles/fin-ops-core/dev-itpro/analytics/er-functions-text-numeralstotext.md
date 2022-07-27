---
title: NUMERALSTOTEXT ER 函數
description: 本主題提供有關如何使用 NUMERALSTOTEXT 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 76431642a6d6961c5c9a2bf15534ad58f83d312dfb3723e75c94fa844717930b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460305"
---
# <a name="numeralstotext-er-function"></a>NUMERALSTOTEXT ER 函數

[!include [banner](../includes/banner.md)]

`NUMERALSTOTEXT` 函數將指定的數字以指定語言拼寫 (即轉換為文字字串) 後作為 *字串值* 回傳。

## <a name="syntax"></a>語法

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>引數

`number`：*整數* 或 *實數*

一個數值，指定必須拼出的數字。

`language`：*字串*

表示語言代碼的 *字串* 值。

`currency`：*字串*

表示貨幣代碼的 *字串* 值。

`print currency name flag`：*布林值*

*布林值* 代表是否必須將貨幣名稱新增到拼寫文字的值。

`decimal points`：*整數*

*整數* 代表拼寫文字應具有的小數位數的值。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

語言代碼是可選的。 如果將其定義為空白字串，則使用執行內容的語言代碼。 預設語言代碼為 **EN-US**。 執行內容的語言代碼在正在執行的電子報表 (ER) 格式的 **資料夾** 或 **檔案** 元素中定義。

貨幣代碼是可選的。 如果將其定義為空白字串，則使用執行內容的公司貨幣。

> [!NOTE] 
> `print currency name flag` 和 `decimal points` 僅針對以下語言代碼分析引數：**CS**、**ET**、**HU**、**LT**、**LV**、**PL** 和 **RU**。 此外，僅針對國家或地區內容支援貨幣名稱變格的公司分析 `print currency name flag` 引數。

## <a name="example-1"></a>範例 1

`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` 會回傳 **一千二百三十四和 56**。

## <a name="example-2"></a>範例 2

`NUMERALSTOTEXT (120, "PL", "", false, 0)` 會回傳 **"Sto dwadzieścia"**。 

## <a name="example-3"></a>範例 3

`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` 會回傳 **"Сто двадцать евро 21 евроцент"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]