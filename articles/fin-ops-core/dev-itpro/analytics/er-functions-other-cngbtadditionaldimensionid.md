---
title: CN_GBT_ADDITIONALDIMENSIONID ER 函數
description: 本主題提供有關如何使用 CN_GBT_ADDITIONALDIMENSIONID 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 9217b70076a369c18a94f820f19ca371c2d8aca61ab72b6be762592f39fa1160
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460468"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a>CN_GBT_ADDITIONALDIMENSIONID ER 函數

[!include [banner](../includes/banner.md)]

`CN_GBT_ADDITIONALDIMENSIONID` 函數回傳一個 *字串* 值，該值表示取自指定字串的單個財務維度識別碼。 指定的字串將所有維度顯示為以逗號分隔的識別碼清單。

## <a name="syntax"></a>語法

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>引數

`text`：*字串*

*字串* 值，將所有維度顯示為以逗號分隔的識別碼清單。

`number`：整數

*整數* 值，用於定義指定字串中請求維度的序列碼。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example"></a>範例

`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` 會回傳 **"CC"**。

## <a name="additional-resources"></a>其他資源

[其他 (商業領域特定) 函數](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]