---
title: GUIDVALUE ER 函數
description: 本主題提供有關如何使用 GUIDVALUE 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 76b918354be9b5b695cfec9d0fe7aca6c5c9e08e01b6e3d0ddfa28af877942e3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460328"
---
# <a name="guidvalue-er-function"></a>GUIDVALUE ER 函數

[!include [banner](../includes/banner.md)]

`GUIDVALUE` 函數將 *字串* 類型的指定輸入轉換為 *GUID* 類型的資料項目。

## <a name="syntax"></a>語法

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>引數

`input`：*字串*

*字串* 類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*GUID*

產生的全域唯一識別碼 (GUID) 值。

## <a name="usage-notes"></a>使用方式說明

若要進行相反方向的轉換 (即將 *GUID* 資料類型的指定輸入轉換為 *字串* 資料類型的資料項目)，可以使用 [TEXT](er-functions-text-text.md) 函數。

## <a name="example"></a>範例

您在模型對應中定義以下資料來源：

- 包含運算式 `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")` 的 *導出欄位* 類型的 **myID** 資料來源
- 參考 UserInfo 表的 *資料表記錄* 類型的 **Users** 資料來源

然後，您可以使用 `FILTER (Users, Users.objectId = myID)` 之類的運算式按 *GUID* 資料類型的 **objectId** 欄位過濾 UserInfo 表。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]