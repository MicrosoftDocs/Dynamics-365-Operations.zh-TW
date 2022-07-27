---
title: 從 Power Apps 嵌入畫布應用程式
description: 本主題說明如何將 Microsoft Power Apps 中的畫布應用程式嵌入用戶端以增強產品的函數。
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: c2f7b660d364be6e62d484e67908201027190a8a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460182"
---
# <a name="embed-canvas-apps-from-power-apps"></a>從 Power Apps 嵌入畫布應用程式

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Microsoft Power Apps 是一項服務，讓開發人員和非技術使用者無需編寫代碼即可為行動裝置、平板電腦和 Web 構建自訂業務應用程式。 財務和營運應用程式支援與 Power Apps 的整合。 您、您的組織或更廣泛的生態系統開發的畫布應用程式可以嵌入到財務和營運應用程式中，以增強產品的函數。 例如，您可以從 Power Apps 構建一個畫布應用程式，以使用從另一個系統檢索到的資訊來補充財務和營運應用程式。

若要進一步了解嵌入畫布應用程式，請觀看短片[如何嵌入畫布應用程式](https://www.youtube.com/watch?v=x3qyA1bH-NY)。

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>將嵌入式畫布應用程式從 Power Apps 新增到頁面

在將 Power Apps 中的畫布應用程式嵌入用戶端之前，您必須找到或構建具有所需視覺效果或函數的應用程式。 本主題不包括對構建應用程式過程的詳細描述。 如果您不熟悉 Power Apps，請參閱[Power Apps 文件](/powerapps/)。

將畫布應用程式嵌入到財務和營運應用程式中有三種方法。 您可以使用最適合您的方案的方法。 

- 將畫布應用嵌入到頁面標準動作窗格上的 **Power Apps** 按鈕中。 以這種方式新增的應用程式顯示為 **Power Apps** 選單按鈕上的項目，並且應用程式在側窗格中打開。 
- 將畫布應用程式直接嵌入現有頁面作為新標籤頁 (樞紐索引標籤、FastTab、刀鋒或工作區部分)。
- 從儀表板為畫布應用程式建立新的整頁體驗。

設定嵌入式畫布應用程式時，您可以選取要作為內容發送到應用程式的單個欄位。 此步驟使應用程式能夠根據您現行正在查看的資料做出回應。

> [!NOTE]
> 您不能使用此機制來嵌入模型導向應用程式。

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>在現有頁面上嵌入畫布應用程式

以下程序顯示如何在 Power Apps 的現有頁面上嵌入畫布應用程式。

1. 轉到要嵌入畫布應用程式的頁面。 此頁面將包含必須作為輸入傳遞給應用程式的所有資料。
2. 開啟 **從 Power Apps 新增應用程式** 窗格：

    - 如果應用程式將直接嵌入頁面，請選取 **選項**\>**個人化此頁面**\>**更多**，然後執行以下步驟之一：

        - 如果 **整頁應用程式** 函數已打開，選取 **新增頁面**，然後選取要新增應用的區域。 若要將應用程式嵌入 **Power Apps** 選單按鈕，請選取動作窗格。 若要將應用程式直接嵌入頁面，請選取適當的索引標籤、FastTab、刀鋒或部分 (如果您在工作區中)。 然後，在 **新增應用程式** 窗格中，選取 **Power Apps**。
        - 如果 **整頁應用程式** 函數已關閉，請選取 **從 Power Apps 新增應用程式**，然後選取要新增應用程式的區域。 若要將應用程式嵌入 **Power Apps** 選單按鈕，請選取動作窗格。 若要將應用程式直接嵌入頁面，請選取適當的索引標籤、FastTab、刀鋒或部分 (如果您在工作區中)。

    - 如果將使用 **Power Apps** 選單按鈕存取應用程式，您可以選取標準動作窗格上的 **Power Apps** 選單按鈕，然後選取 **新增應用程式**。

3. 設定嵌入式應用程式。 如需相關資訊，請參閱本主題後面的[設定畫布應用程式](#configuring-a-canvas-app)章節。
4. 確認設定正確後，選取 **插入**。

    - 如果 **儲存的視圖** 函數已關閉，系統會提示您重新整理瀏覽器以查看嵌入式應用程式。
    - 如果 **儲存的視圖** 函數已打開，您必須儲存視圖才能保留更改。

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>從儀表板嵌入畫布應用程式作為整頁體驗

如果應用程式與現有頁面不相關，或者如果您只想在財務和營運應用程式中將應用程式顯示為整頁體驗，您可能希望從儀表板嵌入畫布應用程式。

> [!NOTE]
> 若要提供此功能，您必須打開函數管理中的 **整頁應用程式** 函數。 

1. 開啟儀表板。
2. 選取並按住 (或按右鍵點選) 頁面，選取 **個人化**，然後選取 **新增頁面**。
3. 在 **新增頁面** 窗格中，選取 **Power Apps**。
4. 設定嵌入式應用程式。 如需相關資訊，請參閱本主題後面的[設定畫布應用程式](#configuring-a-canvas-app)章節。
5. 選取 **儲存** 以將應用程式作為新圖格新增到儀表板。
6. 選取儀表板上的新圖格，並確認畫布應用程式按預期顯示。

### <a name="configuring-a-canvas-app"></a>設定畫布應用程式

嵌入畫布應用程式時，必須設定以下參數：

- **名稱** – 輸入應為包含嵌入式應用程式的按鈕或索引標籤顯示的文字。 通常，您可能希望在此欄位中重複應用程式的名稱。
- **應用程式識別碼** – 為要嵌入的畫布應用程式指定全域唯一識別碼 (GUID)。 若要取出此值，請在 [make.powerapps.com](https://make.powerapps.com)應用程式上尋找，然後查看 **詳情** 下方的 **應用程式識別碼**。
- **為應用程式的輸入內容** – 您可以選取包含要作為輸入傳遞給應用程式的資料的欄位。 如需應用程式如何存取從財務和營運應用程式發送的資料的相關資訊，請參閱本主題後面的[構建利用從財務和營運應用程式發送的資料的應用程式](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps)章節。

    從 10.0.19 版開始，現行法律實體也作為內容傳遞給畫布應用程式，透過 **CMP** URL 參數。 在目標畫布應用使用該資訊之前，此行為不會影響該應用程式。

- **應用程式大小** – 選取您要嵌入的應用程式類型。 為行動裝置構建的應用程式選取 **輕薄** 或為平板電腦構建的應用程式選取 **寬版**。 此參數可確保為嵌入式應用程式指派足夠的空間。
- **法律實體** – 您可以選取應用程式應適用的法律實體。 在預設情況下，該應用程式適用於所有法律實體。 此選項僅在您直接嵌入現有頁面且 **[已儲存視圖](saved-views.md)** 函數關閉時可用。

## <a name="sharing-an-embedded-app"></a>分享嵌入式應用程式

在頁面上嵌入畫布應用程式並確認其工作正常後，您可能希望與系統中的其他使用者分享該應用程式。 若要分享嵌入式畫布應用程式，請按照以下步驟操作。

1. [在 Power Apps 中分享畫布應用程式](/powerapps/maker/canvas-apps/share-app)與相應的使用者，以便他們可以直接在 Power Apps 中存取應用程式。
2. 與所需使用者分享與嵌入式應用程式相關的個人化設定。 您可以使用以下任一方法：

    - **發佈視圖 (建議) ：** 如果打開了 **[已儲存視圖](saved-views.md)** 函數，建議和偏好的方法是建立包含嵌入式畫布應用程式的視圖，然後將該視圖發佈給所需的使用者。 此方法可確保具有已發佈視圖所針對的安全角色的所有使用者都將在頁面上看到畫布應用程式。

        您還可以從儀表板發佈已作為整頁體驗嵌入的畫布應用程式。 在儀表板上，選取並按住（或右鍵點選）與應用程式關聯的圖格，選取 **個人化**，然後選取 **發布頁面**。 顯示類似於 *發布視圖* 體驗的體驗，您可以選取要發佈到的安全角色。 在更新 10.0.21 或更高版本中，如果打開了 **改進的對已儲存視圖的法律實體支援** 功能，您還可以將應用程式發佈到所需的法律實體。

    - 如果 **儲存的視圖** 函數已關閉，系統管理員可以透過 **個人化** 頁面將包含畫布應用程式的個人化設定提供給適當的使用者集。 或者，您可以匯出頁面的個人化設定，然後將它們發送給一個或多個使用者。 然後，每個使用者都可以匯入個人化設定。 個人化工具列具有可讓您匯出和匯入個人化設定的按鈕。

> [!NOTE]
> 如果畫布應用程式已與外部使用者共用，則這些使用者無法使用財務和營運應用程式中的嵌入式應用程式。 但是，他們可以直接在 Power Apps 中存取應用程式。 外部使用者包括不屬於部署財務和營運應用程式的 Microsoft 365 Azure 目錄的來賓和使用者。

如需產品中的個人化功能以及如何使用它們的相關資訊，請參閱[個人化使用者體驗](personalize-user-experience.md)。

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>構建使用從財務和營運應用程式發送的資料的畫布應用程式

當您構建將嵌入財務和營運應用程式的畫布應用程式時，該過程的一個重要部分是使用來自該財務和營運應用程式的輸入資料。 根據 Power Apps 開發經驗，可以使用 **Param("EntityId")** 變量存取從財務和營運應用程式傳遞的輸入資料。 此外，從 10.0.19 版開始，現行法律實體也將透過 **Param("cmp")** 變量傳遞給畫布應用程式。 

例如，在應用程式的 OnStart 函數中，您可以將財務和營運應用程式的輸入資料設定為如下變量：

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>檢視畫布應用程式

若要在財務和營運應用程式的頁面上查看嵌入式畫布應用程式，只需前往具有嵌入式應用程式的頁面。 請記住，可以使用標準動作窗格上的 **Power Apps** 按鈕存取應用程式。 或者，它們可以作為新索引標籤、FastTab、刀鋒或工作區中的新部分直接顯示在頁面上。 當使用者第一次嘗試在頁面上載入應用程式時，系統會提示他們登入。 此步驟可確保使用者具有使用該應用程式的適當權限。

## <a name="editing-an-embedded-app"></a>編輯嵌入式應用程式

將應用程式嵌入到頁面後，您可能需要對應用程式的設定進行一些更改。 例如，您可能想要修改與嵌入式應用相關的標籤，或者已經建立了新版本的應用，您需要更新應用程式識別碼以指向最新。

按照以下步驟編輯嵌入式應用程式的設定：

1. 進入 **編輯應用程式** 窗格。

    - 如果透過 Power Apps 選單按鈕存取嵌入式應用程式，請選取並按住 (或右鍵點選) Power Apps 選單按鈕，然後選取 **個人化**。 從 **選取應用程式** 下拉式選單中選取要設定的應用程式。
    - 如果嵌入式應用程式直接出現在頁面上，請選取 **選項**，然後選取 **個人化此頁面**。 使用 **選取** 工具，點選嵌入式應用程式。
    - 如果嵌入式應用程式是從儀表板新增的，請打開儀表板，選取並按住 (或按右鍵點選) 與畫布應用程式相關的圖格，選取 **個人化**，然後選取 **編輯頁面**。

2. 對應用程式設定進行必要的修改，然後點選 **儲存**。

## <a name="removing-an-app"></a>刪除應用程式

將應用程式嵌入到頁面後，如果需要，有幾種方法可以將其移除：

- 使用本主題前面的 [編輯嵌入式應用程式](#editing-an-embedded-app)章節中的說明進入 **編輯應用程式** 窗格。 確認窗格顯示您要移除的嵌入式應用程式的資訊，然後點選 **刪除** 按鈕。
- 如果嵌入式應用程式是從儀表板新增的，請打開儀表板，選取並按住 (或按右鍵點選) 與畫布應用程式相關的圖格，選取 **個人化**，然後選取 **移除頁面**。 
- 由於嵌入式應用程式儲存為個人化資料，因此清除頁面的個人化也會刪除該頁面上的所有嵌入式應用程式。 請注意，清除頁面的個人化設定是永久性的，無法撤銷。 若要移除頁面上的個人化設定，請選取 **選項**，然後 **個人化此頁面**，最後是 **清除** 按鈕。 重新整理瀏覽器後，此頁面之前的所有個人化設定都將被移除。 如需如何使用個人化最佳化頁面的相關資訊，請參閱[個人化使用者體驗](personalize-user-experience.md)。

## <a name="appendix"></a>附錄

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[開發人員] 在表單上為畫布應用程式建模

雖然本主題側重於透過個性化嵌入畫布應用程式，但開發人員還可以選取使用 Visual Studio 開發體驗將畫布應用程式新增到表單。 為此，只需將 PowerAppsHostControl 新增到表單。 控制上可用的中繼資料屬性提供與個人化體驗相同的功能。

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[開發人員] 指定可以嵌入應用程式的位置

在預設情況下，使用者可以在任何頁面上嵌入應用程式，無論是在 Power Apps 選單按鈕下還是直接在頁面上作為索引標籤、FastTab、刀鋒或作為工作區中的新部分。 但是，如果需要，開發人員還可以透過實現以下方法將此函數設定為僅允許在某些頁面上嵌入應用程式：

- **isPowerAppPersonalizationEnabled** – 如果此方法對特定頁面回傳 False，則 Power Apps 選單按鈕將不會顯示，使用者將無法在此頁面的任何位置嵌入應用程式，包括作為索引標籤。
- **isPowerAppTabPersonalizationEnabled** – 如果此方法為特定頁面回傳 False，則使用者將無法將應用程式直接嵌入頁面作為索引標籤、FastTab 或全景部分。 如果頁面上允許嵌入，使用者仍然可以透過 Power Apps 選單按鈕嵌入應用程式。

以下範例顯示了一個新類，其中包含設定應用程式嵌入位置所需的兩種方法。

```powerapps
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
