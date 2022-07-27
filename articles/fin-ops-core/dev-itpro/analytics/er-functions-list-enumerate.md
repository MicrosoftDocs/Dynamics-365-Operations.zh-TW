---
title: ENUMERATE ER 函數
description: 本主題提供有關如何使用 ENUMERATE 電子報表 (ER) 函數的信息。
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
ms.openlocfilehash: 97677a52e04f03dd39f507b8f63c8daf32140c2321b0d64a8ba5685d2841be3c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460354"
---
# <a name="enumerate-er-function"></a>ENUMERATE ER 函數

[!include [banner](../includes/banner.md)]

`ENUMERATE` 函數回傳一個新的 *記錄清單* 值，該值包含指定清單的列舉記錄。

## <a name="syntax"></a>語法

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>引數

`list`：*記錄清單*

*記錄清單* 資料類型的資料來源的有效路徑。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

回傳的列舉記錄清單公開了以下附加元素：

- 欄位記錄 (**值** 組件)
- 現行記錄索引 (**數字** 組件)

## <a name="example"></a>範例

在下圖中，**列舉** 資料來源被建立為廠商記錄的列舉清單，該清單來自參考 VendTable 表的 **廠商** 資料來源。

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

下圖顯示了電子報表 (ER) 格式。 在這種格式中，建立資料繫結以產生 XML 格式的輸出。 此輸出將各個廠商呈現為列舉節點。

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

下圖顯示了運行設計後格式時的結果。

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]