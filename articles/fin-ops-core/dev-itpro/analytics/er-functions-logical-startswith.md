---
title: STARTSWITH ER 函數
description: 本主題提供有關如何使用 STARTSWITH 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: b378f501ccf812cfa0ae09e7cfbfdcf4c8a24ab8747b8ffe6044769df14a3057
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460567"
---
# <a name="startswith-er-function"></a>STARTSWITH ER 函數

[!include [banner](../includes/banner.md)]

`STARTSWITH` 函數確定指定輸入是否以指定文字開頭。 如果指定輸入以指定文字開頭，則回傳 *布林值* **TRUE**。 否則，它會回傳 **FALSE** 的 *布林值*。

## <a name="syntax"></a>語法

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a>引數

`input`：*字串*

*字串* 類型或字串常數的資料來源項目的有效路徑，其值可能以第二個引數開頭。

`start text`：*字串*

*字串* 資料類型或字串常數的資料來源的有效路徑，其值可能位於第一個引數的開頭。

## <a name="return-values"></a>回傳值

*布林值*

產生的 *布林值* 值。

## <a name="usage-notes"></a>使用方式說明

只有在[Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md)中設定相關對應以存取[Microsoft Dataverse](/power-platform/admin/data-integrator)時，該函數才能指定[FILTER](er-functions-list-filter.md)函數的條件運算式。 否則，設計階段會引發異常。 您收到的訊息建議您使用[WHERE](er-functions-list-where.md)函數而不是 `FILTER` 函數。

## <a name="example-1"></a>範例 1

運算式 `STARTSWITH ("abc", "d")` 回傳 **FALSE**，而運算式 `STARTSWITH ("abc", "A")` 回傳 **TRUE**。

## <a name="example-2"></a>範例 2

如果 **模型** 資料來源的 **地址** 欄位的值以字串 **123 Coffee Street** 開頭，則運算式 `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` 回傳 **TRUE**。 否則，它回傳 **FALSE**。

## <a name="additional-resources"></a>其他資源

[邏輯函數](er-functions-category-logical.md)
