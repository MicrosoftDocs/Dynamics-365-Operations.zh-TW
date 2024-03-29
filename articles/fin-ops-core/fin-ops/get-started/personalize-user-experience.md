---
title: 個人化使用者體驗
description: 本主題說明如何個人化應用程式。
author: jasongre
ms.date: 03/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4bdce3cd12358112e40a783c73795bd6f35545c8
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2022
ms.locfileid: "8460544"
---
# <a name="personalize-the-user-experience"></a>個人化使用者體驗

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題介紹如何個人化應用程式並涵蓋以下主題： 

- **系統範圍的選項** – 這些個人化選項在設定頁面上進行，可供所有使用者使用。 範例包括顏色主題和時區。 
- **受限的個人化存取** – 在此存取級別，與一般頁面使用相關的使用者動作由應用程式自動儲存，並在您下次存取該頁面時恢復。 例如，如果您調整格線列的寬度，應用程式會儲存它們的寬度，以及 FastTab 的展開或摺疊狀態。 
- **完全個人化存取** – 在此存取級別，使用者可以存取應用程式中的所有個人化功能。 特別是，他們可以存取 **個人化** 工具列。 
- **分享個人化** – 擁有完全個人化存取權限的使用者可以匯出他們的頁面個人化並與其他使用者分享。
- **個人化管理** – 有權限的使用者可以存取 **個人化** 管理頁面以管理組織級別的所有個人化設定。 

## <a name="system-wide-options-for-the-current-user"></a>目前使用者的系統範圍選項

**使用者選項** 頁面包含目前使用者的幾個系統範圍的設定。 這些選項可供所有使用者使用，即使是沒有獲得任何個人化存取權限的使用者。 若要開啟 **使用者選項** 頁面，請選取導覽列上的 **設定** 按鈕，然後選取 **使用者選項**。 **使用者選項** 頁面有四個索引標籤，其中包含各種使用者設定：

- **視覺效果** – 選取顏色主題和頁面上元素的預設大小。
- **偏好設定** – 選取每次開啟系統時使用的預設值。 這些值包括預設公司、初始頁面和預設查看/編輯模式。 (檢視/編輯模式確定每次打開頁面時是鎖定查看還是打開頁面進行編輯。) 此索引標籤還包括語言、時區以及日期、時間和數字格式的選項。 最後，此索引標籤包含幾個不同的偏好設定，這些偏好設定因版本而異。
- **帳戶** – 檢視或調整您的使用者名和其他與帳戶相關的選項。
- **工作流程** – 選取與工作流程相關的選項。

除了更改您的使用者設定外，您還可以從 **使用者選項** 頁面查看和刪除您的使用資料和個人化設定。 若要查看您的使用資料，請選取動作窗格上的 **使用方式資料**。 在 **個人化** 索引標籤，您可以查看和管理您對系統中的頁面所做的個人更改。 在此索引標籤上，您還可以重設功能標註 (即引入新系統功能的彈出式視窗)。 然後，您將再次收到有關先前遇到之功能的警報。

> [!NOTE]
> 如果打開了 [已儲存的檢視表](saved-views.md)功能，您可以透過在 **使用者選項** 頁面上選取動作窗格上的 **個人化** 來查看和管理您的個人化。

## <a name="restricted-personalization-access-formerly-implicit-personalizations"></a>受限的個人化存取 (前身為隱含個人化)

在 **受限的個人化存取** 級別，與一般頁面使用相關的使用者動作將由應用程式自動儲存，並在您下次存取該頁面時恢復。 不需要明確儲存動作。 

以下是屬於一般頁面使用且受限制的個人化存取涵蓋的動作清單： 

- **格線欄寬** – 您可以調整格線中資料欄的寬度，方法是選取欄標題左側或右側的調整大小列，然後向左或向右滑動，直到該資料欄達到所需的寬度。 該應用程式儲存您為資料欄設定的寬度。 然後，下次您打開該頁面時，該資料欄將調整為該寬度。
- **格線頁尾和資料欄總計** – *(僅在打開新的格線控制項時可用)* 您可以決定是否應在格線中任何數字列的底部顯示總計，以及是否應顯示格線頁尾。 該應用程式會儲存這些偏好設定，並在您下次打開頁面時套用。 如需詳細資訊，請參閱[格線功能](grid-capabilities.md)。 
- **FastTabs** – 某些頁面具有可擴展的區塊，稱為 *FastTabs*。 該應用程式儲存有關您已展開或摺疊的 FastTab 的資訊。 下次打開頁面時，相同的 FastTab 將根據您與頁面的最後互動來展開或摺疊。 在某些情況下，您可以透過摺疊 FastTab 來幫助提高系統效能，因為應用程式在展開前不必取出 FastTab 的資訊。 如本主題後面所述，您還可以更改 FastTabs 在頁面上的順序。
- **FactBoxes** - 有些頁面有 **相關資訊** 窗格，顯示與頁面目前主題相關的僅供讀取資訊。 **相關資訊** 窗格中的每個區塊都稱為 *FactBox*。 您可以展開或摺疊 **相關資訊** 窗格，也可以展開或摺疊單個 FactBox。 該應用程式儲存這些偏好設定。 下次開啟頁面時，**相關資訊** 窗格和各個 FactBox 將根據您與頁面的最後互動展開或摺疊。 在某些情況下，您可以透過摺疊 **相關資訊** 窗格或 FactBox 來幫助提高系統效能，因為應用程式在展開 FactBox 之前不必取出它們的資訊。
- **動作窗格**- *動作窗格* 出現在大多數頁面頂部附近。 動作窗格包含您可以在目前頁面上執行許多動作的按鈕。 這些按鈕通常組織在索引標籤上。 您可以將整個動作窗格 *釘選* 為開啟狀態，也可以將其預設摺疊。 下次打開頁面時，動作窗格將根據您與頁面的最後互動打開或摺疊。 如果您將動作窗格固定為打開狀態，則會顯示您使用的最後一個索引標籤。
- **QuickFilters**- *QuickFilters* 出現在許多格線上方。 QuickFilter 允許您根據您選取的單欄篩選格線。 該應用程式儲存您篩選的資料欄。 然後，下次您打開該頁面時，格線將預設使用同一欄進行篩選。 但是，您仍然可以選取不同的資料欄來篩選格線。
- **欄標題篩選器** - 當您使用 *欄標題篩選器* 篩選格線時，您可以根據需要更改篩選器運算子以尋找所需的資料。 例如，您可以將運算子從 **開始於** 更改為 **完全是**。 每次您使用欄標題篩選器並更改篩選器運算子時，應用程式都會儲存更改。 然後，下次您在該資料欄上篩選時，篩選器運算子將被恢復。
- **瀏覽窗格** – 您可以透過選取任何頁面左上角的 **展開瀏覽窗格** 按鈕來打開 *瀏覽窗格*。 (此按鈕有時稱為 _**選單** 按鈕_、*漢堡*、*漢堡選單*，或 *漢堡按鈕*。) 您可以將瀏覽窗格釘選為開啟狀態，也可以將其預設摺疊。 將瀏覽窗格釘選為開啟狀態後，該應用程式將保持打開狀態，直到您將其摺疊。

## <a name="full-personalization-access-formerly-explicit-personalizations"></a>完全個人化存取 (以前的明確個人化)

在 **完全個人化存取** 級別，使用者可以存取應用程式提供的所有個人化功能。 由於不同的人和公司在與應用程式互動時有不同的需求，特別是在使用領域方面，個人化提供了工具，讓使用者和組織可以自訂資訊在應用程式內的排序和互動方式。 這些功能是在為您和您的組織量身訂製的應用程式中提供簡化、最佳化體驗的關鍵。 

如果[已儲存的檢視表](saved-views.md)功能打開時，需要顯式儲存才能將這些更改持久儲存到特定檢視表的使用者體驗中。 關閉 **已儲存的檢視表** 功能後，這些更改將自動儲存。

以下部分介紹了在 **完全個人化存取** 級別上可供使用者使用的個人化功能的範圍。 以下是這些功能中的一部分：

- 捷徑選單選項
- **個人化** 工具列
- 向工作區新增圖格、清單和連結
- 將工作區中的摘要新增到儀表板
- 個人化儀表板

### <a name="shortcut-menu-options"></a>捷徑選單選項

捷徑選單提供了更改頁面介面的方法，以便更滿足您的要求或組織的要求。 (捷徑選單也稱為 *按右鍵選單* 或 *內容選單*。)

可以對頁面進行的一些最一般和最重要的更改可直接作為捷徑選單上的選項使用。 例如，如果要在格線中新增或隱藏欄，只需按右鍵點選欄標題，然後選取 **插入資料欄** 或 **隱藏此資料欄**。

此外，可以透過按右鍵點選元素然後選取 **個人化** 來獲得最基本的個人化類型。 (請注意，並非頁面上的所有元素都可以個人化。) 當您使用這種個人化方法時，會出現元素的 *屬性視窗*。

![個人化元素的屬性。](./media/cli-element-property-window.png)

您可以使用屬性視窗透過以下方式個人化元素：

- 更改元素的標籤。
- 隱藏元素，使其不顯示在頁面上。 該欄位中的資料不會被刪除或修改。 該資訊不再顯示在頁面上。
- 在 FastTab 的摘要部分中包含資訊 (如果元素在 FastTab 上)。
- 跳過該欄位，以便它在您瀏覽頁面時永遠不會收到焦點。
- 防止有人編輯欄位中的資料 (適用於任何記錄)。
- 指定資料輸入所需的欄位。 如果在此欄位中未輸入任何值，它將顯示帶有紅色邊方塊和星號以指示此狀態。 此選項僅在版本 10.0.11 開始時可用 [已儲存的檢視表](saved-views.md)和 **使用個人化指定欄位** 功能。

屬性視窗可能包括其他個人化功能，具體取決於元素。 例如，圖格的屬性視窗可以讓您將該圖格提升到儀表板，預設儀表板上的元素的屬性視窗可以讓您建立新的自訂工作區。

### <a name="personalization-toolbar"></a>個人化工具列

如果您想對頁面進行多項更改，或者透過其他機制無法進行的更改 (例如，如果您想重新排序元素)，您可以使用 **個人化** 工具列。 若要開啟 **個人化** 工具列，請執行以下步驟之一：

- 從頁面上的任何元素選取 **Ctrl+Shift+P**。
- 在元素的屬性視窗中選取 **個人化此頁面**。
- 在任何頁面的動作窗格的 **選項** 索引標籤上的 **個人化** 組中選取 **個人化此頁面**。
- 選取 **設定** 按鈕 (齒輪符號)，然後選取 **個人化**。

[![個人化工具列。](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>瀏覽該頁面

當 **個人化** 工具列打開時，底層頁面是僅供讀取的 (換句話說，您不能編輯資料)，但它仍然具有互動性。 具體來說，您可以展開或摺疊 **相關資訊** 窗格、切換索引標籤以及展開或摺疊部分，就像您通常在頁面上執行這些動作一樣。 若要將個人化應用到可摺疊部分或索引標籤 (例如，隱藏 FastTab)，您只需選取當它獲得鍵盤焦點或將游標停在上面或索引標籤上時顯示在該區塊或索引標籤旁邊的按鈕。

#### <a name="personalization-tools"></a>個人化工具

**個人化** 工具列上提供了以下工具：

- 使用 **選取** 工具來選取和更改元素的屬性。 若要使用此工具，請選取 **選取** 按鈕，然後選取所需的元素。 將出現元素的屬性視窗，您可以在其中更改該元素的任何屬性。 您可以對頁面上可以個人化的其他元素重複此過程。 請注意，某些個人化屬性在某些情況下可能不可用。 例如，您不能鎖定必填欄位。
- 使用 **隱藏** 工具隱藏頁面元素。 若要使用此工具，請選取 **隱藏** 按鈕，然後選取要隱藏的元素。 當您使用 **隱藏** 工具，所有目前隱藏的元素都會顯示出來，但它們顯示在陰影容器中。 然後，您可以透過選取一個元素來顯示。 若要查看隱藏元素時頁面的外觀，請切換到另一個個人化工具或關閉個人化工具列。
- 使用 **新增欄位** 工具向頁面新增欄位。 使用此工具時，您只能新增屬於頁面定義一部分的欄位。 如需如何建立不屬於目前頁面定義之新欄位的相關資訊，請參閱[建立和使用自訂欄位](user-defined-fields.md)。 選取工具列上的 **新增欄位** 按鈕後，您必須先選取要新增欄位的格線或部分。 對話方塊將顯示與所選格線或部分相關的欄位清單。 在對話方塊中，從 **推薦欄位** 或 **所有欄位** 清單中選取要新增的一個或多個欄位。 選取所需欄位後，選取 **更新**。 若要刪除您之前新增的欄位，請重複該過程，但清除對話方塊中對該欄位的選取。

    **推薦欄位** 清單顯示組織中其他使用者之前新增的欄位。 此欄位清單根據 **推薦批次處理作業** 的重複頻率進行更新。 使用頁面上的篩選器窗格新增新篩選器欄位時存在類似的體驗。

- 使用 **移動** 工具將元素移動到目前元素組中的不同位置。 請注意，您不能將元素移到其父系群組之外。 若要使用此工具，請選取 **移動** 按鈕，然後選取要移動的元素。 當您選取一個元素時，應用程式會確定允許移動該元素的位置。 這些位置被稱為 *放置區*。 當您在目前的組中拖曳元素時，每個放置區都會在可以放置元素的區域旁邊顯示一條彩色的粗線。
- 使用 **跳過** 工具從頁面的鍵盤索引標籤序列中刪除一個元素。 當您選取工具列上的 **跳過** 按鈕時，目前跳過的所有元素都顯示在陰影容器中。 您可以互動式地刪除或新增欄位到索引標籤序列。
- 如果您希望某個欄位出現在 FastTab 的摘要部分中，請使用 **在標題中顯示** 工具。 當您選取工具列上的 **在標題中顯示** 按鈕時，所有被選為匯總欄位的欄位都顯示在陰影容器中。 您可以透過選取欄位以互動方式將欄位新增到 FastTab 匯總並從匯總中刪除欄位。
- 使用 **必填** 工具指定資料輸入所需的元素。 當您選取工具列上的 **必填** 按鈕時，所有已個人化以使其成為必需的元素都顯示在陰影容器中。 您之後可以使它們不再是必填欄位。 此選項在版本 10.0.12 及更高版本中可用，當 **使用個人化根據需要指定欄位** 功能打開時。
- 使用 **鎖定** 工具將元素標記為可編輯或不可編輯。 當您選取工具列上的 **鎖定** 按鈕時，目前無法編輯的所有元素都顯示在陰影容器中。 您之後可以使它們不再具有可編輯性。 請注意，某些必填欄位，不能設為不可編輯。 這些欄位旁邊會出現一個掛鎖符號。
- 使用 **從 Power Apps 新增應用程式** 工具將使用 Microsoft Power Apps 建立的應用嵌入到頁面中。 如需如何將 Power Apps 中的應用程式嵌入頁面的詳情，請參閱[從 Power Apps 嵌入應用程式](embed-power-apps.md)。 此選項僅在[已儲存的檢視表](saved-views.md)功能關閉時可用。
- 使用 **新增應用程式** 按鈕將應用程式 (從 Microsoft Power Apps 或第三方建立的應用程式) 嵌入到頁面中。 此選項僅在[已儲存的檢視表](saved-views.md)功能打開時可用。 
- 使用 **清除** 工具將頁面重設為其預設安裝狀態。 目前頁面上的所有個人化設定都將被清除。 您無法復原此動作。 因此，僅當您確定要重設頁面時才使用此工具。 打開 **已儲存的檢視表** 功能時，此工具會清除現行檢視表的個人化設定。
- 使用 **匯入** 工具從您或其他人之前建立的檔案中載入個人化設定。 

    - 關閉 **已儲存的檢視表** 功能後，您可以選取是新增現有個人化，還是將現有個人化替換為正在為頁面匯入的個人化。 您無法復原此動作。 因此，在您匯入個人化設定後，您必須手動清除或復原您不想要的任何更改。
    - 打開 **已儲存的檢視表** 功能後，匯入的個人化設定將成為頁面上的檢視表。 如果檢視表已經存在，您可以選取跳過匯入、替換有相同名稱的現行檢視表或重新命名匯入的檢視表。

- 使用 **匯出** 工具將頁面的個人化設定儲存到檔案中。 然後，您可以與其他使用者分享您的個人化設定。 這些使用者只需匯入包含您的頁面個人化設定的檔案。 打開 **已儲存的檢視表** 功能後，此工具會將您目前的檢視表儲存到檔案中以供分享。
- 選取 **關閉** 按鈕以關閉 **個人化** 工具列並將頁面回傳到之前的互動狀態。

傳統上，當使用 **個人化** 工具列時，您的個人化設定會在您建立後立即生效。 但是，如果已打開[已儲存的檢視表](saved-views.md)功能，您必須將個人化明確儲存到您選取的檢視表中。

在某些情況下，當您選取工具時，元素旁邊會出現一個掛鎖符號。 此符號表示您無法修改與所選工具相關的元素屬性，因為對這些屬性的更改將阻止頁面正常工作。

### <a name="adding-tiles-lists-and-links-to-a-workspace"></a>向工作區新增圖格、清單和連結

對於包含清單的某些頁面，**新增到工作區** 個人化功能會在動作窗格的 **選項** 索引標籤上的 **個人化** 組中提供。 此功能允許您將相關資訊從現行清單推送到特定工作區。 工作區中顯示的資訊可以根據整個清單，也可以根據清單的篩選和排序版本。 您還可以指定資訊是否以清單、可以顯示清單中項目數量的摘要圖格，或連結的形式顯示在工作區中。

> [!NOTE]
> 如果打開了[已儲存的檢視表](saved-views.md)功能，您推送到工作區的內容將直接連結到檢視表。 該檢視表的查詢功能可將資料擷取到工作區中，工作區中的相應圖格或連結打開該檢視表的頁面，以便套用檢視表的查詢和個人化。 如果檢視表已更新，相應的工作區元素將會調整為新的檢視表定義。

[![新增至工作區。](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- 若要將清單新增到工作區，請先對頁面上的清單進行排序或篩選，以便它顯示您希望它出現在工作區中的資訊。 (如果 **已儲存的檢視表** 功能已打開，您無法繼續，直到您儲存具有這些條件的檢視表。) 然後選取 **新增到工作區**。 選取一個工作區，然後在 **報表** 欄位中選取 **清單**。 選取 **設定** 後，將出現一個對話方塊，您可以在其中選取應出現在工作區清單中的資料欄。 您還可以指定用於工作區中清單的標籤。
- 若要將圖格新增到工作區，先篩選頁面上的清單，以便它顯示應匯總或您希望快速存取的資料。 (如果 **已儲存的檢視表** 功能已打開，您無法繼續，直到您儲存具有這些條件的檢視表。) 然後選取 **新增到工作區**。 選取一個工作區，然後在 **報表** 欄位中選取 **圖格**。 選取 **設定** 後，將出現一個對話方塊，您可以在其中指定應用於工作區中的圖格的標籤。 您還可以指定圖格是否應顯示計數。 將圖格新增到工作區後，您可以選取它以從工作區打開目前的頁面。 然後，您可以查看與圖格相關的篩選清單。
    - 從版本 10.0.26 開始，如果啟用了 **允許使用者選取和更改圖格尺寸** 功能，您可以在 **設定圖格** 對話方塊中為新圖格從四種可用的 **圖格尺寸** 選取其中之一。 此功能還允許您在直接從工作區建立圖格後調整圖格大小。   
- 若要新增前往工作區的連結，請先篩選頁面上的清單，以便它顯示您感興趣的資料。 (如果 **已儲存的檢視表** 功能已打開，您無法繼續，直到您儲存具有這些條件的檢視表。) 然後選取 **新增到工作區**。 選取一個工作區，然後在 **報表** 欄位中選取 **連結**。 選取 **設定** 後，會出現一個對話方塊，您可以在其中指定應用於連結的標籤。 您還可以選取為可以放置此連結的區塊指定標籤。 如果該部分不存在，將建立一個新區塊。

> [!NOTE]
> 從版本 10.0.25 開始，當您設定清單、圖格或連結時，可能還必須選取您想新增元素的工作區檢視表，如果 **(預覽) 工作區的已儲存檢視表支援** 功能已啟用。 可用的工作區檢視表將出現在每個 **設定** 對話方塊的 **工作區選項** 區塊。 

將清單、圖格或連結新增到工作區後，您可以打開該工作區並根據需要重新排列其中的元素。

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>將工作區中的摘要新增到儀表板

有些工作區包含計數圖格 (即上面有數字的圖格)，您可能希望這些圖格也出現在儀表板上。 在工作區中，按右鍵點選計數圖格，選取 **個人化**，然後在圖格的屬性視窗中，選取 **釘選到儀表板**。 下次打開並重新整理儀表板時，該計數將顯示在該工作區的導覽圖格下方。 您可以選取該計數以直接轉到它所代表的資料。

### <a name="changing-the-size-of-a-tile"></a>更改圖格的大小
從版本 10.0.26 開始，**允許使用者選取和更改圖格大小** 功能允許使用者透過個人化修改任何非 KPI 圖格的大小。 在工作區中，按右鍵點選圖格，然後選取 **個人化**。 在圖格的屬性視窗中，從 **圖格尺寸** 選項選取所需的大小。 圖格尺寸將立即調整。 如果 **(預覽) 工作區的已儲存檢視表支援** 功能已啟用，您可以將此個人化設定儲存到工作區檢視表。  

### <a name="personalizing-your-dashboard"></a>個人化您的儀表板

該儀表板通常是您打開應用程式時看到的第一頁。 透過使用本主題前面描述的相同機制，它可以和系統中的其他頁面一樣進行個人化。 

> [!WARNING]
> 目前，當您在儀表板上隱藏內容時，直接定位圖格而不是其周圍的空間非常重要。 如果您將群組隱藏在圖格周圍，如果稍後新增更多圖格，或者如果系統切換到不同的語言，則可能會出現意外結果。

儀表板上提供的一項獨特個人化功能是新增圖格的功能。 

- 如果 **整頁應用程式** 功能已關閉，您可以透過按右鍵點選儀表板上的元素來新增新圖格，然後選取 **新增工作區**。 在儀表板底部建立一個新的工作區圖格。 您可以根據需要重命名這個新的工作區圖格。 您還可以將清單、圖格和連結新增到工作區，如本主題的[將圖格、清單和連結新增到工作區](personalize-user-experience.md#adding-tiles-lists-and-links-to-a-workspace)章節中所述。
- 如果 **整頁應用程式** 功能已打開，您可以透過按右鍵點選儀表板上的元素來新增新圖格，然後選取 **新增應用程式**。 在對話方塊中，選取是要為新工作區新增圖格還是包含來自 Power Apps 或網站內容的圖格。 然後按照步驟設定您選取的選項。 在儀表板底部建立一個新的圖格。 如需如何新增、編輯、刪除和分享這些嵌入式應用程式的相關資訊，請參閱[從 Power Apps 嵌入畫布應用程式](embed-power-apps.md)和[嵌入第三方應用程式](embed-website.md)。

## <a name="sharing-personalizations"></a>分享個人化

個人化頁面後，您可以使用幾種方法與其他使用者分享您的個人化設定。 在以下清單中，這些方法按最推薦到最不推薦的順序排列。

1. 將檢視表發佈給使用者。
2. 將檢視表或個人化複製給使用者。
3. 匯出和匯入檢視表或個人化。

### <a name="publish-views-to-users"></a>將檢視表發佈給使用者

如果[已儲存的檢視表](saved-views.md)功能已打開，如果頁面支援檢視表，與其他使用者分享個人化設定的最佳方式就是將檢視表發佈給有一個或多個資訊安全角色的使用者。 如需更多資訊，請參閱[發佈檢視表](saved-views.md#publishing-views)。

### <a name="copy-views-or-personalizations-to-users"></a>將檢視表或個人化複製給使用者

如果[已儲存的檢視表](saved-views.md)功能已關閉，或者如果頁面不支援檢視表，則分享個人化設定的推薦方法是在使用者之間複製它們。 此方法僅適用於具有權限的使用者 (例如，系統管理員)。 但是，管理員可以在系統中查詢特定使用者的個人化設定 (如果啟用了已儲存的檢視表，則包括使用者的個人檢視表) 並將設定複製給其他使用者。

如果啟用了已儲存的檢視表，請按照以下步驟複製個人化設定。

1. 進入 **系統管理\>設定\>個人化**。
2. 請按照以下步驟複製個人檢視表：

    1. 選取 **個人檢視表**。
    2. 在清單中選取所需的檢視表。
    3. 選取 **複製到使用者**。
    4. 選取要分發檢視表的使用者。

    請按照以下步驟在不支援檢視表的頁面上複製個人化設定：

    1. 選取 **使用者設定**。
    2. 選取具有您要分發個人化設定的使用者。
    3. 選取 **管理所有個人化**。
    4. 在清單中選取所需的個人化設定。
    5. 選取 **複製到使用者**。
    6. 選取要分發個人化的使用者。

如果未啟用已儲存的檢視表，請按照以下步驟複製個人化設定。

1. 進入 **系統管理\>設定\>個人化**。
2. 選取 **套用**。
3. 選取要分發個人化的使用者。
4. 選取 **選取現有的個人化**。
5. 尋找並選取您感興趣的 (單個) 個人化。
6. 選取 **確定**。

### <a name="export-and-import-views-or-personalizations"></a>匯出和匯入檢視表或個人化

分享個人化的另一種方法是透過匯出和匯入。 個人使用者或代表他們行事的管理員可以使用此方法匯出他們的個人化設定或檢視表，然後將匯出的檔案提供給其他使用者進行匯入。 或者，使用者可以將他們匯出的個人化設定提供給具有管理員權限的使用者，然後該使用者可以使用 **個人化** 管理頁面將個人化檔案同時套用於多個使用者。

> [!IMPORTANT]
> 由於個人化在更新中持續存在，因此在服務更新後或任何其他時間重新匯入所有個人化是不必要的，並且強烈建議不要這樣做。

#### <a name="export"></a>匯出

通常，您可以透過打開相應頁面、打開 **個人化** 工具列，然後選取 **匯出** 來匯出您自己的檢視表或個人化設定。 如需工具列的相關資訊，請參閱本主題前面的[個人化工具列](#personalization-toolbar)章節。 或者，如果 [已儲存的檢視表](saved-views.md)已啟用，您可以進入 **設定\>使用者選項\>個人化** 查看系統中所有個人化設定的清單。 您可以從那裡選取要匯出的檢視表或個人化設定，然後選取 **匯出**。

此外，管理員可以按照以下步驟匯出其他使用者的個人化設定。

1. 進入 **系統管理\>設定\>個人化**。
2. 在 **使用者** 索引標籤，選取所需的使用者。
3. 尋找並選取您感興趣的檢視表或個人化。
4. 選取 **匯出**。

#### <a name="import"></a>匯入

若要匯入檢視表或個人化設定，您只需打開 **個人化** 工具列並選取 **匯入**。 此外，管理員可以匯入檔案並立即將其提供給一個或多個使用者。

如果啟用了已儲存的檢視表，請遵循以下步驟。

1. 進入 **系統管理\>設定\>個人化**。
2. 在動作窗格上，選取 **匯入檢視表\>使用者檢視表**。
3. 選取匯入模式：

    - **選取特定使用者** – 為選定的使用者提供檢視表或個人化設定。
    - **按原樣匯入** – 將檢視表或個人化匯入匯出它的同一使用者。

4. 選取 **瀏覽**，然後找到並選取要匯入的個人化設定。
5. 選取 **下一步**。
6. 如果您選取步驟 3 中的 **選取特定使用者**，選取要匯入個人化的使用者。
7. 選取 **匯入**。
8. 根據需要解決衝突。

如果未啟用已儲存的檢視表，請遵循以下步驟。

1. 進入 **系統管理\>設定\>個人化**。
2. 選取 **套用**。
3. 選取要分發個人化的使用者。
4. 選取 **從檔案匯入個人化**。
5. 選取 **瀏覽**，然後找到並選取要匯入的個人化設定。
6. 選取 **確定**。

## <a name="administration-of-personalizations"></a>個人化管理

**個人化** 頁面是在組織級別管理個人化的中樞。 此頁面上的內容和功能取決於是否已打開 **已儲存的檢視表** 功能。

對於已開啟 **儲存的檢視表** 功能的客戶，請參閱[已儲存的檢視表](saved-views.md)主題中的「全域管理檢視表」章節。

對於尚未打開[已儲存的檢視表](saved-views.md)功能的客戶，此頁面有四個索引標籤：

- **套用** – 您可以為一個或多個使用者匯入或選取個人化設定。 若要將個人化應用到一個或多個使用者，請先選取一個角色和擁有該角色的使用者。 然後選取一個現有的個人化套用到選定的使用者，或者匯入一個個人化檔案。 個人化經過驗證，並將在所有選定使用者下次打開選定頁面時套用到上面。
- **清除** – 您可以清除一個或多個使用者的頁面或工作區的所有個人化設定。 先選取一個頁面或工作區以查看對其進行個人化設定的使用者清單。 然後選取應該清除該頁面或工作區的個人化設定的使用者，然後選取 **清除**。 所選使用者已應用於所選頁面或工作區的所有個人化設定都將被刪除。 您無法復原此動作。 但是，如果為頁面或工作區儲存了個人化設定，則可以重新匯入該個人化設定。
- **使用者** – 選取使用者以查看使用者已個人化的頁面清單。 然後，您可以打開或關閉該使用者對特定頁面或整個系統使用個人化的能力。 您還可以為使用者匯入、匯出或清除個人化設定。 此外，您可以為使用者重設功能標註。 在這種情況下，如果使用者之前關閉了任何引入新功能的彈出視窗，它們將在使用者下次遇到這些功能時再次出現。
- **系統** – 您可以暫時關閉系統中所有使用者的個人化。 在這種情況下，將刪除所有使用者的所有個人化設定，並將所有頁面重設為其預設狀態。 如果您稍後重新打開個人化，則會重新套用所有個人化設定。 您還可以永久刪除系統中所有使用者的所有個人化設定。 已刪除的個人化設定無法還原。 因此，在執行此工作之前，請務必匯出您以後可能需要的任何個人化設定。

## <a name="personalizing-inventory-dimensions"></a>個人化庫存維度

當您對頁面上的庫存維度設定進行個人化設定時，請考慮使用 **顯示維度** 選項建立的設定。 例如，您使用個人化來隱藏批次編號庫存維度的資料欄，但該欄會在下次打開頁面時出現。 出現此問題的原因是 **維度顯示** 設定控制顯示的庫存維度欄。 **尺寸顯示** 設定適用於所有頁面，並覆寫各個頁面上庫存維度欄位的任何個人化設定。

因此，在前面的範例中，如果您不希望批次編號庫存維度的資料欄顯示在頁面上，則必須清除該維度作為該頁面的 **顯示維度** 選項的一部分。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
