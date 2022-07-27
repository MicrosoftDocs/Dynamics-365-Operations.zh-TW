---
title: NULLDATETIME ER 函數
description: 本主題提供有關如何使用 NULLDATETIME 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 79bdcaa90ce4002d92a4a0d959c9b94d8c47d7c7c855584d49818fb713bda4b7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460385"
---
# <a name="nulldatetime-er-function"></a>NULLDATETIME ER 函數

[!include [banner](../includes/banner.md)]

`NULLDATETIME` 函數回傳一個 *日期時間* 值，該值表示國際標準時間 (格林威治平均時間 \[GMT\]) 的 **Null** 日期/時間值 (1900 年 1 月 1 日)。

## <a name="syntax"></a>語法

```vb
NULLDATETIME ()
```

## <a name="return-values"></a>回傳值

*DateTime*

產生的日期/時間值。

## <a name="example"></a>範例

`DATETIMEFORMAT( NULLDATETIME(), "O")` 回傳字串值 **1900-01-01T00:00:00.0000000+00:00**，當它在一個由應用程式使用者啟動的進程中被調用時，該使用者在 **語言和國家/地區偏好** 區段有一個時區值 **(GMT) 世界協調時間**。

## <a name="additional-resources"></a>其他資源

[日期和時間函數](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]