---
title: 流程指南框架
description: 本主題為以 X++ 延伸倉庫行動流程的開發人員提供有關流程指南框架的資訊。
author: Mirzaab
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6882c979ad9b37eb4f95a04259b6ac0f0a0edcdc
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449526"
---
# <a name="process-guide-framework"></a>流程指南框架

[!include [banner](../includes/banner.md)]

本主題為以 X++ 延伸倉庫行動流程的開發人員提供有關流程指南框架的資訊。 倉庫行動流程分成數個小步驟，因此是可以延伸的。 每個步驟的業務邏輯和使用者介面建構已被提取到個別的類別中，因此能夠延伸。

## <a name="overview-of-the-existing-design"></a>現有設計概觀

倉庫行動執行流程是透過單一自訂服務端點公開的。 要求是以 XML 字串形式從行動應用程式到達的，其中包含在行動應用程式中呈現的使用者介面中斷資料，以及使用者輸入的值。

收到要求時，第一步是將此 XML 還原序列化。 **WHSMobileAppServiceXMLTranslator** 類別會將 XML 轉換為容器，其中包含控制資訊與工作階段資訊。

之後，會使用容器中的資訊來推斷使用者正在使用或即將啟動的倉庫流程 (由 **WHSWorkExecuteMode** 列舉代表)，並相應地具現化 **WHSWorkExecuteDisplay** 的衍生類別。 系統會叫用 **displayform()** 方法，然後執行下列動作：

-   處理來自使用者的資料 (委派給 **WHSRFControlData** 類別，但有些流程會透過覆寫 **processControl()** 方法來實作特定的邏輯)。

-   執行業務邏輯。

-   遞增步驟。

-   建構代表新使用者介面的容器 (通常以 **build…()** 方法)。

然後將容器傳回給翻譯器，翻譯器接著會將 XML 序列化，並作為回應傳回到行動裝置。

以下序列圖顯示執行流程的概觀。 請注意，此圖更像是示意圖概觀，而不是實際程式碼的 1：1 表示。

![流程的示意圖概觀。](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>重新設計的原因

上述設計提供一個非常簡單的框架，以建構在行動流程中使用的流程。 然而如上所示，**displayform()** 方法承擔多個責任。 它會將這些責任委派給其他方法和類別，但是在缺乏具體類別責任的情況下，各類別之間會以不一致的方式完成。 此外，隨著支援的案例數目有組織化的成長，其中的一些類別會變得相當複雜。 為了讓事情更加有趣，其中一些類別/方法會被覆蓋並在多種模式中重複使用。 結果是產生極長的方法，且具有高度的循環複雜度。 這在過去導致維護上的問題。 修正這些方法中的程式錯誤是有風險的，並且容易回復故態。
例如，**WhsWorkExecuteDisplay** 類別中的 **processWorkLine()** 方法是從多個流程中參考的 (基本上是執行工作的任何位置)。

為了使這些方法可延伸，其中一種選項是將 **displayForm** 方法分割成更小的方法，並引入可延伸點。 但是由於案例矩陣之故，對撰寫延伸模組和驗證復原的合作夥伴而言，是一項挑戰。 不僅如此，由於缺乏上述的結構化責任分配，因此程式碼會隨著時間以不可預測的方式不斷增長，進而對建構有品質的延伸模組形成挑戰。

因此，重新設計是可永續的選擇，目標是明確定義一個具有獨立責任的類別。 一個類別應該有一個責任，一個變更的理由，及一個延伸的理由。

## <a name="design-overview"></a>設計概觀

在重新設計的框架中，核心策略圍繞兩個原則：將執行流程劃分為單個元件，每個元件具有定義明確的責任及定義明確的延伸點。

新框架的名稱是「ProcessGuide」。 這是因為這些類別的目標是引導使用者完成業務流程 (與豐富型用戶端相反，豐富型用戶端是一種以表單為基礎的體驗，其中使用者在與資料互動上或執行工作的順序方面，擁有更大的彈性)。

> [!NOTE]
> 一個值得注意的細節是刻意省略了 “WHS” 首碼。 雖然行動流程一開始是為了倉庫引入的，但之後它們已經超越了界限，可支援各種生產和庫存管理流程。 因此，倉庫參考被排除在框架的名稱中。

為了識別元件，第一步是查看生產啟動流程 (**WhsWorkExecuteDisplayProdStart** 類別)。 以下是流程示意圖。

![示意圖流程圖。](media/production-start-process-schematic.png)

查看控制流程，以下是所需的元件：

-   一個控制器，用於結合整個業務流程。
-   一個步驟，負責執行流程中的一個步驟。
-   一個資料處理器，用於處理一個步驟中的資料。
-   一個頁面產生器，負責為步驟建立使用者介面。
-   一個瀏覽代理程式，負責步驟轉換。
-   一個類別，負責執行業務流程。

在上面的流程圖中，如果您從步驟 1 開始，並開始處理上一步中的資料，然後以建構 UI 結束，則將在下一步中繼續處理資料。 這會讓連續步驟之間有緊密聯結，因此我們新的概況示意圖如下所示：

![概況示意流程圖。](media/high-level-schematic.png)

以下是重新設計流程中的關鍵元件：

-   **ProcessGuideController** - 此類別會協調業務流程的整體執行。 它定義了具現化步驟和瀏覽代理程式的處理站，處理站隨後會構成流程執行，以及用於取消或結束流程的清理邏輯。

-   **ProcessGuideStep** - 此類別代表業務流程中的一個步驟。 此類別包含了處理站的定義，這些處理站會具現化頁面產生器、動作及資料處理器，並負責以正確的順序叫用它們。

-   **ProcessGuideNavigationAgent** - 此類別負責在步驟之間瀏覽。 當一個步驟完成時，瀏覽代理程式會負責定義下一步，並將上一步為了通訊所需的任何參數傳遞給下一步。

-   **ProcessGuidePageBuilder** - 這個類別負責具現化使用者介面。

-   **ProcessGuide 動作** - 這個類別代表一個動作，向使用者顯示成一個按鈕。

-   **ProcessGuideDataProcessor** - 這個類別負責處理使用者在欄位中輸入的資料。

## <a name="execution-flow"></a>執行流程

執行流程的起點保持不變。 因此，要求仍然透過相同的端點到達，接著將 XML 還原序列化到容器中。 然後將此容器傳遞給 **getNextFormState()**。

有三個重要的類別需注意：

-  **ProcessGuideSessionState** – 這包含工作階段狀態資訊 – 正在執行的模式、傳遞、控制器和步驟。

-  **ProcessGuidePage** – 這包含使用者介面中繼資料的強型別表示。

-  **ProcessGuideRequest** – 這包含上述兩個成員，且為從行動裝置中收到的強型別表示。

這些類別是使用容器資訊建立的 (狀態與使用者輸入的控制資料)。 這提供了一種類型安全的方式來存取與操縱值。 與在此流程中重複存取容器相比，這對可讀性和效能方面都有益處。

此工作階段狀態資訊用於具現化正確的 **ProcessGuideController** 類別。 一旦具現化，便會叫用 **ProcessGuideController** 類別中的 **createResponse()** 方法。 此方法是流程指南邏輯的入口點，在執行後會隨同回應返回 (以 **ProcessGuideResponse** 類別表示)。 然後將回應轉換回容器，並交還給傳統型邏輯，再將其序列化為 XML，並將回應傳回給行動裝置。

接下來，控制器必須找到要執行的下一步。 如果這是一個新流程的開始，控制器將呼叫 **initialStep()**，以取得流程中的第一步。 之後，它會呼叫 **ProcessGuideStep** 中的 **execute()** 方法。 然後，此方法將具現化 **ProcessGuidePageBuilder** 類別，並呼叫 **buildPage()**，這會傳回 **ProcessGuidePage** 物件，此物件是呈現給使用者的使用者介面虛擬表示。 然後該步驟會將結果傳送回控制器，接著控制器將儲存目前工作階段狀態，再將結果以 **ProcessGuideResponse** 類別的形式傳回給 **getNextFormState()**。 此後，回應會轉換回容器，隨後序列化為 XML，並將回應傳送回行動裝置。

以下順序圖解釋此控制流程。 請注意，這是最常見的控制流程，以簡化對設計的解釋。

![控制流程簡化。](media/control-flow.png)

當使用者按一下按鈕 (或掃描值 – 這通常會觸發預設動作) 對行動裝置採取動作時 – 此要求會透過相同的路由到達  **ProcessGuideController** 類別中的 **createResponse()** 方法。 然而這一次控制器會從工作階段狀態資訊中知道使用者處於哪個步驟。 因此，它會具現化適當的 **ProcessGuideStep** 類別，並叫用執行方法。 反過來，**ProcessGuideStep** 會讀取由使用者叫用的動作名稱，然後具現化適當的 **ProcessGuideAction** 類別並呼叫 **execute()**。

**ProcessGuideAction** 類別會負責執行特定的動作，但有兩個要注意的例外狀況。

第一個是 **ProcessGuideOKAction** 類別。 這個動作意味著使用者想要確認並在這個流程中前進。 據此，此方法實際上是對 ProcessGuideStep 類別執行回撥，這表示該步驟會在 **ProcessGuideDataProcessor** 中叫用  **processData()**。 這會處理使用者已輸入的資料，然後更新步驟的狀態並將結果傳回給控制器。 視處理器的結果，此步驟會叫用頁面產生器以產生適當的使用者介面，或將步驟的狀態設定為已完成。 這會反映在下方序列圖的上半部分。

另一個例外狀況是在 **ProcessGuideCancelResetProcessAction** 和 **ProcessGuideCancelExitProcessAction** 類別中實作的取消動作。 這些動作表示要取消流程並返回流程起點或完全離開流程的意圖。 類似於 **確定** 動作，這些動作也會執行對步驟的回撥，這會對 **ProcessGuideController** 發出意圖的信號。 然後控制器會執行必要的狀態變數清理，或將控制項移至流程中的初始步驟，或者完全終止過程。

步驟完成後，如果步驟的狀態設定為 **已完成**，則控制器會具現化 **ProcessGuideNavigationAgent**，這會傳回下一步的名稱。 然後控制器會具現化這個步驟，並調用 **execute()** 方法，再循環繼續。 最常見的是，新步驟叫用對應的 **ProcessGuidePageBuilder**，為要呈現給使用者的下一個畫面產生使用者介面，然後傳回此介面。 下方序列圖的下半部說明此流程。

![序列圖。](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>使用 ProcessGuide 框架產生新流程

解釋控制流程的最佳方式就是使用存在於應用程式中的範例 – 生產啟動流程。

## <a name="overview-of-the-production-start-process"></a>生產啟動流程概觀

讓我們從了解流程開始。 第一步，提示使用者輸入生產訂單識別碼。

![提示輸入生產識別碼。](media/production-id-prompt.png)

當使用者輸入生產訂單識別碼後，會驗證訂單編號。 某些驗證的執行是根據訂單是否位在與使用者用戶登入的同一個倉庫中，以及訂單的狀態。 如果驗證失敗，則會向使用者顯示一則錯誤訊息。 如果驗證成功，則會向使用者顯示生產訂單和品項的詳細資料。

使用者可以取消以返回流程的起點，或按一下 **確定** 進行確認。 若為後者，生產訂單會設定為 **已開始** 狀態、過帳對應的日記帳、控制項移回第一步，並向使用者顯示「工作已完成」訊息。


## <a name="creating-the-controller"></a>建立控制器

建構業務流程的第一步是建立控制器類別，這會從實作控制器預設行為的 **ProcessGuideController** 抽像類別中延伸。 新類別名稱是 **ProdProcessGuideProductionStartController**，並會裝飾 **StartProdOrder** 的 **WHSWorkExecuteMode** 值。 系統會使用在 **WHSWorkExecuteDisplay** 類別中使用的同一個以 **SysExtension** 為基礎具現化，這有助於在使用者為此模式執行功能表項目時具現化控制器。

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> 類別的命名模式為 **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>Controller**。 此模式用於控制器類別，並延伸至其他類別。


## <a name="building-the-first-step"></a>建構第一步

接下來為了定義第一步，請建立從 **ProcessGuideStep** 延伸的 **ProdProcessGuidePromptProductionIdStep** 類別。

具現化類別的工作會委派給步驟處理站，此處理站由 **ProcessGuideController** 基礎類別叫用。 處理站的預設實作會根據名稱具現化該步驟。 因此，若要具現化 **ProdProcessGuidePromptProductionIdStep** 成為控制器的第一步，您必須做兩件事：

-   使用 **ProcessGuideStepName** 屬性裝飾 **ProdProcessGuidePromptProductionIdStep** 類別。

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   在控制器類別中，實作抽象方法 **initialStepName()** 以傳回步驟名稱。

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> **ProcessGuideStepName** 屬性中的值不需要完全符合如上顯示的類別名稱。 但是實作這一點，便可在使用類別時讓交互參照之間能夠統一並具備類型安全性。 建議使用此命名慣例。
>
> 此步驟以 **ProcessGuideStepName** 為基礎的具現化是在 **ProcessGuideStepDefaultFactory** 類別中實作的。 在您需要不同的策略來具現化步驟的這個極少見的狀況下，您必須執行以下動作：
> -   建立一個繼承自 **ProcessGuidStepAbstractFactory** 的新處理站類別。
> -   或者，建立一個新的參數類別來實作 **ProcessGuideIStepCreationParameters** 介面，其中包含處理站需要的參數。
> -   在您的控制器類別中，覆寫 **stepFactory()** 和 **stepCreationParameters()** 方法，以傳回上述處理站和參數。

下一步是實作 **ProdProcessGuidePromptProductionIdStep** 類別的功能。 您必須實作一個邏輯來建構使用者介面、處理使用者輸入的資料，以及決定步驟何時完成。

### <a name="building-the-user-interface-for-the-first-step"></a>建構第一步的使用者介面

使用者介面是使用繼承自 **ProcessGuidePageBuilder** 抽象類別的類別建構的。 針對此步驟，為此類別命名以代表其用途 – **ProdProcessGuidePromptProductionIdPageBuilder**。

此類別的具現化機制類似於從控制器具現化該步驟的方式。 

-   使用 **ProcessGuidePageBuilderName** 屬性裝飾 **ProdProcessGuidePromptProductionIdPageBuilder** 類別。

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   在 **ProdProcessGuidePromptProductionIdStep** 類別中，實作抽象方法 **pageBuilderName()** 以傳回此名稱。

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> 與步驟處理站類似，也有為頁面產生器處理站實作的抽象處理站模式。 因此，在您需要不同的策略來具現化頁面產生器的這個極少見的狀況下，您可以執行以下動作：
> - 建立一個繼承自 **ProcessGuidePageBuilderAbstractFactory** 的新處理站類別。
> - 或者，建立一個新的參數類別來實作 **ProcessGuideIPageBuilderCreationParameters** 介面，其中包含處理站需要的參數。
> - 在您的步驟類別中，覆寫 **pageBuilderFactory()** 和 **pageBuilderCreationParameters()** 方法，以傳回上述處理站和參數。

若要實作使用者介面，您需要一個頁面，其中包含一個文字方塊可輸入生產訂單識別碼，還要有 **確定** 按鈕和 **取消** 按鈕。 **取消** 按鈕應結束流程。

若要實作這一點，您必須在 **ProdProcessGuidePromptProductionIdPageBuilder** 類別中覆寫兩個方法：

-   使用 **addDataControls()** 方法新增文字方塊。

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   使用 **addActionControls()** 方法以新增 **確定** 和 **取消** 按鈕。

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

這會新增資料控制項，然後是按鈕。 但是，如果您想建構一個畫面，其中散置著資料控制項與資料，則您可以很有彈性地改為覆寫 **addControls()** 方法。

另一個需要考慮的案例是當驗證失敗時，例如使用者輸入不正確的生產訂單識別碼，要如何重建頁面。 **ProcessGuidePageBuilder** 基底類別會實作預設行為，這會重建使用者介面、清除掃描的值，並新增帶有錯誤訊息的錯誤控制項。 因為這是您要使用的預設行為，所以您不需要新增任何程式碼來處理錯誤。

> [!TIP]
> 如果您想要針對錯誤情況實作自訂 UI 行為，您可以覆寫一或多個 **rebuildFromRequestPage()**、**isErrorState()** 和 **reuseRequestPageOnError()** 方法。

### <a name="processing-the-user-entered-data-in-the-first-step"></a>處理第一步中使用者輸入的資料

資料的處理是在 **ProcessGuideDataProcessorDefault** 類別中完成的，而這又會叫用傳統型 **WhsRfControlData** 類別。 不需要變更此預設行為，且 **WhsRfControlData** 已經具備邏輯可驗證 **ProdId** 欄位，因此您不需要編寫任何邏輯來處理此狀況。 如果需要延伸模組來驗證邏輯，請考慮使用以 **WhsControl** 為基礎的基於延伸模組機制。

### <a name="determine-if-the-first-step-is-complete"></a>判斷第一步是否完成

驗證成功後，即可將該步驟標記為已完成。 這是在基底類別中完成的，但是您需要實作條件來確定步驟完成。 以下已覆寫的方法可以做到這一點。

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>第二步：檢視訂單詳細資料並確認

在該流程的第二步中，向使用者顯示一個畫面，其中包含訂單的詳細資料。 使用者可以按一下 **確認** 按鈕來確認生產訂單開始，或按一下 **取消** 返回流程的起點。 就此範例而言，將步驟命名為 **ProdProcessGuideConfirmProductionOrderStep**，將頁面產生器類別命名為  **ProdProcessGuideConfirmProductionOrderPageBuilder**。

ProdProcessGuideConfirmProductionOrderStep 類別如下所示。

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

由於使用者在此處未輸入任何值，因此您不需要覆寫 **isComplete()** 方法。 當使用者按一下 **確定** 時步驟即完成。

頁面產生器類別會覆寫 **addDataControls()** 方法以新增三個標籤。 第一個標籤顯示生產訂單識別碼，第二個包含品項資料 (例如品項識別碼、尺寸或描述)，第三個包含數量和測量單位。

接著會覆寫 **addActionControls()** 來新增兩個按鈕 – 一個是 **確定** 按鈕，另一個是 **取消** 按鈕來取消流程並返回流程的起點。

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> 您可以使用 Application Explorer 針對此主題找到 X++ 方法的相同原始程式碼。 篩選類別名稱，然後以右鍵按一下該類別名稱，並選取 **檢視程式碼**。

### <a name="step-3-start-the-production-order"></a>第三步：啟動生產訂單

第三步是執行啟動生產訂單的業務邏輯。 此步驟與先前的步驟略有不同，因為此步驟沒有使用者介面。 當使用者在上一步中按一下 **確定** 時，此步驟會以無訊息的方式執行。

**ProcessGuideStepWithoutPrompt** 抽象類別會實作此類步驟的預設行為。 因此目前步驟應延伸 **ProcessGuideStepWithoutPrompt** 類別並覆寫 **doExecute()** 方法。

以下的程式碼範例顯示類別與 **doExecute()** 方法實作。 此方法只會從工作階段狀態中擷取訂單識別碼與使用者識別碼，並叫用該方法來啟動此生產訂單。

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

如果發生例外狀況，處理邏輯的框架例外狀況會確定此流程已復原到上一步。

> [!NOTE]
> 對 **addProcessCompletionMessage()** 的叫用會將「工作已完成」訊息新增至瀏覽參數。 下一步 (假設其有使用者介面) 將顯示此訊息。 基底類別會處理此邏輯，且不需要將特定程式碼新增至流程類別，就能實現此行為。


### <a name="building-the-navigation-through-the-steps"></a>透過步驟建構瀏覽

**ProcessGuideController** 基底類別會將 **ProcessGuideNavigationAgentDefault** 類別具現化，其依賴於預先定義的瀏覽路由，該路由是來源與目標步驟的簡單對應。 對於生產啟動案例，由於沒有條件式分支，所以此實作就已足夠。 因此您只需要覆寫 **initializeNavigationRoute()** 方法來定義瀏覽路由。

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

有些流程會有條件式分支 (以使用者動作或任何其他條件為基礎)。 此類流程需要執行以下動作：

-   實作從 **ProcessGuideNavigationAgent** 類別繼承的特定瀏覽代理程式。

-   實作繼承自 **ProcessGuideNavigationAgentAbstractFactory** 類別的特定瀏覽代理程式處理站，其中包含的邏輯可根據目前步驟、工作階段狀態、使用者動作或其他邏輯來具現化正確的瀏覽代理程式。

-   或者，覆寫控制器類別中的 **navigationAgentCreationParameters()**，以傳遞適合的參數。

-   覆寫控制器中的 **navigationAgentFactory()**，以具現化上述建立的瀏覽代理程式處理站。

### <a name="action-classes"></a>動作類別

動作類別代表使用者動作，所以此範例使用 **確定** 動作以顯示如何建立動作。

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

此類別必須實作 2 個抽象方法：

-   **label()**，會傳回要在與此動作繫結的按鈕控制項中顯示的標籤。

-   **doExecute()**，會執行動作。 如前所述，**確定** 按鈕只是對步驟執行回撥。 但是，此處的其他動作可能具有更複雜的邏輯。

動作是根據 **ProcessGuideActionName** 屬性的 **SysExtension** 框架具現化的。 與頁面產生器的具現化類似，步驟類別會實作預設動作處理站，並且可以覆寫該處理站。 頁面產生器新增一個像這樣的按鈕控制項。

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

這樣做時，它會要求該步驟為傳遞的名稱建立一個動作類別，並將該動作與按鈕繫結在一起。

### <a name="summary"></a>摘要

為了總結本主題中解釋的所有內容，以下是該流程所需程式碼的綜合摘要：

1.  **ProdProcessGuideProductionStartController**

    1.  覆寫 **initialStepName()** 以提供此步驟的名稱。
    2.  覆寫 **initializeNavigationRoute()** 以建構導覽地圖。

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  覆寫 **isComplete()** 以指定該步驟何時視為完成。
    2.  覆寫 **pageBuilderName()** 以指定要使用的頁面產生器。

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  覆寫 **addDataControls()** 以新增 **Prod ID** 文字方塊。
    2.  覆寫 **addActionControls()** 以新增 **確定** 與 **取消** 按鈕。
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  覆寫 **pageBuilderName()** 以指定要使用的頁面產生器。
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  覆寫 **addDataControls()** 以新增訂單、品項及數量資訊標籤。

    2.  覆寫 **addActionControls()** 以新增 **確定** 與 **取消** 按鈕。
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > **generateItemInfoForProdId()** 方法 (用於產生品項資訊標籤) 不在本主題的討論範圍內。 此方法會查詢一些資料表，以取得品項識別碼、描述及尺寸。 如果您想要進一步瞭解 **generateItemInfoForProdId()**，請查看原始程式碼。

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  覆寫 **doExecute()** 以執行生產啟動流程，並新增流程完成訊息。

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> 請注意，很多常用模式 (發生錯誤時重新產生 UI、設定流程完成訊息、**確定** 及 **取消** 行為) 已移至該框架，因此讓應用程式開發人員免於編寫重複使用的程式碼，這類編寫既容易發生錯誤，並有流程之間行為不一致的風險。 當案例需要偏離常用路徑時，會提供給應用程式開發人員可覆寫適合方法的選項，但這是一種明確且可追蹤的刻意偏離。


### <a name="extending-a-business-process"></a>延伸業務流程

目前為止，本主題重點介紹如何使用 **ProcessGuide** 框架建構新流程。 在最後一節中，提供一些如何延伸此業務流程的範例。

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>在流程中新增步驟 (使用 ProcessGuideNavigationAgentDefault)

延伸位置：

-   流程其 **ProcessGuideController** 類別的子系。

延伸方式：

-   延伸控制器類別中的 **initializeNavigationRoute()** 方法，並叫用 **ProcessGuideNavigationRoute** 類別中的 **addFollowingStep()**。

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>在流程中新增步驟 (使用自訂瀏覽代理程式)

延伸位置：

-   **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent** 的子系。

延伸方式：

-   建立 **ProcessGuideNavigationAgent** 的新子系類別，此類別會傳回所需的步驟名稱。

-   建立從 **ProcessGuideNavigationAgentFactory** 衍生的新類別，這會有條件地傳回上述建立的瀏覽代理程式。

-   延伸控制器類別中的 **navigationAgentFactory()** 方法，以傳回上述建立的處理站。

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>在現有步驟的 UI 中新增新控制項 

延伸位置：

-   步驟其 **ProdProcessGuidePageBuilder** 的子系。

延伸方式：

-   延伸 **addDataControls()** 方法並新增附加控制項。

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>在現有步驟中徹底檢修使用者介面

延伸位置：

-   **ProdProcessGuideStep** 的子系。

延伸方式：

-   建立 **ProdProcessGuidePageBuilder** 類別的新子系類別，並實作所需的使用者介面。

-   在步驟類別中延伸 **pageBuildeName()** 方法，以傳回上述建立類別的 **ProcessGuidePageBuilderNameAttribute**。

### <a name="alter-logic-when-a-step-is-considered-complete"></a>當一個步驟視為完成時改變邏輯

延伸位置：

-   **ProdProcessGuideStep** 的子系。

延伸方式：

-   延伸 **isComplete()** 方法以建構附加邏輯。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]