---
title: GETENUMVALUEBYNAME ER 函數
description: 本主題提供有關如何使用 GETENUMVALUEBYNAME 電子報表 (ER) 函數的資訊。
author: NickSelin
ms.date: 09/23/2020
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
ms.openlocfilehash: 03759852e5ceb13b79b0df4592bdcef76eb0a82865725c00df40b9cc5f786240
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460489"
---
# <a name="getenumvaluebyname-er-function"></a>GETENUMVALUEBYNAME ER 函數

[!include [banner](../includes/banner.md)]

`GETENUMVALUEBYNAME` 函數使用指定為 *字串* 值的列舉名稱在指定的列舉資料來源中搜尋特定的 *Enum* 值。 如果找到 *Enum* 值，則函數將其回傳。 否則，該函數回傳 **Null** 列舉值。

## <a name="syntax"></a>語法

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>引數

`enumeration data source path`：*列舉*

以下列舉類型之一的資料來源的有效路徑：

- 電子報告 (ER) 模型列舉
- ER 格式列舉
- Microsoft Dynamics 365 Finance 列舉

`enumeration value text`：*字串*

一個字串值，表示單個列舉值的名稱。

## <a name="return-values"></a>回傳值

可空白的 *Enum*

產生的列舉值。

## <a name="usage-notes"></a>使用方式說明

如果使用指定為 *字串* 值的列舉值的名稱未找到 *Enum* 值，則不會引發異常。

## <a name="example-1"></a>範例 1

在下圖中，在資料模型中引入了 **ReportDirection** 列舉。 請注意，為列舉值定義了標籤。

![資料模型列舉的可用值。](./media/ER-data-model-enumeration-values.PNG)

以下圖表顯示了以下細節：

- **$Direction** 資料來源在 ER 報告中設定。 此資料來源是基於 **ReportDirection** 模型列舉設定的。
- `$IsArrivals` 運算式旨在使用基於模型列舉的 **$Direction** 資料來源作為此函數的參數。
- 此比較運算式的值為 **TRUE**。

![資料模型列舉範例。](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>範例 2

`GETENUMVALUEBYNAME` 和 [`LISTOFFIELDS`](er-functions-list-listoffields.md) 函數允許您獲取支援的列舉的值和標籤作為文字值。 (支援的列舉是應用程式列舉、資料模型列舉和格式列舉。)

在下圖中，模型對應中引入了 **TransType** 資料來源。 此資料來源指的是 **LedgerTransType** 應用程式列舉。

![參考應用程式列舉的模型對應的資料來源。](./media/er-functions-text-getenumvaluebyname-example2-1.png)

下圖顯示了在模型對應中設定的 **TransTypeList** 資料來源。 此資料來源是基於 **TransType** 應用程式列舉設定的。 `LISTOFFIELDS` 函數用於將所有列舉值作為包含欄位的記錄清單回傳。 這樣，每個列舉值的細節都公開出來了。

> [!NOTE]
> 使用 `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` 運算式為 **TransTypeList** 資料來源設定 **EnumValue** 欄位。 此欄位為此清單中的每條記錄回傳一個列舉值。

![將選定列舉的所有列舉值作為記錄清單回傳的模型對應的資料來源。](./media/er-functions-text-getenumvaluebyname-example2-2.png)

下圖顯示了在模型對應中設定的 **VendTrans** 資料來源。 此資料來源從 **VendTrans** 應用程式表回傳廠商交易記錄。 每個交易的分類帳類型由 **TransType** 欄位的值定義。

> [!NOTE]
> 使用 `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` 運算式為 **VendTrans** 資料來源設定 **TransTypeTitle** 欄位。 如果該列舉值可用，則該欄位以文字形式回傳現行交易的列舉值的標籤。 否則，它回傳一個空白字串值。
>
> **TransTypeTitle** 欄位繫結到資料模型的 **LedgerType** 欄位，該資料模型使此資訊能夠在使用資料模型作為資料來源的每個 ER 格式中使用。

![回傳廠商交易的模型對應的資料來源。](./media/er-functions-text-getenumvaluebyname-example2-3.png)

下圖顯示了如何使用[資料來源偵錯器](er-debug-data-sources.md)來測試設定的模型對應。

![使用資料來源偵錯器測試設定的模型對應。](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

資料模型的 **LedgerType** 欄位按預期公開交易類型的標籤。

如果您打算將這種方法用於大量交易資料，則必須考慮執行效能。 如需相關資訊，請參閱[跟踪 ER 格式的執行以解決效能問題](trace-execution-er-troubleshoot-perf.md)。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)

[追蹤 ER 格式的執行以解決效能問題](trace-execution-er-troubleshoot-perf.md)

[LISTOFFIELDS ER 函數](er-functions-list-listoffields.md)

[FIRSTORNULL ER 函數](er-functions-list-firstornull.md)

[WHERE ER 函數](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]