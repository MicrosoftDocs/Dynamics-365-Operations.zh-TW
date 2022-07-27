---
title: 整合 Supply Chain Management 和 Field Service 之間的採購
description: 本主題介紹雙重寫入整合如何支援從 Supply Chain Management 和 Field Service 建立和更新訂購單。
author: RamaKrishnamoorthy
ms.date: 11/11/2020
ms.topic: article
audience: Application User
ms.reviewer: tfehr
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ab251ee60bf3c831b0139beb9557c6b3faaf9f66
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460551"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>整合 Supply Chain Management 和 Field Service 之間的採購

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Microsoft Dynamics 365 Supply Chain Management 提供強大的採購函數。 Dynamics 365 Field Service 提供支援與服務流程相關聯的採購流程的類似函數。 這兩個應用程式中的函數透過雙重寫入整合，並透過表對應、解決方案邏輯、檢視表和表單啟用由此產生的跨函數用例。

此整合支援建立訂購單，並且在大多數情況下，支援來自兩個應用程式的更新。 但是，Supply Chain Management 控制定價、地址和產品收據。 為同時使用 Field Service 和 Supply Chain Management 的組織啟用了幾個強大的跨職能用例。 這些用例使採購能夠跨兩個系統啟動和追蹤。

下圖顯示了兩個系統中的表以及它們如何相互對應。 Field Service 中的訂購單參考一個 *帳戶* 列，而 Supply Chain Management 中的訂購單參考一個 *供應商* 列。 為了解決整合問題，雙重寫入使用參考將 *廠商* 列與 *帳戶* 列連結起來。 如需相關資訊，請參閱[整合基準廠商](vendor-mapping.md)。

![採購對應。](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>先決條件

若要將 Supply Chain Management 與 Field Service 整合，您必須安裝以下組件：

- Field Service 版本 8.8.31.60 或更高版本，用於全面的訂購單整合
- Supply Chain Management 10.0.14 或更高版本
- 雙重寫入，執行 OneFSSCM 解決方案

## <a name="installation-guidelines"></a>安裝指南

### <a name="prerequisites"></a>先決條件

- **雙重寫入** – 如需相關資訊，請參閱[雙重寫入首頁](dual-write-home-page.md#dual-write-setup)。
- **Dynamics 365 Field Service** - 如需相關資訊，請參閱[如何安裝 Dynamics 365 Field Service](/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service)。

在 Microsoft Dataverse 中啟用它們後，雙重寫入和 Field Service 引入了幾個解決方案層，這些解決方案層使用新的中繼資料、表單、檢視表和邏輯擴展了環境。 這些解決方案可以按任何順序啟用，但您通常按照此處給出的順序進行安裝：

1. **Field Service Common** – 在環境中安裝 Field Service 時安裝 Field Service Common。
2. **Field Service (Anchor)** – 在環境中安裝 Field Service 時安裝 Field Service (Anchor)。 
3. **Supply Chain Management Extended** – 在環境中啟用雙重寫入時，會自動安裝 Supply Chain Management Extended。 
4. **OneFSSCM 解決方案**–OneFSSCM 由最後安裝的解決方案 (Field Service 或 Supply Chain Management)自動安裝。

    - 如果 Field Service 已安裝在環境中，並且您啟用了雙重寫入 (安裝 Supply Chain Management Extended)，則會安裝 OneFSSCM。
    - 如果環境中已安裝 Supply Chain Management Extended，並且您安裝 Field Service，則會安裝 OneFSSCM。

## <a name="initial-synchronization"></a>初始同步處理

若要建立新的訂購單並使用現有的訂購單，您必須在 Supply Chain Management 和 Dataverse。 您使用初始寫入函數來偵測資料表關係並尋找必須為給定對應啟用的資料表。

您必須同步以下資料表：

- 產品範本

    當您執行初始寫入時，您將獲得所需表的完整清單。 這些範本的若干範例如下：

    - 所有產品
    - 已發佈產品 V2
    - Dataverse 發佈的獨特產品

- 網站
- 倉庫
- 採購類別範本

    這些範本的若干範例如下：

    - 採購類別
    - Pro
    - 產品類別階層
    - 產品類別指派

- 廠商範本，例如 Vendor V2
- 聯絡人範本，例如 Dataverse Contacts V2
- 員工範本，例如 Worker

該資料表的同步處理可確保 Supply Chain Management 中的所有文件 (訂購單和產品收據) 在 Dataverse 中提供。

### <a name="account-and-vendor-tables"></a>帳戶和廠商表

Field Service 中的訂購單依賴於客戶表來追蹤廠商。 因此，Dataverse 訂購單表使用帳戶來追蹤廠商。 為了適應這一關鍵差異，必須啟用以下四個工作流程以保持帳戶和廠商同步： 

- 在帳戶表中建立廠商
- 在廠商表中建立廠商
- 在帳戶表中更新廠商
- 在廠商表中更新廠商

如果安裝了 OneFSSCM，因為同時安裝了 Field Service 和 Supply Chain Management Extended，這些工作流程會自動啟用。 如果未安裝 Field Service，但您希望將訂購單表與 Dataverse 整合，則必須啟用這些工作流程。 在這兩種情況下，除非您從頭開始，否則您可能必須確保在建立訂購單之前將所有廠商都建立為 Dataverse 中的帳戶。 否則可能會出現錯誤。

### <a name="initial-synchronization"></a>初始同步處理

滿足所有先決條件後，如果您希望現有訂購單和產品收據在兩個系統中都提供，則必須對以下範本進行初始同步：

- 訂購單標題 V2
- CDS 訂購單明細
- CDS 訂購單明細虛刪除
- 訂購單收據
- 訂購單收據產品

## <a name="mappings-with-logic"></a>邏輯對應

採購整合使用以下邏輯擴展產品對應，以確保在 Dataverse 的產品表中正確設定 **Field Service 產品類型** 欄：

- 如果將 **產品類型** 設定為 *產品*，和 **項目模型組，則將庫存產品** 設定為 *True*，**Field Service 產品類型** 設定為 *庫存*。
- 如果將 **產品類型** 設定為 *產品*，和 **項目模型組，則將庫存產品** 設定為 *False*，**Field Service 產品類型** 設定為 *非庫存*。
- 如果將 **產品類型** 設定為 *服務*，則將 **Field Service 產品類型** 設定為 *服務*。

此外，Dataverse 包括將廠商與其相關帳戶對應的邏輯。 此邏輯設定預設發票廠商帳戶。 在建立時，伺服器端外掛程式邏輯從與帳戶相關的廠商處設定預設發票廠商帳戶。 廠商具有對用於設定此值的發票帳戶的參考。

## <a name="supported-scenarios"></a>支援的案例

- Dataverse 使用者可以建立和更新訂購單。 但是，該流程和資料由 Supply Chain Management 控制。 Supply Chain Management 中對訂購單欄更新的限制在更新來自 Field Service 時適用。 例如，如果訂購單已完成，您將無法更新它。 
- 如果訂購單由 Supply Chain Management 中的變更管理控制，則 Field Service 使用者只有在 Supply Chain Management 核准狀態為 *草稿* 時才能更新訂購單。
- 若干資料欄僅由 Supply Chain Management 管理，無法在 Field Service 中更新。 若要了解哪些資料欄無法更新，請查看產品中的對應表。 為簡單起見，這些資料欄中的大多數在 Dataverse 頁面上設定為僅供讀取。 

    例如，價格資訊列由 Supply Chain Management 管理。 Supply Chain Management 擁有的貿易協議可讓 Field Service 從中受益。 **單價**、**折扣** 和 **淨額** 等資料欄僅來自 Supply Chain Management。 若要確保價格與 Field Service **同步**，輸入訂購單資料後，您應在 Dataverse 的 **訂購單** 和 **訂購單產品頁** 面上使用同步功能。 如需相關資訊，請參閱[按需與 Dynamics 365 Supply Chain Management 採購資料同步](#sync-procurement)。

- **總計** 欄僅在 Field Service 中提供，因為 Supply Chain Management 中沒有訂購單的最新總計。 Supply Chain Management 中的總計是根據 Field Service 中不可用的多個參數計算的。
- 僅指定採購類別或指定產品是 *服務* 產品類型或 Field Service 產品類型的項目的訂購單明細只能在 Supply Chain Management 中啟動。 然後這些明細將同步到 Dataverse 並在 Field Service 中提供。
- 如果僅安裝 Field Service，而不安裝 Supply Chain Management，則 **倉庫** 欄在訂購單上是必要條件。 但是，如果安裝了 Supply Chain Management，則此要求會放寬，因為 Supply Chain Management 允許在某些情況下未指定倉庫的訂購單明細。
- 產品收據 (Dataverse 中的訂購單收據) 由 Supply Chain Management 管理，如果安裝了 Supply Chain Management，則無法從 Dataverse 建立。 來自 Supply Chain Management 的產品收據從 Supply Chain Management 同步到 Dataverse。
- Supply Chain Management 中允許交貨不足。 OneFSSCM 解決方案新增了邏輯，以便在建立或更新產品收據明細 (或 Dataverse 中的訂購單收據產品) 時，在 Dataverse 中建立一個庫存日記帳明細，以針對交貨不足的情況調整訂單的剩餘數量。

## <a name="unsupported-scenarios"></a>不支援的案例

- Field Service 防止將行新增到 Supply Chain Management 中已取消的訂購單。 作為一種解決方法，您可以在 Field Service 中更改訂購單的系統狀態，然後在 Field Service 或 Supply Chain Management 中新增新明細。
- 儘管採購列會影響兩個系統中的庫存量，但這種整合並不能確保 Supply Chain Management 和 Field Service 之間的庫存對齊。 Field Service 和 Supply Chain Management 都有其他更新庫存量的流程。 這些流程不在採購範圍之內。

## <a name="status-management"></a>狀態管理

Field Service 中的訂購單狀態與 Supply Chain Management 中的狀態不同。

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>Field Service 訂購單和訂購單產品狀態

| 標題 – 系統狀態 | 標題 - 核准狀態 | 項目狀態 |
|---|---|---|
| <ul><li>草稿</li><li>已提交</li><li>已取消</li><li>已收到的產品</li><li>已請款</li></ul> | <ul><li>Null</li><li>已核准</li><li>已拒絕</li></ul> | <ul><li>擱置中</li><li>已收到</li><li>已取消</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Supply Chain Management 訂購單和訂購單明細狀態

僅當存在明細工作流程時，明細核准狀態才有效。

| 標題 – 文件狀態 | 標題 - 核准狀態 | 明細狀態 | 明細核准狀態 |
|---|---|---|---|
| <ul><li>未結訂單 (延期交貨)</li><li>已收到</li><li>已請款</li><li>已取消</li></ul> | <ul><li>草稿</li><li>檢閱中</li><li>已核准</li><li>已拒絕</li><li>外部檢閱</li><li>已確認</li><li>已定案</li></ul> | <ul><li>未結訂單 (延期交貨)</li><li>已收到</li><li>已請款</li><li>已取消</li></ul> | <ul><li>未送出</li><li>檢閱中</li><li>已核准</li><li>已拒絕</li></ul> |

以下規則適用於狀態欄：

- 無法從 Field Service 更新 Supply Chain Management 中的狀態。 但是，在某些情況下，當 Supply Chain Management 中的訂購單狀態發生更改時，Field Service 中的狀態也會更新。
- 如果 Supply Chain Management 中的訂購單處於變更管理中，並且正在處理變更，則核准狀態為 *草稿* 或 *檢閱* 中。 在這種情況下，Field Service 核准狀態將設定為 *Null*。
- 如果 Supply Chain Management 中的訂購單核准狀態設定為 *已核准*、*外部檢閱* 中、*已確認* 或 *已定案*，則 Field Service 訂購單核准狀態將設定為 *已核准*。
- 如果 Supply Chain Management 中的訂購單核准狀態設定為 *已拒絕*，則 Field Service 訂購單核准狀態將設定為 *已拒絕*。
- 如果 Supply Chain Management 中的文件抬頭狀態更改為 *未結訂單 (延期交貨)*，並且 Field Service 訂購單狀態為 *草稿* 或 *已取消*，則 Field Service 訂購單狀態將更改為 *已送出*。
- 如果 Supply Chain Management 中的文件抬頭狀態更改為 *已取消*，並且 Field Service 中沒有訂購單收據產品與訂購單關聯 (透過訂購單產品)，則 Field Service 系統狀態設定為 *已取消*。
- 如果 Supply Chain Management 中的訂購單明細狀態為 *已取消*，則 Field Service 中的訂購單產品狀態設定為 *已取消*。 此外，如果 Supply Chain Management 中的訂購單明細狀態從 *已取消* 更改為 *延期交貨*，則 Field Service 中的訂購單產品項目狀態設定為 *待處理*。

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>按需同步 Supply Chain Management 採購資料

Supply Chain Management 包括處理貿易協議、折扣和其他依賴 Supply Chain Management 中的二級流程的方案的採購資料。 採購引擎使用複雜的規則來確定給定訂購單的最佳價格。 當您使用雙重寫入時，資料並不總是在兩個環境中保持同步，尤其是在從 Dataverse 建立或更新該列並可能觸發 Supply Chain Management 中的後續流程的情況下。

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>從 Supply Chain Management 同步採購資料

1. 在 Dataverse，進入 **庫存\>訂購單**。
2. 選取 **新建** 建立新的訂購單，或選取現有訂購單的明細。
3. 從訂購單或訂購單明細。
4. 在動作窗格上，選取 **同步**。

由 Supply Chain Management 共用的 Dataverse 和 Field Service 中的所有資料欄都已同步。

以下是您可能會使用 **同步** 函數的情況：

- 如果您從 Dataverse 對同一列進行多次連續更改，請執行 **同步** 函數。
- 如果您不確定更改是否可能是 Dataverse 的第二次連續更改，則執行 **同步** 函數可能有意義。
- 如果您收到有關從 Supply Chain Management 更新值的錯誤訊息，請執行 **同步** 函數，然後重試 Dataverse 中的更新。

## <a name="cancelling-the-posting-process"></a>取消過帳過程

如果在處理過程中取消了產品收據過帳流程，則雙重寫入可能會在 Dataverse 中建立產品收據列，但不會在 Supply Chain Management 中建立產品收據列。 出現這種情況是因為雙重寫入不支援分散式交易。

## <a name="templates"></a>範本

以下範本可用於整合採購相關文件。

| Supply Chain Management | Field Service | 描述 |
|---|---|---|
| [訂購單標題 V2](mapping-reference.md#183) | msdyn\_Purchaseorders | 此表包含代表訂購單標題的資料欄。 |
| [訂購單明細實體](mapping-reference.md#181) | msdyn\_PurchaseOrderProducts | 此表包含代表訂購單明細的資料列。 產品編號用於同步。 這將產品識別為庫存單位 (SKU)，包括產品尺寸。 如需與 Dataverse 的產品整合的相關資訊，請參閱[統一的產品體驗](product-mapping.md)。 |
| [產品收據抬頭](mapping-reference.md#185) | msdyn\_purchaseorderreceipts | 此表包含在 Supply Chain Management 中過帳產品收據時建立的產品收據抬頭。 |
| [產品收據明細](mapping-reference.md#184) | msdyn\_purchaseorderreceiptproducts | 此表包含在 Supply Chain Management 中過帳產品收據時建立的產品收據明細。 |
| [訂購單明細虛刪除實體](mapping-reference.md#182) | msdyn\_purchaseorderproducts | 此表包含有關虛刪除的訂購單明細的資訊。 Supply Chain Management 中的訂購單明細只有在訂購單已確認或核准後才能虛刪除，如果更改管理已打開。 該資料列存在於 Supply Chain Management 資料庫中並標記為 **已刪除**。 因為 Dataverse 沒有虛刪除的概念，所以將此資訊同步到 Dataverse 很重要。 這樣，Supply Chain Management 中虛刪除的明細可以自動從 Dataverse 中刪除。 在這種情況下，Dataverse 中刪除明細的邏輯位於 Supply Chain Management Extended 中。 |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
