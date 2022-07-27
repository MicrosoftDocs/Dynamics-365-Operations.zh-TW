---
title: 電子報表公式語言
description: 本主題提供有關如何在電子報表 (ER) 中使用公式語言的資訊。
author: NickSelin
ms.date: 05/04/2020
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ef0b9e411fabca1427b985eb51640bfd2a0d59318a456cb5b1ecdea1445fab5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460175"
---
# <a name="electronic-reporting-formula-language"></a>電子報表公式語言

[!include [banner](../includes/banner.md)]

電子報表 (ER) 提供了強大的資料轉換體驗。 [ER 公式設計工具](general-electronic-reporting-formula-designer.md)中用​​於表達所需資料操作的語言類似於 Microsoft Excel 中的公式語言。

## <a name="basic-syntax"></a>基本句法

ER 運算式可以包含以下任何或所有元素：

- [常數](#Constants)
- [運算子](#Operators)
- [參考](#References)
- [路徑](#Paths)
- [函數](#Functions)

## <a name="constants"></a><a name="Constants"></a>常數

設計運算式時，可以使用文字和數字常數 (即未計算的值)。 例如，運算式 `VALUE ("100") + 20` 使用數字常數 **20** 和字串常數 **“100”**，並回傳數值 **120**。

ER 公式設計工具支援逸出序列。 因此，您可以指定應以不同方式處理的運算式字串。 例如，運算式 `"Leo Tolstoy ""War and Peace"" Volume 1"` 回傳文字字串 **Leo Tolstoy "War and Peace" Volume 1**。

## <a name="operators"></a><a name="Operators"></a>運算子

下表顯示了可用於執行基本數學運算 (例如加法、減法、乘法和除法) 的算術運算子。

| 運算子 | 意義               | 範例     |
|----------|-----------------------|-------------|
| +        | 加法              | `1+2`       |
| -        | 減法，否定 | `5-2`，`-1` |
| \*       | 乘法        | `7\*8`      |
| /        | 部門              | `9/3`       |

下表顯示了支援的比較運算子。 您可以使用這些運算子來比較兩個值。

| 運算子 | 意義                  | 範例      |
|----------|--------------------------|--------------|
| =        | Equal                    | `X=Y`        |
| &gt;     | Greater than             | `X>Y`        |
| &lt;     | Less than                | `X<Y`        |
| &gt;=    | 大於或等於 | `X>=Y`       |
| &lt;=    | 小於或等於    | `X<=Y`       |
| &lt;&gt; | 不等於             | `X<>Y`       |

此外，您可以使用 & 符號作為文字連接運算子。 透過這種方式，您可以將一個或多個文字字串連接或連接成一段文字。

| 運算子 | 意義     | 範例                                               |
|----------|-------------|-------------------------------------------------------|
| &        | 連接 | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>運算子優先順序

計算複合運算式各部分的順序很重要。 例如，運算式 `1 + 4 / 2` 的結果取決於是先進行加法還是除法運算。 您可以使用括號明確定義運算式的計算方式。 例如，若要指示應先進行加法運算，可以將前面的運算式更改為 `(1 + 4) / 2`。 如果您沒有明確指出運算式中的運算順序，則該順序基於指派給支援的運算子的預設優先順序。 下表顯示了指派給每個運算子的優先順序。 具有較高優先順序 (例如，7) 的運算子在具有較低優先順序 (例如，1) 的運算子之前進行計算。

| 優先順序 | 運算子      | 句法                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | 分組       | ( … )                                                                   |
| 6          | 會員專屬  | … . …                                                                   |
| 5          | 函數調用  | … ( … )                                                                 |
| 4          | 乘法類 | … \* …<br>… / …                                                         |
| 3          | 加法類       | … + …<br>… - …                                                          |
| 2          | 比較     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | 分隔     | … , …                                                                   |

如果一個運算式包含多個具有相同優先順序的連續運算子，則這些運算從左到右進行計算。 例如，運算式 `1 + 6 / 2 \* 3 > 5` 回傳 **True**。 我們建議您使用括號明確指示運算式中所需的運算順序，以便運算式更易於閱讀和維護。

## <a name="references"></a><a name="References"></a>參考

在運算式設計期間可用的現行 ER 組件的所有資料來源都可以用作命名參考。 現行的 ER 組件可以是模型對應或格式。 例如，現行 ER 模型對應包含 **ReportingDate** 資料來源，它回傳 [*DateTime*](er-formula-supported-data-types-primitive.md#datetime) 資料類型的值。 若要在產生文件中正確格式化該值，您可以將運算式中的資料來源參考為 `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")`。

參考資料來源名稱中不代表字母的所有字元必須以單引號 (') 開頭。 如果參考資料來源的名稱包含至少一個不代表字母的符號，則該名稱必須用單引號引起來。 例如，這些非字母符號可以是標點符號或其他書寫符號。 這裡有些範例：

- **今天的日期和時間** 資料來源必須在 ER 運算式稱為 `'Today''s date & time'`。
- **客戶** 資料來源的 **name()** 方法必須在 ER 運算式中稱為 `Customers.'name()'`。

如果應用程式資料來源的方法有參數，則使用以下句法調用這些方法：

- 如果 **系統** 資料來源的 **isLanguageRTL** 方法具有 [*字串*](er-formula-supported-data-types-primitive.md#string)資料類型的 **EN-US** 參數，則此方法必須在 ER 運算式中稱為 `System.isLanguageRTL("EN-US")`。
- 當方法名稱僅包含字母數字符號時，不需要引號。 但是，如果名稱包含方括號，則資料表的方法需要它們。

將 **系統** 資料來源新增到參考 **全域** 應用程式類的 ER 對應時，運算式 `System.isLanguageRTL("EN-US ")` 會回傳 *布林值* **FALSE**。 修改後的運算式 `System.isLanguageRTL("AR")` 會回傳 *布爾值* **TRUE**。

您可以限制將值傳遞給此類方法的參數的方式：

- 只有常數可以傳遞給這種類型的方法。 常數的值是在設計階段定義的。
- 此類型的參數僅支援[原始](er-formula-supported-data-types-primitive.md) (基礎) 資料類型。 原始資料類型包括 *整數*、*實數*、*布林值* 和 *字串*。

## <a name="paths"></a><a name="Paths"></a>路徑

當運算式參考結構化資料來源時，您可以使用路徑定義來選取該資料來源的特定原始元素。 點字元 (.) 用於分隔結構化資料來源的各個元素。 例如，現行 ER 模型對應包含 **InvoiceTransactions** 資料來源，該資料來源回傳記錄清單。 **InvoiceTransactions** 記錄結構包含 **AmountDebit** 和 **AmountCredit** 欄位，這兩個欄位都回傳數值。 因此，您可以設計以下運算式來計算發票金額：`InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`。 此運算式中的 `InvoiceTransactions.AmountDebit` 構造是用於存取 *記錄清單* 類型的 **InvoiceTransactions** 資料來源的 **AmountDebit** 欄位的路徑。

### <a name="relative-path"></a>相對路徑

如果結構化資料來源的路徑以「at」符號 (@) 開頭，則它是相對路徑。 顯示「at」符號，而不是使用的階層樹狀結構的絕對路徑的剩餘部分。 下圖顯示範例。 這裡，絕對路徑 `Ledger.'accountingCurrency()'` 表示在資料模型的 **AccountingCurrency** 欄位中輸入了來自 **分類帳** 資料來源的會計貨幣值。

![ER 模型對應設計工具頁面上的絕對路徑範例。](./media/ER-FormulaLanguage-AbsolutePath.png)

下圖中的範例顯示了如何使用相對路徑。 相對路徑 `@.AccountNum` 表示 **Intrastat** 資料來源的 **AccountNum** 欄位 (在資料模型的階層樹狀結構中出現在 **AccountNum** 欄位的上一級) 用於在資料模型的 **AccountNum** 中輸入客戶或廠商帳號欄位。

![ER 模型對應設計工具頁面上的相對路徑範例。](./media/ER-FormulaLanguage-RelativePath1.png)

絕對路徑的剩餘部分也顯示在[ER 公式編輯器 ](general-electronic-reporting-formula-designer.md)。

![ER 公式設計工具頁面上的絕對路徑的剩餘部分。](./media/ER-FormulaLanguage-RelativePath2.png)

如需相關資訊，請參閱[在 ER 模型和格式的資料繫結中使用相對路徑](relative-path-data-bindings-er-models-format.md)。

## <a name="functions"></a><a name="Functions"></a>函數

ER 內建函數可用於 ER 運算式。 根據調用函數的參數清單，運算式內容的所有資料來源 (即現行的 ER 模型對應或 ER 格式) 都可以用作調用函數的參數。 常數也可以用作調用函數的參數。 例如，現行 ER 模型對應包含 **InvoiceTransactions** 資料來源，該資料來源回傳記錄清單。 **InvoiceTransactions** 記錄結構包含 **AmountDebit** 和 **AmountCredit** 欄位，這兩個欄位都回傳數值。 因此，若要計算發票金額，您可以設計以下使用內建 ER 進位函數的運算式：`ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`。

當您設計 ER 模型對應和 ER 報告時，您可以使用以下類別的 ER 函數：

- [日期和時間函數](er-functions-category-datetime.md)
- [列出函數](er-functions-category-list.md)
- [邏輯函數](er-functions-category-logical.md)
- [數學函數](er-functions-category-mathematical.md)
- [記錄函數](er-functions-category-record.md)
- [文字函數](er-functions-category-text.md)
- [資料收集函數](er-functions-category-data-collection.md)
- [其他 (商業領域特定) 函數](er-functions-category-other.md)
- [類型轉換函數](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>函數清單擴充

ER 允許您擴展在 ER 運算式中使用的函數清單。 需要一些工程工作。 如需相關資訊，請參閱[擴展電子報表 (ER) 函數清單](general-electronic-reporting-formulas-list-extension.md)。

## <a name="compound-expressions"></a>複合運算式

您可以建立使用來自不同類別的函數的複合運算式，前提是資料類型相符。 一起使用函數時，請比對一個函數的輸出資料類型與另一個函數所需的輸入資料類型。 例如，為避免在將欄位繫結到 ER 格式元素時可能出現「list-is-empty」錯誤，請將 [List](er-functions-category-list.md) 類別中的函數與 [Logical](er-functions-category-logical.md) 類別中的函數組合，如下例所示。 此處，該公式使用 [IF](er-functions-logical-if.md) 函數測試 **IntrastatTotals** 清單是否為空，然後從該清單回傳所需彙總的值。 如果 **IntrastatTotals** 清單為空，則公式回傳 **0** (零)。

```vb
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>多種解決方案

通常，您可以透過使用來自不同類別的函數或來自同一類別的不同函數以多種方式獲得相同的資料轉換結果。 例如，也可以使用 [List](er-functions-category-list.md) 類別中的 [COUNT](er-functions-list-count.md) 函數來設定前面的運算式。

```vb
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>其他資源

[電子報表概觀](general-electronic-reporting.md)

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[擴展電子報表 (ER) 函數清單](general-electronic-reporting-formulas-list-extension.md)

[支援的原始資料類型](er-formula-supported-data-types-primitive.md)

[支援的複合資料類型](er-formula-supported-data-types-composite.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
