---
title: 波次執行通知
description: 本主題說明波次執行通知並介紹設定方式。
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: af3983db1a96116a88914411a26f1ac5d4857ae9
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449970"
---
# <a name="wave-execution-notifications"></a>波次執行通知

[!include [banner](../includes/banner.md)]

*波次執行通知* 功能使用業務事件和動作中心來提供與波次執行相關的通知。 它可讓您指定產生通知的事件類型、產生通知的倉庫以及接收通知的使用者。

**顯示訊息** 按鈕位在導覽列右側 (鐘形符號)，表示動作中心訊息何時提供給目前的使用者。 使用者可以選擇 **顯示訊息** 按鈕開啟動作中心並檢閱訊息。

業務流程執行時將發生商務活動。 業務流程由工作組成。 在業務流程中，參與其中的使用者將執行業務動作來完成這些工作。 商務活動提供了一種機制，讓外部系統可以接收來自財務和營運應用程式的通知。 如此一來，系統可以執行業務動作以回應商務活動。 如需相關資訊，請參閱[商務活動概觀](../../fin-ops-core/dev-itpro/business-events/home-page.md)。

## <a name="turn-the-wave-execution-notifications-feature-on-or-off"></a>打開或關閉波次執行通知功能

從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。 管理員可以透過搜尋 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區中的 *波次執行通知* 功能來開啟或關閉此功能。

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>案例：將波次批次執行通知傳送到動作中心

此案例顯示了透過動作中心將有關波次批次執行錯誤通知傳送給特定角色的端到端流程。

### <a name="make-demo-data-available"></a>設定示範資料為可用

若要操作此方案的內容，您必須安裝示範資料，並且必須選取 **USMF** 法律實體。

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>確保在批次模式下執行波次

1. 前往 **倉庫管理 \> 設定 \> 倉庫管理參數**。
1. 在 **波次處理** FastTab 上，將 **批次處理波次** 設為 *是*。

> [!NOTE]
> 如果要停用波批執行通知，請將 **停用波次處理批次通知** 選項設為 *是*。

### <a name="configure-a-wave-notification-policy"></a>設定波次通知原則

波次通知原則定義傳送的通知類型和收到通知的使用者。

1. 移至 **倉庫管理 \> 設定 \> 波次 \> 波次通知援則**。
1. 建立具有以下設定的記錄：

    - **波次通知原則：***24BatchError*
    - **描述：***倉庫 24 波次批次錯誤*
    - **傳送通知：***僅錯誤*
    - **目標角色：***系統管理員*

        > [!NOTE]
        > 由於此案例使用示範資料，因此為了簡單起見，選擇 *系統管理員* 角色。 因此，由於您以系統管理員使用者身份登入，因此您將收到通知。 但實際上，您通常應該選擇更具體的角色 (例如 *倉庫經理*) 來通知波次批次執行錯誤。

1. 在動作窗格上，選擇 **儲存**。

### <a name="configure-a-wave-template"></a>設定波次範本

波次範本讓您能將波次方法的特定執行個體連結到相應的波次標籤範本。

1. 前往 **倉庫管理 \> 設定 \> 波次 \> 波次範本**。
1. 在清單窗格中，將 **波次範本類型** 欄位設定為 *裝運*，然後為倉庫 24 選擇 *24 裝運預設* 波次範本。
1. 在 **一般** FastTab，將 **波次通知原則** 欄位設定為 *24BatchError*。

### <a name="configure-a-work-template"></a>設定工作範本

在波次執行期間使用工作範本來產生工作。 對於這種情況，波次執行應該觸發錯誤。 透過將工作範本查詢設定為使用不存在的倉庫，您將確保波次執行失敗並因此傳送通知。

1. 前往 **倉庫管理 \> 設定 \> 工作 \> 工作範本**。
1. 在清單窗格中，將 **工作範本類型** 欄位設定為 *銷售訂單*，然後為倉庫 24 選擇 *24 SO 階段* 工作範本。
1. 在動作窗格上，選擇 **編輯查詢**。
1. 在查詢編輯器對話方塊中，在 **範圍** 索引標籤上，編輯以下行 (或新增行，如果不存在)：

    - **表格：** *臨時工作交易*
    - **衍生資料表：** *臨時工作交易*
    - **欄位：***倉庫*
    - **條件：** 將值從 *24* 變更為 *錯誤*。

1. 選取 **確定**，然後確認變更。

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>建立銷售訂單並將其發佈到倉庫

1. 前往 **銷售和行銷 \> 銷售訂單 \> 所有銷售訂單**。
1. 建立具有以下設定的銷售訂單：

    - **客戶帳戶：***US-001*
    - **倉庫：***24*

1. 在 **銷售訂單明細** FastTab 上，新增具有以下設定的銷售訂單行：

    - **品項編號：***A0001*
    - **數量：***10*

    > [!NOTE]
    > 這些品項和數量只是範例。 指定的倉庫必須包含足夠的庫存。

1. 在 **銷售訂單行** FastTab 上仍是選擇新行時，在工具列上選擇 **庫存 \> 預留**。
1. 在 **保留** 頁面，於動作窗格選擇 **保留批號**。 然後關閉頁面。
1. 在動作窗格上，於 **倉庫** 索引標籤，選擇 **發佈到倉庫**。

### <a name="notifications-from-wave-batch-job-execution"></a>來自波次批次作業執行的通知

根據業務事件的設定，您最終將收到有關波次執行失敗的通知。 動作中心訊息將類似於以下範例，並將包含失敗波次的連結。

> **波次執行期間發生錯誤**  
> 執行波次 USMF-000000001 時發生錯誤。  
> 最新訊息：沒有為波次 USMF-000000001 建立任何工作。
>
> **狀態**  
> 使用中
>
> 打開波次詳細資料

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
