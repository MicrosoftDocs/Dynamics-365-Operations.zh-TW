---
title: 與第三方製造執行系統整合
description: 本主題介紹如何整合 Microsoft Dynamics 365 Supply Chain Management 與第三方製造執行系統 (MES)。
author: t-benebo
ms.date: 10/01/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8917c9b265bc3df19517f052e28fb7644057cb46
ms.sourcegitcommit: 19f0e69a131e9e4ff680eac13efa51b04ad55a38
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/22/2022
ms.locfileid: "8450066"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>與第三方製造執行系統整合

[!include [banner](../includes/banner.md)]

一些使用 Microsoft Dynamics 365 Supply Chain Management 的製造組織，會使用 Dynamics 365 中的原生功能來控制其機器、設備和人員的製造活動。 但其他製造組織，尤其是那些具有進階製造需求的製造組織，會使用第三方製造執行系統 (MES)。 組織可能會依據各種原因選擇第三方 MES 解決方案，例如解決方案是專為組織的垂直產業量身訂製的。

在整合式解決方案中，資料交換是完全自動化的，並且幾乎是即時發生的。 因此，兩個系統中的資料都保持最新，無需手動輸入資料。 例如，在 MES 中登記材料消耗時，整合可確保在 Dynamics 365 中也登記相同的消耗。 因此，最新的庫存記錄可用於其他重要流程，例如計劃和銷售。

該解決方案使 Supply Chain Management 使用者能夠更快、更輕鬆、更便宜地與第三方 MES 整合。 其中提供的功能如下：

- 支援[關鍵製造執行流程](#processes-available-for-mes-integration)的業務事件及介面
- 中央儀表板，您可以在其中追蹤事件處理歷程記錄，並對失敗的流程進行疑難排解和修復

下圖顯示了在整合式解決方案中交換的一系列典型業務事件、流程和訊息。

![一般整合案例。](media/3p-mes-scenario.png "一般整合案例。")

## <a name="turn-on-the-mes-integration-feature"></a>開啟 MES 整合功能

在您可以使用此功能之前，管理員必須按照以下步驟在您的系統中開啟該功能。

1. 前往 **系統管理 \> 設定 \> 授權設定**。
1. 確保 **時間和出勤** 授權金鑰已啟用 (顯示勾選標記)。 此授權金鑰是必需的，因為它控制製造執行系統的功能和資料。 如果未啟用，請執行以下步驟：
    1. 進入系統的維修模式，如[維修模式](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)中的說明。
    1. 在 **授權設定** 頁面，選擇 **時間和出勤** 核取方塊。
    1. 關閉維修模式，如[維修模式](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)中的說明
1. 前往 **系統管理 \> 工作區 \> 功能管理**。
1. 開啟以下列方式列出的功能 (也請參閱[功能管理概觀](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md))：
    - **模組：** *生產控制*
    - **功能名稱：** *製造執行系統整合*

## <a name="processes-available-for-mes-integration"></a>可用於 MES 整合的流程

您可以啟用以下任何或所有流程進行整合。

| 流程名稱 | 描述 |
|---|---|
| 下達生產訂單和生產訂單狀態變更業務事件 | 此流程提供了一個 MES 可以監聽的業務事件，以獲取有關應該生產的生產訂單資訊。 與生產訂單相關的參考資料預計將透過開放式資料通訊協定 (OData) 或資料實體從 Supply Chain Management 共享到 MES。 |
| 啟動生產訂單 | 此流程為 Supply Chain Management 提供有關使用 MES 啟動的生產訂單的資訊。 它確保兩個系統都能掌握所有製造活動的最新狀態。 |
| 報告生產或報廢數量 | 此流程為 Supply Chain Management 提供使用 MES 回報生產工作良好及錯誤數量的相關資訊。 它確保車間主管能夠及時了解生產計劃進度。 |
| 報告材料消耗 | 此流程為 Supply Chain Management 提供來自 MES 的已消耗材料數量相關資訊。 這樣最新的庫存記錄可用於其他重要流程，例如計劃和銷售。 |
| 報告作業消耗的時間 | 此流程為 Supply Chain Management 提供有關用於特定作業的時間資訊。 |
| 結束生產訂單 | 此流程告知 Supply Chain Management，MES 已將生產訂單更新為 *結束* 的最終狀態。 此狀態表示生產訂單將不再生產任何數量。 |

## <a name="monitor-incoming-messages"></a>監控內送郵件

要監控系統的內送郵件，請開啟 **製造執行系統整合** 頁面。 您可在其中查看、處理和疑難排解問題。

## <a name="call-the-api"></a>呼叫 API

要呼叫 MES 整合 API，請發送 `POST` 要求至以下端點 URL：

`/api/services/SysMessageServices/SysMessageService/SendMessage`

您發送的要求正文應類似於以下範例。 依據要求替換 `_companyId`、`_messageType` 及 `_messageContent` 的值。 有關 API 支援的各種訊息類型以及如何設計其內容的相關資訊，請參閱下一節。

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>API 訊息類型和內容

本節介紹可以透過 MES 整合 API 交換的每種類型訊息。

### <a name="start-production-order-message"></a>開始生產訂單訊息

*開始生產訂單* 訊息的 `_messageType` 值為 `ProdProductionOrderStart`。 下表顯示了此訊息支援的欄位。

| 欄位名稱 | 狀態 | 類型 |
|---|---|---|
| `ProductionOrderNumber` | 強制 | 字串 |
| `StartedQuantity` | 選擇性 | 真實 |
| `StartedDate` | 選擇性 | 日期 |
| `AutomaticBOMConsumptionRule` | 選擇性 | 列舉 (耗用原則 \| 總是 \| 絕不) |

### <a name="report-as-finished-message"></a>完工報告訊息

*完工報告* 訊息的 `_messageType` 值為 `ProdProductionOrderReportFinished`。 下表顯示了此訊息支援的欄位。

| 欄位名稱 | 狀態 | 類型 |
|---|---|---|
| `ProductionOrderNumber` | 強制 | 字串 |
| `ReportFinishedLines` | 強制 | 行清單 (至少一個)，每個清單包含下表說明的承載 |

下表顯示 `ProdProductionOrderReportFinished` 訊息的 `ReportFinishedLines` 區段中每行支援的欄位。

| 欄位名稱 | 狀態 | 類型 |
|---|---|---|
| `LineNumber` | 選擇性 | 真實 |
| `ItemNumber` | 選擇性 | 字串|
| `ProductionType` | 選擇性 | 列舉 (主要品項\|公式\|物料清單\|合作產品\|副產品\|無)，可擴展 |
| `ReportedErrorQuantity` | 選擇性 | 真實|
| `ReportedGoodQuantity` | 選擇性 | 真實|
| `ReportedErrorCatchWeightQuantity` | 選擇性 | 真實 |
| `ReportedGoodCatchWeightQuantity` | 選擇性 | 真實 |
| `AcceptError` | 選擇性 |布林值 |
| `ErrorCause` | 選擇性 | 列舉 (無\|材料\|機器\|操作人員)，可擴展 |
| `ExecutedDateTime` | 選擇性 | DateTime |
| `ReportAsFinishedDate` | 選擇性 | 日期 |
| `AutomaticBOMConsumptionRule` | 選擇性 | 列舉 (耗用原則 \| 總是 \| 絕不) |
| `AutomaticRouteConsumptionRule` | 選擇性 |列舉 (依途程而定 \| 總是 \| 絕不) |
| `RespectFlushingPrincipleDuringOverproduction` | 選擇性 | 布林值 |
| `ProductionJournalNameId` | 選擇性 | 字串 |
| `PickingListProductionJournalNameId` | 選擇性 | 字串|
| `RouteCardProductionJournalNameId` | 選擇性 | 字串 |
| `FromOperationNumber` | 選擇性 | 整數|
| `ToOperationNumber` | 選擇性 | 整數|
| `InventoryLotId` | 選擇性 | 字串 |
| `BaseValue` | 選擇性 | 字串 |
| `EndJob` | 選擇性 | 布林值 |
| `EndPickingList` | 選擇性 | 布林值 |
| `EndRouteCard` | 選擇性 | 布林值 |
| `PostNow` | 選擇性 | 布林值 |
| `AutoUpdate` | 選擇性 | 布林值 |
| `ProductColorId` | 選擇性 | 字串|
| `ProductConfigurationId` | 選擇性 | 字串 |
| `ProductSizeId` | 選擇性 | 字串 |
| `ProductStyleId` | 選擇性 | 字串 |
| `ProductVersionId` | 選擇性 | 字串 |
| `ItemBatchNumber` | 選擇性 | 字串 |
| `ProductSerialNumber` | 選擇性 | 字串 |
| `LicensePlateNumber` | 選擇性 | 字串 |
| `InventoryStatusId` | 選擇性 | 字串 |
| `ProductionWarehouseId` | 選擇性 | 字串 |
| `ProductionSiteId` | 選擇性 | 字串 |
| `ProductionWarehouseLocationId` | 選擇性 | 字串 |
| `InventoryDimension1` 至 `InventoryDimension12` | 選擇性 | 字串 |

12 個可擴展維度 (`InventoryDimension1` 至 `InventoryDimension12`) 需要自訂，並不總是使用。 有關它們的更多資訊，請參閱[透過擴展新增新的庫存維度](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md)。

### <a name="material-consumption-picking-list-message"></a>材料消耗 (揀料單) 訊息

*材料消耗 (揀料單)* 訊息的 `_messageType` 值為 `ProdProductionOrderPickingList`。 下表顯示了此訊息支援的欄位。

| 欄位名稱 | 狀態 | 類型 |
|---|---|---|
| `ProductionOrderNumber` | 強制 | 字串 |
| `JournalNameId` | 選擇性 | 字串 |
| `PickingListLines` | 強制 | 行清單 (至少一個)，每個清單包含下表說明的承載 |

下表顯示 `ProdProductionOrderPickingList` 訊息的 `PickingListLines` 區段中每行支援的欄位。

| 欄位名稱 | 狀態 | 類型 |
|---|---|---|
| `ItemNumber` | 強制 | 字串 |
| `ConsumptionBOMQuantity` | 選擇性 | 真實 |
| `ProposalBOMQuantity` | 選擇性 | 真實 |
| `ScrapBOMQuantity` | 選擇性 | 真實 |
| `BOMUnitSymbol` | 選擇性 | 字串 |
| `ConsumptionInventoryQuantity` | 選擇性 | 真實 |
| `ProposalInventoryQuantity` | 選擇性 | 真實 |
| `ConsumptionCatchWeightQuantity` | 選擇性 | 真實 |
| `ProposalCatchWeightQuantity` | 選擇性 | 真實 |
| `ConsumptionDate` | 選擇性 | 日期 |
| `OperationNumber` | 選擇性 | 整數 |
| `LineNumber` | 選擇性 | 真實 |
| `PositionNumber` | 選擇性 | 字串 |
| `IsConsumptionEnded` | 選擇性 | 布林值 |
| `ErrorCause` | 選擇性 | 列舉 (無\|材料\|機器\|操作人員)，可擴展 |
| `InventoryLotId` | 選擇性 | 字串 |

### <a name="time-used-for-operation-route-card-message"></a>作業時間 (途程卡) 訊息

*作業時間 (途程卡)* 訊息的 `_messageType` 值為 `ProdProductionOrderRouteCard`。 下表顯示了此訊息支援的欄位。

| 欄位名稱 | 狀態 | 類型 |
|---|---|---|
| `ProductionOrderNumber` | 強制 | 字串 |
| `JournalNameId` | 選擇性 | 字串 |
| `RouteCardLines` | 強制 | 行清單 (至少一個)，每個清單包含下表說明的承載 |

下表顯示 `ProdProductionOrderRouteCard` 訊息的 `RouteCardLines` 區段中每行支援的欄位。

| 欄位名稱 | 狀態 | 類型 |
|---|---|---|
| `OperationNumber` | 強制 | 整數 |
| `OperationPriority` | 選擇性 | 列舉 (主要\|次要 1 \| 次要 2 \| ...\| 次要 20) |
| `OperationId` | 選擇性 | 字串 |
| `OperationsResourceId` | 選擇性 | 字串 |
| `Worker` | 選擇性 | 字串 |
| `HoursRouteCostCategoryId` | 選擇性 | 字串 |
| `QuantityRouteCostCategoryId` | 選擇性 | 字串 |
| `HourlyRate` | 選擇性 | 真實 |
| `Hours` | 選擇性 | 真實 |
| `GoodQuantity` | 選擇性 | 真實 |
| `ErrorQuantity` | 選擇性 | 真實 |
| `CatchWeightGoodQuantity` | 選擇性 | 真實 |
| `CatchWeightErrorQuantity` | 選擇性 | 真實 |
| `QuantityPrice` | 選擇性 | 真實 |
| `ProcessingPercentage` | 選擇性 | 真實 |
| `ConsumptionDate` | 選擇性 | 日期 |
| `TaskType` | 選擇性 | 列舉 (佇列前\|設定\|流程\|重疊\|運輸\|佇列後\|負擔) |
| `ErrorCause` | 選擇性 | 列舉 (無\|材料\|機器\|操作人員)，可擴展 |
| `OperationCompleted` | 選擇性 | 布林值 |
| `BOMConsumption` | 選擇性 | 布林值 |
| `ReportAsFinished` | 選擇性 | 布林值 |

### <a name="end-production-order-message"></a>結束生產訂單訊息

*結束生產訂單* 訊息的 `_messageType` 值為 `ProdProductionOrderEnd`。 下表顯示了此訊息支援的欄位。

| 欄位名稱 | 狀態 | 類型 |
|---|---|---|
| `ProductionOrderNumber` | 強制 | 字串 |
| `ExecutedDateTime` | 選擇性 | DateTime |
| `EndedDate` | 選擇性 | 日期 |
| `UseTimeAndAttendanceCost` | 選擇性 | 布林值 |
| `AutoReportAsFinished` | 選擇性 | 布林值 |
| `AutoUpdate` | 選擇性 | 布林值 |

## <a name="receive-feedback-about-the-state-of-a-message"></a>接收有關訊息狀態的意見反應

在 MES 向 Supply Chain Management 發送訊息後，Supply Chain Management 可能會傳回有關訊息狀態的意見反應。 這種行為也許能在以下情況範例中派上用場：

- 沒有人負責不斷監督 MES 整合。
- 負責監督 MES 整合的人希望在訊息失敗時收到電子郵件通知，以便讓他們知道必須採取行動。
- MES 必須顯示錯誤訊息，以通知車間操作員或 IT 部門人員必須採取行動。
- MES 必須在收到失敗訊息 (例如，因為生產訂單啟動失敗) 後重新計算訂單排程。

在這些情況下，您可以利用 Supply Chain Management 中的標準警示功能。 有關標準警示如何運作的資訊，請參閱以下資源：

- 說明主題：[警示概述](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- 影片：[Dynamics 365 for Finance and Operations 之中的警示選項](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

例如，您可以設定以下警示以提供有關訊息狀態的意見反應：

- 建立訊息 *失敗* 時使用的業務事件 (「向外部發送」)。
- 向 IT 管理員或生產車間經理發送通知和電子郵件。
