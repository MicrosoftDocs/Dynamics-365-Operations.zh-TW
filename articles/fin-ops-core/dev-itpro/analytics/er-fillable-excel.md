---
title: 設計用於產生 Excel 格式文件的設定
description: 本主題介紹如何設計電子報表 (ER) 格式以填入 Excel 範本，然後產生輸出 Excel 格式文件。
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b2f38aa9e5eff9366697afd57ceefd06f026096
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2022
ms.locfileid: "8460495"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>設計用於產生 Excel 格式文件的設定

[!include[banner](../includes/banner.md)]

您可以設計具有 ER 格式組件的[電子報表 (ER)](general-electronic-reporting.md)格式設定，您可以將其設定以產生 Microsoft Excel 活頁簿格式的輸出文件。 為此必須使用特定的 ER 格式組件。

若要進一步了解此函數，請按照主題中的步驟動作，[設計用於以 OPENXML 格式產生報告的設定](tasks/er-design-reports-openxml-2016-11.md)。

## <a name="add-a-new-er-format"></a>新增新的 ER 格式

當您新增新的 ER 格式設定以產生 Excel 活頁簿格式的輸出文件時，您必須選取 **Excel** 值，用於格式的 **格式類型** 屬性或讓 **格式類型** 屬性留白。

- 如果您選取 **Excel**，您可以設定格式以僅產生 Excel 格式的輸出文件。
- 如果將該屬性留白，則可以設定格式以產生 ER 架構支持的任何格式的輸出文件。

若要設定組態的 ER 格式組件，請選取動作窗格上的 **設計工具**，然後在 ER 作業設計工具中打開 ER 格式組件進行編輯。

![設定頁面。](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Excel 檔案組件

### <a name="manual-entry"></a>手動輸入

您必須新增 **Excel\\檔案** 組件到設定的 ER 格式以產生 Excel 格式的輸出文件。

![Excel\檔案組件。](./media/er-excel-format-add-file-component.png)

若要指定輸出文件的配置，請將副檔名為 .xlsx 的 Excel 活頁簿附加到 **Excel\\檔案** 組件作為輸出文件的範本。

> [!NOTE]
> 手動附加範本時，必須使用[文件類型](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types)，這些文件類型已為此目的在[ER 參數](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)中設定。

![向 Excel\檔案組件新增附件。](./media/er-excel-format-add-file-component2.png)

若要指定在執行設定的 ER 格式時如何填入附加範本，您必須新增巢狀 **工作表**、**範圍**，和 **儲存格** 組件到 **Excel\\檔案** 組件。 每個巢狀組件都必須與 Excel 命名項相關。

### <a name="template-import"></a>範本匯入

您可以選取在動作窗格上 **匯入** 索引標籤的 **從 Excel 匯入**，以便將新範本匯入空白 ER 格式。 在這個範例中，**Excel\\檔案** 組件將自動建立，並且匯入的範本將附加到它上面。 所有必需的 ER 組件也將根據發現的 Excel 命名項目清單自動建立。

![選取從 Excel 匯入。](./media/er-excel-format-import-template.png)

> [!NOTE]
> 如果要建立可編輯 ER 格式上的選取性 **工作表** 元素，將 **建立 Excel 工作表格式元素** 選項設定為 **是**。

## <a name="sheet-component"></a>工作表組件

**工作表** 組件表示必須填入的附加 Excel 活頁簿的工作表。 Excel 範本中的工作表名稱在此組件的 **工作表** 屬性中定義。

> [!NOTE]
> 對於包含單個工作表的 Excel 活頁簿，此組件是選取性的。

在 ER 作業設計工具的 **對應** 索引標籤上，您可以為 **工作表** 組件設定 **啟用** 屬性，以便指定是否必須將組件放入產生的文件中：

- 如果 **啟用** 屬性的運算式在執行階段設定退回 **True**，或者如果根本沒有設定運算式，則會將相應的工作表放入產生的文件中。
- 如果 **啟用** 屬性的運算式在執行階段設定返回 **False**，產生的文件將不包含工作表。

![工作表組件的範例。](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>範圍組件

### <a name="nested-components"></a>巢狀組件

#### <a name="data-typing"></a>資料輸入

**範圍** 組件可以有其他巢狀的 ER 組件，用於在相應的範圍內輸入值。

- 如果 **文字** 組的任何組件用於輸入值，該值作為文字值輸入到 Excel 範圍內。

    > [!NOTE]
    > 使用此模式根據套用程式中定義的區域設定輸入值的格式。

- 如果 **Excel** 組的 **儲存格** 組件被用來輸入數值，那麼該數值將作為資料類型的數值被輸入到 Excel 範圍內，該資料類型由該 **儲存格** 組件的繫結定義。 例如，資料類型可能是 **字串**、**實數** 或 **整數**。

    > [!NOTE]
    > 使用此模式使 Excel 套用程式能夠根據打開輸出文件的本地電腦的區域設定輸入值的格式。

#### <a name="row-handling"></a>資料列處理

**範圍** 組件可以設定為垂直複製，以便在 Excel 工作表中產生多資料列。 資料列可以由父系 **範圍** 組件或由其巢狀 **範圍** 組件產生。

在 10.0.26 及更高版本中，您可以強制產生的工作表將產生的資料列保持在同一頁面上。 在 ER 格式設計工具中，將 **將資料列保持在一起** 選項設定為 **是**，用可編輯 ER 格式的於父系 **範圍** 組件。 然後，ER 將嘗試將該範圍產生的所有內容保留在同一頁面上。 如果內容的高度超過現行頁面的剩餘空間，則會新增分頁符號，內容將從下一個新頁面的頂部開始。

> [!NOTE]
> 我們建議您將 **將資料列保持在一起** 選項設定僅適用於跨越產生文件的整個寬度的範圍。
>
> 這 **將資料列保持在一起** 選項僅適用於 **Excel\>檔案** 組件，設定為使用 Excel 活頁簿範本。
>
> **將資料列保持在一起** 選項只能在 **在電子報表架構中啟用 EPPlus 庫使用** 函數已啟用時使用。
>
> 此函數可用於駐留在 **頁面** 組件下方的 **範圍** 組件。 但是，不能保證[頁尾總數](er-paginate-excel-reports.md#add-data-sources-to-calculate-page-footer-totals)透過使用[資料收集](er-data-collection-data-sources.md)資料來源將能正確計算。

若要了解如何使用此選項，請按照[設計 ER 格式以將資料列保持在同一個 Excel 頁面上](er-keep-excel-rows-together.md)中的範例步驟。

### <a name="replication"></a>複寫

**複寫方向** 屬性指定是否以及如何在產生的文件中重複範圍：

- **無複寫** – 產生的文件中不會重複相應的 Excel 範圍。
- **垂直** – 產生的文件中會垂直重複相應的 Excel 範圍。 每個複寫的範圍都將放在 Excel 範本中的原始範圍之下。 重複次數由繫結到此 ER 組件的 **記錄清單** 類型的資料來源中的記錄數定義。
- **水平** – 產生的文件中會水平重複相應的 Excel 範圍。 每個複寫的範圍都將放在 Excel 範本中的原始範圍右側。 重複次數由繫結到此 ER 組件的 **記錄清單** 類型的資料來源中的記錄數定義。

    若要進一步了解有關水平複寫，請按照[使用水平擴展範圍在 Excel 報表中動態新增行列](tasks/er-horizontal-1.md)中的步驟。

### <a name="enabling"></a>啟用

在 ER 作業設計工具的 **對應** 索引標籤上，您可以為 **範圍** 組件設定 **啟用** 屬性，以便指定是否必須將組件放入產生的文件中：

- 如果 **啟用** 屬性的運算式在執行階段設定退回 **True**，或者如果根本沒有設定運算式，則會將相應的範圍放入產生的文件中。
- 如果 **啟用** 屬性的運算式在執行階段設定退回 **False**，並且如果此範圍不代表整資料列或整資料欄，則不會將相應的範圍放入產生的文件中。
- 如果 **啟用** 屬性的運算式在執行階段設定退回 **False**，並且如果此範圍代表整資料列或整資料欄，產生的文件則會包含那些資料列和資料欄作為隱藏的資料列和資料欄。

### <a name="resizing"></a>調整大小

您可以將 Excel 範本設定為使用儲存格來呈現文字資料。 若要確保儲存格中的整個文字在產生的文件中顯示出來，您可以將該儲存格設定為自動將文字自動換行在其中。 您還可以將包含該儲存格的資料列設定為在自動換行不完全可見時自動調整其高度。 如需相關資訊，請參閱[修復儲存格中被截斷的資料](https://support.microsoft.com/office/fix-data-that-is-cut-off-in-cells-e996e213-6514-49d8-b82a-2721cef6144e)中的「儲存格中的自動換行」區段。

> [!NOTE]
> 因為已知的 [Excel 限制](https://support.microsoft.com/topic/you-cannot-use-the-autofit-feature-for-rows-or-columns-that-contain-merged-cells-in-excel-34b54dd7-9bfc-6c8f-5ee3-2715d7db4353)，即使您將儲存格設定為自動換行，並且將包含這些儲存格的資料列設定為自動調整其高度以適合自動換行，您也可能無法使用 **自動調整** 和 **自動換行** Excel 函數來合併儲存格和包含它們的資料列。 

從 Dynamics 365 Finance 10.0.23 版開始，您可以強制 ER 在產生的文件中計算每一行的高度，只要該行包含至少一個設定為自動換行的合併儲存格，就會自動將其高度匹配到巢狀儲存格的內容裡面的文字。 然後使用計算出的高度來調整資料列的大小，以確保資料列中的所有儲存格在產生的文件中都是可見的。 若要在執行任何設定為使用 Excel 範本產生輸出文件的 ER 格式時開始使用此函數，請按照以下步驟。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **電子報表參數**。
3. 在 **電子報表參數** 頁面上，在 **執行階段** 索引標籤，將 **自動調整資料列高** 選項設定 **是**。

如果您想為單個 ER 格式更改此規則，請按照以下步驟更新該格式的草稿版本。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定** 區段中，選取 **報告設定**。
3. 在 **設定** 頁面上，在左側窗格的設定樹狀結構中，選取設計為使用 Excel 範本產生輸出文件的 ER 設定。
4. 在 **版本** FastTab 上，選取狀態為 **草稿** 的設定版本。
5. 在動作窗格上，選取 **設計工具**。
6. 在 **格式設計工具** 頁面上，在左側窗格的格式樹中，選取連結到 Excel 範本的 Excel 組件。
7. 在 **格式** 索引標籤上，在 **調整行高** 欄位中，選取一個值以指定是否應在執行時強制 ER 更改由編輯的 ER 格式產生的輸出文件中的資料列高：

    - **預設** – 使用在 **電子報表參數** 頁面上的 **自動調整資料列高** 欄位中設定的一般設定。
    - **是** – 覆寫一般設定，並在執行時更改資料列高。
    - **否** – 覆寫一般設定，不要在執行時更改資料列高。

## <a name="cell-component"></a>儲存格組件

**儲存格** 組件用於填入 Excel 命名的儲存格、形狀和圖片。 若要指示必須由 **儲存格** ER 組件填入的 Excel 命名物件，您必須在 **儲存格** 組件的 **Excel 範圍** 屬性中指定該物件的名稱。

在 ER 作業設計工具的 **對應** 索引標籤上，您可以為 **儲存格** 組件設定 **啟用** 屬性，以便指定是否必須將物件填入產生的文件中：

- 如果 **啟用** 屬性的運算式在執行階段設定退回 **True**，或者如果根本沒有設定運算式，則會將相應的物件放入產生的文件中。 這個 **儲存格** 組件的繫結程式指定放入相應物件的值。
- 如果 **啟用** 屬性的運算式在執行階段設定返回 **False**，相應的物件將不填入產生的文件中。

當一個 **儲存格** 組件被設定為在儲存格中輸入值，它可以與返回原始資料類型值的資料來源繫結 (例如，**字串**、**實數** 或 **整數**)。 在這種情況下，該值作為相同資料類型的值輸入到儲存格中。

當 **儲存格** 組件被設定為在 Excel 圖形中輸入值，它可以與返回原始資料類型值的資料來源繫結 (例如，**字串**、**實數** 或 **整數**)。 在這種情況下，該值作為該圖形的文字輸入到 Excel 圖形中。 對於不是 **字串** 的資料類型值，文字的轉換是自動完成的。

> [!NOTE]
> 您可以設定 **儲存格** 組件以便僅在支援徒刑文字屬性的情況下填入形狀。

當 **儲存格** 組件被設定為在 Excel 圖片中輸入值，它可以與資料來源繫結，該資料來源返回 **容器** 資料類型的值，代表二進位格式的圖像。 在這種情況下，值作為圖像輸入到 Excel 圖片中。

> [!NOTE]
> 每個 Excel 圖片和形狀都被認為是透過其左上角錨定到特定的 Excel 儲存格或範圍。 如果要複製 Excel 圖片或形狀，則必須將其錨定到的儲存格或區域設定為複制的儲存格或區域。

若要進一步了解如何嵌入圖像和形狀，請參閱[在使用 ER 產生的文件中嵌入圖像和形狀](electronic-reporting-embed-images-shapes.md)。

## <a name="page-break-component"></a>分頁符號組件

**分頁符號** 組件強制 Excel 開始新頁面。 當您想使用 Excel 的預設分頁時，不需要此組件，但當您希望 Excel 遵循您的 ER 格式來構建分頁時，您應該使用它。

## <a name="page-component"></a><a name="page-component"></a>頁面組件

### <a name="overview"></a>概觀

您可以在您希望 Excel 在產生的輸出文件中遵循您的 ER 格式和結構分頁時使用 **頁面** 組件。 當 ER 格式執行位於 **頁面** 組件下方的組件時，自動新增所需的分頁符號。 在此過程中，會考慮產生內容的大小、Excel 範本的頁面安裝以及 Excel 範本中選取的紙張大小。

如果必須將產生的文件拆分成不同的區段，每個區段有不同的分頁，您可以在每個 [工作表](er-fillable-excel.md#sheet-component)組件中設定幾個 **頁面** 組件。

### <a name="structure"></a><a name="page-component-structure"></a>結構

如果 **頁面** 組件下的第一個組件是 [範圍](er-fillable-excel.md#range-component)組件，其中 **複寫方向** 屬性被設定為 **無複寫**，這個範圍被認為是基於現行 **頁面** 組件設定的分頁的頁面標題。 與此格式組件相關的 Excel 範圍在使用現行 **頁面** 組件設定產生的每個頁面的頂部重複。

> [!NOTE]
> 對於正確的分頁，如果 [在頂部重複的資料列](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409)範圍在您的 Excel 範本中設定，此 Excel 範圍的地址必須等於與前面描述的 **範圍** 組件相關的 Excel 範圍的地址。

如果 **頁面** 組件下的最後一個組件是 **範圍** 組件，其中 **複寫方向** 屬性被設定為 **無複寫**，這個範圍被認為是基於現行 **頁面** 組件設定的分頁的頁尾。 與此格式組件相關的 Excel 範圍在使用現行 **頁面** 組件設定產生的每個頁面的底部重複。

> [!NOTE]
> 對於正確的分頁，與 **範圍** 相關的 Excel 範圍不應在執行階段調整組件大小。 我們不建議您使用 **在儲存格中自動換行** 和 **自動調整資料列高** Excel[選項](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84)來格式化儲存格。

您可以在選取性 **範圍** 組件之間新增多個其他 **範圍** 來指定如何填入產生的文件。

如果 **頁面** 組件下方的巢狀 **範圍** 組件集不符合先前描述的結構，驗證[錯誤](er-components-inspections.md#i17)會在 ER 格式設計工具中的設計階段發生。 錯誤訊息通知您該問題可能會導致執行時出現問題。

> [!NOTE]
> 為了產生正確的輸出，如果 **範圍** 組件的 **複寫方向** 屬性被設定為 **無複寫**，並且該範圍被設定為產生頁首或頁尾，則不要為 **頁面** 組件下的任何 **範圍** 組件指定繫結程式。

如果您希望與分頁相關的求和與計數來計算執行總計和每頁總計，我們建議您設定所需的[資料採集](er-data-collection-data-sources.md)資料來源。 若要了解如何使用 **頁面** 組件對產生的 Excel 文件進行分頁，完成[設計 ER 格式以對產生的 Excel 格式的文件進行分頁](er-paginate-excel-reports.md)中的流程。

### <a name="limitations"></a><a name="page-component-limitations"></a>限制

當您使用 Excel 分頁的 **頁面** 組件時，在分頁完成之前，您不會知道產生文件中的最終頁數。 因此，您無法使用 ER 公式計算總頁數，並在最後一頁之前的任何頁面上列印產生文件的正確頁數。

> [!TIP]
> 透過使用頁面頁首和頁尾的特殊 Excel [格式化](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers)在 Excel 頁面頁首或頁尾中實現此結果。

當您更新在 Dynamics 365 Finance 10.0.22 版中可編輯格式的 Excel 範本時，不考慮已設定的 **頁面** 組件。 Finance 的後續版本考慮使用此函數。

如果您將 Excel 範本設定為使用[條件格式](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting)，在某些情況下它可能無法按預期工作。

### <a name="applicability"></a>適用性

僅當組件設定為使用 Excel 中的範本時，**頁面** 組件才適用於[Excel 檔案](er-fillable-excel.md#excel-file-component)格式化組件。 如果您用 Word 範本 [取代](tasks/er-design-configuration-word-2016-11.md) Excel 範本，然後執行可編輯的 ER 格式，**頁面** 組件將被忽略。

**頁面** 組件只能在 **在電子報表架構中啟用 EPPlus 庫使用** 函數已啟用時使用。 如果 ER 試圖在該函數被禁用時處理 **頁面** 組件，則會在執行階段出現例外狀況。

> [!NOTE]
> 如果 ER 格式處理 Excel 範本的 **頁面** 組件，其中至少有公式指向無效的儲存格，則在執行階段引發例外狀況。 若要幫助防止執行階段錯誤，請按照[如何修正 #REF! 錯誤](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be)中所述修復 Excel 範本。

## <a name="footer-component"></a>頁尾組件

**頁尾** 組件用於填入 Excel 活頁簿中產生的工作表底部的頁尾。

> [!NOTE]
> 您可以為每個 **工作表** 組件新增這個組件，以便為產生的 Excel 活頁簿中的不同工作表指定不同的頁尾。

當您設定個人 **頁尾** 組件，您可以使用 **頁首/頁尾外觀** 屬性來指定組件用於的頁面。 以下提供的值：

- **任何** - 為父系 Excel 工作表的任何一頁執行設定的 **頁尾** 組件。
- **首先** - 只對父系 Excel 工作表的第一頁執行設定好的 **頁尾** 組件。
- **偶數** - 只對父系 Exce l工作表的偶數頁執行設定的 **頁尾** 組件。
- **奇數** - 只對父系 Excel 工作表的奇數頁執行設定的 **頁尾** 組件。

對於單 **工作表** 組件，您可以新增幾個 **頁尾** 組件，每個組件對 **頁首/頁尾外觀** 屬性都有不同的值。 這樣，您可以在 Excel 工作表中為不同類型的頁面產生不同的頁尾。

> [!NOTE]
> 確保您新增到單個 **工作表** 組件的每個 **頁尾** 組件都有一個不同的 **頁首/頁尾外觀** 屬性值。 否則，就會發生[驗證錯誤](er-components-inspections.md#i16)。 您收到的錯誤訊息會通知您發生不一致性。

在新增的 **頁尾** 組件下，新增 **文字\\字串** 的所需巢狀組件、**文字\\日期時間**，或其他類型。 為這些組件設定繫結以指定頁尾的填入方式。

您也可以使用特殊的[格式化代碼](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers)正確格式化產生頁尾的內容。 若要了解如何使用此方法，請按照[範例 1](#example-1)，稍後會出現在本主題中。

> [!NOTE]
> 在設定 ER 格式時，請務必考慮 Excel[限制](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3)以及單個頁首或頁尾的最大字元數。

## <a name="header-component"></a>標題組件

**標題** 組件用於填入 Excel 活頁簿中產生的工作表頂部的標題。 它用起來像 **頁尾** 組件。

## <a name="edit-an-added-er-format"></a>編輯新增的 ER 格式

### <a name="update-a-template"></a>更新範本

您可以在動作窗格的 **匯入** 索引標籤上選取 **從 Excel 更新**，將更新的範本匯入可編輯的ER格式。 在此過程中，選定 **Excel\\檔案** 組件的範本將被新範本替換。 可編輯 ER 格式的內容將與更新的 Excel 範本的內容同步。

- 如果在可編輯格式中未找到 ER 格式組件，將為每個 Excel 名稱自動建立一個新的 ER 格式組件。
- 如果找不到合適的 Excel 名稱，每個 ER 格式組件都將從可編輯的 ER 格式中刪除。

> [!NOTE]
> 如果您想在可編輯的 ER 格式中建立選取性的 **工作表** 元素，將 **建立 Excel 工作表元素** 選項設為 **是**。
>
> 如果可編輯的 ER 格式最初包含 **工作表** 元素，我們建議您在匯入更新的範本時將 **建立 Excel 工作表元素** 選項設為 **是**。 否則，原始 **工作表** 元素的所有巢狀元素將從頭開始建立。 因此，重新建立的格式元素的所有繫結都將在更新的 ER 格式中遺失。

![在從 Excel 更新對話方塊中的建立 Excel 工作表格式元素選項。](./media/er-excel-format-update-template.png)

若要進一步了解此函數，請按照[透過重新套用 Excel 範本修改電子報表格式](modify-electronic-reporting-format-reapply-excel-template.md)中的步驟。

## <a name="validate-an-er-format"></a>驗證 ER 格式

當您驗證可編輯的 ER 格式時，會進行一致性檢查以確保 Excel 名稱存在於現行使用的 Excel 範本中。 您將收到任何不一致的通知。 對於某些不一致，將提供自動修復問題的選項。

![驗證錯誤訊息。](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>控制 Excel 公式的計算

當輸出文件在 Microsoft Excel 活頁簿格產生後，此文件的某些儲存格可能包含 Excel 公式。 當 **在電子報表架構中啟用 EPPlus 庫** 函數已啟用，並且該公式透過更改在使用中 Excel 範本中的 **計算選項**[參數](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows)的值計算時，您就可以控制：

- 選取 **自動化**，在每次產生的文件被新的範圍、儲存格等新增時，重新計算所有相關的公式。

    > [!NOTE]
    > 這可能會導致包含多個相關公式的 Excel 範本出現校稜問題。

- 選取 **手動** 以避免在產生文件時重新計算公式。

    > [!NOTE]
    > 當使用 Excel 打開產生的文件進行預覽時，手動強制重新計算公式。
    > 如果您設定的 ER 目標假定使用產生的文件而不在 Excel 中預覽 (PDF 轉換、電子郵件等)，請不要使用此選項，因為產生的文件可能不包含包含公式的儲存格中的值。

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>範例 1：格式化頁尾內容

1. 使用提供的 ER 設定[產生](er-generate-printable-fti-forms.md)可列印的普通發票 (FTI) 文件。
2. 查看產生文件的頁尾。 請注意，它包含有關現行頁碼和文件總頁數的資訊。

    ![查看產生的 Excel 格式文件的頁尾。](./media/er-fillable-excel-footer-1.gif)

3. 在 ER 格式設計工具中，[開起](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format)用於審查的樣本 ER 格式。

    **發票** 工作表的頁尾是根據位於 **頁尾** 組件下的兩個 **字串** 組件的設定產生的。

    - 第一個 **字串** 組件填入以下特殊格式代碼以強制 Excel 套用特定格式：

        - **＆C** – 將頁尾文字居中對齊。
        - **&"Segoe UI,Regular"&8** – 在 "Segoe UI Regular" 中出現的頁尾文字，字型大小為 8 。

    - 第二個 **字串** 組件填入包含現行頁碼和現行文件總頁數的文字。

    ![在格式設計工具頁面上審閱頁尾 ER 格式組件。](./media/er-fillable-excel-footer-2.png)

4. 自訂範例 ER 格式以修改現行頁尾：

    1. [建立](er-quick-start2-customize-report.md#DeriveProvidedFormat)衍生的 **普通發票 (Excel) 自訂** ER 格式，以樣本 ER 格式為主。
    2. 新增第一對新 **字串** 組件為 **發票** 工作表的 **頁尾** 組件：

        1. 新增 **字串** 使公司名稱在左側對齊並以大小 8 的 "Segoe UI Regular" 字型 (**"&L&"Segoe UI,Regular"&8"**) 顯示。
        2. 新增 **字串** 填入公司名稱的組件 (**model.InvoiceBase.CompanyInfo.Name**)。

    3. 新增第二對新 **字串** 組件為 **發票** 工作表的 **頁尾** 組件：

        1. 新增 **字串** 使處理中的資料靠右側對齊並以大小 8 的 "Segoe UI Regular" 字型 (**"&R&"Segoe UI,Regular"&8"**) 顯示。
        2. 新增 **字串** 以自訂格式填入處理日期的組件 (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "yyyy-MM-dd")**)。

        ![在格式設計工具頁面上審閱頁尾 ER 格式組件。](./media/er-fillable-excel-footer-3.png)

    4. **普通發票 (Excel) 自訂** ER 格式的[完整](er-quick-start2-customize-report.md#CompleteDerivedFormat)衍生的草稿版本。

5. [設定](er-generate-printable-fti-forms.md#configure-print-management)列印管理來使用衍生的 **普通發票 (Excel) 自訂** ER 格式而不是樣本 ER 格式。
6. 產生可列印的 FTI 文件，並查看產生的文件的頁尾。

    ![查看產生的 Excel 格式文件的頁尾。](./media/er-fillable-excel-footer-4.gif)

## <a name="example-2-fixing-the-merged-cells-epplus-issue"></a><a name="example-2"></a>範例 2：修復合併儲存格 EPPlus 問題

您可以執行 ER 格式以產生 Excel 活頁簿格式的輸出文件。 當 **在電子報表架構中啟用 EPPlus 庫** 函數在 **函數管理** 工作區啟用時，[EPPlus 庫](https://www.nuget.org/packages/epplus/4.5.2.1)會用於製作 Excel 輸出。 然而，由於已知[Excel 行為](https://answers.microsoft.com/msoffice/forum/all/deleting-a-range-of-cells-that-includes-merged/8601462c-4e2c-48e0-bd23-848eecb872a9)以及 EPPlus 庫的限制，您可能會遇到以下例外狀況：「無法刪除/覆寫合併的儲存格。 一個範圍與另一個合併的範圍部分合併。」 若要了解哪種 Excel 範本可能導致此例外狀況以及如何解決此問題，請完成以下範例。

1. 在 Excel 桌面套用程式中，建立一個新的 Excel 活頁簿。
2. 在工作表 **Sheet1** 上，為儲存格 **A2** 新增 **ReportTitle** 名稱。
3. 合併儲存格 **A1** 和 **A2**。

    ![在 Excel 桌面套用程式中查看在設計的 Excel 工作簿中合併儲存格 A1 和 A2 的結果。](./media/er-fillable-excel-example2-1.png)

3. 在 **設定** 頁面上，[新增新的 ER 格式](er-fillable-excel.md#add-a-new-er-format)來產生 Excel 工作簿格式的輸出文件。
4. 在 **格式設計工具** 頁面上，將設計好的 Excel 活頁簿[匯入](er-fillable-excel.md#template-import)至新增的 ER 格式，作為輸出文件的新範本。
5. 在 **對應** 索引標籤，為 [儲存格](er-fillable-excel.md#cell-component)類型的 **ReportTitle** 組件設定繫結。
6. 執行設定的 ER 格式。 請注意，引發了以下例外狀況：「無法刪除/覆寫合併的儲存格。 一個範圍與另一個合併的範圍部分合併。」

    ![在格式設計工具頁面上查看執行設定的 ER 格式的結果。](./media/er-fillable-excel-example2-2.png)

您可以透過以下任一方式解決此問題：

- **更簡單但不推薦：** 在 **函數管理** 工作區中，關閉 **在電子報表架構中啟用 EPPlus 庫** 函數。 雖然這種方法更簡單，但如果使用它，您可能會遇到其他問題，因為某些 ER 函數僅在 **在電子報表架構中啟用 EPPlus 庫** 函數已啟用時支援。
- **建議。** 請遵循以下步驟：

    1. 在 Excel 桌面套用程式中，通過以下方式之一修改 Excel 活頁簿：

        - 在工作表 **Sheet1** 上，取消合併儲存格 **A1** 和 **A2**。
        - 將 **ReportTitle** 名稱的參考從 **=Sheet1!$A$2** 更改到 **=Sheet1!$A$1**。

        ![在 Excel 桌面套用程式中審查更改所設計的 Excel 活頁簿中的參考資料的結果。](./media/er-fillable-excel-example2-3.png)

    2. 在 **格式設計工具** 頁面上，將修改後的 Excel 活頁簿[匯入](er-fillable-excel.md#template-import)至為可編輯的 ER 格式以更新現有範本。
    3. 執行修改好的 ER 格式。

        ![在 Excel 桌面套用程式中查看產生的文件。](./media/er-fillable-excel-example2-4.png)

## <a name="limitations"></a>限制

### <a name="known-epplus-library-limitations"></a>已知的 EPPlus 庫限制

#### <a name="external-data-sources"></a>外部資料資料來源

如果您的一個範本包含一個基於 PowerPivot 模型的 PivotTable，該模型參考了 [外部資料來源](https://support.microsoft.com/office/create-a-pivottable-with-an-external-data-source-db50d01d-2e1c-43bd-bfb5-b76a818a927b)，並且 **在電子報表架構中啟用 EPPlus 庫的使用方式** 函數，當您執行使用該範本產生 Excel 格式的輸出文件的 ER 格式時，您會收到以下錯誤訊息：「快取來源不是一個工作表。」 若要解決此問題，您有以下選項：

- **建議：** 重新設計您正在使用的 Excel 解決方案：

    1. 在單獨的 Excel 活頁簿 (活頁簿 A) 中隔離包含樞軸的部分。 
    2. 使用 ER 從 Finance 產生具有所需詳情的第二個 Excel 活頁簿 (活頁簿 B)。 
    3. 產生活頁簿 B 後立即參考活頁簿 A 中的活頁簿 B。

- 關閉該函數，**在電子報表架構中啟用 EPPlus 庫** 來使用 EPPlus 以外的選項。 

## <a name="additional-resources"></a>其他資源

[電子報表概述](general-electronic-reporting.md)

[設計用於產生 OPENXML 格式報告的設定](tasks\er-design-reports-openxml-2016-11.md)

[透過重新套用 Excel 範本修改電子報表格式](modify-electronic-reporting-format-reapply-excel-template.md)

[使用水平擴展範圍在 Excel 報表中動態新增資料欄](tasks/er-horizontal-1.md)

[在使用 ER 產生的文件中嵌入圖像和形狀](electronic-reporting-embed-images-shapes.md)

[設定電子報表 (ER) 以將資料提取到 Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
