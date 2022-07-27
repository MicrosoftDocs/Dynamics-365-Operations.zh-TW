---
title: TABLENAME2ID ER 函數
description: 本主題提供有關如何使用 TABLENAME2ID 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: a500eda75fbb5867f74b56753ee45016c60803b06f508340540764a6cd0399cc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460167"
---
# <a name="tablename2id-er-function"></a>TABLENAME2ID ER 函數

[!include [banner](../includes/banner.md)]

`TABLENAME2ID` 函數將指定資料表名稱的資料表識別碼的數字表示形式回傳為 *整數* 值。

## <a name="syntax"></a>語法

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>引數

`text`：*字串*

表示有效資料表名的文字值。

## <a name="return-values"></a>回傳值

*整數*

產生的數值。

## <a name="usage-notes"></a>使用方式說明

即使使用相同的公司名稱，執行此函數在 Microsoft Dynamics 365 Finance 的不同實體中也會產生不同的結果。

## <a name="example"></a>範例

`TABLENAME2ID ("Intrastat")` 會回傳 **1510**。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]