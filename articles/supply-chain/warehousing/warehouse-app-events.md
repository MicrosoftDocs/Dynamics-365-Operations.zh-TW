---
title: 倉庫應用程式事件
description: 本主題說明倉庫應用程式事件處理，用於將倉庫應用程式事件訊息作為批次作業的一部分進行處理。
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8c92bf179006d668f8673e9abc3419a10e644184
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449973"
---
# <a name="warehouse-app-event-processing"></a>倉庫應用程式事件處理

[!include [banner](../includes/banner.md)]

在 Supply Chain Management 中執行的批次作業可以使用佇列中的資料來處理由 Warehouse Management 行動應用程式發出的事件，以便根據需要對訊號事件做出反應。 此功能會將相關事件新增到佇列中，以回應工作人員使用該應用程式執行的某些類型的動作。 例如當使用 *從倉庫應用程式建立和處理轉移單* 功能時，如果系統在執行 **處理倉庫應用程式事件** 批次作業，將在後端建立和更新轉移單標題和行。

## <a name="turn-the-process-warehouse-app-events-feature-on-or-off"></a>打開或關閉處理倉庫應用程式事件功能

從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。 管理員可以透過搜尋位在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區中的 *處理倉庫應用程式事件* 功能開啟這項功能。

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>設定批次作業以處理倉庫應用程式事件

### <a name="process-warehouse-app-events"></a>處理倉庫應用程式事件

設定排程的批次作業來處理倉庫應用程式事件以建立和更新轉移單和行。

1. 依序前往 **倉庫管理 \> 定期任務 \> 處理倉庫應用程式事件**。
1. 處理倉庫應用程式事件對話方塊隨之打開。 展開 **在背景執行** FastTab 上，並將 **批次處理** 設為 **是**。
1. 在 **背景執行** FastTab 上，選取 **重複執行**。
1. **定義重複執行** 對話方塊隨之打開。 根據您的業務需要設定執行排程。
1. 選擇 **確定** 返回 **處理倉庫應用程式事件** 對話方塊。
1. 選取 **處理倉庫應用程式事件** 對話方塊中的 **確定**，將批次工作新增到批次佇列。

## <a name="query-warehouse-app-events"></a>查詢倉庫應用程式事件

您可以查看 Warehouse Management 行動應用程式產生的事件佇列和事件訊息，方法是依序前往 **倉庫管理 \> 查詢和報告 \> 行動裝置記錄 \> 倉庫應用程式事件**。

## <a name="the-standard-event-queue-process"></a>標準事件佇列流程

倉庫應用程式事件佇列通常將與以下描述的流程一起使用：

1. 事件隨事件訊息一起新增到佇列中。 新訊息最初的事件狀態為 **等待**，這代表 **處理倉庫應用程式事件** 批次作業不會接收並處理此訊息。
1. 一旦消息狀態更新為 **已佇列**，**處理倉庫應用程式** 事件批次作業將會接收並處理事件。
1. 批次作業會根據要求的流程是否可行，將事件狀態更新為 **已完成** 或 **失敗**。
1. 當所有相關事件訊息都是 **已完成** 時，該事件將從佇列中刪除。

 有關詳細範例，請參閱[透過倉庫應用程式流程建立轉移單](create-transfer-order-from-warehouse-app.md)。

## <a name="handle-event-errors"></a>處理事件錯誤

作為倉庫事件處理的一部分，要求的訊息活動可能未從批次作業接收流程。 在這種情況下，事件訊息將變更為 **失敗**。 您可以使用 **批次記錄** 資訊以了解原因並採取必要措施糾正任何問題。

有關詳細範例，請參閱[透過倉庫應用程式建立轉移單](create-transfer-order-from-warehouse-app.md)。

若要重設失敗的倉庫應用程式事件訊息：

1. 前往 **倉庫管理 \> 查詢和報告 \> 行動裝置記錄 \> 倉庫應用程式事件**。
1. 在 **倉庫應用程式事件訊息** FastTab，尋找並選取在 **事件狀態** 資料行中顯示 **失敗** 的相關事件。
1. 在 **倉庫應用程式事件訊息** 工具列選擇 **重設**。
1. 繼續工作，直到所有相關訊息都已重設。

您也可以透過使用 **倉庫應用程式事件訊息** 工具列上的 **刪除** 選項刪除 **失敗** 事件訊息。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]