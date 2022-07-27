---
title: REVERSE ER 函數
description: 本主題提供有關如何使用 REVERSE 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 96fc3c2f845f84a5435fd0119a7eaa146caa2dc8da9c931ccfe0915af91ed7cb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460343"
---
# <a name="reverse-er-function"></a>REVERSE ER 函數

[!include [banner](../includes/banner.md)]

`REVERSE` 函數將指定的清單回傳為反向排序順序的 *記錄清單* 值。

## <a name="syntax"></a>語法

```vb
REVERSE (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="example-1"></a>範例 1

如果輸入 *導出欄位* 類型的資料來源 **DS**，並且它包含運算式 `SPLIT ("C|B|A", "|")`，則運算式 `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` 回傳文字值 **「C」**。

## <a name="example-2"></a>範例 2

如果 **廠商** 設定為參考 VendTable 表的電子報表 (ER) 資料來源，則運算式 `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` 回傳按名稱降序排列的廠商清單。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]