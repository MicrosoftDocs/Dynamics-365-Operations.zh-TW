---
title: 需求預測設定
description: 本主題說明為準備需求預測而必須執行的設定工作。
author: ChristianRytt
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f53171361b655ab4ae05894d098203df0af8d60
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449607"
---
# <a name="demand-forecasting-setup"></a>需求預測設定

[!include [banner](../includes/banner.md)]

本主題說明如何設定需求預測。  

## <a name="item-allocation-keys"></a>項目分配索引鍵

項目分配索引鍵建立項目群組。 僅有在項目是項目分配索引鍵的一部分時，才會為項目及其維度計算需求預測。 強制執行此規則以對大量項目進行分組，以便更快的建立需求預測。 預測僅會根據歷史資料建立。

如果在預測建立期間使用項目分配索引鍵，則項目及其維度只能是一個項目分配索引鍵的一部分。

如要建立項目分配索引鍵並向其新增庫存單位 (SKU)，請執行以下步驟。

1. 前往 **主要計劃\>設置\>需求預測\>項目分配金鑰**。
1. 在清單窗格中選擇一個項目分配索引鍵，或在動作窗格上選擇 **新增** 以建立一個新索引鍵。 在新索引鍵或選定索引鍵的標題上，設定以下欄位：

    - **項目分配索引鍵** – 輸入索引鍵的唯一名稱。
    - **名稱** – 輸入該索引鍵的描述性名稱。

1. 按照以下步驟之一將項目新增到選定的項目分配索引鍵或刪除項目：

    - 在 **項目分配** FastTab，使用工具列上的 **新增** 和 **刪除** 按鈕可依據需要新增或刪除項目。 針對每一列選擇項目編號，然後視需要在其他欄中指派維度值。 選擇 **顯示維度** 以變更格線中顯示的維度列集合。 (在需求預測產生時，**百分比** 欄中的值會被忽略。)
    - 如果要向索引鍵新增大量項目，請在動作窗格上選擇 **指派項目** 以開啟一個頁面，您可以在該頁面找到多個項目，並將其指派給選定的索引鍵。

> [!IMPORTANT]
> 請注意在每個項目分配索引鍵中只包含相關項目。 使用時 Microsoft Azure Machine Learning 時，不必要的項目可能會導致成本增加。

## <a name="intercompany-planning-groups"></a>公司間規劃群組

需求預測可以產生跨公司預測。 在 Dynamics 365 Supply Chain Management 中，一起進行規劃的公司會被分組到同一個公司間規劃群組中。 如要為每個公司指定應考量用於需求預測的項目分配索引鍵，請將項目分配索引鍵與公司間規劃群組成員相關聯。

> [!IMPORTANT]
> 規劃最佳化目前不支援公司間規劃群組。 要執行使用規劃最佳化的公司間規劃，請設定包含所有相關公司主計劃的主計劃批次工作。

如要設定您的公司間規劃群組，請按照以下步驟操作。

1. 前往 **主計劃\>設定\>公司間規劃群組**。
1. 在清單窗格中選擇一個規劃群組，或在動作窗格上選擇 **新增** 以建立一個新群組。 在新群組或選定群組的標題上，設定以下欄位：

    - **名稱** – 輸入規劃群組的唯一名稱。
    - **說明** – 輸入規劃群組的簡短說明。

1. 在 **公司間規劃群組成員** FastTab 上，使用工具列上的按鈕為應屬於該組的每個公司 (法律實體) 新增一列。 對於每一列，設定下列欄位：

    - **法律實體** – 選擇作為已選群組成員的公司 (法律實體) 的名稱。
    - **排程順序** – 指派公司相對於其他公司的處理順序。 首先處理低的值。 當對一家公司的需求會影響其他公司時，此訂單可能很重要。 在這些情況下，提供需求的公司應最後處理。
    - **主計畫** – 選擇要為目前公司觸發的主計畫。
    - **自動複製到靜態計劃** – 選則此核取方塊可將計劃結果複製到靜態計劃。
    - **自動複製到動態計劃** – 選則此核取方塊可將計劃結果複製到動態計劃。

1. 預設情況下，如果沒有將項目分配索引鍵指派給公司間規劃群組成員，則系統會為指派至所有公司項目分配索引鍵的所有項目計算需求預測。 **產生統計基準線預測** 對話方塊 (**主計劃\>預測\>需求預測\>統計基準線預測**) 中提供了公司和項目分配索引鍵的其他篩選選項。 如要將項目分配索引鍵指派給所選公司間規劃群組中的公司，請選擇該公司，然後在 **公司間規劃群組成員** FastTab 上選擇工具列上的 **項目分配索引鍵**。

> [!IMPORTANT]
> 請注意在每個公司間規劃群組中僅包含項目分配索引鍵。 使用時 Azure Machine Learning 時，不必要的項目可能會導致成本增加。

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a>設定需求預測參數

使用 **需求預測參數** 頁面以設定幾個選項來控制需求預測在您的系統中的工作方式。

### <a name="open-the-demand-forecasting-parameters-page"></a>開啟需求預測參數頁面

如要設定需求預測參數，請前往 **主計劃\>設定\>需求預測\>需求預測參數**。 由於需求預測是跨公司執行的，因此該設定是全球性的。 換言之，它適用於所有法律實體 (公司)。

### <a name="general-settings"></a>一般設定

使用 **需求預測參數** 頁面的 **一般** 索引標籤來定義需求預測的一般設定。

#### <a name="demand-forecast-unit"></a>需求預測單位

需求預測會產生數量預測。 因此，應表示數量的測量單位必須在 **需求預測單位** 欄位中。 無論每種產品的通常庫存單位如何，此欄位都定義了將用於所有需求預測的單位。 透過使用一致的預測單位，您可以協助確保彙總和百分比分佈是合理的。 有關彙總和百分比分佈的更多資訊，請參閱[對基準線預測進行手動調整](manual-adjustments-baseline-forecast.md)。

對於用於需求預測中包含的 SKU 的每個測量單位，請確認您在此處選擇的測量單位和一般預測測量單位有一個轉換規則。 在您產生預測時，將記錄沒有測量單位轉換的項目清單。 因此，您可以輕鬆更正設定。 有關測量單位以及如何在它們之間轉換的更多資訊，請參閱[管理測量單位](../pim/tasks/manage-unit-measure.md)。

#### <a name="transaction-types"></a>交易類型

使用 **交易類型** FastTab 上的欄位，以選擇在產生統計基準線預測時使用的交易類型。

需求預測可用於預測依賴需求和獨立需求。 例如，如果只有 **銷售訂單** 選項設為 *是*，並且考慮進行需求預測的所有項目都是已售出的項目，則系統會計算獨立需求。 但是，關鍵子元件可以被新增到項目分配索引鍵中並包含在需求預測中。 在這種情況下，如果 **生產明細** 選項設為 *是*，則會計算依賴預測。

您可以使用 **項目分配索引鍵** 索引標籤，為一個以上的特定項目分配索引鍵覆寫交易類型。該索引標籤提供了類似的欄位。

#### <a name="choose-how-to-create-the-baseline-forecast"></a>選擇如何建立基準線預測

該 **預測產生策略** 欄位可讓您選擇用於建立基準線預測的方法。 可用的三個方法如下：

- *複製歷史需求* – 只需複製歷史資料即可建立預測。
- *Azure Machine Learning 服務* – 透過使用 Azure Machine Learning 服務來使用預測模型。 Azure Machine Learning 服務是目前適用於 Azure 的機器學習解決方案。 因此，如果您想使用預測模型，我們建議您使用它。
- *Azure Machine Learning* – 透過使用 Azure Machine Learning 工作室 (經典) 來使用預測模型。 Azure 機器學習工作室 (傳統) 已被取代，並將很快從 Azure 中移除。 因此，如果您是第一次設定需求預測，我們建議您選擇 *Azure Machine Learning 服務*。 如果你目前使用的是 Azure Machine Learning 工作室 (傳統)，應規劃盡快切換到 Azure Machine Learning 服務。

您可以使用 **項目分配索引鍵** 索引標籤，為一個以上的特定項目分配索引鍵覆寫預測產生方法。該索引標籤提供了類似的欄位。

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>全域覆寫預設預測演算法參數

預設預測演算法參數和值會在 **需求預測參數** 頁面進行指派 (**主計劃\>設定\>需求預測\>需求預測參數**)。 但是，您可以在 **需求預測參數** 頁面的 **一般** 索引標籤上，使用 **預測演算法參數** FastTab 來進行全域覆寫。 (您也可以使用 **需求預測參數** 頁面上的 **項目分配索引鍵** 索引標籤為特定分配索引鍵進行覆寫。)

使用工具列上的 **新增** 和 **移除** 按鈕來建立所需的參數覆寫集合。 對於清單中的每個參數，在 **名稱** 欄位，然後在 **值** 欄位輸入適當的值。 此處未列出的所有參數，都將從 **需求預測參數** 頁面上的設定中取得他們的值。 有關如何使用標準參數集並為它們選擇值的更多資訊，請參閱[需求預測模型的預設參數和值](#model-parameters)部分。

### <a name="set-forecast-dimensions"></a>設定預測維度

預測維度表示了為預測進行定義的詳細程度。 公司、站點和項目分配索引鍵是必要的預測維度。 您還可以在倉庫、庫存狀態、客戶群組、客戶帳戶、國家/地區、州和/或項目等級以及所有項目維度等級產生預測。 使用 **需求預測參數** 頁面上的 **預測維度** 索引標籤以選擇產生需求預測時使用的預測維度集。

您可以隨時將預測維度新增到用於需求預測的維度清單中。 您還可以從清單中刪除預測維度。 但是，如果您新增或移除預測維度，則會遺失手動調整。

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>為特定項目分配索引鍵設定覆寫

從需求預測的角度來看，並非所有項目都以相同的方式運作。 因此，您可以為 **一般** 索引標籤上定義的大多數設定，建立分配索引鍵特定的覆寫。但需求預測單位是例外。 如要為特定項目分配索引鍵設定覆寫，請按照以下步驟操作。

1. 在 **需求預測參數** 頁面的 **項目分配索引鍵** 選項卡上，使用工具列按鈕將項目分配索引鍵新增到左側網格，或視需要將它們刪除。 然後選擇要設定覆寫的分配索引鍵。
1. 在 **交易類型** FastTab 上，為屬於所選分配索引鍵的產品啟用用於產生統計基準線預測的交易類型。 該設定與它們在 **一般** 索引標籤上的運作方式一樣，但它們僅適用於選定的項目分配索引鍵。 這裡的所有設定 (*Yes* 的值和 *No* 的值) 會覆寫所有 **一般** 索引標籤上的 **交易類型** 設定。
1. 在 **預測演算法參數** FastTab 上，為屬於所選分配索引鍵的產品選擇預測產生策略和預測演算法參數覆寫。 這些設定與它們在 **一般** 索引標籤上的運作方式一樣，但它們僅適用於選定的項目分配索引鍵。 使用工具列上的 **新增** 和 **移除** 按鈕來定義所需的參數覆寫集合。 對於清單中的每個參數，在 **名稱** 欄位，然後在 **值** 欄位輸入適當的值。 有關如何使用標準參數集並為它們選擇值的更多資訊，請參閱[需求預測模型的預設參數和值](#model-parameters)部分。

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>設定與 Azure Machine Learning 服務的連線

使用 **Azure Machine Learning Web 服務** 索引標籤以設定與 Azure Machine Learning Web 服務的連線。 此解決方案是建立基準線預測的選項之一。 此索引標籤上的這些設定僅在 **預測產生策略** 欄位設定為 *Azure 機器學習服務* 時有效。

有關如何設定 Azure Machine Learning 服務並使用此處的設定進行連線的詳細資訊，請參閱[設定 Azure Machine Learning 服務](#setup-amls)部分。

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>設定與 Azure Machine Learning 工作室 (傳統) 的連線

> [!IMPORTANT]
> Azure 機器學習工作室 (經典) 已棄用。 因此，您不能再於 Azure 中為其建立新工作區。 它已被提供類似功能與更多其他功能的 Azure Machine Learning 服務所取代。 如果您尚未使用 Azure Machine Learning，則應開始使用 Azure Machine Learning 服務。 如果您已經擁有一個為 Azure Machine Learning 工作室 (傳統) 建立的工作區，在該功能從 Azure 中完全刪除前，您都可以繼續使用。 但是，我們建議您盡快更新到 Azure Machine Learning 服務。 即使應用程式會繼續警告您 Azure Machine Learning 工作室 (傳統) 已被棄用，但預測結果不會受到影響。 有關新的 Azure Machine Learning 服務及其設定方式的詳細資訊，請參閱[設定 Azure Machine Learning 服務](#setup-amls)部分。
>
> 只要您的舊 Azure Machine Learning 工作室 (傳統) 工作區仍然可以使用，您就可以在使用 Supply Chain Management 的新、舊機器學習解決方案之間自由切換。

如果您已有可用的 Azure Machine Learning 工作室 (傳統) 工作區，則可以透過將其連線到 Supply Chain Management 來用於產生預測。 您可以使用 **需求預測參數** 頁面上的 **Azure Machine Learning** 索引標籤來建立此連線。 (此索引標籤上的設定僅在 **預測產生策略** 欄位設為 *Azure Machine Learning* 時才有效。) 在您的 Azure Machine Learning 工作室 (傳統) 工作區輸入以下詳細資訊：

- Web 服務應用程式程式編寫介面 (API) 金鑰
- Web 服務端點網址
- Azure 儲存體帳戶名稱
- Azure 儲存體帳戶金鑰

> [!NOTE]
> 僅在您使用自訂儲存體帳戶時，才需要 Azure 儲存體帳戶名稱和金鑰。 如果您部署的是內部部署版本，則必須在 Azure 中擁有自訂儲存體帳戶，以便 Machine Learning 可以存取歷史資料。

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a>需求預測模型的預設參數和值

在您使用機器學習產生預測規劃模型時，您可以透過設定 *預測演算法參數* 的值來控制機器學習選項。 這些值是從 Supply Chain Management 傳送到 Azure Machine Learning 的。 使用 **預測演算法參數** 頁面來控制應提供哪些類型的值，以及每個應該擁有的值。

如要設定用於需求預測模型的預設參數和值，請前往 **主計劃\>設定\>需求預測\>預測演算法參數**。 已提供一組標準參數。 每個參數都有以下欄位：

- **名稱** – 與用於 Azure 相同的參數名稱。 通常，除非您已在 Azure Machine Learning 中自訂實驗，否則不應變更此名稱。
- **描述** – 參數的常見名稱。 此名稱是用於識別系統中其他位置的參數 (例如，在 **需求預測參數** 頁面)。
- **值** – 參數的預設值。 您應輸入的值，取決於您正在編輯的參數。 
- **說明** – 參數的簡短描述以及使用方式。 此描述通常包括有關 **值** 欄位的有效值建議。

依預設會提供以下參數。 (如果您必須還原至此標準清單，請在動作窗格上選擇 **還原**。)

- **信賴等級百分比** – 信賴區間是由一系列的值組成，這些值可作為需求預測的良好估計值。 95% 的信賴等級百分比，表示未來需求超出信賴區間範圍的風險為 5%。
- **強制季節性** – 指定是否強制模型使用特定類型的季節性。 此參數僅適用於 ARIMA 和 ETS。 選項：*AUTO (自動 (預設))*、*NONE (沒有)*、*ADDITIVE (加法類)*、*MULTIPLICATIVE (乘法類)*。
- **預測模型** – 指定要使用的預測模型。 選項：*ARIMA*、*ETS*、*STL*、*ETS+ARIMA*、*ETS+STL*、*ALL*。 如要選擇最適合的模型，請使用 *ALL*。
- **最大預測值** – 指定用於預測的最大值。 格式：+1E[n] 或數值常數。
- **最小預測值** – 指定用於預測的最小值。 格式：-1E[n] 或數值常數。
- **缺少值替換** – 指定歷史資料中間隙部分的填補方式。 選項：*(數值)*、*MEAN*、*PREVIOUS*、*INTERPOLATE LINEAR*、*INTERPOLATE POLYNOMIAL*。
- **缺少值替換範圍** – 指定值替換是否僅適用於每個單獨細微性屬性的日期範圍，還是適用於整個資料集。 以下選項可用於建立系統在填補歷史資料間隙時使用的日期範圍：

    - *全域* – 系統使用所有細微性屬性的完整日期範圍。
    - *HISTORY_DATE_RANGE* – 系統使用的特定日期範圍定義方式，係由 **產生統計基準線預測** 對話方塊的 **歷史範圍** 區段中的 **開始日期** 和 **結束日期** 欄位來決定。
    - *GRANULARITY_ATTRIBUTE* – 系統會使用目前處理的細微性屬性的日期範圍。

    > [!NOTE]
    > 細微性屬性是預測維度 (執行預測的預測維度) 的組合。 您可以在 **需求預測參數** 頁面定義預測維度。

- **季節性提示** – 對於季節性資料，為預測模型提供提示以提高預測正確性。 格式：表示需求模式重複本身的貯體數，以整數表示。 例如，針對本身每六個月重複一次的資料輸入 *6*。
- **測試集大小百分比** – 用作預測正確性計算測試集的歷史資料百分比。

您可以透過前往 **主計劃\>設定\>需求預測\>需求預測參數** 來覆寫這些參數的值。 在 **需求預測參數** 頁面，您可以透過以下方式覆寫參數：

- 使用 **一般** 索引標籤以全域方式覆寫參數。
- 使用 **項目分配索引鍵** 索引標籤以覆寫特定項目分配索引鍵的參數。 為特定項目分配索引鍵覆寫的參數，僅會影響與該項目分配索引鍵關聯的項目預測。

> [!NOTE]
> 在 **預測演算法參數** 頁面上，您可以使用動作窗格上的按鈕將參數新增到清單中，或從清單中移除參數。 然而，除非您已在 Azure Machine Learning 中自訂實驗，否則通常不應使用此方法。

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a>設定 Azure Machine Learning 服務

Supply Chain Management 使用 Azure Machine Learning 服務計算需求預測，而您必須在自己的 Azure 訂閱上設訂和執行該服務。 本節介紹如何在 Azure 中設定 Azure Machine Learning 服務，然後將其連接到您的 Supply Chain Management 環境。

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>在功能管理中啟用 Azure Machine Learning 服務

在您可以使用 Azure Machine Learning 服務進行需求預測之前，您必須打開 Supply Chain Management 中的一項功能以啟用整合。 管理員可利用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：** *主計劃*
- **功能名稱：** *用於需求預測的 Azure Machine Learning 服務*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a>在 Azure 中設定機器學習

若要使 Azure 能夠使用機器學習來處理您的預測，您必須為此目的設定 Azure Machine Learning 工作區。 你有二個選項：

- 如要透過執行 Microsoft 提供的指令碼來設定工作區，請按照[選項 1：執行指令碼以自動設定您的機器學習工作區](#ml-workspace-script)區段中的指示，然後跳到[在 Supply Chain Management 中設定 Azure Machine Learning 服務連線參數](#demand-forecast-parameters)區段。
- 如要手動設定您的工作區，請按照[選項 2：手動設定您的機器學習工作區](#ml-workspace-manual)區段中的指示，然後跳到[在 Supply Chain Management 中設定 Azure Machine Learning 服務連線參數](#demand-forecast-parameters)區段。 此選項會花更多時間，但它也為您提供了更多控制權。

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a>選項 1：執行指令碼以自動設定您的機器學習工作區

本節介紹如何使用 Microsoft 提供的自動化指令碼設定您的機器學習工作區。 如果您願意，可以按照[選項 2：手動設定機器學習工作區](#ml-workspace-manual)一節中的說明，手動設定所有資源。 您不必完成這兩個選項。

1. 在 GitHub 上，打開[使用 Azure Machine Learning 的 Dynamics 365 Supply Chain Management 需求預測範本](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service)存放庫 (repo)，並下載下列檔案：

    - quick_setup.ps1
    - sampleInput.csv
    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. 打開 PowerShell 視窗，然後執行您在上一步驟中下載的 **quick_setup.ps1** 指令碼。 按照螢幕上的說明進行操作。 該指令碼將設定所需的工作區、儲存體、預設資料存放區並計算資源。 但是，您仍必須按照此程序的剩餘步驟以建立所需管道。 (管道提供了一種從 Supply Chain Management 開始預測指令碼的方法。)
1. 在 Azure Machine Learning 工作室中，上傳您在步驟 1 中下載的 **sampleInput.csv** 檔案到名為 *demplan-azureml* 的容器。 (quick_setup.ps1 指令碼建立了這個容器。) 發佈管道和產生測試預測需要此檔案。 如需說明，請參閱[上傳區塊 Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob)。
1. 在 Azure Machine Learning 工作室中，在導覽器中選擇 **Notebooks**。
1. 在 **檔案** 結構中者到下列位置：**Users/\[current user\]/src**。
1. 將您在步驟 1 中下載的其餘四個檔案，上傳到您在上一步中找到的位置。
1. 選擇您剛剛上傳的 **api_trigger.py** 檔案，然後執行該檔案。 它將建立一個可以透過 API 觸發的管道。
1. 您的工作區現已設定完畢。 直接跳到[在 Supply Chain Management 中設定 Azure Machine Learning 服務連線參數](#demand-forecast-parameters)一節。

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a>選項 2：手動設定機器學習工作區

本節介紹如何手動設定機器學習工作區。 只有在您決定不執行自動安裝指令碼時，才必須完成本節中的程序，如[選項 1：執行指令碼來設定您的機器學習工作區](#ml-workspace-script)一節所述。

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a>步驟 1：建立新工作區

使用以下過程建立新的機器學習工作區。

1. 登入您的 Azure 入口網站。
1. 打開 **機器學習** 服務。
1. 在工具列上選擇 **建立** 以開啟 **建立** 精靈。
1. 按照螢幕上的說明完成精靈。 作業時請記住以下幾點：

    - 除非此清單中的其他點有建議不同的設定，否則請使用預設設定。
    - 請務必選擇與部署 Supply Chain Management 執行個體區域相符的地理區域。 否則，您的某些資料可能會通過區域邊界。 如需詳細資訊，請參閱本主題稍後的[隱私權通知](#privacy)。
    - 使用專用資源，例如資源群組、儲存體帳戶、容器登錄、Azure 金鑰保存庫和網路資源。
    - 在 **設定 Azure Machine Learning 服務連線參數** 精靈頁面，您必須提供儲存體帳戶名稱。 使用專用於需求預測的帳戶。 需求預測輸入和輸出資料將儲存在此儲存體帳戶中。

如需詳細資訊，請參閱[建立工作區](/azure/machine-learning/quickstart-create-resources#create-the-workspace)。

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a>步驟 2：設定儲存體

使用以下程序來設定您的儲存體。

1. 在 GitHub 上，打開 [使用 Azure Machine Learning 的 Dynamics 365 Supply Chain Management 需求預測範本](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) (repo)，並下載 **sampleInput.csv** 檔案。
1. 打開您在[步驟 1：建立新工作區](#create-workspace)一節中建立的儲存體帳戶。
1. 按照 [建立一個容器](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)中的說明進行操作，以建立一個名為 *demplan-azureml* 的容器。
1. 上傳您在步驟 1 中下載的 **sampleInput.csv** 檔案到您剛剛建立的容器中。 此檔案是發佈管道和產生測試預測所必要的。 如需說明，請參閱[上傳區塊 Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob)。

##### <a name="step-3-configure-a-default-datastore"></a>步驟 3：設定預設資料存放區

使用以下程序來設定您的預設資料存放區。

1. 在 Azure Machine Learning 工作室中，在導覽器中選擇 **資料存放區**。
1. 建立 *Azure Blob 儲存體* 類型的新資料存放區，該資料存放區指向您在 [步驟 2：設定儲存體](#config-storage)一節中建立的 *demplan-azureml* Blob 儲存體容器。 (如果新資料存放區的驗證類型是 *帳戶金鑰*，為建立的儲存體帳戶提供帳戶金鑰。 有關說明，請參閱[管理儲存體存取金鑰](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)。)
1. 透過開啟新資料存放區的詳細資訊並選擇 **設為預設資料存放區** 以將新資料存放區變為預設資料存放區。

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a>步驟 4：設定運算資源

使用以下程序在 Azure Machine Learning 工作室中設定運算資源，以執行預測產生指令碼。

1. 打開您在[步驟 1：建立新工作區](#create-workspace)部分建立的機器學習工作區詳細資訊頁面。 找出 **工作室 Web 網址** 的值，然後選擇該連結以將其開啟。
1. 在功能窗格上選擇 **計算**。
1. 在 **計算執行個體** 索引標籤上，選擇 **新增** 以開啟精靈，幫助您建立一個新的計算執行個體。 按照螢幕上的說明進行操作。 計算執行個體將用於建立需求預測管道 (管道發佈後可以刪除。) 使用預設設定。
1. 在 **計算叢集** 索引標籤上，選擇 **新增** 以開啟精靈，幫助您建立一個新的計算叢集。 按照螢幕上的說明進行操作。 計算叢集將用於產生需求預測。 它的設定會影響效能和執行的最大並行化等級。 設定以下欄位，但對所有其他欄位使用預設設定：

    - **名稱**- 輸入 *e2ecpucluster*。
    - **虛擬機器大小** – 根據您希望做為需求預測輸入的資料量調整此設定。 節點數不應超過 11，因為觸發需求預測產生需要一個節點，然後可用於產生預測的最大節點數為 10。 (您還將在 parameters.py 檔案中設定節點數[第 5 步：建立管道](#create-pipelines)部分。) 在每個節點上，將有幾個並行執行預測指令碼的背景工作處理序。 您工作中的背景工作處理序總數將為 *節點擁有的核心數* × *節點數*。 例如，如果您的計算叢集有一個 *標準 \_ D4* (八核心) 類型，和最多 11 個節點，且如果 `nodes_count` 值設為 *10* 在 parameters.py 檔案中，有效並行等級為 80。

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a>第 5 步：建立管道

管道提供了一種從 Supply Chain Management 開始預測指令碼的方法。 使用以下程序建立所需管道。

1. 在 GitHub 上，打開[使用 Azure Machine Learning 的 Dynamics 365 Supply Chain Management 需求預測範本](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service)存放庫，並下載下列檔案：

    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. 在 Azure Machine Learning 工作室中，在導覽器中選擇 **Notebooks**。
1. 在 **檔案** 結構中者到下列位置：**Users/\[current user\]/src**。
1. 將您在步驟 1 中下載的四個檔案，上傳到您在上一步中找到的位置。
1. 在 Azure 中，打開並檢閱您剛剛上傳的 **parameters.py** 檔案。 確認 `nodes_count` 值比您在[步驟 4：配定計算資源](#config-compute-resources)部分中為計算叢集配定的值少一。 如果 `nodes_count` 值大於或等於計算叢集中的節點數，管道執行可能可以啟動。 但是，它會在等待所需資源時停止回應。 如需有關節點計數的更多資訊，請參閱[步驟 4：設定計算資源](#config-compute-resources)部分。
1. 選擇您剛剛上傳的 **api_trigger.py** 檔案，然後執行該檔案。 它將建立一個可以透過 API 觸發的管道。

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a>設定新的 Active Directory 應用程式

Active Directory 應用程式需要使用服務主體對專用於需求預測的資源進行驗證。 因此，應用程式應具有產生預測所需的最低權限等級。

1. 登入您的 Azure 入口網站。
1. 在租用戶中註冊一個新的應用程式 Azure Active Directory (Azure AD)。 如需說明，請參閱[使用入口網站建立一個可以存取資源的 Azure AD 應用程式和服務主體](/azure/active-directory/develop/howto-create-service-principal-portal)。
1. 完成精靈後，按照螢幕上的說明進行操作。 使用預設設定。
1. 讓您的新 Active Directory 應用程式存取您在[在 Azure 中設定機器學習](#ml-workspace)部分中建立的以下資源。 如需說明，請參閱[使用 Azure 入口網站指派 Azure 角色](/azure/role-based-access-control/role-assignments-portal?tabs=current)。 此步驟將使系統能夠匯入和匯出預測資料，並從 Supply Chain Management 觸發執行機器學習管道。

    - 機器學習工作區的參與者角色
    - 專用儲存體帳戶的參與者角色
    - 專用儲存體帳戶的儲存體 Blob 資料參與者角色

1. 在您建立的應用程式 **憑證和密碼** 的部分，為應用程式建立一個密碼。 如需說明，請參閱[新增用戶端密碼](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。
1. 記下應用程式 ID 及其密碼。 當您在稍後設定 **需求預測參數** Supply Chain Management 頁面時，將會需要此應用程式詳細資訊。

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a>在 Supply Chain Management 中設定 Azure Machine Learning 服務連線參數

使用以下程序將您的 Supply Chain Management 環境連線到您剛剛在 Azure 中設定的機器學習服務。

1. 登入 Supply Chain Management。
1. 前往 **主計劃\>設定\>需求預測\>需求預測參數**。
1. 在 **一般** 索引標籤上，確認 **預測產生策略** 欄位設為 *Azure Machine Learning 服務*。
1. 在 **項目分配索引鍵** 索引標籤上，確認為每個應使用 Azure Machine Learning 服務進行需求預測的分配索引鍵將 **預測產生策略** 欄位設為 *Azure Machine Learning 服務*。
1. 在 **Azure Machine Learning 服務** 索引標籤，設定以下欄位：

    - **租用戶識別碼** – 輸入您 Azure 租用戶的識別碼。 Supply Chain Management 將使用此識別碼向 Azure Machine Learning 服務進行驗證。 您可以在 Azure 入口網站的 Azure AD **概述** 頁面中找到您的租用戶識別碼。
    - **服務主體應用程式識別碼** – 輸入您在 [Active Directory 應用程式](#aad-app)部分建立的應用程式識別碼。 此值是用於授權對 Azure Machine Learning 服務的 API 請求。
    - **服務主體密碼** – 輸入您在 [Active Directory 應用程式](#aad-app)部分建立的服務主體應用程式密碼。 此值用於取得您對 Azure 儲存體和 Azure Machine Learning 工作區執行授權操作而建立的安全主體存取權杖。
    - **儲存體帳戶名稱** – 輸入您在 Azure 工作區中執行設定精靈時指定的 Azure 儲存體帳戶名稱。 (如需詳細資訊，請參閱[在 Azure 中設定機器學習](#ml-workspace)一節。)
    - **管道端點位址** – 輸入 Azure Machine Learning 服務的管道 REST 端點網址。 您已[在 Azure 中設定機器學習](#ml-workspace)的最後一個步驟中建立了此管道。 如要取得管道網址，請登入您的 Azure 入口網站，並在導覽上選擇 **管道**。 在 **管道** 索引標籤上，選擇名為 **TriggerDemandForecastGeneration** 的管道端點。 然後複製顯示的 REST 端點。

    ![需求預測參數頁面的 Azure Machine Learning 服務索引標籤上的參數。](media/azure-ml-service-parameters.png "需求預測參數頁面的 Azure Machine Learning 服務索引標籤上的參數")

## <a name="privacy-notice"></a><a name="privacy"></a>隱私權注意事項

在您選擇 *Azure Machine Learning 服務* 作為您的預測產生策略時，Supply Chain Management 會自動將您的歷史需求客戶資料 (例如彙總數量、產品名稱及其產品尺寸、運送和接收地點、客戶識別碼以及預測參數) 傳送到您機器學習工作區所在的地理區域及其關聯的儲存體帳戶，以用於預測未來需求。 Azure Machine Learning 服務的地理區域可能與部署 Supply Chain Management 的位置不同。 部分使用者可以在 **需求預測參數** 頁面上透過選擇預測產生策略來控制是否啟用此功能。

## <a name="additional-resources"></a>其他資源

- [需求預測概觀](introduction-demand-forecasting.md)
- [產生統計基準線預測](generate-statistical-baseline-forecast.md)
- [對基線預測進行手動調整](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
