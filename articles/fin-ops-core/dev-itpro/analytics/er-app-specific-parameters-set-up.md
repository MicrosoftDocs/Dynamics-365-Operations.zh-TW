---
title: 為每個法律實體設定 ER 格式的參數
description: 本主題解釋了如何為每個法律實體設定電子報表 (ER) 格式的參數。
author: NickSelin
ms.date: 10/22/2021
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
ms.openlocfilehash: cb600c55cb2d40129d1b29ab989bc8f7cf3f4686
ms.sourcegitcommit: a5861c2fef4071e130208ad20e26cb3a42a45cf1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2021
ms.locfileid: "8460252"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>為每個法律實體設定 ER 格式的參數

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>先決條件

若要完成這些步驟，您必須先完成[設定 ER 格式以使用每個法律實體指定的參數](er-app-specific-parameters-configure-format.md)中的步驟。

若要完成本主題中的範例，您必須擁有以下角色之一的 Microsoft Dynamics 365 Finance 的存取權限：

- 電子報表開發人員
- 電子報表函數
- 系統管理員

## <a name="import-er-configurations"></a>匯入 ER 設定
若要匯入 ER 設定，請執行以下步驟： 

1. 登入到您的環境。
2. 在預設儀表板上，選取 **電子報表**。
3. 選取 **報表設定**。
4. 在 Finance 的現行實體中，匯入您在完成[設定 ER 格式以使用每個法律實體指定的參數](er-app-specific-parameters-configure-format.md)中的步驟時從 Regulatory Configuration Services (RCS) 匯出的設定。 按照以下順序對每個[電子報表 (ER)](general-electronic-reporting.md) 設定進行操作：資料模型、模型對應和格式。

    1. 選取 **Exchange\>從 XML 檔案載入**。
    2. 選取 **瀏覽** 為 XML 格式的 ER 設定選取所需的檔案。
    3. 選取 **確定**。

    下圖顯示了您完成後必須具備的設定。

    ![ER 設定頁面。](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>為 DEMF 公司設定參數

您可以使用 ER 架構為 ER 格式設定應用程式專用的參數。

1. 選取 **DEMF** 法律實體。
2. 在設定樹狀結構中，選取 **學習如何查找 LE 資料的格式** 格式。
3. 在動作窗格上，在 **安裝** 索引標籤，在 **應用程式專用參數** 組，選取 **安裝**。

    ![用於設定參數的 ER 應用程式專用參數頁面。](./media/GER-AppSpecParms-LookupForm.PNG)

    在 **應用程式專用參數** 頁面，您可以為 **學習如何查找 LE 資料的格式** 格式的 **選取器** 資料來源設定規則。

    如果基礎 ER 格式將包含幾個 **查找** 類型的資料來源，您必須在 **查找** FastTab 上選取需要的資料來源，然後才能開始設定資料來源的規則集。

    對於每個資料來源，您可以為所選 ER 格式的每個版本設定單獨的規則。

    在基本 ER 格式的選定版本中可用的所有查找資料來源的整套規則構成了 ER 格式的專用於應用程式的參數。

4. 選取 **1.1.1** 版的 ER 格式。
5. 在 **條件** FastTab 上，選取 **新增**。
6. 在新記錄的 **代碼** 欄位中，選取下拉式箭頭打開查找。

    該查找顯示可供選取的稅碼清單。 這個清單是由 **Model.Data.Tax** 資料來源返回，該資料來源已被設定為基礎 ER 格式。 因為這個資料來源包含 **名稱** 欄位，每個稅收代碼的名稱都會出現在查找中。

    ![代碼欄位在 ER 應用程式專用參數頁面上查找。](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)

7. 選取 **VAT19** 稅務代碼。
8. 在新記錄的 **查找結果** 欄位中，選取下拉式箭頭打開查找。 查找顯示 TaxationLevel 格式列舉的值清單以供選取。

    請注意，如果您選取德語作為您登入使用者的偏好語言，則查找中的值標籤將為德語，前提是它們已翻譯為基本 ER 格式。 此外，如果查找資料來源的標籤已翻譯，該標籤將以使用者的偏好語言顯示在 **查找** 標籤。

    ![在 ER 應用程式專用參數頁面上翻譯成德語的查找欄位。](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9. 選取 **一般稅收** 值。

    透過新增這個記錄，您定義了以下規則：當要求 **選取器** 查找資料來源，並將 **VAT19** 稅收代碼作為參數傳遞時，**一般稅收** 將作為要求的稅收級別被返回。

10. 選取 **新增**，然後按照以下步驟操作：

    1. 在 **代碼** 欄位中，選取 **InVAT19** 稅收代碼。
    2. 在 **查找結果** 欄位中，選取 **一般稅收** 值。

11. 選取 **新增**，然後按照以下步驟操作：

    1. 在 **代碼** 欄位中，選取 **VAT7** 稅收代碼。
    2. 在 **查找結果** 欄位中，選取 **減少稅收** 值。

12. 選取 **新增**，然後按照以下步驟操作：

    1. 在 **代碼** 欄位中，選取 **InVAT7** 稅收代碼。
    2. 在 **查找結果** 欄位中，選取 **減少稅收** 值。

13. 選取 **新增**，然後按照以下步驟操作：

    1. 在 **代碼** 欄位中，選取 **THIRD** 稅收代碼。
    2. 在 **查找結果** 欄位中，選取 **無稅收** 值。

14. 選取 **新增**，然後按照以下步驟操作：

    1. 在 **代碼** 欄位中，選取 **InVAT0** 稅收代碼。
    2. 在 **查找結果** 欄位中，選取 **無稅收** 值。

15. 選取 **新增**，然後按照以下步驟操作：

    1. 在裡面 **代碼** 欄位，選取 **\*非空白\*** 選項。
    2. 在 **查找結果** 欄位中，選取 **其他** 值。

    透過新增這最後一條記錄，您定義了以下規則：當作為參數傳遞的稅收代碼不滿足前面的任何規則時，查找資料來源將返回 **其他** 作為要求的稅收級別。

    ![在 ER 應用專用參數頁面上新增的最後一條記錄。](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)

16. 在 **狀態** 欄位中，選取 **已完成**。

    當您執行狀態為 **已完成** 或 **共用** 的 ER 格式版本時，這套規則必須處於 **已完成** 狀態。 否則，當 **選取器** 查找資料來源正在執行階段，當格式試圖從這組規則中載入資料時，基礎 ER 格式的執行將被中斷。

    當您執行狀態為 **草稿** 的 ER 格式版本時，基本 ER 格式可以存取這套規則，無論其狀態如何。

17. 選取 **儲存**。
18. 關閉 **應用程式專用參數** 頁。

## <a name="run-the-er-format-in-the-demf-company"></a>在 DEMF 公司執行 ER 格式
若要在 DEMF 公司中執行 ER 格式，請執行以下步驟： 

1. 在設定樹狀結構中，選取 **學習如何查找 LE 資料的格式** 格式。
2. 在動作窗格中，選取 **執行**。
3. 在出現的對話方塊中，選取 **確定**。
4. 下載產生的報表並將其儲存在本地。

    在產生的報表中，請注意 **InVAT7** 稅收代碼的摘要是在 **減稅** 級別，而 **VAT19** 和 **InVA19** 稅收代碼的摘要是在 **一般** 級別。 此行為由法律實體相關規則集中的設定決定。

5. 進入 **稅收\>間接稅\>銷售稅\>銷售稅代碼**。
6. 選取 **InVAT7** 稅務代碼。
7. 在動作窗格中，在 **銷售稅代碼** 索引標籤上，在 **查找** 組中，選取 **已過帳的銷售稅**，查看每個稅收代碼的稅值和應用的稅率資訊。

    ![已過帳銷售稅頁面。](./media/GER-AppSpecParms-Statement.PNG)

8. 關閉 **已過帳銷售稅** 頁。

## <a name="set-up-parameters-for-the-usmf-company"></a>為 USMF 公司設定參數
若要為 USMF 公司設定參數，請完成以下步驟： 

1. 選取 **USMF** 法律實體。
2. 進入 **組織管理\>電子報表\>設定**。
3. 在設定樹狀結構中，展開 **學習已參數化調用的模型** 項目，展開 **學習已參數化調用的格式** 項目，並選取 **學習如何查找 LE 資料的格式** 格式。
4. 在動作窗格上，在 **安裝** 索引標籤，在 **應用程式專用參數** 組，選取 **安裝**。
5. 選取所選 ER 格式 **1.1.1** 版。
6. 在 **條件** FastTab 上，選取 **新增**。
7. 在新記錄的 **代碼** 欄位中，選取下拉式箭頭打開查找。

    該查找現在呈現出 **USMF** 公司稅的稅收代碼清單，以供選取。

    ![USMF 公司稅的稅收代碼。](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)

8. 選取 **EXEMPT** 稅務代碼。
9. 在新記錄的 **查找結果** 欄位中，選取 **無稅收** 值。
10. 選取 **新增**。
11. 在新記錄的 **代碼** 領域，選取 **\*非空白\*** 選項。
12. 在新記錄的 **查找結果** 欄位中，選取 **一般稅收** 值。
13. 在 **狀態** 欄位中，選取 **已完成**。
14. 選取 **儲存**。

    ![ER 應用程式專用參數頁面。](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)

15. 關閉 **應用程式專用參數** 頁。

## <a name="run-the-er-format-in-the-usmf-company"></a>在 USMF 公司執行 ER 格式
若要在 USMF 公司執行 ER 格式，請完成以下步驟：

1. 在設定樹狀結構中，選取 **學習如何查找 LE 資料的格式** 格式。
2. 在動作窗格中，選取 **執行**。
3. 在出現的對話方塊中，選取 **確定**。
4. 下載產生的報表並將其儲存在本地。

    在產生的報表中，請注意您現在已將相同的 ER 格式用於不同的法律實體，但未對 ER 格式進行任何調整。

## <a name="reuse-legal-entitydependent-parameters"></a>重複使用法律實體相關參數

### <a name="duplicate-existing-parameters"></a>複製現有參數

#### <a name="export-parameters"></a>匯出參數
若要匯出參數，請完成以下步驟：

1. 進入 **組織管理\>工作區\>電子報表**。
2. 選取 **報表設定**。
3. 在設定樹狀結構中，選取 **學習如何查找 LE 資料的格式** 格式。
4. 在動作窗格上，在 **安裝** 索引標籤，在 **應用程式專用參數** 組，選取 **安裝**。
5. 選取 **1.1.1** 版的 ER 格式。
6. 在動作窗格上，選取 **匯出**。
7. 下載產生的檔案並將其儲存在本地。

    已設定的應用程式專用參數集現已匯出為 XML 檔案。

#### <a name="import-parameters"></a>匯入參數
若要匯入參數，請完成以下步驟：

1. 選取 **1.1.2** 版的 ER 格式。
2. 在動作窗格上，選取 **匯入**。
3. 選取 **是** 確認您要覆寫此格式版本的現有應用程式專用參數。
4. 選取 **瀏覽**，找到包含 **1.1.1** 版本匯出的專用應用程式參數的檔案。
5. 選取 **確定**。

    **1.1.2** 版的 ER 格式現在具有與您最初為 **1.1.1** 版設定的應用程式專用參數。

##### <a name="applicability-considerations"></a>適用性注意事項

ER 格式的應用程式專用參數取決於法律實體。 若要重複使用為不同法律實體中的法律實體設定的應用程式專用參數，您必須在登入到第一個法律實體時匯出它們。 然後在您登入到其他法律實體後匯入它們。

您還可以使用這種匯出-匯入方法將最初在一個 Finance 實體中設定的與 ER 格式相關的應用程式專用參數傳輸到另一個 Finance 實體。

如果您為 ER 格式的版本設定應用程式專用參數，然後將相同格式的更高版本匯入現行 Finance 實體，則現有的特定於應用程式的參數將不會應用於匯入的版本，除非您使用 **使用來自以前版本的 ER 格式的應用程式專用參數** 函數。 若需詳細資訊，請參閱本主題後面的[重複使用現有的參數](#reuse-existing-parameters)節。

當您選取檔案進行匯入時，該檔案中應用程式專用參數的結構會與選取匯入的 ER 格式中 **查找** 類型的相應資料來源的結構進行比較。 在預設情況下，只有當每個應用程式專用參數的結構與選取匯入的 ER 格式中的相應資料來源的結構相符時，才能完成匯入。 如果結構不相符，則會出現警告訊息，通知您無法完成匯入。 如果您強制匯入，所選 ER 格式的現有應用程式專用參數將被清除，您必須從頭開始設定它們。


從 Dynamics 365 Finance 10.0.24 版本開始，您可以透過在 **函數管理** 工作區中啟用 **匯入時對齊 ER 應用程式專用參數** 函數來改變預設行為並避免收到警告訊息。 啟用此函數後，如果您要匯入的應用程式專用參數的結構與選取匯入的目標 ER 格式中的相應資料來源的結構不同，匯入會在以下情況下成功：

- 目標 ER 格式的結構透過向任何現有的 **查找** 類型的資料來源新增新的條件資料欄已經改變。 匯入完成後，應用程式專用參數會更新。 在所有匯入的應用程式專用參數記錄中，每個新增的條件資料欄中的值都使用預設值進行那一資料欄的初始化[資料類型](er-formula-supported-data-types-primitive.md)。
- 透過從任何現有的 **查找** 類型的資料來源中刪除一些條件資料欄，目標 ER 格式的結構已經被改變。 匯入完成後，應用程式專用參數會更新。 在所有匯入的應用程式專用參數記錄中，每個已刪除條件資料欄中的值都被刪除。
- 透過增加新的 **查找** 類型的資料來源，目標 ER 格式的結構已經改變。 當匯入完成後，將新增的查找附加到應用程式專用參數上。
- 目標 ER 格式的結構已透過刪除一些現有的 **查找** 類型的資料來源進行了更改。 匯入完成後，與從目標 ER 格式中刪除的 **查找** 類型的資料來源相關的所有工件都將從匯入的應用程式專用參數中刪除。

匯入完成後，除了剛才描述的更改外，匯入的應用程式專用參數的狀態更改為 **進行中**。 警告訊息通知您必須手動編輯自動調整的應用程式專用參數。

### <a name="reuse-existing-parameters"></a>重複使用現有參數

從 Dynamics 365 Finance 版本 10.0.23 開始，當您執行相同格式的更高版本時，您可以重複使用已為 ER 格式的一個版本設定的應用程式專用參數。 透過此方法，請在 **函數管理** 工作區中啟用 **使用以前版本的 ER 格式中的應用程式專用參數** 函數。 當啟用此函數並且您執行一個嘗試讀取應用程式專用參數的 ER 格式版本時，ER 將嘗試查找已為此格式的執行版本設定的應用程式專用參數。 或者，當它們不可用時，使用此格式的最近前一版本。

> [!NOTE]
> 您只能在現行法律實體的範圍內重複使用應用程式專用參數。
>
> 當您執行較高版本的 ER 格式並嘗試重複使用已為相同格式的較低版本和至少一個 **查找** 類型資料來源的結構設定的應用程式專用參數時，會在執行階段顯示錯誤在更高格式的版本中發生了變化。

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>應用程式專用參數和 ER 格式之間的關係

ER 格式與其應用程式專用參數之間的關係由 ER 格式的獨立於實體的唯一識別碼建立。 因此，當您從 Finance 中刪除 ER 格式時，為 ER 格式設定的應用程式專用參數將保留在 Finance 的現行實體中。 將基本 ER 格式重新匯入此 Finance 實體時，可以存取它們。

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>使用 ER 架構存取應用程式專用參數

在前面的範例中，您已經使用 ER 架構存取了 ER 格式的應用程式專用參數。 這種方法不允許您限制對特定 ER 格式的應用程式專用參數的存取。 如果您必須套用此類限制，請按照以下步驟操作。 

1. 重複使用現有的 **ERSolutionAppSpecificParametersDesigner** 選單項目，或實施您自己的 **ERSolutionAppSpecificParametersDesigner** 選單項目。

    ![顯示 ERSolutionAppSpecificParametersDesigner 的選單項目。](./media/GER-AppSpecParms-LookupForm-Access1.PNG)

2. 請執行以下其中一個步驟：

    1. 建立新的選單項目按鈕，並透過將其 **資料來源** 屬性設定為 **ERSolutionTable** 將其連結到 **ERSolutionTable** 表中的相應記錄。

        ![顯示新的選單項目設定。](./media/GER-AppSpecParms-LookupForm-Access2.PNG)

    2. 建立簡單的按鈕，並覆寫 **已點選** 方法，如下例所示。

        透過使用這種方法，您可以指定唯一的解決方案 ID (透過 **GUID** 值定義) 以允許僅存取特定 ER 格式的應用程式專用參數和從它衍生的子系副本。
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a>其他資源

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[設定 ER 格式以使用每個法律實體指定的參數](er-app-specific-parameters-configure-format.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
