---
title: 在電子報表中設計多語言報告
description: 本主題說明如何使用電子報表 (ER) 標籤來設計和產生多語言報告。
author: NickSelin
ms.date: 11/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eab17635494657740fe46364bde0773dae5b9e4b
ms.sourcegitcommit: 8bcb9c13eccb14e61c39ca6578d135b64090fad2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460411"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>在電子報表中設計多語言報告

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>概觀

作為業務使用者，您可以使用[電子報表 (ER)](general-electronic-reporting.md) 架構來設定必鬚根據各個國家或地區的法律要求產生的輸出文件的格式。 當這些需求要求為不同國家或地區產生不同語言的輸出文件時，您可以設定包含語言相關資源的單一 ER 格式。 這樣，您可以重複使用該格式來為各個國家或地區產生輸出文件。 您可能還希望使用單一 ER 格式為相應的客戶、廠商、子公司或任何其他方產生不同語言的輸出文件。

您可以將 ER 資料模型和模型對應設定為已設定 ER 格式的資料來源，以定義資料流，該資料流程指定將哪些應用程式資料放入產生的文件中。 作為 ER 設定[提供者](general-electronic-reporting.md#Provider)，您可以[發佈](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs)設定的資料模型、模型對應和格式作為 ER 解決方案的組件，以產生特定的輸出文件。 您還可以允許客戶[上傳](general-electronic-reporting-manage-configuration-lifecycle.md)已發佈的 ER 解決方案，以便使用和自訂。 如果您希望客戶可能會說其他語言，您可以設定 ER 組件，以便它們包含與語言相關的資源。 這樣，可編輯的 ER 組件的內容可以在設計階段以客戶的使用者偏好語言呈現。

您可以將語言相關資源設定為 ER 標籤。 然後，您可以使用這些標籤來設定 ER 組件以用於以下目的：

- 在設計階段：

    - 以使用者偏好語言呈現已設定 ER 組件的內容。

- 在執行階段：

    - 為輸出文件產生與語言相關的內容。
    - 以使用者偏好語言提供警告和錯誤訊息。
    - 以使用者偏好語言提示必填欄位。

可以在包含不同組件的每個 ER [設定](general-electronic-reporting.md#Configuration)中設定 ER 標籤。 標籤可以獨立於 ER 資料模型、ER 模型對應和 ER 格式組件的設定邏輯進行維護。

每個 ER 標籤都由 ID 識別，該 ID 在持有該標籤的 ER 設定範圍內是唯一的。 每個標籤都可以包含現行 Microsoft Dynamics 365 Finance 實體中支援的每種語言的標籤文字。 這些支援的語言包括已部署自訂的語言。

## <a name="entry"></a>輸入資料

當您設計 ER 資料模型、ER 模型對應或 ER 格式時，只要您選取可能包含可翻譯內容的欄位，就會顯示 **翻譯** 選項。 當您選取此選項時，您可以將所選欄位連結到 **文字翻譯**<a name="TextTranslationPane">窗格</a>上的 ER 標籤。 您可以選取現有的 ER 標籤，也可以新增新的 ER 標籤 (如果它尚不可用)。 當您選取或新增 ER 標籤時，您可以為現行 Finance 實體中支援的每種語言新增相關文字。

下圖顯示了如何在可編輯的 ER 資料模型中完成此翻譯。 在此範例中，可編輯 **發票模型** 的 **PurchaseOrder** 欄位的 **描述** 屬性被翻譯成奧地利德語 (DE-AT) 和日語 (JA) 語言。

![在 ER 資料模型設計工具中提供 ER 標籤的翻譯。](./media/er-multilingual-labels-refer.png)

只能翻譯位於可編輯 ER 組件中的標籤的標籤文字。 例如，如果您為 ER 模型對應資料來源的標籤屬性選取 **翻譯**，然後選取駐留在父 ER 資料模型中的 ER 標籤，您將看到標籤的內容，但無法更改它。 在這些情況下，無法提供 **翻譯文字** 欄位，如下圖所示。

![在 ER 模型對應設計工具中查看提供的 ER 標籤翻譯。](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> 您不能使用設計工具刪除已在可編輯 ER 組件中輸入的標籤。

## <a name="scope"></a>範圍

ER 標籤可以在 ER 組件的多個可翻譯屬性中參考。

### <a name="data-model-component"></a>資料模型組件

設定 ER 資料模型時，可以為其新增 ER 標籤。 模型項目的 **標籤** 和 **描述** 屬性、每個模型的欄位以及每個<a id="LinkModelEnum"></a>模型列舉值都可以連結到新增到 ER 資料模型的 ER 標籤。

![為 ER 資料模型設計工具中的描述屬性提供翻譯。](./media/er-multilingual-labels-refer.png)

當以這種方式設定 ER 資料模型時，其內容將以每個使用者的偏好語言呈現給 ER 資料模型設計工具的使用者。 因此，簡化了模型維護。 下圖顯示了此函數如何適用於將 DE-AT 和 JA 設定為偏好語言的使用者。

![將 DE-AT 設定為偏好語言的使用者的 ER 資料模型設計工具的配置。](./media/er-multilingual-labels-refer-de.png)

![將 JA 設定為偏好語言的使用者的 ER 資料模型設計工具的配置。](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>模型對應組件

因為 ER 模型對應基於 ER 資料模型，所以所參考的資料模型元素的標籤在模型對應設計工具中以使用者的偏好語言顯示。 下圖顯示了如何使用已新增到已設定資料模型的 **描述** 屬性的標籤在可編輯模型對應中解釋 **PurchaseOrder** 欄位的含義。 請注意，此標籤以使用者的偏好語言顯示 (本例中為 DE-AT)。

![將 DE-AT 設定為偏好語言的使用者的 ER 模型對應設計工具的配置。](./media/er-multilingual-labels-show-mapping.png)

當 **使用者輸入參數** 資料來源的 **標籤** 屬性設定為連結到 ER 標籤時，與此資料來源對應的參數欄位會在執行階段以使用者的偏好語言在使用者對話方塊中顯示給使用者。

### <a name="format-component"></a>格式組件

設定 ER 格式時，可以為其新增 ER 標籤。 每個已設定資料來源的 **標籤** 和 **說明文字** 屬性都可以連結到新增到 ER 格式的 ER 標籤。 每個 <a id="LinkFormatEnum"></a>格式列舉值的 **標籤** 和 **描述** 屬性也可以連結到可從可編輯 ER 格式存取的 ER 標籤。

> [!NOTE]
> 您還可以將這些屬性連結到父 ER 資料模型的 ER 標籤，該模型在為此 ER 資料模型設定的每種 ER 格式中重複使用模型的標籤。

以這種方式設定 ER 格式時，格式的內容將以每個使用者的偏好語言呈現給 ER Operation 設計工具的使用者。 因此，簡化了設定邏輯的格式維護和分析。

因為 ER 格式基於 ER 資料模型，所以在資料模型元素中參考的標籤以使用者偏好語言呈現在 ER 格式設計工具中。

當 **使用者輸入參數** 資料來源的 **標籤** 屬性連結到 ER 標籤時，執行階段使用者對話方塊中與參數對應的欄位作為提示呈現給使用者。 下圖顯示了如何在設計階段將 **使用者輸入參數** 資料來源的 **標籤** 屬性連結到 ER 標籤，以便以不同的使用者偏好語言提示使用者輸入參數 (顯示為美國英語 (EN-US ) 和 DE-AT 語言) 在執行階段。

![在 ER Operation 設計工具中提供使用者輸入參數的屬性翻譯。](./media/er-multilingual-labels-refer-format.png)

![ER 廠商在執行階段為 EN-US 使用者偏好語言處理付款。](./media/er-multilingual-labels-show-runtime-en.png)

![ER 廠商在執行階段為 DE-AT 使用者偏好語言處理付款。](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>運算式

若要在 ER [運算式](er-formula-language.md)中使用標籤，必須使用句法 **@"GER\_LABEL:X"**，其中首碼 **@** 表示運算子參考標籤，**GER\_LABEL** 表示涉及 ER 標籤，**X** 為 ER 標籤 ID。

![在 ER 公式設計工具中設定包含對 ER 標籤的參考的 ER 運算式。](./media/er-multilingual-labels-expression1.png)

若要參考系統 (應用程式) 標籤，請使用句法 **@“X”**，其中首碼 **@** 表示運算子參考標籤，**X** 是系統標籤 ID .

![在 ER 公式設計工具中設定包含對應用程式標籤的參考的 ER 運算式。](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>模型對應

可以使用標籤來設定 ER 模型對應的運算式。 當執行以產生輸出文件的 ER 格式調用此對應時，執行的內容包括語言代碼。 設定的運算式標籤將填入為該內容語言設定的標籤文字。

如果參考的標籤對調用模型對應的格式執行內容的語言沒有翻譯，則使用 EN-US 語言中的標籤文字。

#### <a name="format"></a>格式

可以使用標籤來設定 ER 格式的 ER 運算式。 當執行此格式以產生輸出文件時，執行的內容包括語言代碼。 設定的運算式標籤將填入為該內容語言設定的標籤文字。

![在 ER 公式設計工具中提供可編輯 ER 運算式的 ER 標籤的翻譯。](./media/er-multilingual-labels-refer-in-expression.png)

![在 ER Operation 設計工具中參考 ER 標籤的資料繫結範例。](./media/er-multilingual-labels-refer-in-binding.png)

您可以設定 ER 格式的 **FILE** 組件以產生使用者偏好語言的報告。

![在 ER Operation 設計工具中設定 FILE 組件以產生使用者偏好語言的報告。](./media/er-multilingual-labels-language-context-user.png)

如果以這種方式設定 ER 格式，則使用 ER 標籤的相應文字產生報告。 下圖顯示了 EN-US 和 DE-AT 使用者語言的報告範例。

![以 EN-US 使用者的偏好語言產生的報告的預覽。](./media/er-multilingual-labels-report-preview-en.png)

![以 DE-AT 使用者的偏好語言產生的報告的預覽。](./media/er-multilingual-labels-report-preview-de.png)

如果參考的標籤沒有格式執行內容語言的翻譯，則使用 EN-US 語言的標籤文字。

## <a name="language"></a>語言

ER 支援為產生的報告指定語言的不同方式。 在 **格式** 索引標籤上的 **語言偏好項** 欄位中，您可以選取以下值：

- **公司偏好設定** – 以公司指定的語言產生報告。

    ![在 ER Operation 設計工具中指定公司偏好語言作為產生報告的語言。](./media/er-multilingual-labels-language-context-company.png)

- **使用者偏好設定** – 以使用者的偏好語言產生報告。
- **明確定義** – 以設計階段指定的語言產生報告。

    ![在 ER Operation 設計工具中指定設計階段定義的語言作為產生報告的語言。](./media/er-multilingual-labels-language-context-fixed.png)

- **在執行階段定義** – 以執行階段指定的語言產生報告。 如果您選取此值，請在 **語言** 欄位中設定返回語言的語言代碼的 ER 運算式，例如相應客戶的語言。

    ![在 ER Operation 設計工具中指定執行階段定義的語言作為產生報告的語言。](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="culture-specific-formatting"></a>文化專用格式作業

ER 支援為產生的報告指定文化的不同方式。 因此，正確的文化專用格式作業可用於日期、時間和數值。 當您設計 ER 格式時，在 **格式** 索引標籤上的 **文化偏好設定** 欄位中，您可以為 **常用\\檔案**、**Excel\\檔案**、**PDF\\檔案** 或 **PDF\\合併** 類型的每個格式組件選取以下其中一個值：

- **使用者偏好設定** – 根據使用者的偏好文化設定值的格式。 該文化在 **使用者選項** 頁面的 **偏好** 項索引標籤上的 **日期、時間和數字格式** 欄位中定義。

    ![將使用者的偏好文化定義為 ER Operation 設計工具中產生的報告的文化。](./media/er-multilingual-labels-culture-context-user-preferred.png)

- **明確定義** – 根據設計階段指定的文化設定值的格式。

    ![將設計階段指定的文化定義為 ER Operation 設計工具中產生的報告的文化。](./media/er-multilingual-labels-culture-context-fixed.png)

- **在執行階段定義** – 根據執行階段指定的文化設定值的格式。 如果您選取此值，請在 **對應** 索引標籤上的 **日期、時間和數字格式** 欄位中，設定返回文化代碼的 ER 運算式，例如相應客戶的文化。

    ![將執行階段定義的文化定義為 ER Operation 設計工具中產生的報告的文化。](./media/er-multilingual-labels-culture-context-runtime.png)

> [!NOTE]
> 您為其定義特定文化的 ER 組件可能包含被設定為填入文字值的子 ER 組件。 在預設情況下，父組件的文化用於格式化這些組件的值。 您可以使用以下內建的 ER 函數來設定這些組件的繫結，並為數值格式化應用一種替代文化：
>
> - [DATEFORMAT](er-functions-datetime-dateformat.md#syntax-2)
> - [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md#syntax-2)
> - [NUMBERFORMAT](er-functions-text-numberformat.md#syntax-2)
>
> 在 10.0.20 及更高版本中，**常用\\檔案** 和 **Excel\\檔案** 類型的格式組件的語言環境用於在產生的文件的 [PDF 轉換](electronic-reporting-destinations.md#OutputConversionToPDF)期間格式化值。

## <a name="translation"></a>換算

您可以將所需的 ER 標籤新增到可編輯的 ER 組件。 新增 ER 標籤後，可以透過兩種方式進行翻譯：手動翻譯和自動翻譯。

### <a name="manual-translation"></a>手動翻譯

在 **文字翻譯**[窗格](#TextTranslationPane)上新增 ER 標籤時，您可以手動將其翻譯成現行 Finance 實體支援的所有語言。 您可以在 **系統語言** 或 **使用者語言** 區段的 **語言** 欄位中選取偏好語言，在相應的 **已翻譯文字** 欄位中輸入適當的文字，然後選取 **翻譯**。 必須針對您新增的每種所需語言和每個標籤重複此過程。

### <a name="automatic-translation"></a>自動翻譯

ER 組件的設定在可編輯 ER 組件所在的 ER 設定的草稿版本中完成。

![ER 設定頁面提供對處於草稿狀態的設定版本的存取權限。](./media/er-multilingual-labels-configurations.png)

如本主題前面所述，您可以將所需的 ER 標籤新增到可編輯的 ER 組件。 透過這種方式，您可以使用 EN-US 語言指定 ER 標籤的文字。 然後，您可以使用內建的 ER 函數匯出 ER 組件的標籤。 選取包含可編輯 ER 組件的 ER 設定草稿版本，然後選取 **Exchange\>匯出標籤**。

![ER 設定頁面允許從選定的設定版本中匯出 ER 標籤。](./media/er-multilingual-labels-export.png)

您可以匯出所有標籤，也可以匯出您在匯出之初指定的單一語言的標籤。 標籤匯出為包含 XML 檔案的 ZIP 檔案。 每個 XML 檔案都包含一種語言的標籤。

![包含 DE-AT 語言的 ER 標籤的匯出檔案樣本。](./media/er-multilingual-labels-in-xml.png)

此格式用於由 [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md) 等外部翻譯服務自動翻譯標籤。 當您收到翻譯後的標籤時，您可以將它們匯入回包含擁有這些標籤的 ER 組件的 ER 設定的草稿版本。 選取包含可編輯 ER 組件的 ER 設定草稿版本，然後選取 **Exchange\>載入標籤**。

![ER 設定頁面允許將 ER 標籤匯入到選定的設定版本。](./media/er-multilingual-labels-load.png)

翻譯後的標籤將被匯入到選定的 ER 設定中。 此 ER 設定中存在的已翻譯標籤將被替換。 如果 ER 設定中缺少任何已翻譯的標籤，則會附加該標籤。

## <a name="lifecycle"></a>生命週期

可編輯的 ER 組件的標籤與組件的其他內容一起儲存在 ER 設定的適當版本中。

基礎 ER 組件的標籤可以在您建立以引入修改的 ER 組件的衍生版本中參考。

ER 版本設定控制對 ER 組件中任何屬性的標籤指派。 對標籤指派的更改記錄在已建立為提供的 ER 組件的衍生版本的可編輯 ER 組件的更改清單 (delta) 中。 當衍生版本重新基於新的基礎版本時，這些更改將得到驗證。

## <a name="functions"></a>函數

內建的 [LISTOFFIELDS](er-functions-list-listoffields.md) ER 函數可以存取已為某些 ER 組件項設定的 ER 標籤。

如本主題前面所述，每個 [模型](#LinkModelEnum)或 [格式](#LinkFormatEnum) ER 列舉值的 **標籤** 和 **描述** 屬性都可以連結到可在相應 ER 組件中存取的 ER 標籤。 您可以使用 ER 列舉作為參數來設定調用 **LISTOFFIELDS** 函數的 ER 運算式。 此運算式返回清單，其中包含已定義為此函數參數的 ER 列舉的每個值的記錄。 每條記錄都包含連結到 ER 列舉值的 ER 標籤值：

- 連結到 **標籤** 屬性的 ER 標籤的值儲存在返回記錄的 **標籤** 欄位中。
- 連結到 **描述** 屬性的 ER 標籤的值儲存在返回記錄的 **描述** 欄位中。

## <a name="performance"></a><a name=performance></a>效能

當您將 ER 格式組件設定為以您的偏好 [語言](#language)產生報告，或匯入內容由您的偏好語言解析的入站文件時，我們建議您啟用 **快取現行使用者的偏好語言以進行 ER 執行** 函數在[函數管理](../../fin-ops/get-started/feature-management/feature-management-overview.md)工作區中。 此函數有助於提高效能，特別是對於包含對 ER 公式和繫結中的標籤的多個參考以及許多[驗證](general-electronic-reporting-formula-designer.md#TestFormula)規則以產生您偏好語言的使用者訊息的 ER 格式組件。

當您將 ER 設定版本的狀態從 **草稿** 更改為 **已完成** 時，如果設定版本包含 ER 標籤，則這些標籤將儲存在應用程式資料庫中。 儲存結構描述取決於 **加速 ER 標籤儲存** 函數的狀態：

- 如果未啟用該函數，則所有標籤都作為單個 XML 片段儲存在 **ERSOLUTIONVERSIONTABLE** 表的 **LABELXML** 欄位中。
- 如果啟用該函數，則會在 **ERSOLUTIONVERSIONLABELSTABLE** 表中為每種語言建立單獨的記錄。 此表的 **CONTENTS** 欄位將每種語言的標籤儲存為壓縮的 XML 片段。

我們建議您在 **函數管理** 工作區中啟用 **加速 ER 標籤儲存** 函數。 此函數有助於提高網路頻寬利用率和整體系統效能，因為在大多數情況下，當您使用單一 ER 設定時，會使用單一語言的 ER 標籤。

若要應用選定的儲存結構描述來保留現行 Finance 實體中所有 ER 設定的標籤，請完成以下步驟。

1. 前往 **組織管理** > **定期** > **為所有 ER 設定應用選定的標籤儲存結構描述**。
2. 選取 **確定**。


## <a name="additional-resources"></a>其他資源

- [電子報表概觀](general-electronic-reporting.md)
- [電子報表函數](er-formula-language.md#Functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
