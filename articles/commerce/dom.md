---
title: 分散式訂單管理 (DOM)
description: 本主題描述了 Dynamics 365 Commerce 中的分散式訂單管理 (DOM) 功能。
author: josaw1
ms.date: 02/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f19fbe2a9f768a91c495a6a4bcb0e475adb867ae
ms.sourcegitcommit: 8bea5a0c232ac31dcafddfcc0d715c496d8dd445
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8452958"
---
# <a name="distributed-order-management-dom"></a>分散式訂單管理 (DOM)

[!include [banner](includes/banner.md)]

本主題描述了 Microsoft Dynamics 365 Commerce 中的分散式訂單管理 (DOM) 功能。

DOM 是一套全通路訂單履行最佳化解決方案，有助於在供應鍊網路中充分發揮訂單履行的效益。 DOM 可幫助您確保產品適時從適當的來源以正確的數量交付給您的客戶。 DOM 還可以幫助您實現利潤最大化、成本最小化並滿足服務等級需求。

DOM 使用混合整數規劃 (MIP) 和預測分析模型在批次等級和個別訂單等級執行最佳化。 此功能使零售商能夠使用定義的規則來平衡許多相互衝突的訂單履行需求。 在現代供應網路中，產品履行可能來自多個管道，組織必須快速適應訂單變動、供應商可用性問題和需求高峰。 DOM 可幫助您根據業務限制和目標 (例如透過從最近的來源履行訂單將成本降至最低) 充分發揮訂單履行的效益並尋找正確的產品交付來源。 DOM 使用產品履行來源和運送目的地之間的距離、定義為最佳化目標的成本因素以及定義為約束的規則 (例如履行節點的庫存) 將訂單履行最佳化。 DOM 允許定義多個設定檔，使企業能夠執行不同的最佳化策略，具體取決於業務類型或消費者細分。 

下圖顯示了 DOM 系統中銷售訂單的生命週期。

![DOM 內容中的銷售訂單生命週期。](./media/flow.png "DOM 內容中的銷售訂單生命週期")

## <a name="set-up-dom"></a>設定 DOM

1. 移至 **系統管理 \> 設定 \> 授權設定**。
2. 在 **設定金鑰** 索引標籤上，展開 **Commerce** 節點，然後選擇 **分散式訂單管理** 核取方塊。
3. 移至 **Retail 和 Commerce \> 分散式訂單管理 \> 設定 \> DOM 參數**。
4. 在 **一般** 索引標籤上，設定以下值：

    - **啟用分散式訂單管理** – 將此選項設為 **是**。
    - **確認 DOM 使用 Bing 地圖服務** – 將此選項設為 **是**。

        > [!NOTE]
        > 您只能在 **Commerce 共用參數** 頁面的 **Bing 地圖服務** 索引標籤上的 **啟用 Bing 地圖服務** 選項 (**Retail 和 Commerce \> Headquarters 設定 \> 參數 \> Commerce 共用參數**) 也設為 **是**，並且在 **Bing 地圖服務金鑰** 欄位已輸入有效金鑰時，才可以將此選項設為 **是**。
        >
        > [Bing 地圖服務開發中心](https://www.bingmapsportal.com/)入口網站允許您將對 Bing 地圖服務 API 金鑰的存取限制為您指定的一組網域。 借助此功能，客戶可以定義一組嚴格的參考者值或 IP 位址範圍，以驗證金鑰。 來自您的允許清單的要求將正常處理，而來自您的清單之外的要求將傳回拒絕存取的回應。 為您的 API 金鑰添加網域安全性是選擇性的，而保留原樣的金鑰將繼續發揮作用。 金鑰的允許清單獨立於您的所有其他金鑰，使您能夠為每個金鑰制定不同的規則。 分散式訂單管理不支援設定參考網域的屬性。

    - **保留期間 (天)** – 指定 DOM 執行產生的履行計劃在系統中保留多長時間。 **DOM 履行資料刪除作業設定** 批次處理作業將刪除任何超過您在此處指定的天數的履行計劃。
    - **拒絕期間 (天)** – 指定必須經過多長時間才能將拒絕的訂單明細指派至同一位置。

5. 在 **求解工具** 索引標籤上，設定以下值：

    - **最大自動履行嘗試次數** – 指定 DOM 引擎嘗試將訂單明細代理到某個位置的次數。 如果 DOM 引擎無法在指定的嘗試次數內將訂單明細代理到某個位置，它會將該訂單明細標記為例外狀況。 然後它將在之後的執行中跳過該明細，直到手動重設狀態。
    - **本地商店區域半徑** – 輸入一個值。 此欄位有助於確定如何就距離將位置分組並視為相等。 例如，如果您輸入 **100**，則距離履行地址 100 英里半徑內的每個商店或配送中心都視為相等距離。
    - **求解工具類型** – 選擇一個值。 Commerce 發行了兩種求解工具類型：**生產求解工具** 和 **簡易求解工具**。 對於將執行 DOM 的所有機器 (即屬於 DOMBatch 群組的所有伺服器)，必須選擇 **生產求解工具**。 生產求解工具需要特殊的授權金鑰，預設情況下，該金鑰已授權並部署在實際執行環境中。 在較新的第 2 層以上環境中，已啟用生產求解工具。 對於非實際執行環境，必須手動部署此授權金鑰。 要手動部署授權金鑰，請執行以下步驟：

        1. 在 Microsoft Dynamics Lifecycle Services 中，打開共用資產庫，選擇 **模型** 做為資產類型，並下載 **DOM 授權** 檔案。
        1. 啟動 Microsoft Internet Information Services (IIS) 管理員，用右鍵按一下 **AOSService 網站**，然後選擇 **探索**。 Windows 檔案總管視窗會在 **\<AOS service root\>\\webroot** 開啟。 記下 \<AOS Service root\> 路徑，因為您將在下一步中用到它。
        1. 複製 **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin** 目錄中的組態檔。
        1. 前往 Headquarters 用戶端，打開 **DOM 參數** 頁面。 在 **求解工具** 索引標籤上的 **求解工具類型** 欄位中，選擇 **生產求解工具**，並確認沒有出現錯誤訊息。

        > [!NOTE]
        > 提供的簡易求解工具讓零售商無需部署特殊授權即可試用 DOM 功能。 組織不應在實際執行環境中使用簡易求解工具。
        >
        > 生產求解工具可提高效能 (例如可以在執行中處理的訂單和訂單明細的數量) 和結果的聚合 (因為在某些情況下一批訂單可能不會產生最佳結果)。 一些規則如 **部分訂單** 規則和 **最大位置數** 規則需要生產求解工具。

6. 返回 **Retail 和 Commerce \> 分散式訂單管理 \> 設定 \> DOM 參數**。
7. 在 **數序** 索引標籤上，將所需的數序指派至各種 DOM 實體。

    > [!NOTE]
    > 在將數序指派至實體之前，必須在 **編號序列** 頁面 (**組織管理 \> 編號序列 \> 編號序列**) 中先進行定義。

8. DOM 功能支援定義各種類型的 DOM 規則，而組織可以根據業務需要設定多個規則。 可以為一組位置或單個位置以及特定產品類別、產品或變型定義 DOM 規則。 要建立必須用於 DOM 規則的位置群組，請執行以下步驟：

    1. 移至 **Retail 和 Commerce \> 管道設定 \> 履行群組**。
    2. 選擇 **新增**，然後輸入新群組的名稱和描述。
    3. 選擇 **儲存**。
    4. 選擇 **新增明細** 將單個位置添加到群組中。 或者，選擇 **新增明細** 添加多個位置。

    > [!NOTE]
    > 在 Commerce 版本 10.0.12 及更高版本中，必須在 **功能管理** 工作區中啟用 **能夠在履行群組中將位置指定為 '送貨' 或 '取貨'**。
    >
    > 此功能會在 **履行群組** 頁面添加新設定，讓您能夠定義倉庫是否可用於送貨，或者倉庫/商店組合是否可用於送貨、取貨或兩者。 
    >
    > 如果您啟用該功能，則將更新當您在 POS 中建立取貨或送貨訂單時可用於位置選擇的選項。
    >
    > 當選擇「全部運送」或「運送選取項」作業時，啟用該功能同時會導致 POS 中的頁面更新。

9. 要定義規則，請移至 **Retail 和 Commerce \> 分散式訂單管理 \> 設定 \> 管理規則**。 目前支援以下 DOM 規則：

    - **最低庫存規則** – 此規則類型可讓組織「限制」特定數量的產品，用於訂單履行以外的目的。 例如，組織可能不希望 DOM 考慮商店中所有可用的庫存來履行訂單。 相反地，他們可能想要保留一些庫存給上門客戶。 使用此規則類型時，您可以為每個位置或位置群組的產品類別、單個產品或產品變型定義要保留的最低庫存。 您也可以使用補充類別階層來定義最低庫存。 如果產品屬於多個類別，則補充類別對於您可以使用類別的所有規則具有最高重要性。
    - **履行位置優先規則** – 此規則類型可讓組織定義位置階層，以確定 DOM 引擎在嘗試識別特定產品的履行位置時考慮的優先順序。 優先順序的有效範圍是 1 到 10，其中 1 是最高優先，10 是最低優先。 優先順序較高的位置優先於優先順序較低的位置。 如果將某規則定義為硬性限制規則，則只會將訂單代理到有定義優先順序的位置。 DOM 會優先考慮將訂單完全由一個位置發貨。 因此，如果整個訂單及其明細在優先順序為 1 的位置沒有供貨，則 DOM 將嘗試從優先順序為 2 的位置履行它。
    - **部分訂單規則** – 在 Retail 版本 10.0.5 中，**僅從一個位置履行訂單** 參數已改為 **最大履行位置**。 舊參數可讓使用者設定只從一個位置還是從盡可能多的位置履行訂單。 新參數可讓使用者指定是否可從一組限定的位置 (最多五個) 還是從盡可能多的位置來履行。 對於除了從一個位置履行之外的所有選項，DOM 會將明細分割，因為訂單的處理是按明細進行的。 此規則僅適用於生產求解工具。
    - **離線履行地點規則** – 此規則可讓組織將一個或一組位置指定為離線或無法用於 DOM，這樣就無法將訂單指派到這些位置用於履行。
    - **最大拒絕規則** – 此規則可讓組織定義拒絕的閾值。 當達到閾值時，DOM 處理器會將訂單或訂單明細標記為例外狀況，並將其排除在進一步處理之外。 為了確保效能，DOM 不會查看所有拒絕的記錄。 

        將訂單明細指派至一個位置後，該位置可以拒絕指派的訂單明細，因為它可能因故無法履行該明細。 遭拒的明細會標記為例外狀況並放回集區中以供下次執行時處理。 在下一次執行期間，DOM 將嘗試將遭拒的明細指派至不同的位置。 新位置也可以拒絕指派的訂單明細。 這種指派和拒絕的週期可能發生多次。 當拒絕計數達到定義的閾值時，DOM 會將訂單明細標記為永久例外狀況，並且不會再次選擇該明細進行指派。 唯當使用者手動重設訂單明細的狀態時，DOM 才會再次考慮重新指派訂單明細。

    - **最大距離規則** – 此規則可讓組織定義可以履行訂單的一個位置或一組位置的最大距離。 如果為某個位置定義了重疊的最大距離規則，則 DOM 將套用為該位置定義的最小最大距離。
    - **最大訂單規則** – 此規則可讓組織定義一個位置或一組位置可以處理的最大訂單數目。 在最佳化過程中，系統將考慮尚未從這些位置發貨的訂單。 此檢查是跨設定檔完成的。 因此，如果在同一位置的設定檔中定義了重疊的最大訂單數，系統將考慮在所有設定檔中定義的最大訂單數。 

    以下是可以為上述所有規則類型定義的一些通用屬性：

    - **開始日期** 和 **結束日期** – 您可以使用這些欄位使每個規則日期生效。
    - **已停用** – 在 DOM 執行中，僅會考慮此欄位具有 **否** 值的規則。
    - **硬性限制** – 可以將規則定義為硬性限制或非硬性限制。 每個 DOM 執行都會經歷兩次反覆運算。 在第一次反覆運算中，會將每個規則視為硬性限制規則，無論此欄位的設定為何。 換句話說，會套用每條規則。 唯一的例外是 **位置優先** 規則。 在第二次反覆運算中，將移除未定義為硬性限制規則的規則，並且在套用所有規則時會將未指派至位置的訂單或訂單明細指派至位置。

10. 履行設定檔用於對規則、法律實體、銷售訂單來源和交貨方式的集合進行分組。 每個 DOM 執行都是針對特定的履行設定檔。 透過這種方式，組織可以針對具有特定銷售訂單來源和交貨方式的訂單，為一組法律實體定義和執行一組規則。 因此，如果必須為不同的銷售訂單來源或交貨方式集執行不同的規則集，則可以相應地定義履行設定檔。 要設定履行設定檔，請執行以下步驟：  

    1. 移至 **Retail 和 Commerce \> 分散式訂單管理 \> 設定 \> 履行設定檔**。
    2. 選取 **新增**。
    3. 在 **設定檔** 和 **描述** 欄位中輸入值。
    4. 設定 **自動套用結果** 選項。 如果您將此選項設定為 **是**，設定檔的 DOM 執行結果將自動套用至銷售訂單明細。 如果您將其設為 **否**，則只能在履行計劃中查看結果。 它們不會套用至銷售訂單明細。
    5. 如果您希望為具有每個銷售訂單來源的訂單執行 DOM 設定檔，包括未定義銷售訂單來源的訂單，請將 **處理具有空白銷售來源的訂單** 選項設為 **是**。 若只要為少數銷售訂單來源執行設定檔，您可以在 **銷售來源** 頁面上定義，如稍後解釋。

        > [!NOTE]
        > 在 Commerce 版本 10.0.12 及更高版本中，必須在 **特徵管理** 工作區中啟用 **能夠將履行群組指派至履行設定檔** 功能。 此功能可讓您指定在使用履行設定檔執行最佳化時 DOM 應考慮的倉庫清單。 如果未指定此倉庫清單，DOM 將查看設定檔中定義的法律實體上的所有倉庫。
        >
        > 此功能會在 **履行設定檔** 頁面新增一個可以關聯到單個履行群組的設定。 
        >
        > 如果您選擇履行群組，則該履行設定檔的 DOM 規則將有效率地針對履行群組中包含的「發貨」倉庫執行。 
        > 
        > 要有效使用此功能，請確保有一個包含所有發貨倉庫的履行群組，然後將該履行群組關聯到履行設定檔。

    6. 在 **法律實體** FastTab 上，選擇 **新增**，然後選擇法律實體。
    7. 在 **規則** FastTab 上，選擇 **新增**，然後選擇要連結至設定檔的規則。
    8. 重複前兩個步驟，直到所有必要規則都與設定檔相關聯。
    9. 選擇 **儲存**。
    10. 在動作窗格上的 **設定** 索引標籤上，選擇 **交貨方式**。
    11. 在 **交貨方式** 頁面，選擇 **新增**。
    12. 在 **公司** 欄位中，選擇法律實體。 公司清單僅限於您之前新增的法律實體。
    13. 在 **交貨方式** 欄位中，選擇與此設定檔相關聯的交貨方式。 交貨方式不能與多個作用中的設定檔相關聯。
    14. 重複前兩個步驟，直到所有必要的交貨方式都與設定檔相關聯。
    15. 關閉 **交貨方式** 頁面。
    16. 在動作窗格上的 **設定** 索引標籤上，選擇 **銷售訂單來源**。
    17. 在 **銷售來源** 頁面上，選擇 **新增**。
    18. 在 **公司** 欄位中，選擇法律實體。 公司清單僅限於您之前新增的法律實體。
    19. 在 **銷售來源** 欄位中，選擇要與此設定檔相關聯的銷售來源。 銷售來源不能與多個作用中的設定檔相關聯。
    20. 重複前兩個步驟，直到所有必要的銷售來源都與設定檔相關聯。
    21. 關閉 **銷售來源** 頁面。
    22. 將 **啟用設定檔** 選項設定為 **是**。 如果設定中有任何錯誤，您會收到一則警告訊息。

## <a name="dom-processing"></a>DOM 處理

DOM 只會在批次作業中執行。 要為 DOM 執行設定批次作業，請執行以下步驟。

1. 移至 **Retail 和 Commerce \> 分散式訂單管理 \> 批次處理 \> DOM 處理器作業設定**。
1. 在 **參數** FastTab 上的 **履行設定檔** 欄位中，選擇一個必須執行 DOM 的設定檔。
1. 在 **在背景執行** FastTab 上的 **批次群組** 欄位中，選擇設定的批次群組。
1. 在 **工作描述** 欄位中，輸入批次作業的名稱。
1. 選擇 **定期**，並定義批次作業的週期性。
1. 選擇 **確定**。

在處理時，DOM 將考慮此處描述的訂單和訂單明細：

- 符合 DOM 設定檔中定義的銷售訂單來源、交貨方式和法律實體準則的訂單明細，同時也滿足以下任何準則：

    - 它們是從 Commerce 管道建立的。
    - 它們從未由 DOM 代理。
    - 它們曾由 DOM 代理，但被標記為例外狀況並且低於嘗試次數的最大閾值。
    - 交貨方式不是取貨或電子交付。
    - 它們沒有標記為交貨。
    - 它們未手動排除。

- 未擱置的訂單

在套用規則、庫存限制和最佳化之後，DOM 會選擇離客戶收貨地址最近的位置。 DOM 會將 **交貨** 類型的地址轉換為緯度和經度值。 然後它會將銷售訂單上的交貨地址轉換為緯度和經度值，並更新地址的緯度和經度值以供將來使用。 DOM 依賴 Bing 地圖服務根據地址、城市和郵遞區號資訊來確定準確的緯度和經度值。

DOM 使用 Bing 地圖服務 API 來計算航空或道路距離，具體取決於設定。 然後它使用此資訊來確定運輸成本。 最佳化模型優先考慮從一個位置履行完整訂單。 即使部分訂單在同一城市或郵遞區號中有供貨，該模型也已最佳化以減少發貨數量。 

DOM 透過查看倉庫 V2 實體中的現有庫存來查詢可用庫存。 在每個批次執行期間，DOM 將訂單分成批次，具體取決於設定檔中定義的工作的 **DOM 處理器** 參數值。 該參數的預設值為 **2000**。 例如，如果在一次執行中最佳化了 10,000 個訂單明細，並且 **DOM 處理器** 參數設定為預設值 **2000**，則 DOM 會建立五個批次並同時處理。 然後從最佳化工具獲得履行計劃並套用在明細上。 如果必須在兩個位置之間分割訂單明細，則 DOM 會確保價格和稅費適當分攤於各明細之間。

![銷售訂單準則](./media/ordercriteria.png "銷售訂單準則")

## <a name="results-of-dom-runs"></a>DOM 執行的結果

如果履行設定檔設定為 **自動套用**，執行的結果將自動套用至銷售訂單明細，並且可以分開查看履行計劃。 然而，如果履行設定檔未設定為 **自動套用**，則只能從履行計劃檢視中看到執行的結果。 

要查看產生的所有履行計劃，請執行以下步驟。

1. 移至 **Retail 和 Commerce \> 分散式訂單管理 \> 分散式訂單管理**。
2. 在 **分散式訂單管理** 工作區中，選擇 **履行計劃** 圖標。
3. 選擇相關訂單履行計劃的識別碼以查看履行計劃。

    履行計劃的訂單詳細資料部分會顯示做為執行一部分的原始銷售訂單明細。 除了標準的銷售訂單明細欄位外，訂單詳細資料部分還包括以下三個與 DOM 相關的欄位：

    - **履行類型** – 此欄位指出銷售訂單明細是完全代理、部分代理還是完全不代理到某個位置。
    - **分割** – 此欄位指出一個銷售訂單明細是否已分割並代理到不同位置。
    - **履行位置的數量** – 此欄位指出為一個銷售訂單明細建立了多少履行明細 (根據代理原始銷售訂單明細的位置數量)。

    訂單履行詳細資料部分會顯示原始銷售訂單明細指派至不同位置及其數量。

## <a name="order-line-actions-and-statuses"></a>訂單明細動作和狀態

下文介紹訂單明細的設定。 要打開訂單明細，移至 **Retail 和 Commerce \> 客戶 \> 所有銷售訂單**。

- 如果您在銷售訂單明細的 **一般** 索引標籤上，將 **從 DOM 處理中排除** 選項設定為 **是**，則會將訂單或訂單明細排除在 DOM 處理之外。
- 銷售訂單明細的 **一般** 索引標籤上的 **DOM 狀態** 欄位可以設定為以下值之一：

    - **無** – 訂單明細從未代理過。
    - **完全** – 訂單明細已成功代理並指派至一個位置。
    - **例外狀況** – 訂單明細已成功代理但無法指派至一個位置。 例外狀況有多個子類型，可以從 DOM 工作區查看：

        - **沒有可用數量** – 位置中沒有可指派給訂單的可用庫存。
        - **最大拒絕數** – 訂單明細已達到拒絕的最大閾值。
        - **資料修改衝突** – 自代理訂單以來，銷售訂單明細已更改。 因此，履行計劃不能套用至訂單。
        - **訂單明細特定例外狀況** – 訂單明細有多個例外狀況。

- 在銷售訂單登錄過程中，DOM 可在互動模式中執行。 輸入訂單明細時，在指定產品和數量後，您可以選擇 **更新明細**，然後在 **DOM** 下選擇 **建議履行位置**。 然後，您會看到一個根據 DOM 規則的位置清單，這些是可以滿足訂單明細上的數量的位置。 此清單按距離排序。 選擇一個位置以在銷售訂單明細上設定相關地點和倉庫。 要使此功能發揮作用，必須存在與銷售明細上的銷售來源和交貨方式相符的現有作用中履行設定檔。
- 要查看銷售訂單明細的 DOM 執行記錄，請選擇 **銷售訂單明細**，然後在 **DOM** 下選擇 **查看 DOM 記錄**。 DOM 記錄會顯示由 DOM 執行所產生的所有事件和記錄。 記錄可以幫助您了解為什麼將特定位置指派至訂單明細，以及哪些規則和限制被視為指派的一部分。 在 **管理** 索引標籤上，也可以取得銷售訂單標題層級的 DOM 記錄。

## <a name="run-a-clean-up-job-for-dom-fulfillment-plans"></a>為 DOM 履行計劃執行清理作業

在執行 DOM 處理時，會建立履行計劃。 系統隨著時間會保留許多履行計劃。 要管理系統保留的履行計劃數量，您可以設定一個批次作業，根據 **保留期間 (天)** 值來刪除舊履行計劃。

1. 移至 **Retail 和 Commerce \> 分散式訂單管理 \> 批次處理 \> DOM 履行資料刪除作業設定**。 
1. 在 **批次群組** 欄位中，選擇設定的批次群組。
1. 選擇 **定期**，並定義批次作業的週期性。
1. 選擇 **確定**。

## <a name="more-information"></a>其他資訊

以下是使用 DOM 功能時需要考慮的一些事項：

- 目前，DOM 只查看從 Commerce 管道建立的訂單。 當 **Commerce 銷售** 選項設為 **是** 時，會將銷售訂單識別為銷售訂單。
- Microsoft 尚未測試 DOM 的進階倉儲管理功能。 因此，客戶和合作夥伴必須審慎確定 DOM 是否與他們相關的進階倉儲管理功能和流程相容。 進階倉儲支援可設定的維度，例如庫存狀態，但無法準確了解可用庫存。 DOM 提供了一種可擴充的方法為使用進階倉儲的實作設定可用庫存。 它可用於處理庫存狀態和其他維度的自訂值。

    DOM 中的可擴充性有限，因為最佳化發生在考慮最佳化及其限制的預建 MIP 模型中。 已有幾個可擴充點可用於設訂庫存和後處理最佳化。 DOM 設定檔可能因銷售來源和交貨方式而異。 銷售訂單來源可以在訂單擷取過程中設定，並且可以根據這些值使用不同的最佳化策略。 DOM 還支援建立自訂批次作業，這些作業可以將 DOM 處理器工作做為輸入並使設定檔做為參數傳遞。 因此，最佳化可以一個接著一個地執行，以支援不同的商務案例。

- DOM 僅在 Commerce 的雲端版本上可用。 它在內部部署中不受支援。


[!INCLUDE[footer-include](../includes/footer-banner.md)]