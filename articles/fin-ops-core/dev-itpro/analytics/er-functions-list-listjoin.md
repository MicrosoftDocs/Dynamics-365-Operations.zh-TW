---
title: LISTJOIN ER 函數
description: 本主題提供有關如何使用 LISTJOIN 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9346afc88adb89c08098f39a5fd1c2cb82f664af2244b8cafbbe8a4d2f516c6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460346"
---
# <a name="listjoin-er-function"></a>LISTJOIN ER 函數

[!include [banner](../includes/banner.md)]

`LISTJOIN` 函數回傳一個 *記錄清單* 值，表示從指定的引數建立的新加入記錄清單。

## <a name="syntax"></a>語法

```vb
LISTJOIN (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>引數

`list 1`：*記錄清單*

對 *記錄清單* 資料類型的資料來源的參考。 此引數是強制性的。

`list N`：*記錄清單*

對 *記錄清單* 資料類型的資料來源的參考。 這些附加引數是可選的。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

建立的清單結構僅包含引數中參考的每個記錄清單的結構中存在的欄位。

## <a name="example"></a>範例

您輸入 `Container` 類型的資料來源 **記錄 1**。 此資料來源包含以下 `Calculated field` 類型的巢狀欄位：

- **Code**：此欄位包含一個會回傳 `String` 類型值的運算式。
- **Amount**：此欄位包含一個會回傳 `Real` 類型值的運算式。

您接著輸入 `Container` 類型的資料來源 **記錄 2**。 此資料來源包含以下 `Calculated field` 類型的巢狀欄位：

- **Amount**：此欄位包含一個會回傳 `Real` 類型值的運算式。
- **IsValid**：此欄位包含一個會回傳 `Boolean` 類型值的運算式。

![ER 模型對應設計工具頁面。](./media/er-functions-list-listjoin-image1.gif)

在這種情況下，運算式 `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` 會回傳一個包含兩條記錄的新清單。

![具有兩條記錄的 ER 模型對應設計工具頁面。](./media/er-functions-list-listjoin-image2.gif)

該清單的結構由一個 `Real` 類型的單個 **金額** 欄位組成，因為該欄位是被調用函數的每個引數中唯一出現的欄位。

![ER 模型對應設計工具頁面金額欄位。](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)

[偵錯已執行 ER 格式的資料來源以分析資料流程和轉換](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
