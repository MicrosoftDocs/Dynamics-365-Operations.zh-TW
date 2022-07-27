---
title: NULLCONTAINER ER 函數
description: 本主題提供有關如何使用 NULLCONTAINER 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 13159d9d7c8d1871886beb3cb1938ca8b0097e0efb6f10a9d1b229c49b9ff947
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460342"
---
# <a name="nullcontainer-er-function"></a>NULLCONTAINER ER 函數

[!include [banner](../includes/banner.md)]

`NULLCONTAINER` 函數回傳一個與指定記錄清單或記錄具有相同結構的 Null *容器 (記錄)* 值。

## <a name="syntax"></a>語法

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單* 或 *容器 (記錄)*

*記錄清單* 或 *容器 (記錄)* 類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*容器 (記錄)*

產生的記錄值。

## <a name="usage-notes"></a>使用方式說明

> [!NOTE] 
> 此函數已過時。 改用 `EMPTYRECORD` 函數。 如需相關資訊，請參閱[EMPTYRECORD](er-functions-record-emptyrecord.md)。

## <a name="example"></a>範例

`NULLCONTAINER (SPLIT ("abc", 1))` 回傳一個新的空白記錄，該記錄與 `SPLIT` 函數回傳的清單具有相同的結構。 如需相關資訊，請參閱[SPLIT](er-functions-list-split.md)。

## <a name="additional-resources"></a>其他資源

[記錄函數](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]