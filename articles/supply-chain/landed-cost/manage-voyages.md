---
title: 管理航程
description: 本主題介紹如何使用航程。 航程通常是一條船隻。 不過，依據您的實務和程序，航程也可代表廠商、訂購單或組織需要的其他項目。
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 50b6f306da1d32b1fd98da68bd997de1f1c23ffb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448368"
---
# <a name="manage-voyages"></a>管理航程

[!include [banner](../../includes/banner.md)]

航程通常是一條船隻。 不過，依據您的實務和程序，航程也可代表廠商、訂購單或組織需要的其他項目。

**所有航程** 頁面會提供航程詳細資料、交貨和成本資訊，以及項目、訂購單和轉移訂單的相關資訊。 若要開啟 **所有航程** 頁面，請移至 **到岸成本 \> 航程 \> 所有航程**。 此頁面會顯示目前所有航程的清單。 您可以使用動作窗格上的按鈕來建立、刪除及使用航程。 在清單中選取航程以檢視詳細資料。

> [!NOTE]
> 裝運貨櫃和貨櫃組會與航程連結。 採購明細會與裝運貨櫃連結。 若關閉裝運貨櫃和貨櫃組，仍可直接連結至航程。 此外，此處輸入的成本會分攤到所有附加的採購明細。

## <a name="action-pane"></a>動作窗格

**航程** 頁面動作窗格提供的按鈕，可讓您使用所選的航程。 每個按鈕執行一個動作。 動作窗格也包括索引標籤，每個索引標籤又提供了一組相關按鈕。 除非另有說明，否則 **所有航程** 頁面的清單檢視和所選單一航程的詳細檢視，都會提供所有按鈕和索引標籤。

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>直接出現在動作窗格上的按鈕

下表說明動作窗格上直接的可用按鈕。

| 按鈕 | 描述 |
|---|---|
| 新產品 | 建立航程。 <!-- KFM: Link to scenario --> |
| 刪除 | 刪除目前航程。 只能刪除狀態為 *已確認* 的航程。 航程離開港口並處理在運品後，就無法刪除。 |
| 航程編輯器 | 開啟 **航程編輯器** 頁面，即可新增或移除航程的採購明細、建立新的貨櫃，並修改航程本身的詳細資料。 |
| 航程成本 | 開啟 **航程成本** 頁面，即可檢視航程內的所有貨物，並為其新增航程成本。 航程成本手動增加至航程時，會自動新增至 **成本查詢** 頁面，並依據 **航程成本** 頁面指定的方法分攤到每個貨物。 |

### <a name="buttons-on-the-voyage-tab"></a>航程索引標籤上的按鈕

下表說明動作窗格 **航程** 索引標籤上的可用按鈕。 只有在 **所有航程** 頁面的清單檢視會提供此索引標籤。

| 按鈕 | 描述 |
|---|---|
| 裝運貨櫃 | 在此開啟的頁面，會顯示與所選航程相關聯的所有裝運貨櫃。 可能會有一或多個貨櫃。 |
| 貨櫃組 | 在此開啟的頁面，會顯示與所選航程相關聯的所有貨櫃組。 可能會有一或多個貨櫃組。 |

### <a name="buttons-on-the-manage-tab"></a>管理索引標籤上的按鈕

下表說明動作窗格 **管理** 索引標籤上的可用動作。

| 按鈕 | 描述 |
|---|---|
| 收到的文件 | 更新航程，將 **收到的文件** 選項設為 *是*。 您可以使用此按鈕鎖定品項和/或採購明細，使其無法進一步更新。 |
| 在運輸途中 | 依據 **[到岸成本參數](landed-cost-parameters.md)** 頁面的設定，將 **航程狀態** 欄位更新為在途狀態。 此流程不需要其他邏輯。 依據[追蹤控制中心](delivery-information-setup.md)的設定，航程也可自動更新為在途狀態。
| 準備好進行成本核算 | 依據 **[到岸成本參數](landed-cost-parameters.md)** 頁面的設定，將 **航程狀態** 欄位更新為準備好進行成本核算狀態。 處理所有發票 (庫存發票和航程成本發票) 並接收貨物時，航程就能核算成本。 若尚未核算航程相關的估計成本，則嘗試處理航程的成本核算時會出現錯誤。 |
| 已計算成本 | 所有訂購單和航程成本的發票發出後，會清除所有不正確的成本核算。 當您選擇此按鈕時，會出現 **航程更新 - 已計算成本** 對話方塊。 在此，您可選擇在標準財務日期過帳或指定過帳日期，並執行此動作。 您可依需求不斷重新執行此動作。 您也可使用 **航程更新 - 已計算成本** 對話方塊來建立排程，以定期任務 (批次工作) 的方式執行此動作。 建議您將此動作設為批次工作，定期予以執行。 |
| 過帳收貨清單 | 過帳航程內所有訂購單明細的收貨清單。 若為多公司航程，每家公司都會開啟新的收貨清單過帳對話方塊，並於每個法律實體內進行處理。 |
| 過帳產品收貨 | 航程內所有訂購單明細的過帳產品收據。 只有當貨物 **不會** 經過在運品處理流程時，才要使用航程相關聯的訂購單明細產品收貨流程。 若貨物會經過在運品處理流程，當您嘗試過帳訂購單明細的產品收貨時會出現錯誤。 若為多公司航程，每家公司都會開啟新的交貨單過帳對話方塊。 |
| 過帳發票 | 航程內所有訂購單明細的過帳發票。 若航程內的貨物會經過在運品處理流程，則會先開立訂購單明細的發票，才能完成收貨流程。 原始訂購單開立發票時，將建立與原始訂購單明細相關聯的在運品訂單。 之後，倉庫即可接收這些訂單。 若為多公司裝運，每家公司都會開啟新的發票過帳對話方塊。 |
| 船舶轉運單 | 過帳航程內所有轉移訂單明細的轉移訂單航程。 選取此按鈕時，只能更新轉移訂單。 |
| 接收轉移訂單 | 過帳航程內所有轉移訂單明細的轉移訂單收貨。 |
| 接收在運品 | 接收航程內所有在途的訂單明細。 若要接收航程內的在運品，此按鈕是選項之一 (共三個選項)。 (其他兩個選項為本表格稍後說明的 **建立到貨日記帳** 按鈕及 Warehouse Management mobile app。) 此為最簡單的選項，其處理方式會將在運品從在運品倉庫移至最終目的地倉庫。 若您希望對此流程有更多的掌控權，請使用到貨日記帳或行動裝置來處理收貨事宜。 |
| 查找自動成本 | 查找相關的航程成本。 如果這些成本已找到或更新，您會收到以下訊息：「存在未開立發票的成本明細。 您要進行覆寫嗎？」 將找出航程建立時未建立關聯的成本。 不會覆寫附加至航程且已開立發票的航程成本。 |
| 建立到貨日記帳 | <p>開啟 **建立到貨日記帳** 對話方塊，即可建立到貨日記帳來指定位置。 此對話方塊會提供下列選項：</p><ul><li>**從在運品建立** 或 **從轉移訂單建立** – 您是否使用在運品處理程序，將影響此選項的標籤。 在此設為 *是* 來開啟到貨日記帳頁面，即可處理航程相關在運品的標準到貨日記帳。 若該項目已由最終目的地倉庫接收，就不會新增至到貨日記帳明細。</li><li>**初始化數量** – 此選項設為 *是*，即可依據航程明細指定的貨物數量，將接收的數量初始化。 若已接收部分航程明細，則此數量為剩餘的數量。 建議您將此選項設為 *是*。</li><li>**從訂單明細建立** – 此選項設為 *是*，即可從訂單明細中取得該值。</li></ul><p>若要接收航程內的貨物，此按鈕是選項之一 (共三個選項)。 (其他選項為本表稍早說明的 **接收在運品** 按鈕及 Warehouse Management mobile app。)</p> |
| 應計成本 | 若借方分類帳科目已指定某成本類型，則可計入該成本。 此按鈕通常在庫存在運輸途中，或收到貨物並開具發票時使用。 |
| 彙總成本 | 將成本從裝運貨櫃等級轉移至航程等級。 若為共用服務/裝運情境，也就是多個實體共用一個裝運貨櫃或貨箱空間，建議使用此按鈕。 例如，此航程有一個 40 英尺的裝運貨櫃及一個 20 英尺的裝運貨櫃，並依據體積來分攤。 此時，共用或使用 20 英尺裝運貨櫃的貨物/實體可能會吃虧。 部分組織為了公平分配成本，可能會希望將成本轉移到航程，並以航程等級的分攤方法進行分配。 |
| 變更旅程圖範本 | 在此開啟的對話方塊，可讓您變更旅程圖範本。 變更範本後，將刪除航程成本。 因此，建議您選擇 **查找自動成本** (請參閱本表格稍早的說明) 或再次手動增加成本。 |

### <a name="buttons-on-the-general-tab"></a>一般索引標籤上的按鈕

下表說明動作窗格 **一般** 索引標籤上的可用按鈕。

| 按鈕 | 描述 |
|---|---|
| 收貨清單 | 開啟航程內所有訂購單明細的產品收貨清單。 若為多公司航程，每家公司都會開啟新的收貨清單。 若尚未處理任何產品收貨清單，則無法使用此按鈕。 |
| 產品收貨 | 開啟航程相關聯的訂購單明細的產品收貨記錄 (若使用此記錄)。 若尚未過帳任何產品收貨，則無法使用此按鈕。 若您使用在運品處理流程，將不會使用產品收貨流程。 |
| 品項到貨 | 開啟品項到貨日記帳 (如使用)。 |
| 追蹤 | 開啟 **入站追蹤** 頁面，即可更新裝運貨櫃與航程內的貨物預期到貨日期，進而更新訂購單明細的預期交貨日期。 |
| 成本查詢 | <p>開啟 **成本查詢** 頁面，顯示航程的所有成本。</p><p>選擇動作窗格上的 **檢視**，即可調整檢視。 您可檢視任何等級，以及品項和成本類型代碼。</p><p>只有與庫存交易直接相關的成本類型代碼才會出現在 **成本查詢** 頁面。 移除成本類型代碼，即可將成本分組來調整頁面。 如果您使用尺寸和顏色，此功能會很實用。</p><p>**成本查詢** 頁面只會顯示 **借方** 欄位設為 *品項* 的成本類型代碼。</p> |
| 在運品訂單 | 開啟 **在運品訂單** 頁面，只會顯示所選航程的在運品記錄。 |

## <a name="lines-view"></a>明細檢視

若要開啟 **明細** 檢視，請開啟航程，然後選取航程標題右上角的 **明細** 索引標籤。

### <a name="information-on-the-voyage-header-fasttab"></a>航程標題 FastTab 上的資訊

航程 **明細** 檢視的 **航程標題** FastTab 內有航程說明的基本資訊。 此 FastTab 的許多欄位也會出現在 **標題** 檢視，請見本主題稍後的說明。

### <a name="information-on-the-voyage-lines-fasttab"></a>航程明細 FastTab 上的資訊

航程 **明細** 檢視的 **航程明細** FastTab 與航程詳細資料和航程層級的成本核算資訊有關。 在此，您可檢視航程附加的裝運貨櫃、貨櫃組和品項。 也會顯示航程內品項的價格與數量。 您可選取相關連結，即可檢視所列出的裝運貨櫃或貨櫃組。

### <a name="information-on-the-line-details-fasttab"></a>明細詳細資料 FastTab 上的資訊

航程 **明細** 檢視的 **明細詳細資料** FastTab 會提供 **航程明細** FastTab 目前所選的明細的詳細資訊。 請注意，此 FastTab 的詳細資料包括每條明細在貨櫃中佔據的位置及其聲明的數量。

## <a name="header-view"></a>標題檢視

若要開啟 **標題** 檢視，請開啟航程，然後選取航程標題右上角的 **標題** 索引標籤。

### <a name="settings-on-the-general-fasttab"></a>一般 FastTab 上的設定

下表說明航程 **標題** 檢視 **一般** FastTab 可用的欄位。

| 欄位 | 描述 |
|---|---|
| 航程 | 輸入航程或航班編號。 |
| 訂艙參考 | 若承運者或運送中心提供參考編號來辨識航程 (即承運者或運送中心的內部參考)，請輸入於此處。 |
| 船舶 | 輸入或選擇船隻。 如果船隻未以值的方式列出，您可以以任意文字形式輸入船隻識別碼。 在此情況下，主資料表不會更新，以便稍後可以在此欄位中選擇船隻識別碼。 |
| 外部航程識別碼 | 輸入該航程公開的識別碼 (如航班編號)。 |
| 主要空運單/提單 | 輸入主要空運單或提單編號。 採用空運時可指定此值。 |
| 航空分運單/提單 | 輸入裝運貨櫃的航空分運單或貨代提單。 |
| 租賃 | 選取此核取方塊，代表此貨櫃為租賃貨櫃，必須歸還。 |
| 描述 | 輸入航程說明以利辨識。 |
| 航程狀態 | 航程的狀態。 值包括 *已建立*、*在運輸途中*、*收到的文件* 和 *已計算成本*。 此欄位並非由邏輯計算。 只會由過帳動作更新。 *已計算成本* 值代表已收到庫存和所有航程成本的發票。 除非收到發票，否則航程無法變成 *已計算成本* 狀態。 |
| 訂購單狀態 | 航程所有相關訂購單中的最高狀態。 |
| 收到的文件 | 此值會呈現您的公司是否收到航程相關的所有文件。 若要變更此值，請於動作窗格 **管理** 索引標籤的 **航程更新** 群組中，選擇 **收到的文件**。 |
| 裝運公司 | 選取此航程的裝運公司。 此欄位可用於決定自動成本。 |
| 姓名 | **裝運公司** 欄位選取的公司名稱。 |
| 測量 | 此欄位可測量自動成本。 不知道貨物個別體積或重量的組織通常會使用測量，但這需要比金額或數量更精準的分攤作業。 貨運業者將提供重量或立方測量，您可以將其放在品項或訂購單的等級。 如果參數已選擇，它便可以自動更新，或者也可以手動輸入。 |
| 測量單位 | 適用於 **測量** 欄位中數字的測量單位。 |
| 棧板數量 | 指定航程明細的棧板數量。 若 **到岸成本參數** 頁面 **一般** 索引標籤的 **自動更新箱數** 選項設為 *是*，則此欄位會自動更新。 |

### <a name="settings-on-the-delivery-fasttab"></a>交貨 FastTab 上的設定

下表說明航程 **標題** 檢視 **交貨** FastTab 可用的欄位。

| 欄位 | 描述 |
|---|---|
| 建立日期和時間 | 建立航程記錄的日期與時間。 |
| 工廠交貨日期 | 此欄位會從航程連結的訂購單中，選取最早的工廠交貨日期。 工廠交貨日期會出現在訂購單標題，可使用追蹤控制功能更新。 |
| 出貨日期 | 飛機或船隻離開來源地的預計日期。 |
| 出發日期 | 出發日期通常是飛機或船隻實際離開海外空港或港口的日期。 出貨日期和出發日期不一定一樣。 **出發日期** 欄位僅供參考。 不會用於估計預期交貨日期。 追蹤控制功能可用於估計預期交貨日期，且可設定此欄位，讓追蹤控制功能自動填入。 |
| 入庫日期 | 此欄位會從航程連結的訂購單中，選取貨物可供出售的最早日期。 |
| 預估交貨日期 | 預估交貨日期通常是貨物抵達倉庫的期限日期。 此欄位僅供參考。 不會用於貨物的主規劃。 訂購單明細的預期交貨日期會用於航程內貨物的主規劃，會由追蹤控制功能更新。 可設定此欄位，讓追蹤控制功能自動填入。 |
| 實際交貨日期 | 與航程連結的貨物中，最早的交貨日期。 |
| 運輸港口的 ETA | 依據裝運代理機構提供的資訊，輸入航程預期會抵達運輸港的日期。 |
| 收到原始文件 | 輸入收到原始文件的日期。 |
| 經紀商告知 | 輸入告知經紀商的日期。 |
| 寄出的原始提單 | 輸入原始提單發送的日期。 |
| 貨物放行 | 輸入貨物從海關放行的日期。 |
| 客戶預約 | 輸入客戶預約日期，亦即您預期客戶取得貨物所有權的日期。 |
| 倉庫交貨 | 輸入貨物交貨至倉庫的日期。 |
| 驗證日期 | 輸入驗證日期。 |
| 交貨說明 | 輸入收到交貨說明的日期。 |
| 交貨模式 | 此欄位提供的資訊係關於航程交貨方法，以及交貨方法相關聯的自動成本選擇。 |
| 起點港口 | 航程出發的運輸港。 |
| 終點港口 | 航程抵達的運輸港。 裝運貨櫃可能有不同港口，因為該船隻可能會在多個港口停靠。 確認裝運貨櫃層級的「終點」港口，即可準確提供航程內每個裝運貨櫃的港口詳細資料。 貨運相關聯的自動成本則取決於裝運貨櫃類型、「終點」港口和「起點」港口。 |
| 本地業者 | 此欄位僅供參考。 本地業者應該可以從廠商資料表中選擇。 |
| 本地運輸日期 | 預訂的本地運輸日期。 此欄位可以幫助倉庫執行其計劃。 |
| 本地運輸時間 | 預訂的本地運輸時段。 此欄位可以幫助倉庫執行其計劃。 |
| 旅程圖範本 | 為航程指定的旅程範本。 旅程圖範本可用於輸入裝運貨櫃和航程的「終點」港口和「起點」港口。 這些值可額外協助辨識此航程相關聯的自動成本。 |

### <a name="settings-on-the-other-fasttab"></a>其他 FastTab 上的設定

下表說明航程 **標題** 檢視 **其他** FastTab 可用的欄位。

| 欄位 | 描述 |
|---|---|
| 備註 | 輸入與航程相關的其他資訊。 |
| 評價日期 | 從航程連結的訂購單中，選取最早的工廠交貨日期。 |
| 待定航程 | 您可藉此來代表運送或航程是否已啟程。 此資訊僅供參考。  |
| 剩餘裝運貨櫃 | 若航程有多個貨櫃，此為尚未收到的貨櫃數量。 |

## <a name="voyage-update-periodic-tasks"></a>航程更新定期任務

**到岸成本** 模組包括數個航程相關的定期任務，可大量更新航程的多個方面。 若要執行或排程這些定期任務，請移至 **到岸成本 \> 定期任務 \> 航程更新**，並選取下列一種任務類型：

- **收到的文件** – 此任務可讓您同時為多個航程將 **收到的文件** 設為 *是*。 使用 **篩選** 設定來定義您要更新的一組航程。
- **在運輸途中** – 此任務可讓您同時為多個航程，依據 **[到岸成本參數](landed-cost-parameters.md)** 頁面的設定，將 **航程狀態** 欄位設定為在途狀態。 使用 **篩選** 設定來定義您要更新的一組航程。
- **準備好進行成本核算** – 此任務可讓您同時為多個航程，依據 **[到岸成本參數](landed-cost-parameters.md)** 頁面的設定，將 **航程狀態** 欄位設定為準備好進行成本核算狀態。 您通常會將此任務設為定期執行。
- **已計算成本** – 此任務可讓您同時為多個航程，依據 **[到岸成本參數](landed-cost-parameters.md)** 頁面的設定，將 **航程狀態** 欄位設定為已計算成本狀態，前提是這些航程已計算成本但尚未更新。 您通常會將此任務設為定期執行。