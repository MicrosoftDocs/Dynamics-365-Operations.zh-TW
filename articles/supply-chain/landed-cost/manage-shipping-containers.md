---
title: 管理裝運貨櫃
description: 本主題介紹如何使用裝運貨櫃。 裝運貨櫃是用於將實際分組在一起的貨物組合在一起。 它們也用於必須僅在這些貨物之間分攤成本的情況下，通常是因為它們在實體上是在一起的。
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: d3a47aa2ae36cd36a7e92aa2503252021e03f739
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448653"
---
# <a name="manage-shipping-containers"></a>管理裝運貨櫃

[!include [banner](../../includes/banner.md)]

裝運貨櫃是用於將實際分組在一起的貨物組合在一起。 它們也用於必須僅在這些貨物之間分攤成本的情況下，通常是因為它們在實體上是在一起的。

若要透過裝運貨櫃頁面檢視並處理貨物，請前往 **到岸成本 \> 裝運貨櫃 \> 所有運輸貨櫃**。 **所有運輸貨櫃** 頁面會顯示所有可用的裝運貨櫃清單。 您可以使用動作窗格上的按鈕來建立、刪除及使用裝運貨櫃。 選擇清單中的任何裝運貨櫃，以在 **裝運貨櫃** 頁面查看其詳細資訊。

裝運貨櫃詳情頁面的上部顯示了裝運貨櫃和成本核算資訊。 **明細** 部分顯示附加到貨櫃的帳頁、品項和訂購單或轉移單。

## <a name="action-pane"></a>動作窗格

**所有運輸貨櫃** 的動作窗格與 **裝運貨櫃** 頁面提供的按鈕，可讓您使用所選的裝運貨櫃。 每個按鈕執行一個動作。 動作窗格也包括索引標籤，每個索引標籤又提供了一組相關按鈕。 除非另有說明，以下小節中描述的所有按鈕和索引標籤都可在清單檢視 (即，在 **所有運輸貨櫃** 頁面) 和詳細檢視 (即在 **裝運貨櫃** 頁) 中使用。

### <a name="buttons-on-the-manage-tab"></a>管理索引標籤上的按鈕

下表說明動作窗格 **管理** 索引標籤上的可用按鈕。

| 按鈕 | 描述 |
|---|---|
| 過帳收貨清單 | 過帳收貨清單，或檢視裝運貨櫃中所有訂購單明細的產品收貨清單。 若為多公司裝運，每家公司都會開啟新的收據清單過帳對話方塊。 |
| 過帳產品收貨 | 裝運貨櫃內所有訂購單明細的過帳產品收據。 |
| 過帳發票 | 裝運貨櫃內所有訂購單明細的過帳發票。 若為多公司裝運，每家公司都會開啟新的發票過帳對話方塊。 |
| 船舶轉運單 | 過帳裝運貨櫃內所有轉移訂單明細的轉移訂單裝運。 只有裝運貨櫃中屬於轉移訂單類型的那些明細才會出現在對話方塊中。 |
| 接收轉移訂單 | 過帳裝運貨櫃內所有轉移訂單明細的轉移訂單收據。 接收對話方塊是在裝運貨櫃或航程中接收貨物最簡單的方法，也是三個可用選項之一。 您也可以透過到貨日記帳或行動裝置處理接收。 |
| 建立到貨日記帳 | 您可以使用進階倉庫功能為組織產生到貨日記帳。 選項為 _初始化數量_ (推薦) 以及 _從在運品建立_，或 _從訂購單建立_。 最後兩個選項取決於在運品處理是否正在被使用。 |
| 重新命名 | 打開一個對話方塊，您可以在其中重新命名選定的裝運貨櫃。 |
| 變更旅程圖範本 | 變更旅程圖範本。 在您變更旅程範本後，您可能必須選擇 **查找自動成本** 或再次手動新增成本，因為裝運成本將被刪除。 |
| 轉換為租賃 | 將選定的裝運貨櫃轉換為租賃裝運貨櫃。 |

### <a name="buttons-on-the-general-tab"></a>一般索引標籤上的按鈕

下表說明動作窗格 **一般** 索引標籤上的可用按鈕。

| 按鈕 | 描述 |
|---|---|
| 收貨清單 | 過帳裝運貨櫃內所有訂購單明細的收貨清單。 若為多公司航程，每家公司都會開啟新的收據清單過帳對話方塊。 |
| 產品收據 | 檢視產品收據記錄 (如果已使用)。 僅當貨物不使用在運品功能時，才會使用產品收貨流程。 |
| 品項到貨 | 檢視裝運貨櫃的品項到貨日記帳 (如果已使用該日記帳)。 |
| 分段 | 分段是用於識別不同部分的旅程。 前置時間可以與每個分段相關聯，以幫助追蹤運送。 如需詳細資訊，請參閱[多分段旅程設定](multi-leg-journey-setup.md)。 |
| 追蹤 | 檢視或更新運送追蹤。 |
| 在運品訂單 | 你可以從貨櫃直接打開 **在運品** 頁面。 該頁面僅顯示已選取裝運貨櫃的在運品記錄。 |

## <a name="header-view"></a>標題檢視

若要開啟 **標題** 檢視，請開啟裝運貨櫃，然後選取裝運貨櫃標題右上角的 **標題** 索引標籤。

### <a name="settings-on-the-general-fasttab"></a>一般 FastTab 上的設定

下表說明裝運貨櫃 **標題** 檢視的 **一般** FastTab 上可用的設定。

| 欄位 | 描述 |
|---|---|
| 裝運貨櫃 | 裝運貨櫃的名稱。 |
| 航程 | 與裝運貨櫃相關的航程。 |
| 裝運貨櫃類型 | 輸入裝運貨櫃類型。 此欄位必須設定。 您可以使用它來確定運費成本，例如，透過選擇與裝運貨櫃類型關聯的自動成本。 |
| 船舶 | 輸入或選擇船隻。 如果船隻未以值的方式列出，您可以以任意文字形式輸入船隻識別碼。 在此情況下，主資料表不會更新，以便稍後可以在此欄位中選擇船隻識別碼。 如需詳細資訊，請參閱[船隻](shipping-information-setup.md#vessels)。 |
| 單位類型 | 單元類型是用為分組並識別裝運貨櫃的其他方式。 它們會在裝運貨櫃頁面上顯示並進行選擇。 如需更多資訊，請參閱[設定單位類型](shipping-container-setup.md#unit-types)。 |
| 冷凍類型 | 冷凍類型是用為分組並識別裝運貨櫃的其他方式，通常用於冷凍貨櫃。 它們會在裝運貨櫃頁面上顯示並進行選擇。 如需更多資訊，請參閱[設定冷凍類型](shipping-container-setup.md#refrigeration-types)。 |
| 測量 | 該欄位允許在 **到岸成本** 模組指定測量。 不知道貨物個別體積或重量的組織通常會使用測量，但這需要比金額或數量更精準的分攤作業。 貨運業者將提供重量 (以公斤為單位) 或立方測量，您可以將其放在品項或訂購單的等級。 如果參數已選擇，它便可以自動更新，或者也可以手動輸入。 |
| 測量單位 | 適用於 **測量** 欄位中數字的測量單位。 |
| 實際重量 | 您可以記錄貨箱或貨櫃的實際重量。 此值可用於驗證裝運貨櫃設定中允許的最大重量。 |
| 紙箱數 | 如果該參數已選擇，紙箱數量會自動更新。 |
| 貨物描述 | 可以在裝運貨櫃或帳頁標題上選擇貨物描述。 它可用於幫助識別航程、裝運貨櫃或貨物帳頁。 如需詳細資訊，請參閱[貨物描述](shipping-information-setup.md#description-of-goods)。 |
| 航空分運單/提單 | 您可以指定裝運貨櫃的航空分運單或提單。 |
| 備註 | 與裝運貨櫃相關的其他資訊。 |
| 可退貨 | 指示裝運貨櫃是否可以在航程後退貨的一個值。 |
| 航程狀態 | 與裝運貨櫃關聯的旅程狀態。 |
| 訂購單狀態 | 與裝運貨櫃關聯的訂購單狀態。 |

### <a name="settings-on-the-delivery-fasttab"></a>交貨 FastTab 上的設定

下表說明裝運貨櫃 **標題** 檢視的 **交貨** FastTab 上可用的設定。

| 欄位 | 描述 |
|---|---|
| 建立日期和時間 | 貨櫃建立時的日期與時間。 |
| 工廠交貨日期 | 此日期通常提供給工廠/廠商，以指出您預計貨物何時離開其場所。 當您在亞洲工廠作業時，通常會需要此日期，但不需您期望貨物的截止日期。 (對比之下，對於本地交貨，期望貨物的截止日期是必要的。) 此欄位可以從裝運貨櫃清單的訂購單明細中填寫。 您也可以在此手動輸入。 |
| 出貨日期 | 此日期可以列印在訂購單文件上。 它通常會通知工廠/廠商貨物應交付到港口的日期。 此欄位僅供參考。 它不會用於估計裝運貨櫃中貨物的預計交貨日期。 該欄位可以設為在追蹤控制頁面更新時自動更新。 |
| 入庫日期 | 與航程相關的訂購單中的貨物可以出售的最早日期。|
| 預估交貨日期 | 通常，該日期是貨物抵達倉庫的日期。 此欄位僅供參考。 它不會用於計算裝運貨櫃中訂購單明細的主計劃。 訂購單明細上的預期交貨日期會透過追蹤控制進行更新。 該欄位可以設為在追蹤控制頁面更新時進行更新。 |
| 出發日期 | 一般來說，這是飛機或船隻實際離開海外機場或港口的日期。 |
| 運輸港口的 ETA | 目的地港口的預計到貨日期 (「到」港)。 |
| 收到原始文件 | 選擇性：更新收到原始文件的日期。 |
| 經紀商告知 | 選擇性：更新告知經紀商的日期。 |
| 寄出的原始提單 | 選擇性：更新原始提單發送的日期。 |
| 貨物放行 | 選擇性：更新貨物放行的日期。 |
| 客戶預約 | 選擇性：更新客戶預約日期。 |
| 倉庫交貨 | 選擇性：更新貨物交貨至倉庫的日期。 |
| 驗證日期 | 選擇性：更新驗證日期。 |
| 交貨說明 | 選擇性：更新交貨說明的日期。 |
| 起點港口 | 品項啟運的港口。 |
| 終點港口 | 品項運抵的港口。 |
| 本地業者 | 此欄位僅供參考。 本地業者應該可以從廠商資料表中選擇。 |
| 本地運輸日期 | 輸入預訂的本地運輸日期。 此欄位可以幫助倉庫執行其計劃。 |
| 本地運輸時間 | 輸入時段。 此欄位可以幫助倉庫執行其計劃。 |
| 旅程圖範本 | 為航程指定的旅程範本。 旅程範本提供了「目的」和「出發」港口的詳細資料，以及與裝運貨櫃的追蹤控制相關的前置時間。 |

### <a name="settings-on-the-other-fasttab"></a>其他 FastTab 上的設定

下表說明裝運貨櫃 **標題** 檢視的 **其他** FastTab 上可用的設定。

| 欄位 | 描述 |
|---|---|
| 租賃 | 指示裝運貨櫃是否為租賃裝運貨櫃的值。 租賃成本可能與租賃貨櫃有關。 |
| 轉換為租賃 | 指示裝運貨櫃是否轉換為租賃裝運貨櫃的值。 租賃成本可能與租賃貨櫃有關。 |
| 原始航程 | 如果裝運貨櫃被移至新航程，原始航程。 |
| 已使用 | 使用它來記錄是否使用了租賃的裝運貨櫃。 此資訊僅供參考。 |
| 預期裝載日期 | 裝運貨櫃預計裝載貨物的日期。 |
| 我們的序號 | 輸入貴公司內部用於裝運貨櫃的序號。 |
| 裝運公司序號 | 輸入運輸公司或代理人為裝運貨櫃提供的序號。 |
| 檢驗證書申請日期 | 要求對裝運貨櫃進行檢查的日期。 |
| 檢驗證書收到日期 | 收到檢驗證書的日期。 |
| 檢驗證書到期日期 | 檢驗證書將到期的日期。 |
| 檢驗證書編號 | 完成檢驗後發給證書的證書編號。 |

## <a name="lines-view"></a>明細檢視

若要開啟 **明細** 檢視，請開啟裝運貨櫃，然後選取裝運貨櫃標題右上角的 **明細** 索引標籤。

### <a name="information-on-the-shipping-container-fasttab"></a>裝運貨櫃 FastTab 上的資訊

在 **明細** 檢視中的 **裝運貨櫃** FastTab 會顯示有關帳頁的資訊。 大部分的此資訊也出現在 **標題** 檢視中，如本主題前面所述。

### <a name="information-and-buttons-on-the-lines-fasttab"></a>明細 FastTab 上的資訊和按鈕

**明細** 檢視中的 **明細** FastTab 會顯示目前裝運貨櫃中包含的每個完整或部分訂購單明細的詳細資訊。

下表說明 **明細** 檢視的 **明細** FastTab 中的可用按鈕。

| 按鈕 | 描述 |
|---|---|
| 移除 | 從航程中移除所選的訂購單明細。 |
| 庫存 \> 交易 | 檢視所選訂購單明細的庫存交易。 請注意，如果您正在使用在運品，還會顯示原始訂單和在運品訂單。 |
| 庫存 \> 顯示維度 | 打開一個對話方塊，為正在檢視的交易選取要顯示的庫存維度。 |
| 重新整理 | 更新與所選訂購單明細的明細數量、重量或體積相關的資訊。 |

### <a name="information-on-the-lines-details-fasttab"></a>明細詳細資料 FastTab 上的資訊

**明細** 檢視中的 **明細詳細資料** FastTab 會顯示有關目前在 **明細** FastTab 上選擇的訂購單明細的詳細資料。