---
title: 電子報表 (ER) 中的公式設計工具
description: 本主題提供有關如何在電子報表 (ER) 中使用公式設計工具的資訊。
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
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
ms.openlocfilehash: eec63fb1782c5afed0320eb841b6bfc92af31a691731ef6bac5d00ed442c0dcd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460213"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>電子報表 (ER) 中的公式設計工具

[!include [banner](../includes/banner.md)]

本主題說明如何在電子報表 (ER) 中使用公式設計工具。 當您在 ER 中為特定電子文件設計格式時，您可以使用公式來轉換資料，以使其滿足文件履行和格式的要求。 這些公式類似於 Microsoft Excel 中的公式。 公式中支援各種類型的函數：文字、日期和時間、數學、邏輯、資訊和資料類型轉換函數，以及其他特定於業務領域的函數。

## <a name="formula-designer-overview"></a>公式設計工具概述

ER 支援公式設計工具。 因此，在設計階段，您可以設定可在執行階段用於以下工作的運算式：

- 轉換從應用程式資料庫接收並應輸入到設計為 ER 格式資料來源的 ER 資料模型中的資料。 (例如，這些轉換可能包括篩選、分組和資料類型轉換。)
- 必須根據特定 ER 格式的配置和條件發送到產生電子文件的格式資料。 (例如，可以根據請求的語言或文化或編碼進行格式化)。
- 控制建立電子文件的過程。 (例如，運算式可以啟用或禁用格式的特定元素的輸出，具體取決於處理資料。 他們還可以中斷文件建立過程或向使用者發送訊息。)

當您執行以下任何動作時，您可以打開 **公式設計工具** 頁面：

- 將資料來源項目繫結到資料模型組件。
- 將資料來源項目繫結到格式組件。
- 完整維護作為資料來源一部分的導出欄位。
- 定義使用者輸入參數的可見性條件。
- 設計格式的轉換。
- 定義格式組件的啟用條件。
- 為格式的 FILE 組件定義檔案名。
- 定義過程控制驗證的條件。
- 定義過程控制驗證的訊息文字。

## <a name="data-binding"></a><a name="Binding"></a>資料繫結

ER 公式設計工具可用於定義轉換從資料來源接收的資料的運算式，以便在執行階段透過以下方式將資料輸入資料使用者：

- 從應用程式資料來源和執行階段參數到 ER 資料模型
- 從 ER 資料模型到 ER 格式
- 從應用程式資料來源和執行階段參數到 ER 格式

下圖顯示了這種類型的運算式的設計。 在此範例中，運算式將 Intrastat 表中 **Intrastat.AmountMST** 欄位的值進位到小數點後兩位，然後回傳進位的值。

[![資料繫結運算式。](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

下圖顯示了如何使用這種類型的運算式。 在本例中，設計運算式的結果被輸入到 **稅金報表模型** 資料模型的 **Transaction.InvoicedAmount** 組件中。

[![正在使用資料繫結運算式。](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

在執行階段，設計的公式 `ROUND (Intrastat.AmountMST, 2)` 將 Intrastat 表中每條記錄的 **AmountMST** 欄位的值進位到小數點後兩位。 然後它在 **稅務報表** 資料模型的 **Transaction.InvoicedAmount** 組件中輸入進位的值。

## <a name="data-formatting"></a><a name="Transformation"></a>資料格式設定

ER 公式設計工具可用於定義對從資料來源接收的資料進行格式化的運算式，以便可以將資料作為產生電子文件的一部分發送。 您可能具有必須作為典型規則套用的格式，該規則應重複用於格式。 在這種情況下，您可以在格式設定中引入該格式一次，作為具有格式運算式的命名轉換。 然後，此命名轉換可以連結到許多格式組件，其中必鬚根據您建立的格式化運算式對輸出進行格式化。

下圖顯示了這種類型轉換的設計。 在此範例中，**TrimmedString** 轉換透過刪除前導和尾隨空格來截斷 *字串* 資料類型的傳入資料。 然後它回傳截斷的字串值。

[![轉換。](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

下圖顯示了如何使用這種類型的轉換。 在此範例中，幾個格式組件在執行階段將文字作為輸出發送到產生的電子文件。 所有這些格式組件都按名稱參考 **TrimmedString** 轉換。

[![正在使用轉換。](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

當格式組件 (例如上圖中的 **partyName** 組件) 參考 **TrimmedString** 轉換時，該轉換會將文字作為輸出發送到產生的電子文件。 此文字不包括前導和尾隨空格。

如果您有必須單獨套用的格式，您可以將該格式作為特定格式組件繫結的單獨運算式引入。 下圖顯示了這種類型的運算式。 在此範例中，**partyType** 格式組件透過一個運算式繫結到資料來源，該運算式將來自資料來源中的 **Model.Company.RegistrationType** 欄位的傳入資料轉換為大寫文字。 然後，運算式將該文字作為輸出發送到電子文件。

[![將格式套用於單個組件。](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="process-flow-control"></a><a name="Validation"></a>程式流程控制

ER 公式設計工具可用於定義控制產生電子文件流程的運算式。 您可以執行以下工作：

- 定義確定何時必須停止文件建立過程的條件。
- 指定運算式，為使用者建立有關已停止進程的訊息或拋出有關報表產生的持續過程的執行記錄訊息。
- 指定產生電子文件的檔案名稱，並控制其建立條件。

流程控制的每條規則都被設計為單獨的驗證。 下圖顯示了這種類型的驗證。 以下是本範例中的設定說明：

- 在產生 XML 檔案期間建立 **INSTAT** 節點時評估驗證。
- 如果交易清單為空白，則驗證停止執行過程並回傳 **FALSE**。
- 驗證回傳一條錯誤訊息，其中包含使用者偏好語言的標籤 SYS70894 的文字。

[![驗證。](./media/picture-validation.jpg)](./media/picture-validation.jpg)

ER 公式設計工具還可用於為產生的電子文件產生檔案名並控制檔案建立過程。 下圖顯示了此類型程式流程控制的設計。 以下是本範例中的設定說明：

- 來自 **model.Intrastat** 資料來源的記錄清單分為批次。 每個批次最多包含 1,000 條記錄。
- 輸出建立一個 ZIP 檔案，其中包含一個 XML 格式的檔案，用於建立的每個批次。
- 運算式透過連線檔案名和副檔名回傳用於產生電子文件的檔案名稱。 對於第二批和所有後續批次，檔案名包含作為後綴的批次 ID。
- 一個運算式啟用 (透過回傳 **TRUE**) 包含至少一條記錄的批次的檔案建立過程。

[![程式流程控制。](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="document-content-control"></a><a name="Enabled"></a>文件內容控制

ER 公式設計工具可用於設定運算式，以控制在執行階段將哪些資料放入產生的電子文件中。 運算式可以啟用或禁用格式的特定元素的輸出，具體取決於處理資料和設定的邏輯。 可以在 **Operations 設計工具** 頁面的 **對應** 索引標籤上的 **啟用** 欄位中為單個格式元素輸入這些運算式。 您可以輸入運算式作為回傳 *布林值* 的邏輯條件：

- 如果條件回傳 **True**，則執行目前格式元素。
- 如果條件回傳 **False**，則跳過目前格式元素。

下圖顯示了這種類型的運算式。 (以 Microsoft 提供的 **ISO20022 貸記轉移 (NO)** 格式設定的11.12.11版為例)。**XMLHeader** 格式元件被設定為根據 ISO20022 XML 訊息標準來描述貸記轉帳訊息的結構。 **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** 格式組件被設定為將 **Ustrd** XML 元素新增到產生的訊息中，並將匯款資訊以非結構化格式作為以下 XML 元素的文字放置：

- **PaymentNotes** 組件用於產生付款單的文字。
- **DelimitedSequence** 組件產生以逗號分隔的發票編號，用於結算目前的貸記轉帳。

[![PaymentNotes 和 DelimitedSequence 組件。](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> 使用問號標記 **PaymentNotes** 和 **DelimitedSequence** 組件。 問號表示組件的使用是有條件的。 在這種情況下，組件的使用基於以下標準：
>
> - 為 **PaymentNotes** 組件定義的 `@.PaymentsNotes <> ""` 運算式使 (透過回傳 **TRUE**) **Ustrd** XML元素被填入付款通知的文字，如果該文字在目前貸記轉帳中不是空白。
>
>    [![PaymentNotes 組件的運算式。](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - 為 **DelimitedSequence** 組件定義的 `@.PaymentsNotes = ""` 運算式使 **Ustrd** XML 元素 (透過回傳 **TRUE**) 被填入一個逗號分隔的發票號碼清單，這些發票號碼用於結算目前的貸記轉帳，如果該貸記轉帳的付款說明文字是空白的。
>
>    [![DelimitedSequence 組件的運算式。](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> 基於這種設定，為每個債務人付款產生的訊息，即 **Ustrd** XML元素，將包含付款說明的文字，或者當該文字為空白時，包含用於結算付款的發票號碼的逗號分隔清單。

## <a name="validation-of-configured-formulas"></a><a name="TestFormula"></a>驗證設定的公式

在 **公式設計師** 頁面，選取 **測試** 驗證設定的公式如何運作。

[![選取測試以驗證公式。](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

當需要公式參數的值時，您可以從 **公式設計工具** 頁面打開 **測試運算式** 對話方塊。 在大多數情況下，必須手動定義這些參數，因為設定的繫結不會在設計階段執行。 **公式設計工具** 頁面上的 **測試結果** 索引標籤顯示了設定公式的執行結果。

以下範例說明如何測試為外貿領域設定的公式，以確保 Intrastat 商品代碼僅包含數字。

測試此公式時，您可以使用 **測試運算式** 對話方塊指定 Intrastat 商品代碼的值以進行測試。

[![指定用於測試的 Intrastat 商品代碼。](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

指定 Intrastat 商品代碼並選取 **確定** 後，**公式設計工具** 頁面上的 **測試結果** 索引標籤將顯示設定公式的執行結果。 然後，您可以評估結果是否可以接受。 如果結果不可接受，您可以更新公式並再次測試。

[![測試結果。](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

某些公式無法在設計階段進行測試。 例如，公式可能會回傳無法在 **測試結果** 索引標籤上顯示的資料類型的結果。在這種情況下，您會收到一條錯誤訊息，指出無法測試該公式。

[![錯誤訊息。](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>其他資源

- [電子報表概觀](general-electronic-reporting.md)
- [電子報表公式語言](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]