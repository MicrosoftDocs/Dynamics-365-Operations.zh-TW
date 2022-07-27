---
title: 計劃直接轉運
description: 本主題介紹進階計劃直接轉運，其中訂單所需的庫存數量直接從收貨或製造處直接運到正確的出庫裝卸站或暫存區。 來自入庫來源的所有剩餘庫存會透過常規入庫流程運到正確的儲存位置。
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: c28639a4a575f5f356bf947ba8e0aee6bcd256b4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448581"
---
# <a name="planned-cross-docking"></a>計劃直接轉運

[!include [banner](../includes/banner.md)]

本主題介紹進階計劃直接轉運。 直接轉運是一種倉庫流程，其中訂單所需的庫存數量直接從收貨或建立處直接運到正確的出庫裝卸站或暫存區。 來自入庫來源的所有剩餘庫存會透過常規入庫流程運到正確的儲存位置。

直接轉運讓員工跳過對已經為出庫訂單標記的庫存進行入庫和出庫揀選。 因此，盡可能減少接觸庫存的次數。 此外，由於與系統的交互較少，因此更能節省倉庫車間的時間與空間。

您必須先設定一個新的直接轉運範本，其中指定供應來源及其他的直接轉運需求集，才能夠執行直接轉運。 建立出庫訂單時，必須針對包含相同品項的入庫訂單標記該行項 您可以在直接轉運範本上選取指令代碼欄位，方法類似於設定補貨訂單和採購訂單。

在收到入庫訂單時，直接轉運設定會自動識別自動轉運需求，並會根據位置指令設定為所需數量建立的移動工作。

> [!NOTE]
> 當直接轉運工作取消時，*不會* 將直接轉運交易取消註冊，即使已在倉庫管理參數中開啟此功能的設定也不會取消註冊。

## <a name="turn-on-the-planned-cross-docking-features"></a>開啟計劃直接轉運功能

如果您的系統尚未包含本主題中說明的功能，請移至[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)，並依下列順序開啟以下功能：

1. *計劃直接轉運*
1. *具有位置指令的直接轉運範本*
    > [!NOTE]
    > 此功能使 **指令代碼** 欄位能夠在直接轉運範本上指定，方法類似設定補貨範本。 啟用此功能可防止您在最終 *放置* 行項的直接轉運工作範本行項上新增指令代碼。 這可確保在考慮工作範本之前，會在工作建立期間決定最終放置位置。

## <a name="setup"></a>設定

### <a name="regenerate-load-posting-methods"></a>重新產生負載過帳方法

計劃直接轉運是作為裝載過帳方法實作的。 開啟該功能後，您必須重新產生方法。

1. 移至 **倉庫管理 \> 設定 \> 裝載過帳方法**。
1. 在動作窗格上，選取 **重新產生方法**。

    重新產生完成後，您應該會看到一個方法，其 **方法名稱** 值為 *planCrossDocking*。

1. 關閉頁面。

### <a name="create-a-cross-docking-template"></a>建立直接轉運範本

1. 移至 **倉庫管理 \> 設定 \> 工作 \> 直接轉運範本**。
1. 在動作窗格上，選擇 **新增** 建立範本。
1. 在標題中，設定以下值：

    - **序號：** *1*

        此欄位定義評估範本的順序。

    - **直接轉運範本識別碼：** *51*
    - **描述：** *51 號倉庫*
    - **需求發佈原則：** *供應收取前*
    - **倉庫：** *51*

1. **規劃** FastTab 上的設定會控制範本的運作方式。 設定以下值：

    - **要求：** *無*

        此欄位會定義需求庫存的需求。 如果在發佈之前，必須將需求與供應連結，請選取 *標記*。 如果在發佈之前必須針對供應情況保留需求訂單，請選取 *保留訂單*。

    - **位置類型：** *運送位置*

        此欄位定義直接轉運工作是否應使用運送中的暫存/裝載位置，或者是否應使用位置指令來尋找自己的暫存/裝載位置。

    - **工作範本：** 將此欄位保留空白。

        此欄位定義建立直接轉運工作時應使用的工作範本。

    - **供應收取時重新驗證：** *否*

        此選項定義在收貨期間是否應重新驗證供應。 如果此選項設定為 *是*，則應檢查最大時間範圍和到期天數範圍。

    - **指令代碼：** 將此欄位保留空白

        此選項由 *具有位置指令的直接轉運範本* 功能啟用。 此系統使用位置指令來幫助確定要將直接轉運移至的最佳位置。 您可以透過為每個相關的直接轉運範本指派指令代碼來設定它。 如果設定指令代碼，系統將在產生工作時按指令代碼搜尋位置指令。 如此一來，您可以限制用於特定直接轉運範本的位置指令。

    - **驗證時間範圍：** *是*

        此選項定義在選取供應來源時，是否應評估時間範圍上限。 如果此選項設定為 *是*，則與時間範圍上限和下限相關的欄位會變為可用。

    - **時間範圍上限：** *5*

        此欄位定義供應到達和需求離開之間允許的最長時段。

    - **時間範圍上限單位：** *天*
    - **時間範圍下限：** *0*

        此欄位定義供應到達和需求離開之間允許的最短時段。

    - **時間範圍下限單位：** *天*
    - **到期天數範圍：** *0*

        *先到期先出 (FEFO) 條件：* 此欄位定義目前在倉庫中第一個到期批次的到期日期與正在接收批次的到期日之間的天數上限。

1. 在 **供應來源** FastTab 上，您指定對此範本有效的供應類型。 選取 **新增**，然後設定以下值：

    - **序號：** *1*
    - **供應來源：** *採購訂單*

> [!NOTE]
> 您可以設定查詢來控制何時使用特定的直接轉運範本。 直接轉運範本的查詢只有 *InventTable* (品項) 資料表和內部聯結的 *WHSInventTable* (WHS 品項) 資料表。 如果要將其他資料表新增至查詢，您只可以使用 *存在聯結* 或 *不存在聯結* 將它們聯結在一起。 當您對已聯結資料表進行篩選時，會為已聯結資料表中每個符合的記錄擷取主要資料表中的記錄。 如果聯結類型是 *存在聯結*，則搜尋會在找到第一個符合的項目後結束。 例如，如果您將銷售訂單行項資料表聯結至品項資料表，則系統會驗證並傳回至少一個銷售訂單行項具有已定義條件的品項。 基本上，會從父系 (品項) 資料表擷取資料，而不是從子系 (銷售訂單行項) 資料表擷取。 因此，按來源文件 (例如銷售訂單行項或客戶) 進行篩選的功能無法開箱即用。

### <a name="create-a-work-class"></a>建立工作類別

1. 前往 **倉庫管理 \> 設定 \> 工作 \> 工作類別**。
1. 在動作窗格上，選取 **新增** 建立工作類別。
1. 設定以下值：

    - **工作類別識別碼：** *CrossDock*
    - **描述：** *直接轉運*
    - **工單類型：** *直接轉運*

### <a name="create-a-work-template"></a>建立工作範本

1. 前往 **倉庫管理 \> 設定 \> 工作 \> 工作範本**。
1. 將 **工單類型** 欄位設定為 *直接轉運*。
1. 在動作窗格上，選取 **新增** 將一行新增到 **概觀** 索引標籤。
1. 在新的明細上，設定以下值：

    - **序號：** *1*
    - **工作範本：** *51 直接轉運*
    - **工作範本描述：** *51 直接轉運*

1. 選取 **儲存**，讓 **工作範本詳細資料** FastTab 可供使用。
1. 在 **工作範本詳細資料** FastTab 上，選取 **新增** 在格線中新增一行。
1. 在新的明細上，設定以下值：

    - **工作類型：** *揀貨*
    - **工作類別識別碼：** *CrossDock*

1. 選取 **新增** 以新增另一行，並在該行設定以下值：

    - **工作類型：** *放置*
    - **工作類別識別碼：** *CrossDock*

1. 選取 **儲存**，並確認已選取 *51 直接轉運* 範本的 **有效** 核取方塊。
1. 選擇性：如果您想設定條件來控制使用工作範本的時間與位置，請選取 **編輯查詢**。

    您可以設定查詢來控制何時使用特定的工作範本。 例如，您可以指定範本只能用於特定位置的工作。 如果您希望在特定位置套用直接轉運工作範本，則必須對 **開始位置** 欄位篩選，而不是對 **位置** 欄位，因為入庫流程 (採購、直接轉運和補貨) 的工作是從放置行開始建立的。 建立工作時，位置指令會將 **位置** 欄位設定為放置位置。 但是，揀貨位置儲存在 **開始位置** 欄位中。

> [!NOTE]
> *揀貨* 與 *放置* 工作類型的工作類別識別碼必須相同。

### <a name="create-location-directives"></a>建立位置指令

1. 前往 **倉庫管理 \> 設定 \> 位置指令**。
1. 在左側窗格中，將 **工單類型** 欄位設定為 *直接轉運*。
1. 在動作窗格上選取 **新增**，然後設定以下值：

    - **序號：** *1*
    - **名稱：** *51 直接轉運放置*
    - **工作類型：** *放置*
    - **站點：** *5*
    - **倉庫：** *51*

1. 選擇 **儲存**，使 **行項** FastTab 可用。
1. 在 **行項** FastTab 上選擇 **新增**，以在格線中新增一行。
1. 在新的明細上，設定以下值：

    - **起始數量：** *1*
    - **終止數量：** *1,000,000*

1. 選擇 **儲存**，使 **位置指令動作** FastTab 可用。
1. 在 **位置指令動作** FastTab 上選擇 **新增**，以在格線中新增一行。
1. 在新的明細上，設定以下值：

    - **名稱：** *Baydoor*
    - **固定位置使用：** *固定和非固定位置*

1. 選擇 **儲存**，使 **位置指令動作** 工具列的 **編輯查詢** 按鈕可用。
1. 選擇 **編輯查詢** 開啟查詢編輯器。
1. 在 **範圍** 索引標籤上，確定設定以下兩行：

    - 明細 1：

        - **資料表：** *位置*
        - **衍生資料表：** *位置*
        - **欄位：** *倉庫*
        - **標準：** *51*

    - 明細 2：

        - **資料表：** *位置*
        - **衍生資料表：** *位置*
        - **欄位：** *位置*
        - **條件：** *Baydoor*

1. 選擇 **確定** 關閉查詢編輯器。

### <a name="create-a-mobile-device-menu-item"></a>建立行動裝置功能表項目

1. 移至 **Warehouse Management\>設定\>行動裝置\>行動裝置功能表項目**。
1. 在左側窗格的功能表項目清單中，選擇 **採購入庫**。
1. 請選取 **編輯**。
1. 在 **工作類別** FastTab 上選擇 **新增**，以在格線中新增一行。
1. 在新的明細上，設定以下值：

    - **工作類別識別碼：** *CrossDock*
    - **工單類型：** *直接轉運*

1. 選取 **儲存**。

## <a name="scenario"></a>案例

### <a name="create-a-purchase-order"></a>建立採購訂單

按照以下步驟建立採購訂單作為供應來源。

1. 前往 **採購和資源開發 \> 訂購單 \> 所有訂購單**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **建立採購訂單** 對話方塊中，設定以下值：

    - **廠商帳戶：** *104*
    - **倉庫：** *51*

1. 選擇 **確定**，並記下訂單編號。
1. 一個新行隨即新增至 **採購訂單行** FastTab。 在此行中設定以下值：

    - **品項編號：** *A0001*
    - **數量：** *5*

### <a name="create-a-sales-order"></a>建立銷售訂單

按照以下步驟建立銷售訂單作為需求來源。

1. 前往 **銷售和行銷\>銷售訂單\>所有銷售訂單**。
1. 在動作窗格上，選擇 **新增**。
1. 在 **建立銷售訂單** 對話方塊中，設定以下值：

    - **使用者帳戶：** *US-002*
    - **倉庫：** *51*

1. 選取 **確定**。
1. 一個新行隨即新增至 **銷售訂單行** FastTab。 在此行中設定以下值：

    - **品項編號：** *A0001*
    - **數量：** *3*

### <a name="create-planned-cross-docking"></a>建立計劃直接轉運

按照以下步驟從銷售訂單建立計劃直接轉運。

1. 在您剛剛建立的銷售訂單的 **銷售訂單詳細資料** 頁面上，在動作窗格上 **倉庫** 索引標籤的 **動作** 群組中，選擇 **發佈到倉庫**。

    發佈到倉庫的動作會為銷售訂單行建立運送和裝載行，並嘗試配置庫存。
    
    您會收到一則提供資訊的訊息。 您也會收到以下警告訊息：「沒有為 wave XXXX 建立任何工作。 相關詳細資料請參閱工作建立歷程記錄。」 這是預期的行為，因為倉庫中沒有庫存。

1. 在 **銷售訂單行** FastTab 的 **倉庫** 功能表上，選擇 **運送詳細資料**。

    **運送詳細資料** 頁面會出現並顯示為銷售訂單建立的運送。

1. 請注意在 **裝載行** FastTab 上 **計劃直接轉運數量** 欄位設定為 *3*。 因為倉庫中沒有可用庫存，但有效的供應來源將在直接轉運範本中定義的時間範圍到達，所以建立了直接轉運數量。
1. 在 **裝載行** FastTab 上選擇 **計劃直接轉運**，以檢視已建立直接轉運的詳細資料。

## <a name="process-the-cross-docking"></a>處理直接轉運

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a>在倉庫行動應用程式上接收的採購訂單

系統會將採購訂單中 5 個單位的數量接收到收貨地點，並建立兩個工作。

建立的第一個工作識別碼其 **工單類型** 的值為 *直接轉運*，並連結到銷售訂單。 它的數量為 3，並會導向到最終運送位置，以便可以立即出貨。

建立的第二個工作識別碼其 **工單類型** 的值為 *採購訂單*，並連結到採購訂單。 它剩下 2 個單位的數量未直接轉運並運到存放處入庫。

1. 以倉庫 *51* 使用者身分登入行動裝置。
1. 移至 **入庫 \> 購買接收**。
1. 在 **PONum** 欄位中，輸入您的採購訂單編號。
1. 在 **Qty** 欄位中，輸入 *5*。
1. 選取 **確定**。
1. 在下一頁將 **品項** 欄位設定為 *A0001*。
1. 選取 **確定**。
1. 在下一頁選擇 **確定**，以確認 **PONum**、**品項** 及 **數量** 值。

    您會收到「工作已完成」訊息。

1. 選擇 **取消** 以退出。

### <a name="put-away-to-cross-docking-and-bulk"></a>入庫到直接轉運和散裝

目前，兩個工作識別碼具有相同的目標牌照。 若要完成後續步驟，您必須獲取工作識別碼和目標牌照識別碼。 您可以從採購訂單行和銷售訂單行的工作詳細資料中獲取此資訊。 或者，您可以移至 **倉庫管理 \> 工作 \> 工作詳細資料**，並篩選 **倉庫** 值為 *51* 的工作。

1. 在行動裝置上，移到 **入庫 \> 採購入庫**，並輸入工作中的目標牌照。
1. 在 **識別碼** 欄位中，輸入工作詳細資料中的目標牌照識別碼。

    直接轉運揀貨頁面會顯示揀貨位置 (*RECV*)、目標牌照 (*牌照*)、品項 (*A0001*) 及數量 (*3*)。

1. 選取 **確定**。
1. 在 **目標 LP** 欄位中，輸入應放置 (直接轉運) 到運送位置的牌照識別碼其目標牌照。 您可以選擇您選擇的任何牌照識別碼。
1. 選取 **確定**。
1. 在下一頁的 **識別碼** 欄位中，輸入目標牌照識別碼。
1. 選取 **確定**。
1. 確認揀選剩餘 2 個單位數量的工作，然後選擇 **確定**。
1. 在下一頁選擇 **完成** 結束揀貨流程，並開始入庫流程。

    行動應用程式會向您顯示品項放置的位置和牌照。

1. 選擇 **確定** 確認散裝儲存區 **放置**。
1. 在下一頁選擇 **確定** 以確認直接轉運 **放置**。

    您會收到「工作已完成」訊息。

1. 選擇 **取消** 以退出。

下圖顯示已完成的直接轉運工作在 Microsoft Dynamics 365 Supply Chain Management 中的顯示方式。

![直接轉運工作已完成。](media/PlannedCrossDockingWork.png "直接轉運工作已完成")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]