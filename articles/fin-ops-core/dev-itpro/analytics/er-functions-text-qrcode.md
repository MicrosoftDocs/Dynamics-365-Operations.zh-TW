---
title: QRCODE ER 函數
description: 本主題提供有關如何使用 QRCODE 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: e9d5bd1fee8c310053b01ababb0eaafc6d5470a62786de1f502f175e634bda64
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460303"
---
# <a name="qrcode-er-function"></a>QRCODE ER 函數

[!include [banner](../includes/banner.md)]

`QRCODE` 函數回傳一個 *容器* 值，該值以二進位格式顯示指定字串的快速回應碼 (QR 碼) 影像。

## <a name="syntax"></a>語法

```vb
QRCODE (text)
```

## <a name="arguments"></a>引數

`text`：*字串*

表示原始文字的 *字串* 值。

## <a name="return-values"></a>回傳值

*容器*

產生的二進位流。

## <a name="example"></a>範例

您可以使用預定義的範本設定電子報表 (ER) 格式以產生 Microsoft Office 格式 (Excel 活頁簿或 Word 文件) 的輸出文件。 此範本可能包含 **圖片** 物件 (Excel 活頁簿) 或 **圖片內容控制項目** (Word 文件) 作為 QR 碼影像的預留位置。 您需要將用於填入此預留位置的 **儲存格** 元素新增到設定的 ER 格式中。 若要指定將哪些信息儲存在 QR 碼中，您需要為此 **儲存格** 元素定義一個繫結。 例如，您可以將此類繫結設定為包含以下運算式：

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

當您運行設定的 ER 格式時，**model.ListOfShelfLabels** 資料來源的 **LabelText** 欄位的文字值將用於產生二維碼影像。 此影像將替換文件範本中的二維碼影像預留位置，用於產生輸出文件。 掃描產生文件的此影像時，它會回傳從 **model.ListOfShelfLabels** 資料來源的 **LabelText** 欄位中獲取的文字。 如需相關資訊，[在使用 ER 產生的檔案中嵌入圖像和形狀](electronic-reporting-embed-images-shapes.md)

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]