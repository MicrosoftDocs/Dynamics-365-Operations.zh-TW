---
title: GETLABELTEXT ER 函數
description: 本主題提供有關如何使用 GETLABELTEXT 電子報表 (ER) 函數的信息。
author: NickSelin
ms.date: 01/04/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 911567a94b80c2b762a37e83d37fc500132edb18
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460593"
---
# <a name="getlabeltext-er-function"></a>GETLABELTEXT ER 函數

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

`GETLABELTEXT` 函數搜尋特定標籤以回傳一個 *[字串](er-formula-supported-data-types-primitive.md#string)* 值，該值表示指定標籤在指定語言中的翻譯。

## <a name="syntax"></a>語法

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>引數

### <a name="label-id"></a>標籤識別碼

`label id`：*字串* 或 *標籤 ID*

以下標籤類型之一的有效 ID：

- [電子報表 (ER)](general-electronic-reporting.md)標籤
- Microsoft Dynamics 365 Finance 標籤

#### <a name="usage-notes"></a>使用方式說明

透過使用以下支援的模式之一，只能將此引數定義為常數：

- 對於 ER 標籤：

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- 對於 Finance 標籤：

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> 在設計階段，如果使用提供的標籤 ID 找不到任何標籤，則會在 **[公式設計工具](er-advanced-formula-editor.md)** 頁面上顯示一條驗證錯誤訊息。

### <a name="language"></a>語言

`language`：*字串*

表示語言代碼的字串。

#### <a name="usage-notes"></a>使用方式說明

此引數可以定義為文字常數或回傳 *字串* 值的資料來源欄位的路徑。

> [!NOTE]
> 在設計階段，如果在定義為文字常數時使用提供的 `language` 引數找不到語言代碼，則會顯示驗證錯誤訊息。
>
> 在執行階段，如果使用提供的 `language` 引數沒有找到語言代碼，則回傳指定標籤的 `EN-US` 系統語言的翻譯。

## <a name="return-values"></a>回傳值

*字串*

產生的文字值。

## <a name="example-1-system-label"></a><a name=example-1></a>範例 1：系統標籤

運算式 `GETLABELTEXT (@"SYS70894", "en-us")` 和 `GETLABELTEXT ("SYS70894", "en-us")` 會回傳 `@SYS70894` 應用程式標籤的英文翻譯「Nothing to print」。

## <a name="example-2-er-label"></a><a name=example-2></a>範例 2：ER 標籤

您開始編輯從 **ISO20022 貸記轉帳 (DE)** 設定 [衍生](er-quick-start2-customize-report.md#DeriveProvidedFormat)的 ER [設定](general-electronic-reporting.md#Configuration)，輸入 *[匯出欄位](er-calculated-field-ds-performance.md)* 類型的新資料來源，並為此資料來源設定運算式 `GETLABELTEXT(@"GER_LABEL:VendorName", "de")`。 在這種情況下，在執行階段，資料來源會回傳最初在基本 **ISO20022 貸記轉帳 (DE)** ER 設定中設定的 `@GER_LABEL:VendorName` ER 標籤的德語翻譯「Kreditorenname」。

## <a name="additional-resources"></a>其他資源

[文字函數](er-functions-category-text.md)

[在電子報表中設計多語言報表](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
