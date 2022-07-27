---
title: 具有優先順序的規劃
description: 本主題介紹 Microsoft Dynamics 365 Supply Chain Management的具有優先順序的規劃功能。
author: ChristianRytt
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 41c4f3e9bd41735b213743bd8b4cdd8d9657a073
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2021
ms.locfileid: "8449421"
---
# <a name="priority-based-planning"></a>具有優先順序的規劃

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

本主題介紹 Microsoft Dynamics 365 Supply Chain Management的具有優先順序的規劃功能。 該功能增加了對需求導向規劃的支援，這是需求導向的材料需求規劃 (DDMRP) 的一個步驟。 具有優先順序的規劃使規劃最佳化能夠產生以規劃優先順序而非需求日期導向的計劃訂單。

具有優先順序的規劃使您可以優先處理補貨訂單，以確保緊急需求優先於不太重要的需求。 例如，缺貨補貨訂單將優先於標準補充補貨訂單。 系統可以自動將較大的訂單拆分為單獨的較小訂單，其中訂單行按優先順序分組。 然後它可以先處理所有高優先順序的訂單。

要快速了解此功能，請觀看以下影片：[Dynamics 365 Supply Chain Management中的具有優先順序的規劃的規劃最佳化支援](https://youtu.be/GmMHzFETTQc)。

## <a name="turn-on-priority-based-planning-in-your-system"></a>在您的系統中開啟具有優先順序的規劃

使用此功能之前，您必須先在系統中開啟。 管理員可利用[功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：** *總規劃*
- **功能名稱：** *規劃最佳化的優先順序導向的MRP 支援*

## <a name="where-and-how-planning-priorities-are-assigned"></a>在何處以及如何分配規劃優先順序

有關供需的 *規劃優先順序* 資訊是具有優先順序的規劃的骨幹。 規劃優先順序定義了需求或供應行的重要性。 規劃最佳化會在 **涵蓋範圍代碼** 欄位設為 *優先順序* 時使用它。

規劃優先順序通常是一個介於 0（零）和 100 之間的數字，其中 0 表示最高重要性。 它顯示並設定在 **規劃優先順序** 欄位。 您可以在以下頁面上找到該欄位：**需求預測行**，**銷售訂單詳細資料**，**採購單詳細資料**，**轉移訂單詳細資料**，和 **計劃訂單詳細資料**。

當相關品項或涵蓋範圍群組的 **涵蓋範圍代碼** 欄位設為 *優先順序* 時，規劃最佳化透過使用需求導向的方法來平衡供需，因為它計算規劃優先順序，並且對每項發佈的產品考慮為 **品項涵蓋範圍** 頁面上的 **最小**，**再訂購點**，和 **最大** 欄位所設定的值。

> [!NOTE]
> 僅當啟用規劃最佳化時，該 *優先順序* 值才可用於 **涵蓋範圍代碼** 欄位。

相關的 *規劃優先順序模型* 控制規劃優先順序並按優先順序範圍拆分計劃訂單。 它們還讓您為每種供應或需求類型設定預設規劃優先順序值並定義優先順序計算方法。

## <a name="types-of-priority-calculation-methods"></a>優先順序計算方法的類型

每個規劃優先順序模型都有一個 **優先順序計算方法** 設定，該設定控制總規劃如何將優先順序應用於計劃訂單。 可用的值為 *最大庫存數量的百分比* 和 *優先順序範圍*。 *優先順序範圍* 代表著 *最大庫存數量的百分比* 方法更進階的版本。

### <a name="percent-of-maximum-inventory-quantity"></a>最大庫存數量的百分比

在 *最大庫存數量的百分比* 計算方法中，供應優先順序計算找到當前的 *總可用庫存*（淨流量）佔 **最大庫存數量值的百分比**，該值為項目設定的值。 然後對每個品項和廠商建立一個計劃訂單（除非最大訂單數量用於強制拆分）。 該訂單的規劃優先順序計算為最大值的百分比。

使用下列公式：

*最大值百分比* = (*淨流量位置* × 100) ÷ *品項涵蓋範圍的最大庫存數量值*

在這個公式中，*淨流量位置* 按以下方式計算：

*淨流量位置* = *現有* + *訂購* – *合格的需求*

- *訂購* 是預期供給。
- *合格的需求* 表示需求日期在規劃時界內的淨需求。

在總規劃執行期間，當淨流量位置小於項目的再訂購點數量時，將建立新的計劃訂單。 計劃訂單數量是 **最大庫存數量** 在項目層級設定的值和淨流量位置的差。 計劃訂單優先順序按 **最大庫存數量** 值的 *淨流量位置* 百分比計算。

> [!NOTE]
> 即使需求超過總供應，計算的優先順序也不能為負。 如果需求超過總供應，則計算的優先順序設為 0（零）。

### <a name="priority-ranges"></a>優先順序範圍

此 *優先順序範圍* 計算方法比 *最大庫存數量的百分比* 方法更進階，且是在規劃優先順序模型層級進行設定。 可以建立幾個新的計劃供應訂單來滿足每個項目的需求。 計劃供應的優先順序遵循 **規劃優先順序模型** 頁面上的 **規劃優先順序範圍** 網格內定義的值。

當 **優先順序計算方法** 欄位設為 *優先順序範圍* 時，則以下附加規則生效：

- 如果規劃優先順序模型的 **考慮需求優先順序** 選項設為 *是*，則在每條需求行上設定的優先順序將限制優先順序範圍貯體。 任何新的計劃供應訂單的優先順序將不低於需求的優先順序。 範圍的上限值被視為與需求的優先順序值進行比較的閾值。 如果需求的優先順序正好在兩個範圍的上限閾值之間，則會選擇具有最高優先順序（即最低優先順序值）的範圍。
- 如果規劃優先順序模型的 **計劃訂單建立** 欄位設為 *具有最重要優先順序的單一供應*，將只會建立一個供應來滿足最大需求。 優先順序將被設為會觸發供應的第一個範圍的優先順序。
- 如果沒有現有庫存、沒有供應、沒有需求，則 **規劃優先順序範圍** 網格內的行將會被使用，該網格的 **起始數量** 欄位設為 *零*。
- 如果有需求，但沒有現有庫存或預期供給，則 **規劃優先順序範圍** 網格內的行將會被使用，該網格的 **起始數量** 欄位設為 *零或更少*。
- 當評估需求所在的範圍時，**考慮需求優先順序** 選項的設定將仍然有效。

## <a name="differences-between-traditional-timeline-calculations-and-priority-based-planning"></a>傳統的時間表計算與具有優先順序的規劃之間的差異

具有優先順序的規劃在以下方面不同於傳統的時間表計算：

- 所有一般的預先規劃處理器仍然有效。 這些預先處理器包括將已核准的計劃訂單與銷售需求、採購申請對應和保留邏輯掛鉤。 僅處理這些預先處理器未滿足的需求。
- 在掛鉤期間，無論其優先順序如何，都會考慮所有供應。 此供應包括現有庫存、已發佈供應和已核准計劃訂單的非掛鉤部分。
- 在整個涵蓋期間，不能將“負天數”需求與供應掛鉤。
- 當供應與需求掛鉤時，具有最高優先順序（即最低優先順序值）的供應會首先用完。 現有供應的優先順序值為 0（零）。 因此，它將作為第一個來源被消耗。
- 新的計劃供應行將根據最小訂單大小、最大訂單大小、數量倍數等一般規則建立。

## <a name="planning-priority-models"></a>規劃優先順序模型

*規劃優先順序模型* 被分配到涵蓋範圍群組並控制計劃訂單的規劃優先順序。 它們定義決定如何為每個計劃訂單計算規劃優先順序值以及如何將優先順序指派給計劃訂單、供應行和需求行的邏輯。

要使用規劃優先順序模型，請前往 **總規劃\>設定\>規劃優先順序模型**。 如前所述，模型最重要的其中一個設定是 **優先順序計算方法** 值。 此設定控制總規劃將優先順序值指派給計劃訂單時使用的計算方法。

> [!NOTE]
> 規劃優先順序模型適用組織範圍的所有法律實體。

### <a name="coverage-group"></a>涵蓋範圍群組

設定一個您計劃用於具有優先順序的規劃的新涵蓋範圍群組，依照[定義項目的涵蓋規則](../tasks/define-coverage-rules-items.md)所述。 建立該涵蓋範圍群組後，設定以下附加欄位：

- **涵蓋範圍代碼**- 如果該涵蓋範圍群組將使用具有優先順序的規劃，則選擇 *優先順序*。
- **規劃優先順序模型**–選擇任何組織範圍的規劃優先順序模型。

### <a name="item-coverage"></a>品項涵蓋範圍

依照[涵蓋範圍設定](../coverage-settings.md)中所述，設定品項涵蓋範圍設定。 依預設，為涵蓋範圍群組所選的 **涵蓋範圍代碼** 值會複製到品項涵蓋範圍設定。 但是，您可視需要覆寫該預設值。 在某些情況下，品項涵蓋範圍記錄的 **涵蓋範圍代碼** 欄位設為 *規劃*，但沒有為相關的涵蓋範圍群組定義規劃優先順序模型。 在這些情況下，任何 **優先順序計算方法** 欄位設為 *最大庫存數量的百分比* 和 **計劃訂單建立** 欄位設為 *具有最重要優先順序的單一供應* 的模型將依預設應用。

將 **涵蓋範圍代碼** 欄位設為 *優先順序*，使品項涵蓋範圍設定中的 **再訂購點** 欄位可用。 在該欄位中，輸入系統在確定何時下達計劃訂單時應使用的再訂購點數量，該計劃訂單的 **涵蓋範圍代碼** 值為 *優先順序*。

再訂購點數量通常計算為前置時間的需求加上最小值（安全庫存）。 它必須是介於 **最小** 和 **最大** 值。

例如，您可依下列方式設定欄位：

- **最小：** *10*
- **再訂購點：** *45*
- **最大：** *60*

對於此範例，再訂購點數量是基於 7 天的前置時間和 5 天的平均每日使用量。 因此，前置時間的需求為 35。 然後新增最小值 10（安全庫存）以獲得再訂購點 45 。 使用此設定時，將在預計的現有等級低於 45 時建議供應。 訂單優先順序將根據規劃優先順序設定。

### <a name="manage-planning-priority-models"></a>管理規劃優先順序模型

要使用您的規劃優先順序模型。 請依下列步驟操作。

1. 前往 **總規劃 \> 設定 \> 規劃優先順序模型**。
1. 在清單窗格中選擇一個現有模型，或在動作窗格上選擇 **新增** 以建立一個新模型。
1. 在記錄的標頭上設定以下欄位：

    - **名稱** – 輸入該模型的名稱。 該名稱在您組織中的所有法律實體中必須是唯一的。
    - **描述** – 輸入該模型的描述。
    - **優先順序計算方法**–選擇下列其中一個值：

        - *優先順序範圍*–當您選擇此值時，**規劃優先順序範圍** 網格變為可供使用。 在那裡，您必須建立幾個優先順序範圍來定義規劃優先順序值。
        - *最大庫存數量的百分比*–根據預計庫存等級超過最大庫存數量，將規劃優先順序值計算為百分比。

    - **計劃訂單建立**–此欄位在 **優先順序計算方法** 欄位設為 *優先順序範圍* 時可用。 選擇下列其中一個值：

        - *具有最重要優先順序的單一供應*–不要根據優先順序範圍拆分計劃訂單。 計劃訂單的規劃優先順序是根據最重要的優先順序範圍（即最低規劃優先順序值）。
        - *根據優先順序範圍拆分*–根據規劃優先順序範圍，將需求拆分為多個計劃訂單。 單個計劃訂單的規劃優先順序由相關規劃優先順序範圍的規劃優先順序定義。

    - **考慮需求優先順序**–將此選項設為 *是*，限制為供應建立的新計劃訂單的優先順序。 （優先順序將不低於相關需求的優先順序。）如果您將此選項設為 *否*，則計算供應訂單的優先順序時，將不考慮需求訂單的優先順序。

1. 如果您將 **優先順序計算方法** 欄位設為 *優先順序範圍*，使用 **規劃優先順序範圍** FastTab 工具列上的 **新增** 和 **移除** 按鈕，可視需要新增或移除優先順序範圍列。 如果存在多列，且您插入新的一列，則規劃優先順序將會自動設為所選列及其上一列的平均值。 對於每一列，設定下列欄位：

    - **規劃優先順序**–輸入 0.00 到 100.00 之間的任何值。 此值表示用於列的規劃優先順序。 最低優先順序值代表最高優先順序。 已指派一個預設值，但您可以根據需要更改它。 相同的 **規劃優先順序** 值不能用於同一規劃優先順序模型中的多個規劃優先順序範圍。
    - **描述**–輸入規劃優先順序範圍的描述（例如 *再訂購點到最大值*）。
    - **起始數量**–規劃優先順序範圍的下限。 此值是唯讀，而且是根據先前規劃優先順序範圍的 **最終數量** 和 **最終數量的百分比** 值。
    - **最終數量**–從品項涵蓋範圍中選擇應用於定義範圍上限的欄位。 支援以下值，且該值將會影響下一個範圍的 **起始數量** 值：

        - *零*–該值表示負到零的範圍（*零或更少* 到 *零*）。 對於選擇該值的列，**最終數量的百分比** 欄位是唯讀，且一律設為 *100* 百分比。
        - *最小庫存數量*–該值代表 **品項涵蓋範圍** 頁面上品項的 **最小** 值。 對於選擇該值的列，**最終數量的百分比** 欄位是可編輯的，且用於設定下一個範圍的 **起始數量** 值（例如，到 *最小庫存數量的 80%*）。
        - *再訂購點*–該值代表 **品項涵蓋範圍** 頁面上品項的 **再訂購點** 值。 對於選擇該值的列，**最終數量的百分比** 欄位是可編輯的，且用於設定下一個範圍的 **起始數量** 值（例如，到 *再訂購點的 80%*）。
        - *最大庫存數量*–該值代表 **品項涵蓋範圍** 頁面上品項的 **最大** 值。 對於選擇該值的列，**最終數量的百分比** 欄位是可編輯的，且用於設定下一個範圍的 **起始數量** 值（例如，到 *最小庫存數量的 80%*）。
        - *無限*–該值表示範圍的無限上限（*無限或更少* 到 *無限*）。 對於選擇該值的列，**最終數量的百分比** 欄位是唯讀，且一律設為 *100* 百分比。

    - **最終數量的百分比**–根據 **最終數量** 欄位選取的值，輸入用於計算規劃優先順序範圍上限的百分比值。 例如，如果 **最終數量** 欄位設為 *最小庫存數量*，而 **最終數量的百分比** 欄位設為 *50*，則上限將為相關品項涵蓋範圍最低庫存數量的 50%。

1. 在 **規劃優先順序預設值** FastTab 上，您可視需要設定欄位，為每種類型的供應或需求行（銷售訂單、採購單、轉移訂單或需求預測）定義預設規劃優先順序。 只能輸入正值。

## <a name="view-and-maintain-planning-priority"></a>檢視和維護規劃優先順序

規劃優先順序顯示並設定在 **規劃優先順序** 欄位內。 您可以在下表列出的頁面上找到此欄位。 優先順序是一個設為介於 0（零）和 100 之間的數字，其中 0 表示最高重要性。

| 頁面 | 欄位位置 | 值來源 |
|---|---|---|
| 需求預測行 | <p>**品項** 索引標籤</p><p>（在上部選擇一行，然後選擇 **品項** 索引標籤。）</p> | 預設值或手動設定的值 |
| 銷售訂單詳細資料 | <p>在 **行項詳細資料** FastTab 上的 **交貨** 索引標籤。</p><p>（選擇 **銷售訂單行** FastTab 上的一行，然後在 **行項詳細資料** FastTab 上選擇 **交貨** 索引標籤。）</p> | 預設值、來自公司間的值或手動設定的值 |
| 採購單詳細資料 | <p>在 **行項詳細資料** FastTab 上的 **交貨** 索引標籤。</p><p>（選擇 **採購單行** FastTab 上的一行，然後在 **行項詳細資料** FastTab 上選擇 **交貨** 索引標籤。）</p> | 在確定期間根據計劃訂單設定的值、來自公司間的值或手動設定的值 |
| 轉移訂單詳細資料 | <p>在 **行項詳細資料** FastTab 上的 **交貨** 索引標籤。</p><p>（選擇 **轉移訂單行** FastTab 上的一行，然後在 **行項詳細資料** FastTab 上選擇 **交貨** 索引標籤。）</p> | 在確定期間根據計劃訂單設定的值或手動設定的值 |
| 計劃訂單詳細資料 | **一般** FastTab | 在總規劃期間計算的值或手動設定的值 |

### <a name="intercompany-trade"></a>公司間貿易

此在公司間供求行的 **規劃優先順序** 值在關聯實體之間共享。 任何一方的修改都將反映在連結的訂單行上。

這裡有些範例：

- 使用者將公司間銷售訂單行的規劃優先順序從 20 更改為 30。 此更改反映在連結的公司間採購訂單行上。
- 使用者將公司間採購單行的規劃優先順序從 40 更改為 50。 此更改反映在連結的公司間銷售訂單行上。