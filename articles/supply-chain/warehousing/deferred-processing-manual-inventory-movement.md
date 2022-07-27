---
title: 手動庫存移動的延遲處理
description: 本主題說明如何在 Microsoft Dynamics 365 Supply Chain Management 中使用手動庫存移動延遲處理。
author: Mirzaab
ms.date: 04/27/2021
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: Mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 21dd01448fcf6c2b3ca90a5476fad061bb0f55e4
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449913"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>手動庫存移動的延遲處理

[!include [banner](../includes/banner.md)]

本主題說明如何在 Microsoft Dynamics 365 Supply Chain Management 中使用手動庫存移動延遲處理。

延遲處理可以讓倉庫工作人員繼續進行其他工作，同時在背景處理放置作業。 當伺服器處理時間，遇到偶發的或計劃外的增加時，增加的處理時間可能會影響工作人員的效率，這時延遲處理就非常有用。 *庫存移動* 工作類型，現在已新增至支援此功能的工作類型當中。

背景處理是通過使用[處理倉庫應用程式事件功能](warehouse-app-events.md)達成。

## <a name="turn-on-this-feature-for-your-system"></a>為您的系統啟用此功能

若要使用此功能，請在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 開啟以下功能。 您必須按以下順序打開：

1. *組織範圍內的工作阻塞*<br>(從 Supply Chain Management 版本 10.0.21 開始，此功能為強制性的，因此預設開啟且無法再次關閉。)
1. *處理倉庫應用程式事件*<br>(從 Supply Chain Management 版本 10.0.25 開始，此功能為預設開啟)。
1. *延遲放置作業*
1. *手動庫存移動作業的延遲處理*<br>(從 Supply Chain Management 版本 10.0.25 開始，此功能為強制性的，因此預設開啟且無法再次關閉。)

## <a name="configure-the-work-processing-policies"></a>設定工作處理原則

若要使用延遲處理，您必須設置和使用工作處理原則。 若要延遲放置處理，[延遲處理倉庫工作功能](deferred-put.md)支持以下工作類型：*銷售訂單*、*轉移訂單問題*，和 *補貨*。 *手動庫存移動作業延遲處理* 功能，新增一種新的工作類型：*庫存移動*。

若要設定工作延遲處理原則，請按照以下步驟。

1. 前往 **倉庫管理 \> 設定 \> 工作 \> 工作延遲處理**。
1. 在清單中選擇一個現有原則，或在動作窗格上選擇 **新建**，以建立一個的挑選原則。 每個原則的標題，都有以下欄位：

    - **工作處理原則名稱** – 工作處理原則的名稱。
    - **說明** – 工作處理原則的說明。

1. 在 **處理規則** FastTab 上，設定應用於原則的集合物件規則。 依據您的需求，使用工具列上的按鈕，新增或移除規則。 對於每個規則，設定下列欄位：

    - **工單類型** – 選擇原則適用的工作類型。
    - **作業** – 選擇該原則用於處理的作業。 如果您選擇 **工單類型** 中的 *庫存變動* 欄位，則不必設置此欄位，因為挑選作業和放置作業，都作為單個事件處理。
    - **工作處理方法** – 選擇用於處理工作明細的方法。 如果您選擇 *即時*，該行為類似於沒有使用工作處理原則來處理該明細的行為。 如果您選擇 *延遲*，系統將應用使用批處理框架的延遲處理。
    - **延遲處理閾值** – 如果您將此字段設置為 *0* (零)，則沒有閾值。 在這種情況下，可能的話會使用 *延遲* 處理方法。 如果特定的閾值計算低於閾值，則會使用 *即時* 方法。 否則，可能的話會使用 *延遲* 方法。 對於銷售和轉移相關的工作，閥值計算為正在處理工作與來源載入明細關聯的數量。 對於補充工作，閾值計算為正在補充的工作明細數量。 例如，通過設置閾值，銷售為 *5*，您就可以確保，少於五個來源載入明細的較小工作，不會使用延遲處理，但較大的工作將使用延遲。 閥值只有在 **工作處理方法** 欄位設定為 *延遲* 時才會生效。
    - **延遲處理批次群組** – 指定用於處理的批次群組。 如果您在 **供單類型** 欄位選擇 *庫存變動*，您不必設定該欄位，因為已選擇 **處理倉庫應用事件** 對話框的批次群組。

## <a name="assign-the-work-creation-policy"></a>指派工作建立原則

如需指派工作建立原則的詳細資訊，請參見[倉庫工作的延遲處理](deferred-put.md)。

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>設定批次作業以處理倉庫應用程式事件

若要使用 *人工庫存移動操作的延遲處理* 程序，請設定批次作業的排程。

1. 依序前往 **倉庫管理 \> 定期任務 \> 處理倉庫應用程式事件**。
1. 在 **處理倉庫應用程式事件** 對話框中，**於背景中執行** FastTab 上，將 **批次處理** 選項設定為 *是*。
1. 選擇 **定期**，並設定滿足您業務需求的執行排程。
1. 在每個對話框中，選擇 **確定**。

## <a name="inquire-about-the-warehouse-app-events"></a>查詢關於倉庫應用程式事件

您可以透過前往 **倉庫管理 \> 查詢合報告 \> 行動裝置紀錄 \> 倉庫應用程式事件**，查看倉庫應用程式產生的事件佇列和事件訊息。

第一次建立時。*庫存移動* 事件訊息的狀態為 *已進入佇列*。 此狀態表明 **處理倉庫應用事件** 批處理作業，將獲取事件訊息並進行處理。 當狀態更新為 *已完成* 時，所有相關事件都會從佇列中刪除。

所有的 *庫存變動* 事件類型，會累積在每個事件類型和倉庫下的集合暫存表。

批次作業會根據 **處理倉庫應用事件** 對話框中設定的定期，處理倉庫應用程式事件。 因此，處理完一條訊息之前，您可以通過在 **識別碼** 欄位，查找倉庫識別碼。

訊息的詳細資訊包含移動的詳細資訊 (例如，「從」和「到」位置)。

如需更多相關資訊，請參閱[倉庫應用程式事件處理](warehouse-app-events.md)。

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>設定行動裝置功能表，以跳過延遲處理原則

如何設定行動裝置功能表，以跳過延遲處理策略的詳細資訊，請參閱[倉庫工作的延遲處理](deferred-put.md)。

## <a name="impact-on-closed-work-dates"></a>對非工作日的影響

有關對非工作日影響的詳細信息，請參閱[倉庫工作的延遲處理](deferred-put.md)。

## <a name="additional-resources"></a>其他資源

- [倉庫工作的延遲處理](deferred-put.md)
- [倉庫應用程式事件處理](warehouse-app-events.md)
- [為倉庫工作設定行動裝置](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
