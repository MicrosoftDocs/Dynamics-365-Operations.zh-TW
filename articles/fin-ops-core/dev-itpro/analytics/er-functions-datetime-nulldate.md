---
title: NULLDATE ER 函數
description: 本主題提供有關如何使用 NULLDATE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 657766a838fbcd32c6b8bb0ba1f728e9dbbac92e103c219f3eeeab7ecd8c747d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460387"
---
# <a name="nulldate-er-function"></a>NULLDATE ER 函數

[!include [banner](../includes/banner.md)]

`NULLDATE` 函數回傳代表 **Null** 日期 (1900 年 1 月 1 日) 的 *日期* 值。

## <a name="syntax"></a>語法

```vb
NULLDATE () as 
```

## <a name="return-values"></a>回傳值

*日期*

產生的日期值。

## <a name="example-1"></a>範例 1

`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` 基於指定的自訂格式回傳 **Null** 日期，1900 年 1 月 1 日，為 **「1900-01-01」**。

## <a name="example-2"></a>範例 2

當 **DocumentDate** 欄位的值等於 **Null** 日期時，運算式 `IF( Invoice.DocumentDate = NULLDATE(), true, false)` 回傳 **True**。 在此範例中，**Invoice** 是 **Finance/Table 記錄** 類型的電子報表 (ER) 資料來源，它參考 CustInvoiceJour 表。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]