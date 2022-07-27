---
title: 設定 ER 格式以使用每個法律實體指定的參數
description: 本主題說明如何設定電子報表 (ER) 格式以使用為每個法律實體指定的參數。
author: NickSelin
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 2bf4d1ecad3e25299df7c87ffa2236736ddcac300a5ded779616b25920745d7e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460253"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>設定 ER 格式以使用每個法律實體指定的參數

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>概觀

在您將設計的許多電子報表 (ER) 格式中，您必須使用一組特定於您的實體的每個法律實體的值來過濾資料 (例如，用於過濾稅務交易的稅碼)。 現行，當以 ER 格式設定該類型的過濾時，在 ER 格式的運算式中使用依賴於法律實體的值 (例如，稅碼) 來指定資料過濾規則。 因此，ER 格式是法律實體專用的，並且要產生所需的報告，您必須為必須執行 ER 格式的每個法律實體建立原始 ER 格式的衍生副本。 每個衍生的 ER 格式都必須編輯，以便將特定於法律實體的值帶入其中、每當更新原始 (基本) 版本時重新設定基礎、從測試環境中匯出，並在必須部署以供生產使用時匯入到生產環境中等。 因此，這種類型的已設定 ER 解決方案的維護既複雜又耗時，原因如下：

-   法律實體越多，必須維護的 ER 格式設定就越多。
-   ER 設定的維護要求業務使用者具有 ER 知識。

ER 應用程式專用參數函數讓函數強大的使用者能夠以 ER 格式設定資料過濾，以便能夠參考一組抽象規則。 這組規則可以設定為使用以 ER 格式提供的資料來源。 然後，商務使用者可以使用基於相應 ER 格式的設定和將由 ER 格式資料來源存取的現行法律實體資料自動產生的使用者界面 (UI) 來指定 ER 架構之外的真實規則。 為 ER 格式指定的規則集可以從 Dynamics 365 Finance (Finance) 實體的現行法律實體匯出。 然後可以將其作為相同 ER 格式的一組規則匯入同一 Finance 實體或不同實體的另一個法律實體。

## <a name="prerequisites"></a>先決條件

若要完成本主題中的範例，您必須擁有對 Regulatory Configuration Services (RCS) 實體的存取權限，該實體已為 Finance 的同一租使用者設定了以下角色之一。

- 電子報表開發人員
- 電子報表函數
- 系統管理員

我們建議您完成[支援導出欄位類型之 ER 資料來源的參數化調用](er-calculated-field-type.md)主題中的步驟。 如果您已經完成了這些步驟，則可以跳過以下 **將 ER 設定匯入 RCS** 區段中的步驟。

## <a name="import-er-configurations-into-rcs"></a>將 ER 設定匯入 RCS

下載並在本地儲存以下 ER 設定。

| **內容描述**                        | **檔案名稱**                                        |
|------------------------------------------------|------------------------------------------------------|
| 樣本 **ER 資料模型** 設定檔案    | [學習已參數化調用的模型.版本.1.xml](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| 樣本 **ER 中繼資料** 設定檔      | [學習已參數化調用的中繼資料.版本.1.xml](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| 樣本 **ER 模型對應** 設定檔 | [學習已參數化調用的對應.版本.1.1.xml](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| 樣本 **ER 格式** 設定             | [學習已參數化調用的格式.版本.1.1.xml](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

下一步，登入到您的 RCS 執行個體。

在這個範例中，您將為 Litware, Inc 的樣本公司建立設定。 在完成這個程序之前，您必須完成 RCS 中[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)主題中的步驟。

1.  在預設儀表板上，選取 **電子報表**。
2.  選取 **報表設定**。
3.  按以下順序將您之前下載的 ER 設定匯入 RCS：資料模型、中繼資料、模型對應和格式。 對於每個 ER 設定，請執行以下步驟：

    1.  選取 **Exchange**。
    2.  選取 **從 XML 文件載入**。
    3.  選取 **瀏覽** 為 XML 格式的 ER 設定選取所需的檔案。
    4.  選取 **確定**。

## <a name="review-the-er-solution-that-is-provided"></a>查看提供的 ER 解決方案

1.  在設定樹狀結構中，展開 **學習已參數化調用的模型** 項目。
2.  選取 **學習已參數化調用的格式** 項目。
3.  選取 **設計工具**。
4.  選取 **展開/折疊**。

    **學習已參數化調用的格式** ER 格式旨在產生 XML 格式的稅收報表，該報表呈現多個稅收級別 (一般、減稅和無)。 每個級別都有不同數量的細節。

    ![ER 格式的多級別，學習已參數化調用的格式。](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  在 **對應** 索引標籤、展開 **模型**、**資料**，和 **摘要** 項目。

    **Model.Data.Summary** 資料來源返回稅務交易清單。 這些交易按稅碼匯總。 如需這個資料來源，**Model.Data.Summary.Level** 導出欄位已設定為返回每個匯總記錄的稅收級別的代碼。 對於任何可以在執行階段從 **Model.Data.Summary** 資料來源中擷取到的稅收代碼，導出欄位將稅收級別代碼 (**一般**、**減稅**、**無** 或 **其他**) 作為文字值返回。 將 **Model.Data.Summary.Level** 導出欄位用於過濾 **Model.Data.Summary** 資料來源的記錄，並透過 **Model.Data2.Level1**、**Model.Data2.Level2** 和 **Model.Data2.Level3** 欄位，將過濾後的資料登入每個代表稅收級別的 XML 元素中。

    ![稅務交易的 Model.Data.Summary 資料來源清單。](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    **Model.Data.Summary.Level** 導出欄位已設定好以便包含 ER 運算式。 將稅碼 (**VAT19**、**InVAT19**、**VAT7**、**InVAT7**、**THIRD**，和 **InVAT0**) 寫碼到這個設定中。 因此，此 ER 格式取決於設定這些稅碼的法律實體。

    ![帶有寫死稅碼的 Model.Data.Summary.Level 導出欄位。](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    若要為每個法律實體支援一組不同的稅碼，您必須執行以下步驟：

    - 為每個法律實體建立 ER 格式的衍生版本。
    - 根據法律實體設定，更新 **Model.Data.Summary.Level** 導出欄位中的稅收代碼。

6.  關上 **格式設計工具** 頁面。

## <a name="create-a-derived-format"></a>建立衍生格式

接下來，您將使用 ER 應用程式專用參數函數來支援單個 ER 格式的每個法律實體的不同稅碼集。

1.  在設定樹狀結構中，展開 **學習已參數化調用的模型** 項目。
2.  選取 **學習已參數化調用的格式** 項目。
3.  選取 **建立設定**。
4.  選取 **源自名稱：學習已參數化調用的格式，Microsoft** 選項。
5.  在 **名稱** 欄位中，輸入 **Format to learn how to lookup LE data**。
6.  選取 **建立設定**。

## <a name="configure-a-derived-format"></a>設定衍生格式

### <a name="add-a-format-enumeration"></a>增加格式列舉

接下來，您將新增新的 ER 格式列舉。 此格式列舉值將提供給商務使用者，他們將為 ER 格式中使用的各種稅收級別指定與法律實體相關的稅碼集。

1.  選取 **設計工具**。
2.  選取 **格式列舉**。
3.  選取 **新增**。
4.  在 **名稱** 欄位中，輸入 **List of taxation levels**。
5.  選取 **儲存**。
6.  在 **格式列舉值** 索引標籤，選取 **新增**。
7.  在 **名稱** 欄位，輸入 **Regular taxation**。
8.  請再選取一次 **新增**。
9.  在 **名稱** 欄位，輸入 **Reduced taxation**。
10. 請再選取一次 **新增**。
11. 在 **名稱** 欄位，輸入 **No taxation**。
12. 請再選取一次 **新增**。
13. 在 **名稱** 欄位中，輸入 **Other**。

    ![格式列舉頁面上的新記錄。](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    由於商務使用者可能使用不同的語言來指定法律實體相關的稅碼集，我們建議您將此列舉的值翻譯成在 Finance 中設定為這些使用者的偏好的語言。

14. 選取 **不徵稅** 記錄。
15. 點選 **標籤** 欄位。
16. 選取 **翻譯**。
17. 在 **文字翻譯** 窗格中，在 **標籤 ID** 欄位，輸入 **LBL_LEVELENUM_NO**。
18. 在 **預設語言的文字** 欄位，輸入 **No taxation**。
19. 在 **語言** 欄位，選取 **DE**。
20. 在 **已翻譯文字** 欄位中，輸入 **keine Besteuerung**。
21. 選取 **翻譯**。

    ![文字翻譯滑出。](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. 選取 **儲存**。
23. 關閉 **格式列舉** 頁。

### <a name="add-a-new-lookup-data-source"></a>新增新的查找資料來源

接下來，您將新增新資料來源，以指定業務使用者如何指定法律實體相關規則，以識別每個匯總交易記錄的正確稅收級別。

1.  在 **對應** 索引標籤上，選取 **新增**。
2.  選取 **格式列舉\查找**。

    您剛剛發現業務使用者為稅收級別識別指定的每個規則都將返回 ER 格式列舉值。 請注意，除了 **格式列舉** 塊之外，還可以在 **資料模型** 和 **Dynamics 365 for Operations** 塊下存取 **查找** 資料來源類型。 因此，ER 資料模型列舉和應用程式列舉可用於指定為該類型的資料來源返回的值的類型。 若要進一步了解 **查找** 資料來源，請參閱[設定查找資料來源以使用 ER 應用程式特定參數函數](er-lookup-data-sources.md)。
    
3.  在 **名稱** 欄位中，輸入 **Selector**。
4.  在 **格式列舉** 欄位中，選取 **稅收級別清單**。

    您規定，對於在此資料來源中指定的每個規則，商務使用者必須選取 **稅收級別清單** 格式列舉中的一個值作為返回值。
    
5.  選取 **編輯查找**。
6.  選取 **資料欄**。
7.  展開 **模型** 項目。
8.  展開 **資料** 項目。
9.  展開 **稅金** 項目。
10. 選取 **Model.Data.Tax.Code** 項目。
11. 選取 **新增** 按鈕 (向右箭頭)。

    ![資料欄滑出。](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    您剛規定，對於這個資料來源中指定的每一條用於稅收級別確認的規則，商務使用者必須選取其中一個稅收代碼作為條件。 商務使用者可以選取的稅收代碼清單將由 **Model.Data.Tax** 資料來源返回。 因為這個資料來源包含 **名稱** 欄位中，稅碼的名稱將針對呈現給業務使用者的查找中的每個稅碼值顯示。
    
12. 選取 **確定**。

    ![查找設計工具頁面。](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    業務使用者可以新增多個規則作為該資料來源的記錄。 每條記錄將由行列代碼編號。 規則將按照行號遞增的順序進行評估。

    因為您在這個查找資料來源中選取了 **稅收代碼** 欄位作為規則的條件，而且將 **稅收代碼** 設定為 **字串** 資料型別的欄位，每個規則將在執行階段透過比較傳遞到資料來源的稅收代碼和資料來源的這個記錄中定義的稅收代碼來進行評估。

    當找到一個滿足設定條件的規則時，這個資料來源會返回在 **查找結果** 欄位中定義的規則的查找值。 如果沒有找到規則，則引發異常通知使用者現行資料來源不能返回正確的值。

13. 選取 **儲存**。
14. 關上 **查找設計工具** 頁面。
15. 選取 **確定**。

    請注意，您新增了一個新的資料來源，對於任何作為 **字串** 資料類型的 **代碼** 參數的參數傳遞給資料來源的稅收代碼，它將返回作為 **稅務級別清單** 格式列舉的值的稅收水準。
    
    ![使用新資料來源格式化設計工具頁面。](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    已設定規則的評估取決於為定義這些規則的條件而選取的欄位的資料類型。 當您選取被設定為 **數字** 或 **日期** 資料類型的欄位時，標準將與前面描述的 **字串** 資料型別的標準不同。 如需 **數字** 和 **日期** 欄位，規則必須指定為一個值範圍。 當傳遞給資料來源的值在設定的範圍內時，規則的條件將被視為滿足。
    
    下圖顯示了此安裝類型的範例。 除了 **Model.Data.Tax.Code** 欄位的 **字串** 資料類型外，將 **實數** 資料類型的 **Model.Tax.Summary.Base** 欄位用來指定查找資料來源的條件。
    
    ![帶有附加資料欄的查找設計工具頁面。](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    因為 **Model.Data.Tax.Code** 和 **Model.Tax.Summary.Base** 欄位被選定為這個查找資料來源，這個資料來源的每個規則將被設定為以下方式。
    
    -   在顯示的清單中，**稅收級別清單** 必須選取格式列舉作為返回值。
    -   必須輸入稅碼作為此規則的條件。 只有 **Model.Data.Tax** 資料來源提供的稅收代碼才適用。
    -   必須輸入稅基金額的最小值和最大值作為此規則的條件。

    以下是在執行階段評估此資料來源的每個規則的方式：
    -   傳遞給這個資料來源的 **字串** 資料型別的代碼是否等於一個規則的稅收代碼？
    -   傳遞給這個資料來源的 **實數** 資料類型的值是否在特定的最小和最大值之間？

    當兩個條件都滿足時，規則將被視為適用。

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>翻譯新增的查找資料來源的標籤

由於商務使用者可能使用不同的語言來指定依賴於法律實體的稅收代碼集，我們建議您翻譯您新增的任何查找資料來源的標籤，以便在相應的頁面上以每個使用者的偏好語言呈現。

1.  選取 **Model.Data.Selector** 資料來源。
2.  選取 **編輯**。
3.  點選 **標籤** 欄位。
4.  選取 **翻譯**。
5.  在 **文字翻譯** 窗格中，在 **標籤 ID** 欄位，輸入 **LBL_SELECTOR_DS**。
6.  在 **預設語言的文字** 欄位，輸入 **Select tax level by tax code**。
7.  在 **語言** 欄位，選取 **DE**。
8.  在 **翻譯文字** 欄位，輸入 **Steuerebene für Steuerkennzeichen auswählen**。
9.  選取 **翻譯**。
10. 選取 **確定**。

    ![資料來源屬性滑出。](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>新增新欄位以使用設定的查找

1.  展開 **Model.Data** 項目。
2.  選取 **Model.Data.Summary** 項目。
3.  選取 **新增**。
4.  選取 **函數/導出欄位**。
5.  在 **名稱** 欄位中，輸入 **LevelByLookup**。
6.  選取 **編輯公式**。
7.  在 **公式欄位** 中，輸入 **Model.Selector(Model.Data.Summary.Code)**。
8.  選取 **儲存**。

    ![將 Model.Selector(Model.Data.Summary.Code) 新增到公式設計工具頁面。](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  關上 **公式編輯器** 頁面。
10. 選取 **確定**。

    ![使用新增的公格式化設計工具頁面。](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    注意，您新增的 **LevelByLookup** 導出欄位將返回稅收級別，作為每個匯總的稅收交易記錄的 **稅收級別清單** 格式列舉的值。 記錄的稅收代碼將被傳遞給 **Model.Selector** 查找資料來源，該資料來源的一套規則將被用於選取正確的稅收級別。

### <a name="add-a-new-format-enumeration-based-data-source"></a>新增新的基於格式列舉的資料來源

接下來，您將新增一個參考您之前新增的格式列舉的新資料來源。 稍後將在 ER 格式運算式中使用此資料來源的值。

1.  選取 **新增根**。
2.  選取 **格式列舉\查找**。
3.  在 **名稱** 欄位中，輸入 **TaxationLevel**。
4.  在 **格式列舉** 欄位中，選取 **稅收級別清單**。
5.  選取 **儲存**。

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a>修改現有欄位以開始使用查找

接下來，您將修改現有的計算欄位，使其使用設定的查找資料來源返回正確的稅級值，具體取決於稅碼。

1.  選取 **Model.Data.Summary.Level** 項目。
2.  選取 **編輯**。
3.  選取 **編輯公式**。

    請注意，現行的運算式 **Model.Data.Summary.Level** 欄位包括以下寫死稅碼：
    
    CASE (@.Code, "VAT19", "Regular", "InVAT19", "Regular", "VAT7", "Reduced", "InVAT7", "Reduced", "THIRD", "None", "InVAT0", "None", "Other")

4.  在 **公式** 欄位中，輸入 **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Regular", TaxationLevel.'Reduced taxation', "Reduced", TaxationLevel.'No taxation', "None", "Other")**。

    ![ER 作業設計工具頁面。](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    注意，**Model.Data.Summary.Level** 欄位的運算式現在將返回稅收級別，基於現行記錄的稅收代碼和業務使用者在 **Model.Data.Selector** 查找資料來源中設定的一套規則。
    
5.  選取 **儲存**。
6.  關閉 **公式設計工具** 頁面。
7.  選取 **確定**。
8.  選取 **儲存**。
9.  關閉 **格式設計工具** 頁面。

## <a name="complete-the-draft-version-of-a-derived-format"></a>完成衍生格式的草稿版本

1.  在 **版本** FastTab 上，選取 **更改狀態**。
2.  選取 **完成**。
3.  選取 **確定**。

## <a name="export-completed-version-of-modified-format"></a>導出修改格式的完成版本

1.  在設定樹狀結構中，選取 **學習如何查找 LE 資料的格式** 項目。
2.  在 **版本** FastTab 上，選取有 **已完成** 狀態的記錄。
3.  選取 **Exchange**。
4.  選取 **導出為 XML 檔案**。
5.  選取 **確定**。
6.  網路瀏覽器下載 **學習如何查找 LE 資料的格式.xml** 檔案。 將此檔案儲存在本地。

對 **學習如何查找 LE 資料** 的格式的父項重複本節中的步驟，並將以下檔儲存在本地。

-   學習已參數化調用的格式.xml
-   學習已參數化調用的對應.xml
-   學習已參數化調用的模型.xml

若要學習如何使用設定好的 **學習如何查找 LE 資料的格式** ER 格式來設定與法律實體相關的稅收代碼集，以按不同的稅收水準過濾稅收交易，請完成[為每個法律實體設定 ER 格式的參數](er-app-specific-parameters-set-up.md)主題中的步驟。

## <a name="additional-resources"></a>其他資源

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[為每個法律實體設定 ER 格式的參數](er-app-specific-parameters-set-up.md)

[設定查找資料來源以使用 ER 應用程式特定參數函數](er-lookup-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
