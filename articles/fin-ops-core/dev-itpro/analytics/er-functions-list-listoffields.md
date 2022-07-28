---
title: LISTOFFIELDS ER 函數
description: 本主題提供有關如何使用 LISTOFFIELDS 電子報表 (ER) 函數的資訊。
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
ms.openlocfilehash: 1d15649aed4343f2ed9192834047a17e273e29f190aa83c386bebe7857b47908
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460347"
---
# <a name="listoffields-er-function"></a>LISTOFFIELDS ER 函數

[!include [banner](../includes/banner.md)]

`LISTOFFIELDS` 函數回傳基於 *列舉* 或 *容器 (記錄)* 類型的指定參數的結構建立的 *記錄清單* 值。

## <a name="syntax-1"></a>語法 1

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>語法 2

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>引數

`path`：資料來源參考

以下資料類型之一的資料來源的有效參考路徑：

- 模型列舉
- 格式列舉
- 應用程式列舉
- 容器 (記錄)

`language`：*字串*

表示語言代碼的文字。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

建立的清單由具有以下欄位的記錄組成：

- **名稱**(*字串* 資料類型)
- **標籤**(*字串* 資料類型)
- **描述**(*字串* 資料類型)
- **IsTranslated**(*布林值* 資料類型)

如果 `path` 引數是指 *容器 (記錄)* 類型的資料來源類型的資料來源，則對於參考的容器記錄的每個欄位，則將新記錄新增到建立的清單中。 對於建立的每個記錄，**名稱** 欄位回傳建立現行記錄的參考容器記錄的欄位名稱。

如果 `path` 引數是指 *列舉* 類型之一的資料來源，則對於參考列舉的每個列舉值，則將新記錄新增到建立的清單中。 對於建立的每個記錄，**名稱** 欄位回傳現行記錄建立的參考列舉的值，**描述** 欄位回傳該列舉的描述，**標籤** 欄位回傳該列舉的標籤。

在執行階段，使用語法 1 時，**標籤** 和 **描述** 欄位必須回傳基於正在執行的電子報告 (ER) 格式的語言設定的值：

- 如果可用的語言的標籤和描述可用，則 **標籤** 和 **描述** 欄位回傳基於該語言的值，並且 **iStryslated** 欄位回傳 **True**。
- 如果沒有請求的語言的標籤和描述，則 **標籤** 和 **描述** 欄位回傳基於預設的 **EN-US** 語言的值，並且 **IsTranslated** 欄位回傳 **False**。

在執行階段，當使用語法 2 時，**標籤** 和 **描述** 欄位必須回傳基於定義為稱為函數的第二個參數的語言的值：

- 如果可用的語言的標籤和描述可用，則 **標籤** 和 **描述** 欄位回傳基於該語言的值，並且 **iStryslated** 欄位回傳 **True**。
- 如果沒有請求的語言的標籤和描述，則 **標籤** 和 **描述** 欄位回傳基於 **EN-US** 語言的值，並且 **IsTranslated** 欄位回傳 **False**。

## <a name="example-1"></a>範例 1

在下面的插圖中，在 ER 資料模型中引入了列舉。

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

以下圖表顯示了以下細節：

- 模型列舉作為資料來源插入到報表中。
- ER 運算式使用模型列舉作為 `LISTOFFIELDS` 函數的參數。
- 透過使用建立的 ER 運算式將 *記錄清單* 類型的資料來源插入報告中。

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

下面的範例顯示了使用 `LISTOFFIELDS` 函數建立的 *記錄清單* 類型的資料來源的 ER 格式元素。

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

下圖顯示了運行設計後格式時的結果。

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> 基於父 **FILE** 和 **FOLDER** 格式元素的語言設定，在 ER 格式的輸出中輸入了標籤和描述的翻譯文字。

## <a name="example-2"></a>範例 2

您使用 *導出欄位* 資料來源類型來設定 **enumType\_de** 和 **enumType\_deCH** 資料來源，用於 **enumType** 資料模型列舉：

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

在這種情況下，您可以使用以下運算式來獲取瑞士德語中列舉值的標籤 (如果該翻譯可用)。 如果瑞士德語翻譯不可用，則標籤為德語。

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]