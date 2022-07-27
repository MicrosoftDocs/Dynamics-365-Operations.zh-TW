---
title: 靈活的倉庫級維度保留原則
description: 本主題描述的庫存保留原則，可讓銷售批次追蹤產品與在支援 WMS 的工作中執行物流的企業，在即使與產品關聯的預留階層不允許預留特定批次的情況下，也能為客戶銷售訂單保留特定批次。
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReservationHierarchy, WHSWorkTrans, WHSWorkInventTrans, WHSInventTableReservationHierarchy, WHSReservationHierarchyCreate, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 0fe4b377ec80601f616f81f71222129256dfd448
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2021
ms.locfileid: "8447540"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>靈活的倉庫級維度保留原則

[!include [banner](../includes/banner.md)]

當 *Batch-below\[location\]* 類型的庫存預留階層與產品相關聯時，銷售批次追蹤產品並將其物流作為啟用 Microsoft Dynamics 365 Warehouse Management 系統 (WMS) 操作的企業，將無法保留那些特定批次的客戶銷售訂單產品。

以相似的方式，當銷售訂單上的產品與預設預留階層關聯時，這些產品便不能保留特定授權。

此主題描述即使產品與 *批次以下\[位置\]* 預留階層關聯，也允許這些企業保留特定批次或授權的庫存保留原則。

## <a name="inventory-reservation-hierarchy"></a>庫存預留階層

本節總結了現有的庫存預留階層資訊。

庫存預留階層指示，就儲存體維度而言，需求訂單包含站點、倉庫和庫存狀態的強制性維度。 換句話說，強制性維度是在預留階層中位置維度之上的所有維度，而倉庫邏輯則負責將位置指派給請求的數量並預留位置。 在需求訂單和倉庫工作之間的互動中，需求訂單應該指明訂單必須從哪裡發貨 (即特定站點與倉庫)。 然後，倉庫會依賴其邏輯，以在倉庫場址找到所需數量。

但是，為反映企業的營運模式，追蹤維度 (批次和序號) 具有更大的靈活性。 庫存預留階層可以適應適用於以下條件的案例：

- 在倉庫儲存空間中取得數量 *之後*，企業會依賴其倉庫工作來管理具有批次或序號之數量的揀貨。 此模型通常被稱為 *批次以下\[位置\]* 或 *序列以下\[位置\]*。 對向售貨公司提出需求的客戶而言，當產品的批次或序號識別碼並不重要時，通常會使用這種方式。
- 在倉庫儲存空間中取得數量 *之前*，企業會依賴其倉庫工作來管理具有批次或序號之數量的揀貨。 如果客戶的訂單規格中需要批號或序號，則它們會被記錄在需求訂單上，而且在倉庫中尋找數量的倉庫工作不允許進行更改。 此模型通常被稱為 *批次以上\[位置\]* 或 *序列以上\[位置\]*。 因為位置以上的維度是必須滿足之需求的具體要求，所以倉庫邏輯不會對它們進行指派。 需求訂單上或相關保留中 **必須** 始終指定這些維度。

在這些案例中，挑戰在於只能為每個已發布產品指派一個庫存預留階層。 因此，對於 WMS 處理追蹤項目而言，在階層指派判斷何時應保留批次或序號後 (在接受需求訂單時或在倉庫揀貨工作期間)，此時間即不能臨時更改。

## <a name="flexible-reservation-for-batch-tracked-items"></a>批次追蹤項目的靈活預留

### <a name="business-scenario"></a>商務案例

在此案例中，一家公司使用了一種依批號進行成品追蹤的庫存策略。 此公司也使用了 WMS 工作負載。 由於此工作負載具備的完善邏輯，可用於規劃和執行啟用批次項目的倉庫揀貨和運輸工作，因此多數成品都與 *批次以下\[位置\]* 庫存預留階層關聯。 這種工作設定的優勢在於，關於揀選的批次，以及放入倉庫的位置決定 (實際上是預留決策)，會被推遲到倉庫揀選工作開始時才進行。 它們並不是在客戶下訂單時進行的。

雖然 *批次以下\[地點\]* 預留階層能夠充分滿足公司業務目標，但公司的許多既有客戶在重新訂購產品時，會要求與之前購買的批次相同。 因此，該公司正在尋求批次保留規則處理方式的靈活性，於是根據客戶對同一項目的需求，便出現了以下行為：

- 銷售處理人員接單時可以記錄和保留批號，且該批號在倉庫工作過程中不能進行變更和/或被其他需求取用。 此行為有助於將訂購的批號確實運交給客戶。
- 如果客戶不在乎批號，則在完成銷售訂單登記和預訂後，倉庫工作可以在揀貨工作中決定批號。

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>允許在銷售訂單上保留特定批次

為了適應與 *批次以下\[位置\]* 庫存預留階層關聯的項目批次預留行為靈活性，庫存管理員必須在 **庫存預留階層** 頁面上的 **批號** 層級選取 **允許依需求訂單進行預留** 核取方塊。

![讓庫存預留階層變為彈性。](media/Flexible-inventory-reservation-hierarchy.png)

選擇階層中的 **批號** 層級時，將自動選擇該層級以上和 **位置** 層級以上的所有維度。 (預設情況下，所有高於 **位置** 層級的維度都會被預先選擇。) 此行為反映出的邏輯，是當您在訂單明細上保留特定批號後，批號和位置範圍內的所有維度也會自動保留。

> [!NOTE]
> **允許依需求訂單進行預留** 核取方塊僅適用低於倉庫位置維度的預留階層等級。
>
> **批號** 和 **牌照** 是階層中唯一對彈性保留原則開放的層級。 換句話說，您不能在 **位置** 或 **批號** 層級選擇 **允許依需求訂單進行預留** 核取方塊。
>
> 如果您的預留階層包括序號維度 (必須始終低於 **批號** 層級)，且如果您已為批號打開了特定批次的保留，則根據適用於 *序號以下\[地點\]* 保留原則，系統將繼續處理序號保留和揀選工作。

在任何時候，您都可以為部署中的現有 *批次以下\[位置\]* 預留階層允許特定批次的保留。 此變更不會影響變更發生之前建立的任何預留和未結倉庫工作。 但是，如果與該預留階層關聯的一或多個項目存在 **訂購保留**、**預留實物** 或 **已訂購** 發貨類型的庫存交易記錄，則無法清除 **允許依需求訂單進行預留** 核取方塊。

> [!NOTE]
> 如果項目的現有預留階層不允許在訂單上指定批次，您可以將其重新分配到允許批次規範的預留階層，前提是兩個層次結構中的層次結構級別結構相同。 使用 **變更項目的預留階層** 功能進行重新指派。 當您希望阻止對批次追蹤項目的子集進行靈活的批次預留，但允許對產品組合其餘部分進行靈活預留時，此變更便可能與此相關。

無論您是否選擇了 **允許依需求訂單進行預留** 核取方塊，如果您不想為訂單明細上的項目預留特定批次編號，則對 *批次以下\[位置\]* 預留階層有效的預設倉庫工作邏輯仍將適用。

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>為客戶訂單保留特定批號

在批次追蹤項目的 *批次以下\[位置\]* 庫存預留階層設定為允許在銷售訂單上預留特定批號後，銷售訂單處理者可以根據客戶的請求，透過以下方式之一處理同一項目的客戶訂單：

- **在不指定批號的情況下輸入訂單詳細資訊** - 當產品的批次規格對客戶不重要時，應使用此方法。 與在系統中處理此類型訂單相關聯的所有現有流程保持不變。 使用者無需考慮其他事項。
- **輸入訂單詳細資訊並保留特定批號** - 當客戶請求特定批次時，應使用此方法。 通常，客戶在重新訂購以前購買的產品時會請求特定批次。 這種特定於批次的保留類型稱為 *訂單承諾保留*。

以下規則集在處理數量，且批號承諾到特定訂單時有效：

- 要允許根據 *批次以下\[位置\]* 預留政策為項目保留特定批號，系統必須透過位置保留所有維度。 該範圍通常包括牌照維度。
- 為使用訂單承諾批次保留的銷售明細建立揀貨工作時，不使用位置指令。
- 在訂單承諾批次的倉庫處理過程中，使用者和系統都不允許變更批號。 (此處理包括例外狀況處理。)

以下範例顯示了端到端流程。

## <a name="example-scenario-batch-number-allocation"></a>範例案例：批號分配

為了進行此範例，必須安裝示範資料，並且必須使用 **USMF** 示範資料公司。

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a>設定庫存預留階層以允許特定於批次的保留

1. 前往 **倉庫管理**\>**設定**\>**庫存\>預留階層**。
2. 選擇 **新增**。
3. 在 **名稱** 欄位中，輸入一個名稱 (例如，**BatchFlex**)。
4. 在 **描述** 欄位中，輸入描述 (例如，**批次低於彈性**)。
5. 在 **已選擇** 欄位中，選擇 **序號** 和 **所有者**，然後選擇向左箭頭按鈕以將其移動到 **可用** 欄位。
6. 選擇 **確定**。
7. 在 **批號** 維度層級的列中，選擇 **允許依需求訂單進行預留** 核取方塊。 **牌照** 與 **位置** 層級將自動選擇，並且您無法清除它們的核取方塊。
8. 選擇 **儲存**。

### <a name="create-a-new-released-product"></a>建立新的已發布產品

1. 使用以下值設定產品的三個主資料參數：

    - 在 **儲存維度群組** 欄位，選擇 **Ware**。
    - 在 **追蹤維度群組** 欄位中，選擇 **Batch-Phy**。
    - 在 **預留階層** 欄位中，選擇 **BatchFlex**。

2. 建立兩個批號，如 **B11** 和 **B22**。
3. 使用以下值將項目數量新增到現有庫存。

    | 倉庫 | 批次編號 | 位置 | 牌照 | 數量 |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | 無          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a>輸入銷售訂單詳細資料

1. 前往 **銷售和行銷**\>**銷售訂單**\>**所有銷售訂單**。
2. 選擇 **新增**。
3. 在銷售訂單標頭上的 **客戶帳戶** 欄位中，輸入 **US-003**。
4. 為新項目新增一明細，然後在數量輸入 **10**。 確認 **倉庫** 欄位設為 **24**。
5. 在 **銷售訂單明細** FastTab 上，選擇 **庫存**，然後在 **維護** 群組中，選擇 **批次保留**。 **批次保留** 頁面顯示可用於為訂單明細進行保留的批次清單。 在此範例中，批號 **B11** 顯示數量為 **20**，批號 **B22** 顯示數量為 **10**。 請注意，如果該明細上的項目與 *批次以下\[位置\]* 預留階層相關聯，則無法從該明細存取 **批次保留** 頁面，除非它被設定為允許特定批次的保留。

    > [!NOTE]
    > 如要為銷售訂單保留特定批次，您必須使用 **批次保留** 頁面。
    >
    > 如果您直接在銷售訂單明細上輸入批號，則系統的行為就像您為項目輸入了特定的批次值一樣，該項目受 *批次以下\[位置\]* 保留策略的約束。 保存該明細時，您將收到一條警告訊息。 如果您確認應直接在訂單明細上指定批號，則該明細將不會由一般倉庫管理邏輯進行處理。
    >
    > 如果您從 **保留** 頁面保留數量，則不會保留任何特定批次，並且該明細的倉庫操作執行將遵循 *批次以下\[位置\]* 保留原則下適用的規則。

    通常，此頁面對於具有 *批次以上\[位置\]* 類型的關聯預留階層的項目的運作方式和互動方式相同。 但是，仍有以下適用的例外情況：

    - **承諾給來源明細的批號** FastTab 會顯示為訂單明細保留的批號。 網格中的批次值將顯示在訂單明細的整個履明細週期中，包括倉庫處理階段。 對比之下，在 **概觀** FastTab 上，一般訂單明細保留 (即為 **位置** 層級以上的維度執行的保留) 將顯示在網格中，直到建立倉庫工作為止。 然後，工作實體會接管明細保留，並且明細保留不會再顯示於頁面上。 **承諾給來源明細的批號** FastTab 有助於確保銷售訂單處理者可以在客戶訂單生命週期的任何時間點 (直到開立發票) 都能檢視承諾給客戶訂單的批號。
    - 除了保留特定批次外，使用者還可以手動選擇批次的特定位置和牌照，而不是讓系統自動選擇。 此能力與訂單承諾批次保留機制的設計有關。 如前所述，在根據 *批次以下\[位置\]* 保留原則為項目保留批號時，系統必須透過位置向上保留所有維度。 因此，倉庫工作將具有與使用訂單的使用者保留的相同儲存維度，並可能不會一律表示便於，甚至可能進行揀貨工作的項目儲存位置。 如果訂單處理者知道倉庫限制，他們可能希望在保留批次時手動選擇特定位置和牌照。 在這種情況下，使用者必須使用 **顯示維度** 頁面標頭上的功能，並且必須在 **概述** FastTab 上的網格中新增位置和牌照。

6. 在 **批次保留** 頁面上，選擇批次 **B11** 的明細，然後選擇 **保留明細**。 在自動預訂期間，沒有用於指派位置和牌照的指定邏輯。 您可以在 **保留** 欄位中手動輸入數量。 請注意，在 **承諾給來源明細的批號** FastTab 上，批次 **B11** 顯示為 **已承諾**。

    ![將特定批號承諾給批次保留頁面上的銷售訂單明細。](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > 銷售訂單明細上的數量保留可以跨多個批次完成。 同樣，可以針對多個位置和牌照進行同一批次的保留 (如果這些位置已啟用了牌照)。
    >
    > 為銷售訂單明細上的數量保留特定批次也可以是部分的。 例如，可以保留的總數量為 100 個單位，以便將特定批次承諾 20 個單位，而在網站和倉庫層級為任何可用批次保留 80 個單位。 在此情況下，WMS 將使用兩條單獨的工作明細來處理揀選工作。

7. 請前往 **產品資訊管理**\>**產品**\>**已發佈的產品**。 選擇您的項目，然後選擇 **管理庫存**\>**檢視**\>**交易**。

    ![作為庫存交易類型的訂單承諾保留。](media/Inventory-transactions-for-order-committed-reservation.png)

8. 檢閱與銷售訂單明細保留相關項目的庫存交易。

    - **參考** 欄位設為 **銷售訂單** 且 **核發** 欄位設為 **預留實物** 的交易，表示高於 **位置** 層級庫存維度的訂單明細保留。 根據項目的庫存預留階層，這些維度是站點、倉庫和庫存狀態。
    - **參考** 欄位設為 **訂單承諾保留** 且 **核發** 欄位設為 **預留實物** 的交易，表示特定批次的訂單明細保留及其上方的所有庫存維度。 根據項目的庫存預留階層，這些維度是批號和位置。 在此範例中，位置是 **Bulk-001**。

9. 在銷售訂單標頭上，選擇 **倉庫**\>**動作**\>**發佈到倉庫**。 訂單明細現在已列入波次，並建立了負載和工作。

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>檢閱和處理具有訂單承諾批號的倉庫工作

1. 在 **銷售訂單明細** FastTab 上，選擇倉庫 **運送**\>**工作詳細資料**。

    處理承諾到銷售訂單明細的批次數量揀貨工作具有以下特徵：

    - 為了建立工作，系統會使用工作範本而非位置指令。 將為工作範本定義的所有標準設定 (如最大揀貨明細數量或特定測量單位) 將套用於判斷何時應建立新工作。 但是，與用於識別揀貨位置的位置指令關聯規則則不會列入考慮，因為訂單承諾保留已指定了所有庫存維度。 這些庫存維度包括倉庫儲存層級的維度。 因此，工作將繼承這些維度，而不必參考位置指令。
    - 批號未顯示在揀貨明細上 (與為具有關聯的 *批次以上\[位置\]* 預留階層的項目建立的工作明細情況一樣。) 而是在工作明細的工作庫存交易中顯示「來自」批號和所有其他儲存維度顯示，而該交易是引用自關聯的庫存交易。

        ![源自訂單承諾保留工作的倉庫庫存交易。](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - 建立工作後，庫存交易 **參考** 欄位設為 **訂單承諾保留** 的項目會被移除。 **引用** 欄位設為 **工作** 的庫存交易現在保存了所有數量的庫存維度上的實體保留。

        倉庫工作可以繼續以通常的方式處理工作的執行。 但是，行動裝置上的說明將指示工作人員選擇特定的批號。 在倉庫環境中，位置是由牌照所控制，在工作人員到達將同一批次儲存在多個牌照上的位置後，他們可以從尚未保留的任何牌照中執行揀貨 (例如，透過另一個訂單承諾保留或源自該類型保留的工作)。

        如果從工作明細上指定的位置揀貨是不切實際的，則倉庫工作員可以使用以下動作之一從更方便的位置重新導向特定批次的揀選：

        - 行動裝置上的標準 **覆寫位置** 動作 (如果已啟用倉庫工作人員的 **允許揀料位置覆寫** 設定)
        - **工作清單詳細資訊** 頁面上的 **變更位置** 動作。 

2. 在行動裝置上，完成揀選與放置工作。

    現在已為銷售訂單明細完成揀選批號 **B11** 的 **10** 個數量，並放入 **裝卸站門** 位置。 此時，它已準備好裝載到卡車上並發送到客戶的地址。

## <a name="flexible-license-plate-reservation"></a>靈活的牌照保留

### <a name="business-scenario"></a>商務案例

在此情況下，公司會使用倉庫管理和工作處理，並在建立工作之前在 Supply Chain Management 外部的個別棧板/容器層級處理裝載計劃。 這些容器由庫存維度中的牌照表示。 因此，對於此方法，在完成揀貨工作之前，必須將特定牌照預先指派至銷售訂單明細。 該公司正在尋求牌照保留規則處理方式的靈活性，以便發生以下行為：

- 銷售處理人員接單時可以記錄和保留牌照，並且不能被其他要求佔用。 此行為有助於將計劃的牌照確實運交給客戶。
- 如果車牌尚未分配到銷售訂單明細，倉庫人員可以在銷售訂單登記和保留完成後，在揀貨工作中選擇牌照。

### <a name="turn-on-flexible-license-plate-reservation"></a>開啟靈活的牌照保留

在使用靈活的牌照保留前，必須先在系統中開啟兩個功能。 管理員可以使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定，來檢查該功能的狀態並在需要時將其打開。 您必須按以下順序打開這些功能：

1. **功能名稱：** *靈活的倉庫級維度保留*
1. **功能名稱：** *靈活的訂單承諾牌照保留*

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a>在銷售訂單上保留特定牌照

如要在訂單上啟用牌照保留，您必須在與相關項目關聯的階層的 **庫存保留階層** 頁面上，為 **牌照** 層級選取 **允許依需求訂單進行預留** 核取方塊。

![靈活的牌照保留階層的庫存預留階層頁面。](media/Flexible-LP-reservation-hierarchy.png)

您可以在部署中的任何時間點對訂單啟用牌照保留。 此變更不會影響變更發生之前建立的任何預留或未結倉庫工作。 但是，如果與該預留階層關聯的一或多個項目存在問題狀態為 *依訂單*、*訂購保留* 或 *預留實物* 的未結出庫庫存交易，則您無法清除 **允許依需求訂單進行預留** 核取方塊。

即使已為 **牌照** 層級選擇了 **允許依需求訂單進行預留** 核取方塊，仍然可以 *不* 在訂單上保留特定的牌照。 在此情況下，將套用對預留階層有效的預設倉庫工作邏輯。

如要保留特定牌照，您必須使用[開放式資料通訊協定 (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md)程序。 在應用程式中，您可以使用 **在 Excel 中開啟** 命令的 **每個牌照的訂單承諾保留** 選項直接從銷售訂單執行此保留。 在 Excel 增益集中打開的實體資料中，您必須輸入以下與保留相關的資料，然後選擇 **發佈** 將資料發送回 Supply Chain Management：

- 參考 (僅支援 *銷售訂單* 值。)
- 訂單編號 (該值可以從批次中得出。)
- 批次識別碼
- 牌照
- 數量

如果您必須為批次追蹤的項目保留特定的牌照，請使用 **批次保留** 頁面，如[輸入銷售訂單詳細資訊](#sales-order-details)部分中所述。

當倉庫工作處理使用訂單承諾牌照保留的銷售訂單明細時，將不會使用位置指令。

如果倉庫工作項目由等於完整棧板的明細組成，且具有已承諾數量的牌照，則可以使用行動裝置功能表項目最佳化揀選過程，其中 **依牌照處理** 選項設為 *是*。 然後，倉庫工作人員可以掃描牌照以完成揀貨，而不必逐一掃描工作中的項目。

![依牌照處理選項的移動設備功能表項目設為「是」。](media/Handle-by-LP-menu-item.png)

因為 **依牌照處理** 功能不支援涵蓋多個棧板的工作，因此最好為不同的牌照設定單獨的工作項目。 如要使用此方法，請將 **訂單承諾牌照識別碼** 欄位新增為 **工作範本** 頁面上的工作標題中斷。

> [!NOTE]
> 對於訂單承諾工作建立流程，「訂單承諾庫存維度」值將指派至揀貨工作明細，並且無法直接檢視牌照值。 設定行動裝置功能表項目時，僅支援 *使用者導向* 程序。

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a>範例案例：設定和處理訂單承諾的牌照保留

此案例顯示如何設定和處理訂單承諾的牌照保留。

### <a name="make-demo-data-available"></a>設定示範資料為可用

此方案是指為 Supply Chain Management 提供的標準示範資料中所包含的值和記錄。 如果要使用此處提供的值來完成案例，請確保在安裝了示範資料的環境中工作。 此外在開始之前，先設定法律實體為 **USMF**。

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a>建立允許保留牌照的庫存預留階層

1. 前往 **倉庫管理\>設定\>庫存\>預留階層**。
1. 選擇 **新增**。
1. 在 **名稱** 欄位中，輸入一個值 (例如，*FlexibleLP*)。
1. 在 **描述** 欄位中，輸入值 (例如，*Flexible LP reservation*)。
1. 在 **已選擇** 清單中，選擇 **批號**、**序號** 和 **擁有者**。
1. 選擇 **移除** 按鈕 ![向後箭號。](media/backward-button.png) 將已選擇的記錄移動到 **可用** 清單。
1. 選擇 **確定**。
1. 在 **牌照** 維度層級的列中，選擇 **允許依需求訂單進行預留** 核取方塊。 **位置** 層級將自動選擇，並且您無法清除其核取方塊。
1. 選擇 **儲存**。

### <a name="create-two-released-products"></a>建立兩個已發佈產品

1. 請前往 **產品資訊管理 \> 產品 \> 已發佈的產品**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **新發佈的產品** 對話方塊中，設定以下值：

    - **產品編號：** *Item1*
    - **品項編號：** *Item1*
    - **項目模型群組：** *FIFO*
    - **品項群組：** *Audio*
    - **儲存維度群組：** *Ware*
    - **追蹤維度群組：** *None*
    - **預留階層：** *FlexibleLP*

1. 選擇 **確定** 以建立產品並關閉對話方塊。
1. 新產品已開啟。 在 **倉庫** FastTab 上，將 **單元序列群組識別碼** 欄位設為 *個*。
1. 重複上述步驟以建立具有相同設定的第二個產品，但將 **產品編號** 和 **品項編號** 欄位設為 *Item2*。
1. 在動作窗格中的 **管理庫存** 索引標籤，從 **檢視** 群組選擇 **現有庫存**。 然後選擇 **數量調整**。
1. 調整下表中指定新項目的現有庫存。

    | 項目  | 倉庫 | 位置 | 牌照 | 數量 |
    |-------|-----------|----------|---------------|----------|
    | Item1 | 24        | FL-010   | LP01          | 10       |
    | Item1 | 24        | FL-011   | LP02          | 10       |
    | Item2 | 24        | FL-010   | LP01          | 5        |
    | Item2 | 24        | FL-011   | LP02          | 5        |

    > [!NOTE]
    > 您必須建立兩個牌照並使用允許混合項目的位置，例如 *FL-010* 和 *FL-011*。

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a>建立銷售訂單並保留特定牌照

1. 前往 **銷售和行銷\>銷售訂單\>所有銷售訂單**。
1. 選擇 **新增**。
1. 在 **建立銷售訂單** 對話方塊中，設定以下值：

    - **客戶帳戶：** *US-001*
    - **倉庫：** *24*

1. 選擇 **確定** 以關閉 **建立銷售訂單** 對話方塊，並開啟新的銷售訂單。
1. 在 **銷售訂單明細** FastTab 上，新增具有以下設定的明細：

    - **品項編號：** *Item1*
    - **數量：** *10*

1. 新增具有以下設定的第二銷售訂單明細：

    - **品項編號：** *Item2*
    - **數量：** *5*

1. 選擇 **儲存**。
1. 在 **明細詳細資訊** FastTab 上的 **設定** 索引標籤上，記下每個明細的 **批次識別碼** 值。 保留特定牌照時需要這些值。

    > [!NOTE]
    > 如要保留特定的牌照，您必須使用 **每個牌照的訂單承諾保留** 資料實體。 如要在特定牌照上保留批次追蹤項目，您也可以使用 **批次保留** 頁面，如[輸入銷售訂單詳細資訊](#sales-order-details)部分中所述。
    >
    > 如果您直接在銷售訂單明細上輸入牌照並將其確認至系統，則 Warehouse Management 處理將不會用於該明細。

1. 選擇 **在 Microsoft Office 中開啟**，選擇 **每個牌照的訂單承諾保留**，並下載檔案。
1. 在 Excel 中打開下載的檔案，然後選擇 **啟用編輯** 以使 Excel 增益集能夠執行。
1. 如果您是第一次執行 Excel 增益集，請選擇 **信任此增益集**。
1. 如果系統提示您登入，請選擇 **登入**，然後使用您用於登入 Supply Chain Management 的相同認證進行登錄。
1. 如要在特定牌照上保留項目，請在 Excel 增益集中，選擇 **新建** 以新增保留明細，然後設定以下值：

    - **批次識別碼：** 輸入您為 *Item1* 的銷售訂單明細找到的 **批次識別碼** 值。
    - **牌照：** *LP02*
    - **ReservedInventoryQuantity：** *10*

1. 選擇 **新增** 以新增另一個保留明細，並設定以下值：

    - **批次識別碼：** 輸入您為 *Item2* 的銷售訂單明細找到的 **批次識別碼** 值。
    - **牌照：** *LP02*
    - **ReservedInventoryQuantity：** *5*

1. 在 Excel 增益集中，選擇 **發佈** 以將資料傳送回 Supply Chain Management。

    > [!NOTE]
    > 僅當發佈完成且沒有錯誤時，保留明細才會顯示在系統中。

1. 返回 Supply Chain Management。 
1. 若要查看項目的預訂，請在 **銷售訂單明細** FastTab 的 **庫存** 功能表上，選擇 **維護 \> 保留**。 請注意，對於 *Item1* 的銷售訂單明細，會保留 *10* 個庫存，對於 *Item2* 的銷售訂單明細，則保留 *5* 個庫存。
1. 若要檢閱與銷售訂單明細保留相關的庫存交易，請在 **銷售訂單明細** FastTab 的 **庫存** 功能表上，選擇 **檢視 \> 交易**。 請注意，有兩個與保留相關的交易：一個是 **參考** 欄位設為 *銷售訂單* 的交易，另一個是 **參考** 欄位設為 *訂單承諾保留* 的交易。

    > [!NOTE]
    > **參考** 欄位設為 *銷售訂單* 的交易，表示高於 **位置** 層級 (站點、倉庫，與庫存狀態) 庫存維度的訂單明細保留。 **引用** 欄位設為 *訂單承諾保留* 的交易，表示特定牌照和位置的訂單明細保留。

1. 如要發佈銷售訂單，請在動作窗格，**倉庫** 索引標籤的 **動作** 群組中，選擇 **發佈到倉庫**。

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a>使用指派的訂單承諾牌照檢閱和處理倉庫工作

1. 在 **銷售訂單明細** FastTab 上的 **倉庫** 功能表上，選擇 **工作詳細資訊**。

    與為特定批次完成保留時一樣，系統在為使用牌照保留的銷售訂單建立工作時不使用位置指令。 由於訂單承諾保留指定了所有庫存維度 (包括位置)，因此不必使用位置指令，因為這些庫存維度只是在工作中輸入的。 它們會顯示在 **工作庫存交易** 頁面上的 **從庫存維度** 區段中。

    > [!NOTE]
    > 工作建立後，庫存交易 **參考** 欄位設為 *訂單承諾保留* 的項目會被移除。 **引用** 欄位設為 *工作* 的庫存交易現在保存了所有數量的庫存維度上的實際保留。

1. 在行動裝置上，使用選擇了 **依牌照處理** 核取方塊的功能表項目完成揀選與放置工作。

    > [!NOTE]
    > **依牌照處理** 功能可幫助您處理整個牌照。 如果您必須處理牌照的一部分，則不能使用此功能。
    >
    > 我們建議您為每個牌照產生單獨的工作。 若要達到此結果，請使用 **工作範本** 頁面上的 **工作標題中斷** 功能。

    牌照 *LP02* 現在為銷售訂單行挑選並放入 *貝多爾* 地點。 此時，它已準備好進行裝載並分派給客戶。

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a>例外狀況處理具有訂單承諾批號的倉庫工作

揀選訂單承諾批號的倉庫工作受與常規工作相同的標準倉庫例外狀況處理和工作之約束。 通常，打開的工作或工作明細可以被取消，可以因為使用者位置已滿而中斷，可以進行揀貨短缺，並且可以由於移動而更新。 同樣，已完成的工作揀選數量也可以被減少，或者工作也可以被反轉。

以下關鍵規則適用於所有這些例外狀況處理動作：為客戶保留的批號永遠無法替換為其他批號，但其儲存維度 (位置和牌照) 可以透過使用者手動更新或系統自動更新來變更。 系統會根據在自動保留特定批次，但未指定儲存維度時套用的儲存維度相同隨機指派來進行自動更新。

### <a name="example-scenario"></a>範例案例

此方案的一個範例是，使用 **減少揀貨數量** 功能取消選取以前完成的工作。 此範例假設您已經完成了[範例案例：批號分配](#Example-batch-allocation)中描述的步驟。 它會從該範例繼續。

1. 前往 **倉庫管理**\>**裝運**\>**使用中裝運**。
2. 選擇與您的銷售訂單裝運相關的負載。
3. 從 **載入訂單明細** FastTab，選擇 **減少揀貨數量**。
4. 在 **減少揀貨數量** 頁面的 **移動到位置** 欄位上，選擇 **FL-001**。
5. 在 **移動到牌照** 欄位中，選擇 **LP33**。
6. 在網格中的 **要取消揀貨的庫存數量** 欄位中，輸入 **10**。
7. 選擇 **確定**。

以下是取消揀貨動作的結果：

- 之前關閉的工作狀態設為 **已取消**。
- 為批號 **B11** 的取消揀貨數量 **10** 建立 **庫存移動** 類型的新工作。 這項工作代表了從 **裝卸站門** 位置到位置 **FL-001** 的牌照 **LP33** 的移動。 該狀態設為 **關閉**。
- 系統重新保留最初訂購的批號，並指派位置和牌照識別碼。 (此過程等同於為給定批號的訂單明細執行 **保留明細** 函式)。 因此，批次 **B11** 在 **批次保留** 頁面的 **批號已承諾給來源明細** FastTab 上顯示為已承諾，並且 **保留** 欄位包含批號 **B11** 的數量為 **10**。 此外，**位置** 欄位設為 **FL-001**，且 **牌照** 欄位設為 **LP11**。 (如果這些欄位不可見，您可以將它們新增到網格中。)

下表提供顯示系統如何處理特定倉庫工作的訂單承諾批次保留的概觀。 若要解釋表中的內容，假定每個倉庫工作是在源自訂單承諾批次保留的現有倉庫工作的內容中執行，或者每個倉庫工作的執行都會影響該類型的工作。

> [!NOTE]
> 在這些表中，「可用批次數量」欄指示除了已為目前訂單承諾保留預留的數量，或已由源自該類型保留的倉庫工作預留的數量外，也指示是否還有可用批次數量。

#### <a name="override-the-pick-location-on-the-open-work"></a>覆寫開放工作上的揀貨位置

<table>
<thead>
<tr>
<th>關鍵設定參數</th>
<th>批次數量可用</th>
<th>關鍵使用者步驟</th>
<th>倉庫工作</th>
<th>訂單承諾批次保留</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>在背景工作角色上啟用<strong>允許揀貨位置覆寫</strong>選項。</td>
<td>是</td>
<td>
<ol>
<li>當您開始揀貨工作時，請選擇 Warehouse Management 行動應用程式上的<strong>覆寫位置</strong>功能表項目。</li>
<li>選擇<strong>建議</strong>。</li>
<li>確認根據批次數量可用性建議的新位置。</li>
</ol>
</td>
<td>在目前工作中，會發生以下動作：
<ul>
<li>揀貨明細上的位置更新為新位置。 (如果位置是由牌照控制的，則將隨機牌照指派至工作庫存交易，並且工作者可從具有可用數量的任何牌照中選取。)</li>
<li>如果該數量是在新位置的多個牌照上找到的，則原始揀貨明細將分割為多個明細以符合每個牌照。</li>
</ul>
</td>
<td>不適用</td>
</tr>
<tr>
<td>否</td>
<td>
<ol>
<li>當您開始揀貨工作時，請選擇 Warehouse Management 行動應用程式上的<strong>覆寫位置</strong>功能表項目。</li>
<li>手動輸入地點。</li>
</ol>
</td>
<td><strong>覆寫位置</strong>動作是不可能的。 它失敗了，並擲回一個錯誤。</td>
<td>不適用</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>Full 按鈕 – 因為使用者位置溢位而分割工作明細

<table>
<thead>
<tr>
<th>關鍵設定參數</th>
<th>批次數量可用</th>
<th>關鍵使用者步驟</th>
<th>倉庫工作</th>
<th>訂單承諾批次保留</th>
</tr>
</thead>
<tbody>
<tr>
<td>行動裝置功能表項目上的<strong>允許工作分割</strong>選項為已啟用。</td>
<td>不適用</td>
<td>
<ol>
<li>當您處理揀貨工作時，請選擇 Warehouse Management 行動應用程式上的 <strong>Full</strong> 功能表項目。</li>
<li>在<strong>揀貨數量</strong>欄位中，輸入所需揀選的部分數量以指示全容量。</li>
</ol>
</td>
<td>
<ul>
<li>在目前工作中，數量會更新為必須揀選的剩餘數量。</li>
<li>揀選數量的新工作已建立並關閉。</li>
</ul></td>
<td>不適用</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>減少已完成工作的揀選數量 (從負載)

<table>
<thead>
<tr>
<th>關鍵設定參數</th>
<th>批次數量可用</th>
<th>關鍵使用者步驟</th>
<th>倉庫工作</th>
<th>訂單承諾批次保留</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>不適用</td>
<td>是</td>
<td>
<ol>
<li>打開負載明細的<strong>減少揀貨數量</strong>頁面。</li>
<li>輸入要取消揀貨的全部數量。</li>
<li>選擇「移動至」位置/牌照。</li>
</ol>
</td>
<td>
<ul> 
<li>與負載明細關聯的工作已被取消。</li>
<li>庫存移動的新工作已建立並關閉。</li>
</ul>
</td>
<td>已為同一批次重新保留數量。 系統會隨機指派一個數量可用的位置和牌照 (如果該位置是牌照控制的)。</td>
</tr>
<tr>
<td>否</td>
<td>參閱上一列。</td>
<td>參閱上一列。</td>
<td>為同一批次以及在取消揀貨期間輸入的相同位置和牌照 (如果該位置受牌照控制) 重新保留數量。</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>在倉庫內移動項目

> [!NOTE]
> 此倉庫動作僅適用於 **工作建立流程** 類型的移動，不適用於範本移動。

<table>
<thead>
<tr>
<th>關鍵設定參數</th>
<th>批次數量可用</th>
<th>關鍵使用者步驟</th>
<th>倉庫工作</th>
<th>訂單承諾批次保留</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>已在工作者上啟用<strong>允許具有關聯工作庫存的移動</strong>選項。</td>
<td>是</td>
<td>
<ol>
<li>在 Warehouse Management 行動應用程式上開始移動。</li>
<li>輸入「從」和「到」位置。</li>
</ol></td>
<td>
<ul>
<li>對於受移動影響的所有現有工作，揀貨位置將更新為新的「到」位置。</li>
<li>庫存移動的新工作已建立並關閉。</li>
</ul>
</td>
<td>受給定位置的數量移動影響的所有現有保留，都將為同一批次重新保留。 系統會隨機指派一個數量可用的位置和牌照 (如果該位置是牌照控制的)。</td>
</tr>
<tr>
<td>否</td>
<td>參閱上一列。</td>
<td>參閱上一列。</td>
<td>受給定位置的數量移動影響的所有現有保留都將重新保留給同一批次，以及新的「到」位置與牌照 (如果位置受牌照控制)。</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>還原已完成工作的揀選數量 (從負載或波次)

<table>
<thead>
<tr>
<th>關鍵設定參數</th>
<th>批次數量可用</th>
<th>關鍵使用者步驟</th>
<th>倉庫工作</th>
<th>訂單承諾批次保留</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>不適用</td>
<td>是</td>
<td>
<ol>
<li>打開<strong>還原工作</strong>頁面。</li>
<li>在請求頁面上，選擇<strong>將項目留在目前位置</strong>選項。</li>
</ol>
</td>
<td>已取消與負載關聯的所有工作。</td>
<td>已為同一批次重新保留數量。 系統會隨機指派一個數量可用的位置和牌照 (如果該位置是牌照控制的)。</td>
</tr>
<tr>
<td>否</td>
<td>參閱上一列。</td>
<td>參閱上一列。</td>
<td>該數量將重新保留給同一批次，以及用於在撤銷時留下數量的位置和牌照。</td>
</tr>
<tr>
<td>是</td>
<td>
<ol>
<li>打開<strong>還原工作</strong>頁面。</li>
<li>在請求頁面上，選擇<strong>將項目指派至此位置</strong>選項。</li>
</ol>
</td>
<td>
<ul>
<li>目前工作已被取消。</li>
<li>庫存移動的新工作已建立並關閉。</li>
</ul>
</td>
<td>已為同一批次重新保留數量。 系統會隨機指派一個數量可用的位置和牌照 (如果該位置是牌照控制的)。</td>
</tr>
<tr>
<td>否</td>
<td>參閱上一列。</td>
<td>參閱上一列。</td>
<td>該數量將重新保留給同一批次，並在撤銷時為數量指派到的位置和牌照重新保留。</td>
</tr>
<tr>
<td>是/否</td>
<td>
<ol>
<li>打開<strong>還原工作</strong>頁面。</li>
<li>在請求頁面上，選擇<strong>將項目移動至此位置</strong>選項。</li>
</ol>
</td>
<td>撤銷不受支援。</td>
<td>不適用</td>
</tr>
<tr>
<td>是/否</td>
<td>
<ol>
<li>打開<strong>還原工作</strong>頁面。</li>
<li>在請求頁面上，選擇<strong>根據位置指令移動項目</strong>選項。</li>
</ol>
</td>
<td>撤銷不受支援。 </td>
<td>不適用</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>揀貨短缺數量 - 在您執行揀貨工作時，將數量登錄為在位置/牌照上實際找不到的數量

<table>
<thead>
<tr>
<th>關鍵設定參數</th>
<th>批次數量可用</th>
<th>關鍵使用者步驟</th>
<th>倉庫工作</th>
<th>訂單承諾批次保留</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>已設定<strong>揀貨短缺</strong>類型的工作例外狀況，其中<strong>項目重新分配</strong> = <strong>無</strong>，<strong>調整庫存</strong> = <strong>是</strong>，而<strong>刪除保留</strong> = <strong>否</strong>。</td>
<td>是</td>
<td>
<ol>
<li>當您執行揀貨工作時，請選擇 Warehouse Management 行動應用程式上的 <strong>Shortpick</strong> 功能表項目。</li>
<li>在<strong>揀貨數量</strong>欄位中，輸入 <strong>0</strong> (零)。</li>
<li>在<strong>原因</strong>欄位中，輸入<strong>無重新分配</strong>。</li>
</ol>
</td>
<td>
<ul>
<li>目前工作已關閉，揀貨數量為 0 (零)。</li>
<li>建立<strong>計數</strong>類型和<strong>已售出</strong>問題類型的庫存交易來表示該調整。</li>
</ul>
</td>
<td>已為同一批次重新保留數量。 系統會隨機指派一個數量可用的位置和牌照 (如果該位置是牌照控制的)。</td>
</tr>
<tr>
<td>否</td>
<td>參閱上一列。</td>
<td>
<ul>
<li>揀貨短缺動作失敗，並擲回錯誤。</li>
<li>目前的工作保持未結狀態。</li>
</ul>
</td>
<td>不適用</td>
</tr>
<tr>
<td rowspan='2'>已設定<strong>揀貨短缺</strong>類型的工作例外狀況，其中<strong>項目重新分配</strong> = <strong>無</strong>，<strong>調整庫存</strong> = <strong>是</strong>，而<strong>刪除保留</strong> = <strong>是</strong>。</td>
<td>是</td>
<td>
<ol>
<li>當您執行揀貨工作時，請選擇 Warehouse Management 行動應用程式上的 <strong>Shortpick</strong> 功能表項目。</li>
<li>在<strong>揀貨數量</strong>欄位中，輸入 <strong>0</strong> (零)。</li>
<li>在<strong>原因</strong>欄位中，輸入<strong>無重新分配</strong>。</li>
</ol>
</td>
<td>
<ul>
<li>目前工作已關閉，揀貨數量為 0 (零)。</li>
<li>建立<strong>計數</strong>類型和<strong>已售出</strong>問題類型的庫存交易來表示該調整。</li>
</ul>
</td>
<td>受揀貨短缺位置中的數量調整影響的所有現有保留都將為同一批次重新保留。 系統會隨機指派一個數量可用的位置和牌照 (如果該位置是牌照控制的)。</td>
</tr>
<tr>
<td>否</td>
<td>參閱上一列。</td>
<td>參閱上一列。</td>
<td>受揀貨短缺位置中的數量調整影響的所有現有保留都將被移除。</td>
</tr>
<tr>
<td>已設定<strong>揀選短缺</strong>類型的工作例外狀況，其中<strong>項目重新分配</strong> = <strong>手動</strong>，<strong>調整庫存</strong> = <strong>是</strong>，而<strong>刪除保留</strong> = <strong>否/是</strong>。 此外，在背景工作角色上啟用<strong>允許手動重新分配項目</strong>選項。</td>
<td>是</td>
<td>
<ol>
<li>當您執行揀貨工作時，請選擇 Warehouse Management 行動應用程式上的 <strong>Shortpick</strong> 功能表項目。</li>
<li>在<strong>揀貨短缺數量</strong>欄位中，輸入 <strong>0</strong> (零)。</li>
<li>在<strong>原因</strong>欄位中，選擇<strong>手動重新分配的揀貨短缺</strong>。</li>
<li>在清單中選擇位置/牌照。</li>
</ol>
</td>
<td>
<ul>
<li>在目前工作中，會發生以下動作：
<ul>
<li>揀貨明細已關閉，揀貨數量為 0 (零)。</li>
<li>放置明細已取消。</li>
<li>已建立一個新的揀貨明細。 它會使用使用者選擇的位置/牌照。</li>
<li>已建立一個新的放置明細。</li>
</ul>
</li>
<li>建立<strong>計數</strong>類型和<strong>已售出</strong>問題類型的庫存交易來表示該調整。</li>
</ul>
</td>
<td>不適用</td>
</tr>
<tr>
<td>已設定<strong>揀貨短缺</strong>類型的工作例外狀況，其中<strong>項目重新分配</strong> = <strong>手動</strong>，<strong>調整庫存</strong> = <strong>是</strong>，而<strong>刪除保留</strong> = <strong>否</strong>。 此外，在背景工作角色上啟用<strong>允許手動重新分配項目</strong>選項。</td>
<td>否</td>
<td>
<ol>
<li>當您執行揀貨工作時，請選擇 Warehouse Management 行動應用程式上的 <strong>Shortpick</strong> 功能表項目。</li>
<li>在<strong>揀貨短缺數量</strong>欄位中，輸入 <strong>0</strong> (零)。</li>
<li>在<strong>原因</strong>欄位中，選擇<strong>手動重新分配的揀貨短缺</strong>。</li>
</ol>
</td>
<td>揀貨短缺動作失敗，並擲回錯誤。</td>
<td>不適用</td>
</tr>
<tr>
<td>已設定<strong>揀貨短缺</strong>類型的工作例外狀況，其中<strong>項目重新分配</strong> = <strong>手動</strong>，<strong>調整庫存</strong> = <strong>是</strong>，而<strong>刪除保留</strong> = <strong>是</strong>。 此外，在背景工作角色上啟用<strong>允許手動重新分配項目</strong>選項。</td>
<td>否</td>
<td>
<ol>
<li>當您執行揀貨工作時，請選擇 Warehouse Management 行動應用程式上的 <strong>Shortpick</strong> 功能表項目。</li>
<li>在<strong>揀貨短缺數量</strong>欄位中，輸入 <strong>0</strong> (零)。</li>
<li>在<strong>原因</strong>欄位中，選擇<strong>手動重新分配的揀貨短缺</strong>。</li>
<li>在清單中選擇位置/牌照。</li>
</ol>
</td>
<td>
<ul>
<li>在目前工作中，會發生以下動作：
<ul>
<li>揀貨明細已關閉，揀貨數量為 0 (零)。</li>
<li>放置明細已取消。</li>
</ul>
</li>
<li>建立<strong>計數</strong>類型和<strong>已售出</strong>問題類型的庫存交易來表示該調整。</li>
</ul>
</td>
<td>受揀貨短缺位置/牌照中的數量調整影響的所有現有保留都將被移除。</td>
</tr>
<tr>
<td>已設定<strong>揀貨短缺</strong>類型的工作例外狀況，其中<strong>項目重新分配</strong> = <strong>自動</strong>，<strong>調整庫存</strong> = <strong>是/否</strong>，而<strong>刪除保留</strong> = <strong>是/否</strong>。</td>
<td>不適用</td>
<td>
<ol>
<li>當您執行揀貨工作時，請選擇 Warehouse Management 行動應用程式上的 <strong>Shortpick</strong> 功能表項目。</li>
<li>在<strong>揀貨短缺數量</strong>欄位中，輸入 <strong>0</strong> (零)。</li>
<li>在<strong>原因</strong>欄位中，選擇<strong>自動重新分配的揀貨短缺</strong>。</li>
</ol>
</td>
<td>不支援涉及自動重新分配的揀貨短缺。</td>
<td>不支援涉及自動重新分配的揀貨短缺。</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>變更庫存狀態

> [!NOTE]
> 此倉庫動作可以從多個入口點執行。 此處顯示的範例使用 **按位置的庫存** 頁面上的 **庫存狀態變更** 動作。

<table>
<thead>
<tr>
<th>關鍵設定參數</th>
<th>批次數量可用</th>
<th>關鍵使用者步驟</th>
<th>倉庫工作</th>
<th>訂單承諾批次保留</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>在<strong>倉庫</strong>索引標籤的<strong>倉庫</strong>記錄中，<strong>移除保留與標記</strong>欄位設為<strong>保留</strong>或<strong>標記與保留</strong>。</td>
<td>是</td>
<td>
<ol>
<li>選擇特定位置。</li>
<li>選擇具有特定項目、位置和牌照的明細 (如果該位置受牌照控制)。</li>
<li>選擇<strong>庫存狀態變更</strong>。</li>
<li>將<strong>庫存狀態</strong>欄位設為<strong>封鎖</strong>。</li>
</ol>
</td>
<td>對於為工作保留的數量，庫存狀態不允許變更。</td>
<td>
<ul>
<li>已為同一批次重新保留數量。 系統會隨機指派一個數量可用的位置和牌照 (如果該位置是牌照控制的)。</li>
<li>已建立兩個<strong>庫存狀態變更</strong>類型的庫存交易來表示庫存狀態維度的變更。</li>
<li>已建立<strong>庫存封鎖</strong>類型的庫存交易和<strong>預留實物</strong>發貨類型以表示鎖定數量的保留。</li>
</ul>
</td>
</tr>
<tr>
<td>否</td>
<td>參閱上一列。</td>
<td>對於為工作保留的數量，庫存狀態不允許變更。</td>
<td>
<ul>
<li>該保留已移除。</li>
<li>已建立兩個<strong>庫存狀態變更</strong>類型的庫存交易來表示庫存狀態維度的變更。</li>
<li>已建立<strong>庫存封鎖</strong>類型的庫存交易和<strong>預留實物</strong>發貨類型以表示鎖定數量的保留。</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'>在<strong>倉庫</strong>索引標籤的<strong>倉庫</strong>記錄中，<strong>移除保留與標記</strong>欄位設為<strong>無</strong>。</td>
<td>是</td>
<td>
<ol>
<li>選擇特定位置。</li>
<li>選擇具有特定項目、位置和牌照的明細 (如果該位置受牌照控制)。</li>
<li>選擇<strong>庫存狀態變更</strong>。</li>
<li>將<strong>庫存狀態</strong>欄位設為<strong>封鎖</strong>。</li>
</ol>
</td>
<td>對於為工作保留的數量，庫存狀態不允許變更。</td>
<td>已為同一批次重新保留數量。 系統會隨機指派一個數量可用的位置和牌照 (如果該位置是牌照控制的)。</td>
</tr>
<tr>
<td>否</td>
<td>參閱上一列。</td>
<td>對於為工作保留的數量，庫存狀態不允許變更。</td>
<td>不允許變更庫存狀態。</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>限制

- 靈活型倉庫級維度保留功能不支援以下功能：

    - 實秤重量管理
    - 實際負數庫存
    - 針對訂購供應的保留
    - 轉移訂單和原物料揀貨

- 按指令單位包裝的容器合併規則具有限制。 對於訂單承諾保留，建議您不要使用已啟用 **按指令單位包裝** 欄位的容器建立範本。 在目前設計中，建立倉庫工作時不使用位置指令。 因此，在容器化波次步驟中僅會套用單元序列群組 (庫存單元) 中的最低單元。

## <a name="see-also"></a>另請參閱

- [Warehouse Management 中的批號](/dynamicsax-2012/appuser-itpro/batch-numbers-in-warehouse-management)
- [為銷售訂單保留相同批次](../sales-marketing/reserve-same-batch-sales-order.md)
- [在行動裝置上挑選最舊的批次](pick-oldest-batch.md)
- [批次和牌照確認](batch-and-license-plate-confirmation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]