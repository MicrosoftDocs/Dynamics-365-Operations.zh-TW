---
title: JSONVALUE ER 函數
description: 本主題提供有關如何使用 JSONVALUE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 10/25/2021
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
ms.openlocfilehash: ff33098e5be4dd9748d01d45b596360617305724
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2021
ms.locfileid: "8460488"
---
# <a name="jsonvalue-er-function"></a>JSONVALUE ER 函數

[!include [banner](../includes/banner.md)]

`JSONVALUE` 函數解析在指定路徑存取的 JavaScript Object Notation (JSON) 格式的資料，並擷取具有指定 ID 的標量值。 然後它將提取的標量值作為 *字串* 值回傳。

## <a name="syntax"></a>語法

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>引數

`input`：*字串*

包含 JSON 資料的 *字串* 類型資料來源的有效路徑。

`path`：*字串*

JSON 資料的標量值的識別碼。 使用正斜杠 (/) 分隔相關 JSON 節點的名稱。 使用括號 (\[\]) 表示法來指定 JSON 陣列中特定值的索引。 請注意，此索引使用從零開始的編號。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example-1"></a>範例 1

**JsonField** 資料來源包含以下 JSON 格式的資料：**{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**。 在這種情況下，運算式 `JSONVALUE (JsonField, "BuildNumber")` 回傳 *字串* 資料類型的以下值：**「7.3.1234.1」**。

## <a name="example-2"></a>範例 2

*導出欄位* 類型的 **JsonField** 資料來源包含以下運算式：`"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`

此運算式設定為回傳一個 [*字串*](er-formula-supported-data-types-primitive.md#string)值，該值表示 JSON 格式的以下資料。

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

在這種情況下，運算式 `JSONVALUE(json, "workers/[1]/emails/[0]")` 回傳 *字串* 資料類型的以下值：`JohnS@Contoso.com`。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
