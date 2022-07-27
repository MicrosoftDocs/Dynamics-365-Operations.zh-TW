---
title: LIST ER 函數
description: 本主題提供有關如何使用 LIST 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: ac8d3971a5502ce567069e0c97247d75a25ae3d38e2cd91e875d4c0d2681d01d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460350"
---
# <a name="list-er-function"></a>LIST ER 函數

[!include [banner](../includes/banner.md)]

`LIST` 函數回傳一個 *記錄清單* 值，該值包含從指定引數建立的新記錄清單。

## <a name="syntax"></a>語法

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>引數

`record 1`：*容器 (記錄)*

對 *記錄* 資料類型的資料來源的參考。 此為必填引數。

`record N`：*容器 (記錄)*

對 *記錄* 資料類型的資料來源的參考。 這些附加引數是可選的。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

建立的清單結構僅包含引數中提過的每個記錄結構中存在的欄位。

## <a name="example"></a>範例

您輸入 *容器* 類型的資料來源 **記錄 1**。 此資料來源包含以下 *導出欄位* 類型的巢狀欄位：

- **Code：** 此欄位包含一個會回傳 *字串* 類型值的運算式。
- **Amount：** 此欄位包含一個會回傳 *實數* 類型值的運算式。

您接著輸入 *容器* 類型的資料來源 **記錄 2**。 此資料來源包含以下 *導出欄位* 類型的巢狀欄位：

- **Amount：** 此欄位包含一個會回傳 *實數* 類型值的運算式。
- **IsValid：** 此欄位包含一個會回傳 *布林值* 類型值的運算式。

在這種情況下，運算式 `LIST('Record 1', 'Record 2')` 會回傳一個包含兩條記錄的新清單。 該清單的結構由一個 *實數* 類型的單個 **金額** 欄位組成，因為該欄位是被調用函數的每個參數中唯一出現的欄位。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]