---
title: 確定計劃訂單
description: 本主題說明如何確定計劃訂單。 當計劃訂單確定後，它們便成為實際的採購單、轉移訂單或生產訂單。
author: ChristianRytt
ms.date: 04/22/2021
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 7e3a86e2aa0e7182f7f9e853b9e8667e677a8ad6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449922"
---
# <a name="firm-planned-orders"></a>確定計劃訂單

[!include [banner](../../includes/banner.md)]

計劃訂單必須是 *已確定*（即已發佈）作為總規劃程序的一部分。 當計劃訂單確定後，它們便成為實際的採購單、轉移訂單或生產訂單。 這些訂單也被稱為 *已發佈訂單* 或 *未結訂單*。

確定計劃訂單的三種方法：

- **手動確定**–在列表中選擇特定的計劃訂單，然後手動啟動流程。
- **自動確定**–為涵蓋範圍群組、個別項目以及項目和總規劃的組合定義預設的確定時界。 然後，在總規劃執行期間，如果訂單日期在確定的指定時界內，計劃訂單將會自動確定。
- **查詢式確定**–定義查詢以根據其屬性選擇計劃訂單。 您可以設定批次作業以定期執行查詢和確定匹配訂單。

本主題詳細介紹了每種方法。

## <a name="enable-the-features-that-are-described-in-this-topic"></a><a name="enable-features"></a>啟用本主題中描述的功能

多數計劃訂單功能在使用規劃最佳化的 Microsoft Dynamics 365 Supply Chain Management的所有標準安裝中皆可使用。 但是，必須先在功能管理中開啟本主題描述的一些功能，然後才能使用它們。

### <a name="turn-parallelized-firming-of-planned-orders-on-or-off"></a>開啟或關閉計劃訂單的平行化確定

透過跨多個執行緒平行化，平行化確定有助於加快確定程序。 當許多計劃訂單被確定時，這種方法會很實用。 若要使用此功能，您必須開啟系統中的 *計劃訂單的平行確定* 功能。 從 Supply Chain Management 版本 10.0.21 開始，此功能預設開啟。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25之前的版本，那麼您可以前往 [功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)並搜尋 *計劃訂單的平行確定* 功能，然後開啟或關閉此功能。

### <a name="enable-planned-order-firming-with-filtering"></a>透過篩選啟用計劃訂單確定

透過篩選計劃訂單確定，您可以定義選擇要確定的計劃訂單的邏輯準則。 您還可以預覽已選擇的計劃訂單，在背景執行程序，和/或將其安排為批次作業。

從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。 管理員可以透過搜尋位在 [功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區中的 *透過篩選計劃訂單確定* 功能而開啟該功能。

### <a name="enable-auto-firming-for-planning-optimization"></a>為規劃最佳化啟用自動確定

自動確定讓您確定計劃訂單，作為在確定的時界內總規劃程序的一部分。 內建於 Supply Chain Management 的規劃引擎一律支援自動確定。 但是，若也要與規劃最佳化一起使用，您必須開啟該功能。

要使此功能在您的系統中可用，請前往 [功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), 並開啟 *規劃最佳化的自動確定* 功能。 (從 Supply Chain Management 版本 10.0.21 開始，此功能為預設開啟)。

## <a name="manually-firm-planned-orders"></a>手動確定計劃訂單

要手動確定計劃訂單，請查找並選擇要確定的計劃訂單，然後手動啟動確定程序。

1. [打開任何計劃訂單的清單頁面](approved-planned-order.md#view-planned-orders)。
1. 使用 **篩選** 欄位，**計劃** 欄位和列標題篩選和排序清單，以便可以找到您正在尋找的計劃訂單。
1. 選取您要確定的每個計劃訂單的核取方塊。 如果您要確定頁面上目前列出的所有計劃訂單（依照您應用的篩選器），請跳過此步驟。
1. 在動作窗格上，選擇以下其中一個按鈕：

    - **確定**–僅確定選定的計劃訂單。
    - **確定全部**–無論選中任何核取方塊，確定頁面上目前列出的所有計劃訂單（依照您應用的篩選器）。 如果您要確定許多計劃訂單，此選項會很實用。

1. 在 **確定** 對話方塊內，在 **參數** FastTab 上，設定以下欄位。 （其中許多欄位的預設值來自 **總規劃參數** 頁面上的 **標準更新** 索引標籤。）

    - **更新標記**–選擇確定計劃訂單時要使用的庫存標記原則。
    - **如果發生錯誤，請停止確定**–若其中一個發生錯誤，將此選項設為 *是* 以停止確定所有選定的計劃訂單。 如果 **平行化確定** 選項設為 *是*，則此選項必須設為 *否*。
    - **平行化確定**–此選項僅在您已開啟系統中的 [*計劃訂單的平行確定* 功能](#enable-features)，且您已選擇兩個或更多的計劃訂單進行確定的狀況下才可使用。 將其設為 *是*，平行執行確定程序。 平行確定有助於提高效能。
    - **執行緒數目** –此選項僅在您已開啟系統中的 [*計劃訂單的平行確定* 功能](#enable-features)，且您已將 **平行化確定** 選項設為 *是* 的狀況下才可使用。 輸入用於平行化確定程序的執行緒數目。 有關如何在總規劃中使用此選項的建議，請參閱[提高總規劃效能](../master-planning-performance.md#number-of-threads)。

        > [!NOTE]
        > **執行緒數目** 欄位的值為 *0*（零）時，會增加總規劃的執行時間。 因此，我們建議您一律將此欄位的值設為大於 0。

    - **按廠商分組**–將此選項設為 *是*，對計劃採購單進行分組，並在確定期間為每個廠商建立一份採購單。 或者，您可以建立一個採購單，其中每個計劃訂單都有一行。
    - **按買家群組分組**–將此選項設為 *是*，對計劃採購單進行分組，並建立一份合併廠商和買家群組的採購單。 要使用此選項，您必須將 **按廠商分組** 選項設為 *是*。
    - **按採購合約分組**–將此選項設為 *是*，對與現有採購合約具有相同廠商的計劃採購單進行分組，並為每個採購合約建立一份採購單。 此選項在 **按廠商分組** 已啟用的狀況下會自動啟用。 要使用 **按採購合約分組**，必須將 **總規劃參數** 頁面上的 **查找採購合約** 設為 *是*。
    - **按期間分組**（在 **採購單** 部分）–選擇計劃採購單分組依據的期間。 要使用此選項，您也必須設定 **按廠商分組** 選項。
    - **按期間分組**（在 **轉移** 部分）–選擇計劃轉移訂單分組依據的期間。 這些訂單將會依照 **從倉庫** 和 **到倉庫** 值進行分組。

    > [!NOTE]
    > 每個“分組依據”選項都會使系統將每個計劃訂單轉為由分組產生的單個採購單中的一行。

    ![確定對話方塊中的參數FastTab。](./media/manual-firming.png "確定對話方塊中的參數FastTab。")

1. 在 **在背景執行** FastTab 上，設定作業使其以批次模式執行。 但是，當您進行手動確定時，設定週期性排程毫無意義。 這些欄位的運作方式就如同它們為 Supply Chain Management 中其他的[背景作業](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md)類型運作時一樣。 但是，對於手動確認，批次作業將僅處理當前選擇的計劃訂單。 它不會處理任何符合頁面上當前應用的篩選器的訂單。
1. 選擇 **確定** 以套用您的設定並產生已確定訂單。

## <a name="auto-firm-planned-orders"></a>自動確定計劃訂單

自動確定讓您確定計劃訂單，作為總規劃程序的一部分。 您可以為涵蓋範圍群組、個別項目以及項目和總規劃的組合定義一個確定時界。 然後，在總規劃執行期間，如果訂單日期在確定的指定時界內，計劃訂單將會自動確定。 規劃最佳化和內建總規劃操作產生的計劃訂單處理訂單日期（即開始日期）的方式不同。

> [!NOTE]
> 計劃採購單的自動確認只能發生在與廠商相關的項目。
> 
> 如果已開啟追蹤修訂，則已確定的衍生訂單（即分包採購單）的狀態將會是 *檢閱中*。

> [!IMPORTANT]
> 在本節所描述的功能可以與規劃最佳化一起使用之前，如本主題開頭所述，您必須開啟系統中的 [*規劃最佳化的自動確定* 功能](#enable-features)。 自動確定一律可與內建總規劃引擎一起使用。

### <a name="auto-firming-with-planning-optimization-vs-the-built-in-planning-engine"></a>使用規劃最佳化的自動設定與內建規劃引擎

規劃最佳化和內建規劃引擎均可用於自動確定計劃訂單。 但是，其中有一些重要差異。 例如，規劃最佳化是使用訂單日期（即開始日期）決定要確定哪些計劃訂單，然而內建規劃引擎則是使用需求日期（即結束日期）。 下表總結了這些差異。

| 功能 | 規劃最佳化 | 內建規劃引擎 |
|---|---|---|
| **日期基準** | 自動確認會依照訂單日期（開始日期）。 | 自動確認會依照需求日期（結束日期）。 |
| **前置時間** | 由於訂單日期（開始日期）會觸發確定，因此您不必將前置時間視為確定時界的一部分。 | 為幫助保證及時確定訂單，確定時界必須長於前置時間。 |
| **本週訂單** | 要確定必須在本週開始的所有訂單，確定時界必須為一週。 | 要確定必須在本週開始的所有訂單，確定時界必須是前置時間再加上一週。 |

### <a name="set-up-auto-firming-and-the-firming-time-fence"></a>設定自動確定和確定時界

如本節後面所述，您可以指派一個自動確定時界至相關涵蓋設定來開啟自動確定。 如果沒有為任何涵蓋設定開啟自動確定，或者若規劃是從特定頁面開始，例如已發佈產品的 **淨需求** 頁面，則會略過自動確定程序。

自動確定的分組和標記選項從 **總規劃參數** 頁面上的 **標準更新** 索引標籤獲取其值。

自動確定時界由您為相關涵蓋設定輸入的天數定義。 您可以透過下列方式開啟自動確定和控制確定時界：

- 要定義涵蓋範圍群組的預設確定時界，請前往 **總規劃\>設定\>涵蓋範圍\>涵蓋範圍群組**，然後選擇一個涵蓋範圍群組。 接著，在 **其他** FastTab上，在 **自動確定時界（天）** 欄位，輸入天數。
- 要覆寫特定項目涵蓋範圍群組所定義的確定時界，請前往 **產品資訊管理\>已發佈產品**。 在動作窗格上，選擇 **計劃**，接著選擇 **品項涵蓋範圍**。 在 **一般** 索引標籤上，選擇 **覆寫時界**，接著，在 **自動確定時界（天）** 欄位，輸入天數。
- 要覆寫特定總規劃的涵蓋範圍群組和品項涵蓋範圍所定義的確定時界，請前往 **總規劃\>設定\>總規劃**，然後選擇一個總規劃。 接著，在 **時界（天）** FastTab 上，將 **確定** 選項設為 *是*，並輸入天數。

如果您將前面提到的所有時界設為 *0*（零），自動確定則會有效停用相關的涵蓋項目。

## <a name="firm-planned-orders-by-using-a-query"></a>使用查詢確定計劃訂單

查詢式確定允許您依照預先定義的準則計劃確定。 與自動確認不同，查詢式確定允許在不同時間點自動確認不同的訂單子集。 此外，您可以使用手動或自動操作來確定不同類型的計劃訂單。 您還可以根據您的設定預覽選擇的已確定訂單。 因此，您可以確認選擇符合您的期望。

您可以合併自動確定與查詢式確定。 例如，查詢式確定作業的前向時界比匹配的自動確定涵蓋範圍設定的時界長。 因此，查詢式確認作業將在觸發自動確認之前處理其計劃訂單。 您可以利用此行為來安排特定廠商的訂單，而不是其他廠商的類似產品訂單。

> [!IMPORTANT]
> 在本節所描述的功能可以使用之前，如本主題開頭所述，您必須開啟系統中的 [*透過篩選計劃訂單確定* 功能](#enable-features)。

要使用查詢式確定程序確定計劃訂單，請執行以下步驟。

1. 移至 **主規劃 \> 主規劃 \> 執行 \> 計劃訂單確定**。
1. 在 **計劃訂單確定** 對話方塊內，在 **參數** FastTab 上，設定基本處理、標記和分組選項。 這些選項的運作方式就如同它們在 **確定** 對話方塊內的運作一樣。 （有關說明，請參見上一節。）然後，在 **計劃** 部分，設定以下 **計劃訂單確定** 對話方塊特有的欄位：

    - **計劃**–選擇在確定此查詢找到的計劃訂單期間應套用的總規劃。
    - **確定時界未來天數**–選擇總規劃必須在未來多久時間內計算各種要求和其他考慮因素。
    - **確定時界過去天數**–選擇總規劃必須在過去多久時間內計算各種要求和其他考慮因素。

    ![計劃訂單確定對話方塊中的參數 FastTab。](./media/planned-order-firming-main-1.png "計劃訂單確定對話方塊中的參數 FastTab。")

1. 要指定訂單中應包含哪些記錄，請選擇 **要包括的記錄** FastTab上的 **篩選** 按鈕。 將出現一個標準查詢對話，您可以在其中定義選擇條件、排序條件和聯結。 這些欄位的運作方式就如同它們為 Supply Chain Management 中其他查詢類型運作時一樣。 此處欄位是唯讀的，並顯示與您的查詢相關的值。

    ![計劃訂單確定對話方塊上的要包括的記錄 FastTab。](./media/planned-order-firming-main-2.png "計劃訂單確定對話方塊上的要包括的記錄 FastTab。")

1. 根據您目前的設定，選擇 **預覽**，預覽已確定訂單的內容。 將要確定的計劃訂單列表將會顯示為訊息。 接著您可以根據需求調整設定，直到預覽顯示您想要的已確定訂單。

    ![已確定訂單的預覽範例。](./media/planned-order-firming-preview.png "已確定訂單的預覽範例。")

    > [!WARNING]
    > 此功能將確定所有符合篩選條件的計劃訂單。 不加批判地確定計劃訂單會導致建立大量不需要的採購、轉移和生產訂單。 在您繼續之前，請一律使用 **預覽** 按鈕以驗證將包含的記錄。

1. 在 **在背景執行** FastTab 上，設定作業使其以批次模式執行，和/或設置定期排程。 這些欄位的運作方式就如同它們為 Supply Chain Management 中其他的[背景作業](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md)類型運作時一樣。
1. 選擇 **確定** 以套用您的設定並產生已確定訂單。

## <a name="track-firmed-orders"></a>追蹤已確定訂單

要追蹤已確定的計劃訂單，請執行以下步驟。

1. [打開任何計劃訂單的清單頁面](approved-planned-order.md#view-planned-orders)。
1. 打開或選擇您要追蹤的計劃訂單。
1. 在動作窗格上的 **檢視** 索引標籤上，於 **檢視** 群組中選取 **確定記錄**。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
