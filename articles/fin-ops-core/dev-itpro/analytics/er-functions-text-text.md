---
title: TEXT ER 函數
description: 本主題提供有關如何使用 TEXT 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 38550b8b5181b49bcb8504129932f185ea95e038e38d4581bc3e0fa076f4fb50
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460153"
---
# <a name="text-er-function"></a>TEXT ER 函數

[!include [banner](../includes/banner.md)]

`TEXT` 函數在將指定的數字轉換為根據現行應用程式實體的伺服器區域設定格式化的文字字串後，將其作為 *字串* 值回傳。

## <a name="syntax"></a>語法

```vb
TEXT (number)
```

## <a name="arguments"></a>引數

`number`：*整數* 或 *實數*

必須轉換為文字字串的數字。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="usage-notes"></a>使用方式說明

對於 *實數* 類型的值，字串轉換限制為兩位小數。

## <a name="example"></a>範例

如果 Microsoft Dynamics 365 Finance 實體的伺服器區域設定定義為 **EN-US**，則 `TEXT (NOW ())` 將現行財務工作階段日期 2015 年 12 月 17 日回傳為文字字串 **「12/17/2015 07:59:23 AM」**。 `TEXT (1/3)` 會回傳 **"0.33"**。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]