---
title: ORDERBY ER 函數
description: 本主題提供有關如何使用 ORDERBY 電子報表 (ER) 函數的資訊。
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
ms.openlocfilehash: 963d55bcf98a9109c8b6ceb57edf5b55f15a2b0f
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460344"
---
# <a name="orderby-er-function"></a>ORDERBY ER 函數

[!include [banner](../includes/banner.md)]

`ORDERBY` 函數在根據指定引數排序後將指定清單作為 *記錄清單* 值回傳。 這些引數可以定義為運算式。

## <a name="syntax-1"></a><a name="syntax-1"></a>語法 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>語法 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> Microsoft Dynamics 365 Finance 10.0.25 及更高版本支援此語法。

## <a name="arguments"></a>引數

`location`*[字串](er-formula-supported-data-types-primitive.md#string)*

應該執行排序的位置。 以下選項有效：

- 「查詢」
- 「InMemory」

`list`：*[記錄清單](er-formula-supported-data-types-composite.md#record-list)*

*記錄清單* 資料類型的資料來源的有效路徑。

`expression 1`：*欄位*

被調用函數的 `list` 引數參考的資料來源欄位的有效路徑。 參考的欄位必須是原始資料類型的欄位。 此為必填引數。

`expression N`：*欄位*

被調用函數的 `list` 引數參考的資料來源欄位的有效路徑。 參考的欄位必須是原始資料類型的欄位。 這些附加引數是可選的。

## <a name="return-values"></a>回傳值

*記錄清單*

產生的記錄清單。

## <a name="usage-notes"></a>使用方式說明

### <a name="syntax-1"></a>語法 1

資料排序總是在應用程式伺服器的記憶體中完成。 如需相關詳情，請參閱[範例 1](#example-1)。

### <a name="syntax-2"></a>語法 2

### <a name="sorting-in-memory"></a>在記憶體中排序

當 `location` 引數指定為 **InMemory** 時，資料排序在應用程式伺服器的記憶體中完成。 如需相關詳情，請參閱[範例 2](#example-2)。

### <a name="sorting-in-database"></a>在資料庫中排序

當 `location` 參數指定為 **查詢** 時，資料排序在資料庫級別完成。 在這種情況下，`list` 引數必須指向以下[電子報表 (ER)](general-electronic-reporting.md) 資料來源之一，該資料來源指定可以為其建立直接資料庫查詢的應用程式來源：

- *資料表記錄* 類型的資料來源
- *資料表記錄* 類型的資料來源的關係
- *導出欄位* 類型的資料來源

`expression 1` 和 `expression N` 引數必須指向 ER 資料來源的欄位，該欄位指定也可以為其建立直接資料庫查詢的應用程式源的相關欄位。

如果無法建立直接資料庫查詢，則 ER 模型對應設計工具中會出現驗證[錯誤](er-components-inspections.md#i18)。 您收到的訊息指出包含 `ORDERBY` 函數的 ER 運算式不能在執行階段執行。

為了獲得更好的效能，我們建議您在為可能包含大量記錄的應用程式資料來源 (例如，對於交易性應用程式表) 設定排序時使用 **查詢** 選項。

> [!NOTE]
> `ORDEBY` 函數本身不能轉換為直接的資料庫查詢。 因此，包含此函數的 ER 資料來源不可查詢。 它也不能用於 [FILTER](er-functions-list-filter.md) 和 [ALLITEMSQUERY](er-functions-list-allitemsquery.md) 等 ER 函數的範圍，其中只能使用可查詢的資料來源。

如需相關詳情，請參閱[範例 3](#example-3)和[範例 4](#example-4)。

### <a name="comparability"></a>可比較性

由於 SQL 資料庫引擎和 Finance 應用程式伺服器可以對單個字元使用不同的排名值，因此在使用[字串](er-formula-supported-data-types-primitive.md#string)欄位進行排序時，同一記錄清單的排序結果可能會有所不同。 如需相關詳情，請參閱[範例 5](#example-5)。

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a>範例 1：記憶體式預設執行

如果輸入 *導出欄位* 類型的資料來源 **DS**，它包含運算式 `SPLIT ("C|B|A", "|")`，運算式 `FIRST( ORDERBY( DS, DS. Value)).Value` 回傳文字值 **「A」**。

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a>範例 2：記憶體式明確執行

如果 **廠商** 被設定為參考 **VendTable** 表的 *資料表記錄* 類型的 ER 資料來源，則運算式 `ORDERBY (Vendor, Vendor.'name()')` 和運算式 `ORDERBY ("InMemory", Vendor, Vendor.'name()')` 回傳按名稱升序排列的廠商清單。

在 ER 模型對應設計工具中設定運算式 `ORDERBY ("Query", Vendor, Vendor.'name()')` 時，在設計階段會出現驗證[錯誤](er-components-inspections.md#i8)，因為 `Vendor.'name()'` 路徑參考了具有邏輯的應用程式方法 不能轉換為直接的資料庫查詢。

## <a name="example-3-database-query"></a><a name="example-3"></a>範例 3：資料庫查詢

如果 **TaxTransaction** 被設定為參考 **TaxTrans** 表的 *資料表記錄* 類型的ER資料來源，運算式 `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` 在應用資料庫層面對記錄進行排序，並以遞增排列按稅碼回傳稅收交易清單。

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a>範例 4：可查詢的資料來源

如果將 **TaxTransaction** 設定為參考 **TaxTrans** 表的 *資料表記錄* 類型的 ER 資料來源，則可以設定 **TaxTransactionFiltered** ER 資料來源，使其包含將獲取的運算式 `FILTER(TaxTransaction, TaxCode="VAT19")` 指定稅碼的交易。 因為設定的 **TaxTransactionFiltered** ER 資料來源是可查詢的，所以運算式 `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` 可以設定為以遞增排列回傳按交易日期的過濾稅務交易清單。

如果將 **TaxTransactionOrdered** 設定為 *導出欄位* 類型的 ER 資料來源，其中包含運算式 `ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` 和 *導出欄位* 類型的 ER 資料來源，其中包含運算式 `FILTER(TaxTransactionOrdered, TaxCode="VAT19")`，在 ER 模型對應設計工具的設計階段發生驗證[錯誤](er-components-inspections.md#i18)。 發生此錯誤是因為 [FILTER](er-functions-list-filter.md#usage-notes) 函數的第一個引數必須參考可查詢的 ER 資料來源，但包含 `ORDERBY`函數的 **TaxTransactionOrdered** 資料來源不可查詢。

## <a name="example-5-comparability"></a><a name="example-5"></a>範例 5：可比較性

### <a name="prerequisites"></a>先決條件

1. 輸入包含運算式 `SPLIT ("D1|_D2|D3", "|")` 的 *導出欄位* 類型的資料來源 **DS1**。
2. 開啟 **[財務維度值](../../../finance/general-ledger/financial-dimensions.md)** 頁面，選取 **CostCenter** 維度。
3. 輸入以下維度值：**D1**、**\_D2**，和 **D3**。

### <a name="sorting-in-memory"></a>在記憶體中排序

1. 設定包含運算式 `ORDERBY("InMemory", DS1, DS1.Value)` 的 *導出欄位* 類型的資料來源 **DS2**。
2. 請注意，運算式 `FIRST(DS2).Value` 回傳文字值 **「D1」**，運算式 `INDEX(DS2, COUNT(DS2)).Value` 回傳文字值 **「\_D2」**，運算式 `STRINGJOIN(DS2, DS2.Value, "|")` 回傳文字值 **「D1\|D3\|\_D2」**。

### <a name="sorting-in-database"></a>在資料庫中排序

1. 輸入參考 **FinancialDimensionValueEntity** 實體的 *資料表記錄* 類型的資料來源 **DS3**。
2. 設定包含運算式 `FILTER(DS3, DS3.FinancialDimension="CostCenter")` 的 *導出欄位* 類型的資料來源 **DS4**。
3. 設定包含運算式 `ORDERBY(DS4, DS4.DimensionValue)` 的 *導出欄位* 類型的資料來源 **DS5**。
4. 請注意，運算式 `FIRST(DS5).Value` 回傳文字值 **「\_D2」**，運算式 `INDEX(DS5, COUNT(DS5)).Value` 回傳文字值 **「D3」**，運算式 `STRINGJOIN(DS5, DS5.Value, "|")` 回傳文字值 **「\_D2\|D1\|D3」**。

## <a name="additional-resources"></a>其他資源

[列出函數](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
