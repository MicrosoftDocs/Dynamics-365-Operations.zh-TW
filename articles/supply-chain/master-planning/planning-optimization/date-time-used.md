---
title: Planning Optimization 使用的日期與時間參數
description: 本主題提供有關 Planning Optimization 在其作業期間使用的日期和時間參數的資訊。
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: dc44778dba0a5b914c524ff2ad026ab2f8eb88aa
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2021
ms.locfileid: "8449406"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>Planning Optimization 使用的日期與時間參數

[!include [banner](../../includes/banner.md)]

本主題提供有關 Planning Optimization 在其作業期間使用的日期和時間參數的資訊。

雖然內建的主計劃引擎使用交易日期進行所有的計算，但是 Planning Optimization 使用轉換為當前日期的日期和時間值。 這種行為差異可能導致以下情況，例如，在執行主計劃當天午夜建立的預測交易，將不會包括在內，因為 Planning Optimization 認為它們是在當前日期之前建立的。

## <a name="parameters-for-issue-and-demand-transactions"></a>問題和需求交易的參數

以下資料表列出 Planning Optimization 在處理問題和需求交易時使用的參數。

| 參數 | Planning Optimization 中的參數名稱 | 描述 | Microsoft Dynamics 365 Supply Chain Management 中的對等欄位 (在 ReqTrans 資料表中) |
|---|---|---|---|
| 計劃的發佈時間 | `PlannedIssueTime` | 當前計劃的發佈日期。 | **迄今為止** (`FuturesDate`) 和 **延遲至時間** (`FuturesTime`) |
| 要求的發佈時間 | `RequestedIssueTime` | 使用者要求，並於 Supply Chain Management 中設定的發佈日期。 此參數僅適用於已發佈或已批准的計劃訂單。 對於計劃訂單，預設為空白。 | **要求的日期** (`ReqDateDlvOrig`) |
| 所需的發佈時間 | `RequiredIssueTime` | 由 Planning Optimization 調整所需的發佈日期。 如果在運行計劃優化時請求的發佈時間是過去的時間，則所需的發佈時間將調整為不早於今天日期的第一個開放日。 如果請求的發佈時間在日曆中被標記為已封鎖，則所需的發佈時間將調整為該日期之前的第一個開放日。 | **所需日期** (`ReqDate`) 和 **所需時間** (`ReqTime`) |
| 發佈時間延遲 | `IssueTimeDelay` | 計劃發佈時間和無論是要求批准的發佈時間，和已發佈訂單，或是所需的發佈時間之間的時間差。 | **延遲 (天)** (`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>接收與供應交易參數

以下資料表列出 Planning Optimization 在處理收貨和供應交易時使用的參數。

| 參數 | Planning Optimization 中的參數名稱 | 描述 | Supply Chain Management 中的對等欄位 (在 ReqTrans 或 ReqPO 資料表中) |
|---|---|---|---|
| 計劃可用時間 | `PlannedAvailabilityTime` | 收貨計劃可用的日期。 | **所需日期** (`ReqDate`) 和 **所需時間** (`ReqTime`) |
| 計劃收貨時間 | `PlannedReceiptTime` | 收據到達位置的日期。 | 如果訂單尚未發布，**迄今為止** (`FuturesDate`)、**延遲到時間** (`FuturesTime`)，和 **交貨日期** (`ReqDateDlv`) 或 **要求日期** (`ReqDateDlvOrig`)。 |
| 所需可用時間 | `RequiredAvailabilityTime` | 由 Planning Optimization 調整所需的可用日期。 | **所需日期** (`ReqDate`) 和 **所需時間** (`ReqTime`) |
| 預計收貨時間 | `ExpectedReceiptTime` | 已發佈收據的預計收貨日期。 該值由使用者在 Supply Chain Management 中設定，而且不會由 Planning Optimization 調整。 此參數僅適用於已發佈的收貨。 | **要求的日期** (`ReqDateDlvOrig`) |
| 所需收貨時間 | `RequiredReceiptTime` | 由 Planning Optimization 調整所需的收貨日期。 | **所需日期** (`ReqDate`) 和 **所需時間** (`ReqTime`) |
| 計劃訂購時間 | `PlannedOrderingTime` | 由 Planning Optimization 計算訂購日期。 | **訂購日期** (`ReqDateOrder`) 和 **訂購時間** (`ReqTimeOrder`) |
| 計劃活動開始時間 | `PlannedActivityStartTime` | 此收據的活動應開始的日期。 | **開始日期** (`SchedFromDate`) |
| 收貨時間延遲 | `ReceiptTimeDelay` | 計劃收貨時間與要求收貨時間之間的時間差。 | **延誤 (天)** (`FuturesDays`) 和 **延遲到時間** (`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>Planning Optimization 使用資料參數的範例

以下插圖的計劃是以日等級的，但是 Planning Optimization 可以在更詳細的等級上執行。 例如，由於差額可以小時為單位，因此計劃訂購時間可以是 2021 年 1 月 22 日 11:35 等等。

### <a name="example-1-simple-scenario"></a>範例 1：簡單案例

一份採購訂單，涵蓋了一份要求發出時間為 1 月 22 日的銷售訂單。 使用以下設定：

- 沒有交期
- 沒有日曆 (所有日子都開放。)
- 沒有差額

以下插圖顯示此案例。 (選擇插圖，可打開更大的版本。)

[![簡單案例。](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>範例 2：交期案例

一份採購訂單，涵蓋了一份要求發出時間為 1 月 22 日的銷售訂單。 使用以下設定：

- 三天的交貨時間
- 沒有日曆 (所有日子都開放。)
- 沒有差額

以下插圖顯示此案例。 (選擇插圖，可打開更大的版本。)

[![交期案例。](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>範例 3：差額案例

一份採購訂單，涵蓋了一份要求發出時間為 1 月 22 日的銷售訂單。 使用以下設定：

- 三天的交貨時間
- 四天訂貨差額
- 五天可用差額
- 沒有日曆 (所有日子都開放。)

以下插圖顯示此案例。 (選擇插圖，可打開更大的版本。)

[![差額案例。](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>範例 4：延遲案例

一份採購訂單，涵蓋了一份要求發出時間為 1 月 22 日的銷售訂單。 此範例使用與範例 3 相同的設定，但計劃日期已移至 1 月 15 日。 向後調度 (紅色標記) 失敗，因為計劃的訂購時間必須早於今天的日期。 因此，主要計畫肯定會提前安排，並且會出現延遲。

以下插圖顯示此案例。 (選擇插圖，可打開更大的版本。)

[![延遲案例。](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>範例 5：轉移案例

來自倉庫 1 的一份銷售訂單的請求發貨時間為 1 月 22 日，該銷售訂單由來自倉庫 2 的一份轉移訂單覆蓋，該轉移訂單由計劃採購訂單覆蓋。 使用以下設定：

- 三天的轉移交期 (倉庫 1)
- 兩天的購買交期 (倉庫 2)
- 沒有日曆 (所有日子都開放。)

以下插圖顯示此案例。 (選擇插圖，可打開更大的版本。)

[![轉移案例。](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>範例 6：帶日曆案例的交期

一份採購訂單，涵蓋了一份要求發出時間為 1 月 22 日的銷售訂單。 使用以下設定：

- 三天的交貨時間
- 發佈日曆 (週五關閉)
- 可用日曆 (週四和周五關閉)
- 收貨日曆 (週二、週三和周日休息)
- 交期日曆 (週四和周五關閉)
- 訂購日曆 (週一和周六開放)

以下插圖顯示此案例。 (選擇插圖，可打開更大的版本。)

[![帶日曆案例的交期。](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>範例 7：帶日曆案例的延遲

一份採購訂單，涵蓋了一份要求發出時間為 1 月 22 日的銷售訂單。 此範例使用與範例 6 相同的設定，但計劃日期已移至 1 月 13 日。 向後調度 (紅色標記) 失敗，因為計劃的訂購時間必須早於今天的日期。 因此，主要計畫肯定會提前安排，並且會出現延遲。

以下插圖顯示此案例。 (選擇插圖，可打開更大的版本。)

[![帶日曆案例的延遲。](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)
