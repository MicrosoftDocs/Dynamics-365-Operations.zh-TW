---
title: 設計生產現場執行介面
description: 本主題說明如何設定表單控件，以便將預設的生產現場執行樣式套用至表單控件。
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: ef39dc6414f0afdadd4a4b5a41e1fb1fe60e4974
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449475"
---
# <a name="style-the-production-floor-execution-interface"></a>設計生產現場執行介面

[!include [banner](../includes/banner.md)]

本主題說明如何設定表單控件，以便將預設的生產現場執行樣式套用至表單控件。

## <a name="forms-and-dialogs"></a>表單和對話方塊

只有符合以下條件，才能將樣式套用至表單或對話方塊：

- 如果表單需要仿照現有的報告進度表單，則表單或對話方塊的名稱必須以「`JmgProductionFloorExecutionCustomInputDialog`」作為開頭。 
- 表單或對話方塊可以包含詳細資料表單部分。 若要對其套用樣式，詳細資料表單部分的名稱必須以「`JmgProductionFloorExecutionCustomDetailsDialog`」作為開頭。
- 如果表單或對話方塊需要有一個簡易視圖，則簡易視圖的名稱必須以「`JmgProductionFloorExecutionCustomDialog`」作為開頭。 具有簡易視圖的表單範例包括啟動表單和間接活動表單。
- 對話方塊中的所有控件都必須按照本主題中的說明進行設定。

> [!IMPORTANT]
> 此清單前兩個項目符號中提到的功能必須使用 Supply Chain Management 10.0.19 或更新版本。

只有符合以下條件，才能將樣式套用至對話方塊中的 **確定** 按鈕：

- 按鈕包含在表單群組中。
- 群組名稱以「`OkButtonGroup`」作為開頭。

只有符合以下條件，才能將樣式套用至對話方塊中的 **取消** 按鈕：

- 按鈕包含在表單群組中。
- 群組名稱以「`CancelButtonGroup`」作為開頭。

### <a name="header"></a>頁首

下圖顯示典型的表單或對話方塊標題。

![典型的表單或對話方塊標題。](media/pfe-styles-header.png "典型的表單或對話方塊標題")

在 Visual Studio 中，標題是使用與下圖所示類似的結構建立。

![建立標題的典型程式碼結構。](media/pfe-styles-header-code-structure.png "建立標題的典型程式碼結構")

若要將文字新增到標題中，請使用下列範例中的程式碼。

```xpp
private void setCaption()
{
    HeaderFieldWithSeparatorText1.text("Report Progress");
    HeaderFieldWithSeparatorText2.text(ProdId);

    …

    HeaderFieldText.text(OprNum);
}
```

編寫標頭程式碼時，請採用以下規則：

- 主要群組的名稱必須是「`TableRowHeaderGroup`」。
- 每個文字塊 (由項目符號分隔) 必須以「`HeaderFieldWithSeparatorText`」作為開頭。
- 最後的文字名稱必須以「`HeaderFieldText`」作為開頭。
- 可以略過「`CaptionImage`」。

### <a name="progress-indicator"></a>進度指示器

您可以加入進度指示器，將其顯示在標題右側。 下圖顯示一個進度指示器。

![典型的進度指示器。](media/pfe-styles-header-progress.png "典型的進度指示器")

若要顯示進度指示器，則必須將文字欄位命名為「`ShowProgress`」。

## <a name="grid"></a>方格

系統會自動套用樣式。 不需要特別特定。

網格應該有 `TabularView` 樣式，而且必須覆寫自訂表單上的 `run()` 方法，因為系統尚未支援新網格。 新增以下程式碼。

```xpp
public void run()
{
    super();
    // To opt out a page from the new grid
    this.forceLegacyGrid();
}
```

若要在主要視圖中重新整理資料，您可能需要在動作的 `click` 方法中使用類似 `this.parmParentForm().updateLayout();` 的程式碼。 (例如，查看 `JmgProductionFloorExecutionReportFeedbackAction` 類別。) 只要確保新表單 (`formCaller.parmDataSource(this.dataSource(1));`) 的 `init` 方法中已設定 `parmDataSource`。 例如，查看 `JmgProductionFloorExecutionMainGrid` 表單。

## <a name="card-view"></a>卡片檢視

只有符合以下條件，才能將樣式套用至卡片檢視控件：

- 每個卡片檢視都包含在一個表單群組中。
- 群組名稱以「`CardGroup` (例如：`CardGroupJobsView`)」作為開頭。

下圖顯示沒有內含控件的卡片檢視。

![沒有元素的卡片檢視。](media/pfe-styles-empty-card.png)

下圖顯示內含控件的卡片檢視。

![包含顯示 Hz 元素的卡片。](media/pfe-styles-elements.png)

![包含維護要求元素的卡片。](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>商用名片

只有符合以下條件，才能將樣式套用至商用名片：

- 每個商用名片都包含在一個表單群組中。
- 群組名稱以「`BusinessCardGroup` (例如：`BusinessCardGroupJobsList`)」作為開頭。

請在商用名片上設定以下屬性：

- **樣式：** *list*
- **擴充樣式：** *cardList*
- **多個選擇：** *No*
- **顯示列標籤：** *No*

![商用名片。](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>選項按鈕

只有符合以下條件，才能將樣式套用至選項按鈕：

- 每個選項按鈕都包含在表單群組中。
- 群組名稱以「`RadioTextBelow`」或「`RadioTextRight`」作為開頭，實際取決於您想要顯示文字的位置。

請在選項按鈕上設定以下屬性：

- **切換按鈕：** *Check*
- **切換值：** *On* (如果應選擇選項按鈕)；否則請設為 *Off*

下圖是文字顯示在選項按鈕下方的範例。

![下面包含文字的選項按鈕。](media/pfe-styles-radio-text-below.png)

下圖是文字顯示在選項按鈕右方的範例。

![右側含有文字的選項按鈕。](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Internet Explorer 中的選項按鈕

Internet Explorer 不支援選項按鈕樣式。 下圖顯示 Internet Explorer 中選項按鈕的外觀。

![Internet Explorer 中的選項按鈕。](media/pfe-styles-browser.png)

## <a name="buttons"></a>按鈕

只有符合以下條件，才能將樣式套用至按鈕：

- 每個按鈕群組都包含在表單群組中。 群組中的所有按鈕都會有相同的樣式。
- 對於群組名稱沒有規定。

請在按鈕上設定以下屬性：

- **按鈕顯示：** *TextWithImageLeft*
- **正常影像：** 此屬性不能為空白。 例如，請使用 *CoffeeScript*。
- **文字：** 此屬性不能為空白。 例如，請使用 *Start Break*。
- **寬度：** *Auto* 或 *SizeToContent*
- **高度：** *Auto* 或 *SizeToContent*

### <a name="primary-button"></a>主要按鈕

只有符合以下條件，才能將樣式套用至主要按鈕：

- 按鈕包含在表單群組中。
- 群組名稱以「`DefaultButtonGroup`」或「 `PrimaryButtonGroup`」作為開頭 (例如：`DefaultButtonGroup10`)。

![主要按鈕。](media/pfe-styles-first.png)

### <a name="secondary-button"></a>次要按鈕

只有符合以下條件，才能將樣式套用至次要按鈕：

- 按鈕包含在表單群組中。
- 該群組命名為 **右側面板**，或群組名稱以「`SecondaryButtonGroup`」作為開頭。

![次要按鈕。](media/pfe-styles-second.png)

### <a name="third-group-button"></a>第三組按鈕

只有符合以下條件，才能將樣式套用至第三組按鈕：

- 按鈕包含在表單群組中。
- 該群組命名為 **左側面板**，或群組名稱以「`ThirdButtonGroup`」作為開頭。

![第三組按鈕。](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>第四組按鈕

只有符合以下條件，才能將樣式套用至第四組按鈕：

- 按鈕包含在表單群組中。
- 群組名稱以「`FourthButtonGroup`」作為開頭。

請在按鈕上設定以下屬性：

- **按鈕顯示：** *TextOnly*
- **正常影像：** 此屬性必須為空白。
- **文字：** 此屬性不能為空白。 例如，使用 *View* 或 *Edit*。
- **寬度：** *Auto*
- **高度：** *Auto*

![第四組按鈕。](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>扁平按鈕

只有符合以下條件，才能將樣式套用至扁平按鈕：

- 按鈕包含在表單群組中。
- 群組名稱以「`FlatButtonGroup`」作為開頭。

請在按鈕上設定以下屬性：

- **按鈕顯示：** *ImageOnly*
- **正常影像：** 此屬性不能為空白。 例如，請使用 *CoffeeScript*。
- **文字：** 此屬性必須為空白。
- **寬度：** *Auto* 或 *SizeToContent*
- **高度：** *Auto* 或 *SizeToContent*

![扁平按鈕。](media/pfe-styles-flat-button.png)

### <a name="continue-button"></a>繼續按鈕

只有符合以下條件，才能將樣式套用至繼續按鈕：

- 按鈕包含在表單群組中。
- 群組名稱以「`ContinueButtonGroup`」作為開頭。

請在按鈕上設定以下屬性：

- **按鈕顯示：** *ImageOnly*
- **正常影像：** *Forward*
- **文字：** 此屬性必須為空白。
- **寬度：** *Auto* 或 *SizeToContent*
- **高度：** *Auto* 或 *SizeToContent*

![繼續按鈕。](media/pfe-styles-continue-button.png)

## <a name="combo-box"></a>下拉式方塊

下拉式方塊是三個控件的組合：輸入控件、清除輸入控件的按鈕和執行搜尋的按鈕。

只有符合以下條件，才能將樣式套用至下拉式方塊：

- 下拉式方塊包含在表單群組中。
- 群組名稱以「`Combobox`」作為開頭。
- 在群組中，第一個控件是 `AxFormStringControl` 控件。 此控件顯示目前的值，該控件也是由使用者輸入所需值的位置。
- 第二個控件是 `CommonButton` 控件，名稱以「`ClearButton`」作為開頭。 此按鈕必須包含使用 `enable` 屬性的程式碼以便顯示或隱藏按鈕。 例如，若要在使用者正在輸入控件中輸入資訊時顯示或隱藏 **清除** 按鈕，您可以使用以下程式碼。

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    您應該備妥一種可在輸入控件中設定資料的方法。 啟用該方法中的 **清除** 按鈕。 範例如下。

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    針對 **清除** 按鈕的 `clicked` 方法使用下列程式碼。

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    如果使用 `init` 方法初始化表單，請設定輸入控件 (`AxFormStringControl`) 的值。 如果該值不為空，請啟用 **清除** 按鈕。 如果該值為空白，請停用 **清除** 按鈕。

- 第三個控件是 `CommonButton` 控件，名稱以「`SearchButton`」作為開頭。

下圖顯示兩個下拉式方塊控件。 左側的下拉式方塊的文字方塊為空白，而 **清除** 按鈕已停用。 右側的下拉式方塊的文字方塊內含文字，而 **清除** 按鈕已啟用。

![包含和不含清除按鈕的下拉式方塊。](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>快速篩選器

快速篩選器控件會將搜尋欄位新增到頁面。 只要滿足以下要求，您就能將樣式套用至快速篩選器：

- 快速篩選器包含在表單群組中。
- 群組名稱以「`SearchInputGroup`」作為開頭。
- 在群組中，第一個控件是 `QuickFilter` 控件。 (此控件是使用者輸入搜尋字串的地方。)
- 第二個控件是 `FormStaticTextControl` ，名稱為「`NumberOfResults`」。 (這是選用控件。 如果納入該控件，其會顯示找到的項目數量。)
- 第三個控件是 `CommonButton` 控件，名稱以「`ClearButton`」作為開頭。

下圖顯示兩個快速篩選器控件。 左側的快速篩選器為空白，結果數量不可見。 右側的快速篩選器包含搜尋字串，並顯示結果數量。

![包含和不含搜尋字串的快速篩選器控件範例。](media/pfe-styles-quick-filter.png "包含和不含搜尋字串的快速篩選器控件範例")

## <a name="center-align-elements-on-a-tab"></a>將索引標籤上的元素置中對齊

若要將索引標籤上的元素置中對齊，則群組名稱必須以「`TabContentGroup`」作為開頭，且群組必須具有以下屬性：

- **寬度模式：**`SizeToAvailable`
- **高度模式：**`SizeToAvailable`

## <a name="align-a-grid-detail-part-and-quick-filter"></a>對齊網格、詳細資料部分和快速篩選器

若要排列自訂網格、詳細資料部分和快速篩選器，使其與標準設計相似，請在配置這些項目時考慮以下幾點：

- 如果網格有快速篩選器，則網格和快速篩選器都應位於名稱以「 `GridGroup`」為開頭的群組內。
- 若要對詳細資料部分套用樣式，群組名稱必須以「`DetailInformationGroup`」作為開頭。

下圖顯示典型的網格，其中包括快速篩選器和右側的詳細資料部分。

![包含快速篩選器和詳細資料部分的典型網格。](media/pfe-styles-align-grid.png "包含快速篩選器和詳細資料部分的典型網格")

在 Visual Studio 中，網格、詳細資料部分和快速篩選器是使用與下圖所示類似的結構建立。

![對齊網格、詳細資料部分和快速篩選器的典型程式碼結構。](media/pfe-styles-header-code-structure2.png "對齊網格、詳細資料部分和快速篩選器的典型程式碼結構")

## <a name="additional-resources"></a>其他資源

- [自訂生產現場執行介面](production-floor-execution-customize.md)
- [設計生產現場執行介面](production-floor-execution-tabs.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
