---
title: 庫存能見度保留
description: 本主題將說明如何設定庫存能見度的保留功能以建立保留項目、消耗保留項目及/或取消保留指定的庫存數量。
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 5e6752539a6381e1f7271883102391374e04f3aa
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449820"
---
# <a name="inventory-visibility-reservations"></a>庫存能見度保留

[!include [banner](../includes/banner.md)]


本主題將說明如何設定庫存能見度的保留功能以建立保留項目、消耗保留項目及/或取消保留指定的庫存數量。

保留項目會標記將來使用的庫存數量。 建立保留項目時，系統會阻止其他訂單保留或消耗保留的貨物，直到保留項目被消耗或取消保留。 對庫存能見度服務使用 API 呼叫即可建立、消耗及取消保留。

您可以選擇設定 Microsoft Dynamics 365 Supply Chain Management (和其他第三方系統) 自動沖銷以庫存能見度保留的數量。 沖銷數量會從庫存能見度的保留記錄中刪除。

當您開啟保留功能時，Supply Chain Management 會自動準備沖銷使用庫存能見度保留的項目。

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>開啟並設定保留功能

若要開啟保留功能，請按照以下步驟執行。

1. 登入 Power Apps 並開啟 **庫存能見度**。
1. 開啟 **設定** 頁面。
1. 在 **功能管理** 索引標籤中，開啟 *OnHandReservation* 功能。
1. 登入 Supply Chain Management。
1. 前往 **[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** 工作區，並啟用 *庫存能見度與保留沖銷整合* 功能 (需要 10.0.22 或更高版本)。
1. 前往 **庫存管理 \> 設定 \> 庫存能見度整合參數**，開啟 **保留沖銷** 索引標籤並進行以下設定：
    - **啟用保留沖銷**：設為 *是* 以啟用此功能。
    - **保留沖銷修飾詞**：選擇會沖銷在庫存能見度上設定的保留項目的庫存交易狀態。 此設定會決定觸發沖銷的訂單處理階段。 該階段由訂單的庫存交易狀態追蹤。 選擇下列其中一個選項：
        - *訂購*：若為 *交易中* 狀態，訂單將在建立時傳送沖銷要求。 沖銷數量將是建立訂單的數量。
        - *保留*：若為 *保留已訂購交易* 狀態，訂單將在保留、揀貨、裝箱單過帳或開立發票時傳送沖銷要求。 系統僅會在上述程序啟動第一步時觸發一次該要求。 沖銷數量將是相應訂單明細庫存交易狀態從 *訂購* 變更為 *訂購保留* (或更晚狀態) 時的數量。

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>使用庫存能見度中的保留功能

呼叫保留 API 時，系統會標記指定商品和數量的保留。 您必須定義保留階層並發布與該保留階層相符的要求。 接著即可透過直接呼叫保留 API 來進行保留。

### <a name="configure-the-reservation-hierarchy"></a>設定保留階層

保留階層會說明保留庫存時必須指定的維度序列。 保留階層的運作方式與現有查詢所用的索引階層相同。

保留階層的結構可能與索引階層不同。 您可以藉由這種獨立性實施類別管理，讓使用者將維度細分成詳細資料，以指定更精確的保留要求。

若要在 Power Apps 中設定未確認保留階層，請開啟 **設定** 頁面，然後在 **未確認保留階層** 索引標籤中新增及/或修改維度及其階層級別，藉此設定保留階層。

未確認保留階層應包含 `SiteId` 和 `LocationId`，這些元件會建構分割區設定。

若需如何設定保留的相關資訊，請參閱[保留設定](inventory-visibility-configuration.md#reservation-configuration)。

### <a name="call-the-reservation-api"></a>呼叫保留 API

若要在庫存能見度服務中設定保留，可以提交 POST 要求至服務網址，例如 `/api/environment/{environment-ID}/onhand/reserve`。

保留要求本文必須包含組織識別碼、產品識別碼、保留數量和維度。 該要求會為每個保留記錄產生一組唯一的保留 ID。 預訂記錄包含產品識別碼和維度的唯一組合。

在您呼叫保留 API 時，您可以透過指定要求本文中的 `ifCheckAvailForReserv` 布林值來控制保留驗證。 `True` 的值表示需要驗證，而 `False` 的值表示不需要驗證。 預設值為 `True`。

如果您要取消保留或取消保留指定的庫存數量，請將數量設為負值，然後將 `ifCheckAvailForReserv` 參數設為 `False` 以略過驗證。

提供以下要求本文範例做為參考。

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Supply Chain Management 中的沖銷保留

對於包含指定保留沖銷修飾詞的庫存交易狀態，當符合以下所有條件時，交易更新將沖銷相應的保留記錄：

- 庫存交易的保留 ID 符合庫存能見度服務中保留記錄的保留 ID。
- 庫存交易維度與庫存能見度服務中的保留記錄維度相同。
- 已完成或已略過的訂單流程反映到庫存交易狀態時，庫存交易狀態的變化會觸發保留沖銷。

沖銷數量遵循庫存交易記錄指定的庫存數量。 如果庫存能見度服務中沒有保留數量，則沖銷不會生效。

### <a name="set-up-the-reservation-offset-modifier"></a>設定保留沖銷修飾詞

如果您尚未設定，請按照[開啟並設定保留功能](#turn-on) 中的說明設定保留修飾詞。

### <a name="set-up-reservation-ids"></a>設置保留 ID

保留 ID 是不重複的識別碼，用於標記庫存能見度中的保留記錄。 在 Supply Chain Management 中，使用者將保留項目放入訂單明細，即可標記相應保留記錄的沖銷。

若要在 Supply Chain Management 中設定保留 ID，請執行以下步驟。

1. 開啟銷售訂單 (例如從 **所有銷售訂單** 頁面)。
1. 在 **銷售訂單明細** FastTab 上，請選取銷售訂單明細。
1. 在工具列的 **銷售訂單明細** FastTab 上，選取 **更新明細 \> 庫存 \> 庫存能見度整合**。
1. 輸入相關的保留 ID。

庫存狀態變更符合沖銷修飾詞設定。
