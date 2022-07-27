---
title: 電子報表公式支援的原始資料類型
description: 本主題提供有關電子報表 (ER) 公式中支援的原始資料類型的資訊。
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 96fdf33f4cc5f22015c00c57858bd438e6465764
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460577"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>電子報表公式支援的原始資料類型

[!include [banner](../includes/banner.md)]

本主題提供有關[電子報表 (ER)](general-electronic-reporting.md) 運算式中支援的原始資料類型的資訊。 以下是原始資料類型的清單：

- [布林值](#boolean)
- [日期](#date)
- [日期時間](#datetime)
- [列舉](#enumeration)
- [GUID](#guid)
- [整數](#integer)
- [Int64](#int64)
- [實數](#real)
- [字串](#string)

## <a name="boolean"></a><a name="boolean"></a>布林值

*布林值* 原始資料類型包含會被評估為 *True* 或 *False* 的值。 您可以在需要 *布林值* 運算式的任何地方使用保留的文字關鍵字 **True** 和 **False**。 預設值為 *False*。

*布林值* 的內部表示是一個 *整數*。 *整數* 值 0 (零) 被評估為 *False*，而所有其他 *整數* 值被評估為 *True*。 當您在 [ER 公式設計工具](er-advanced-formula-editor.md)中 [驗證](general-electronic-reporting-formula-designer.md#TestFormula)回傳 *布林值* 的設定運算式時，當運算式回傳 *False* 時，測試結果窗格將顯示 *0* (零)。 否則，測試結果窗格將顯示 *1*。

*布林值* 沒有隱含轉換。 但是，您可以使用 [TEXT](er-functions-text-text.md) 函數將 *布林值* 顯式轉換為 *字串*：

- 將 *False* 值轉換為文字字串 **False**。
- 將 *True* 值轉換為文字字串 **True**。

> [!NOTE]
> 這種轉換不依賴於提供的語言和文化[內容](er-design-multilingual-reports.md)。

比較 [運算子](er-formula-language.md#Operators)是唯一可以與 *布林值* 資料類型。 以下運算子可用於比較兩個 *布林值*：\<\> 和 =。

## <a name="date"></a><a name="date"></a>日期

*日期* 原始資料類型包含日、月和年。 可以使用以下函數啟動日期：

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [SESSIONTODAY](er-functions-datetime-sessiontoday.md)
- [TODAY](er-functions-datetime-today.md)

*日期* 資料類型可以儲存 1900 年 1 月 1 日到 2154 年 12 月 31 日之間的日期。 預設值為 **Null**，內部表示為日期 1900 年 1 月 1 日。

*日期* 沒有隱含轉換。 但是，您可以使用以下明確轉換函數：

- [DATEFORMAT](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [TEXT](er-functions-text-text.md)

[ADDDAYS](er-functions-datetime-adddays.md) 函數允許您從日期中新增和減去天數。 透過這種方式，您可以將日期移動到未來和過去的特定天數。 [DAYS](er-functions-datetime-days.md) 函數可讓您將日期彼此相減並計算天數之差。 如需 *日期* 值轉換的相關資訊，請參閱[日期和時間類別中的 ER 函數清單](er-functions-category-datetime.md)。

比較 [運算子](er-formula-language.md#Operators)是唯一可以與 *日期* 資料類型。 以下運算子可用於比較兩個 *日期* 值：\<\>、\<, \<=, =, \> 和 \>=。

## <a name="datetime"></a><a name="datetime"></a>日期時間

*日期時間* 原始資料類型結合了 *日期* 類型和一個表示自午夜以來經過的時間的值。 時間以小時、分鐘、秒和秒的分數表示。 *日期時間* 值還包含有關時區的資訊。

*日期時間* 資料類型可以儲存 1900 年 1 月 1 日 (往返[格式](/dotnet/standard/base-types/standard-date-and-time-format-strings)為 1900-01-01T00:00:00.0000000+00:00) 和 2154 年 12 月 31 日 (2154/12/31T11:59:59.9999999+00 之間的日期:00 以往返格式)。 *日期時間* 中的最小時間單位是百萬分之一秒。

> [!NOTE]
> 當 **hh** [規範](/dotnet/standard/base-types/standard-date-and-time-format-strings)用於小時時，12:59:59:9999999 以上的時間值不能解釋為有效時間。
>
> 當 **HH** 規範用於小時時，23:59:59:9999999 以上的時間值不能解釋為有效時間。

預設值為 **Null**，內部表示為日期 1 月 1 日，1900 (1900-01-01T00:00:00.0000000+00:00 的往返格式)。

可以使用以下函數啟動日期時間：

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [SESSIONNOW](er-functions-datetime-sessionnow.md)
- [NOW](er-functions-datetime-now.md)

*日期時間* 沒有隱含轉換。 但是，您可以使用以下明確轉換函數：

- [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [TEXT](er-functions-text-text.md)

如需 *日期時間* 值轉換的相關資訊，請參閱[日期和時間類別中的 ER 函數清單](er-functions-category-datetime.md)。

比較 [運算子](er-formula-language.md#Operators)是唯一可以與 *日期時間* 資料類型。 以下運算子可用於比較兩個 *日期時間* 值：\<\>、\<, \<=, =, \> 和 \>=。

## <a name="enumeration"></a><a name="enumeration"></a>列舉

*列舉* 原始資料類型是常值清單。 您可以使用在應用程式[原始程式碼](../dev-ref/xpp-data-primitive.md#enum)中定義的列舉。 您還可以在 ER 資料模型和 ER 格式組件中引入您自己的列舉。

應用程式 *列舉* 可用於任何 ER 模型對應和 ER 格式的運算式。

下圖顯示了如何將 **CustVendCorrectiveReasonCode** 模型列舉新增到可編輯的 ER 資料模型。

[![在 ER 資料模型設計工具中設定模型列舉。](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

模型 *列舉* 可用於在引入 *列舉* 的資料模型下建立的任何 ER 模型對應和 ER 格式的運算式中。

下圖顯示了如何將 **Natura 反向充電子類別清單** 格式列舉新增到可編輯的 ER 格式。

[![在 ER 格式設計工具中設定格式列舉。](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

格式 *列舉* 只能在引入 *列舉* 的 ER 格式的運算式中使用。

您必須使用適當類型的 ER 資料來源將特定列舉作為常量或作為執行 ER 解決方案的使用者在執行階段在對話方塊中定義的值帶到已設定的 ER 組件。

- 可以使用 **Dynamics 365 for Operations\列舉** 和 **一般\使用者輸入參數** 資料來源存取應用程式列舉。 下圖顯示了如何將參考 **NoYes** 應用程式列舉的 **appenumNoYes** 和 **uipNoYes** 資料來源新增到可編輯的 ER 格式。

    [![在 ER 格式設計工具中新增應用程式列舉資料來源。](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- 資料模型列舉可以透過使用 **資料模型\列舉** 和 **資料模型\列舉使用者輸入參數** 資料來源來存取。 下圖顯示了如何將參考 **CustVendCorrectiveReasonCode** 資料模型列舉的 **CustVendCorrectiveReasonCode** 資料來源新增到可編輯的 ER 格式。

    [![在 ER 格式設計工具中新增模型列舉資料來源。](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- 可以使用 **格式\列舉** 和 **格式\列舉使用者輸入參數** 資料來源存取格式列舉。 下圖顯示了如何將參考 **Natura 反向充電子類別** 格式列舉的 **NaturaReverseCharge** 資料來源新增到可編輯的 ER 格式。

    [![在 ER 格式設計工具中新增格式列舉資料來源。](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

*列舉* 沒有隱含轉換。 但是，您可以使用 [TEXT](er-functions-text-text.md) 轉換函數將 *列舉* 轉換為文字字串。 這種轉換不依賴於語言。 若要了解如何將 *列舉* 值與適當的特定於語言的標籤相關，請參閱 [LISTOFFIELDS](er-functions-list-listoffields.md) 和 [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md) 函數的用法範例。

比較 [運算子](er-formula-language.md#Operators)是唯一可以與 *列舉* 資料類型。 以下運算子可用於比較兩個 *列舉*：\<\> 和 =。

## <a name="guid"></a><a name="guid"></a>GUID

*GUID* 原始資料類型包含全域唯一識別碼 (GUID) 值。 GUID 是一個可以在所有需要唯一識別碼的地腦和網路中使用的值。 這個數字不太可能重複。 有效的 GUID 滿足以下所有規格：

- 必須有 32 個十六進位數字。
- 此外，必須在以下位置嵌入四個連接號字元：8-4-4-4-12。
- 此外，可以在字串的開頭和結尾新增可選的大括號 \{\}。 例如，兩者 **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}** 和 **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** 是有效的 GUID 字串。
- 因此，總共必須有 36 個或 38 個字元，具體取決於是否新增大括號。
- 用作十六進位數字的字母可以是大寫 (A–F)、小寫 (a–f) 或大小寫混合。

可以使用以下明確轉換函數：

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [TEXT](er-functions-text-text.md)

比較 [運算子](er-formula-language.md#Operators)是唯一可以與 *GUID* 資料類型。 以下運算子可用於比較兩個 *GUID*：\<\> 和 =。

## <a name="integer"></a><a name="integer"></a>整數

*整數* 原始資料類型表示沒有小數點的數字。 整數用作重複陳述式中的控制變量或記錄清單中的指數。

*整數* 文字是直接在 ER [運算式](general-electronic-reporting-formula-designer.md#formula-designer-overview) (公式) 中輸入的整數，例如 **12345**。 *整數* 是 32 位元寬。 預設值為 **0**，內部表示是一個長數。 *整數* 會自動轉換為 *實數*。

此外，可以使用以下明確轉換函數：

- [INTVALUE](er-functions-conversion-intvalue.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

*整數* 的範圍是 \[-2,147,483,647 : 2,147,483,647\]。 此範圍內的所有整數都可以用作常值。

所有比較和數學 [運算子](er-formula-language.md#Operators)都可以與 *整數* 資料類型一起使用。

## <a name="int64"></a><a name="int64"></a>Int64

*int64* 原始資料類型表示沒有小數點的數字。 *Int64* 值用作重複陳述式中的控制變量或記錄識別碼。

*int64* 是 64 位元寬。 預設值為 **0**，內部表示是一個長數。 *int64* 會自動轉換為 *實數*。

此外，可以使用以下明確轉換函數：

- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

*int64* 的範圍是 \[-9,223,372,036,854,775,807 : 9,223,372,036,854,775,807\]。

所有比較和數學 [運算子](er-formula-language.md#Operators)都可以與 *int64* 資料類型一起使用。

## <a name="real"></a><a name="real"></a>實際

除了整數之外，*實數* 原始資料類型還可以儲存十進位值。 您可以在任何需要 *實數* 的地方使用十進位常值。 十進位常值是直接在代碼中輸入的小數，例如 **2.19**。

> [!NOTE]
> 在 ER 運算式中，句點 (.) 一律用作小數點分隔符號。

實數可以在所有運算式中使用，並且可以與比較運算子和算術運算子一起使用。 *實數* 的精確度為 16 位有效數字。 *實數* 的預設值為 **0.0**，內部表示為二進位編碼數字 (BCD)。 BCD 編碼可以精確表示 0.1 倍數的值。 *實* 變量的範圍是 -(10)<sup>127</sup> 到 (10)<sup>127</sup>。 此範圍內的所有實數都可以用作 ER 運算式中的常值。

*實數* 沒有隱含轉換。 但是，您可以使用以下函數將 *實數* 明確轉換為其他資料類型，並將其他資料類型明確轉換為 *實數*：

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)
- [VALUE](er-functions-conversion-value.md)

所有比較和數學 [運算子](er-formula-language.md#Operators)都可以與 *實數* 資料類型一起使用。

## <a name="string"></a><a name="string"></a>字串

*字串* 原始資料類型表示用作文字、帳號、地址和電話號碼的字元序列。

*字串* 常值是用引號 ("") 括起來的字元。 在 ER 運算式中需要 *字串* 值的任何地方都可以使用 *字串* 常值。 您可以在邏輯運算式中使用字串，例如比較。 您還可以使用 **\&** 運算子或 [CONCATENATE](er-functions-text-concatenate.md) 函數連接 *字串* 值。

> [!NOTE]
> 如果您連接兩個 *字串* 值，並且希望結果 *字串* 跨越多行，請在值之間使用換行符分隔符號。 對於 TEXT 輸出，此分隔符號可以是使用 [CHAR](er-functions-text-char.md)(10) 或 CHAR(13) 運算式產生的字元。 對於 HTML，它可以是 **\<br\>** 標記。

*字串* 的預設值是沒有字元的空白文字字串，內部表示是字元清單。

字串沒有自動轉換。 但是，可以使用以下明確轉換函數：

- [CHAR](er-functions-text-char.md)
- [FORMAT](er-functions-text-format.md)
- [LEFT](er-functions-text-left.md)
- [LEN](er-functions-text-len.md)
- [MID](er-functions-text-mid.md)
- [PADLEFT](er-functions-text-padleft.md)
- [REPLACE](er-functions-text-replace.md)
- [RIGHT](er-functions-text-right.md)
- [TEXT](er-functions-text-text.md)
- [TRANSLATE](er-functions-text-translate.md)
- [TRIM](er-functions-text-trim.md)
- [UPPER](er-functions-text-upper.md)

如需 *字串* 值轉換的相關資訊，請參閱[文字類別的 ER 函數清單](er-functions-category-text.md)。

*字串* 可以包含不定數量的字元。

所有比較 [運算子](er-formula-language.md#Operators)都可以與 *字串* 資料類型一起使用。

## <a name="additional-resources"></a>其他資源

- [電子報表概觀](general-electronic-reporting.md)
- [電子報表公式語言](er-formula-language.md)
- [支援的複合資料類型](er-formula-supported-data-types-composite.md)
