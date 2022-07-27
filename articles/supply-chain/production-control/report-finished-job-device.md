---
title: 從工作卡裝置報告為完成
description: 本主題介紹如何設定系統，以便工作卡裝置的使用者可以將成品從生產訂單報告為完工入庫。
author: johanhoffmann
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 67fa97c938f091c23a41ddd5aaf34a32c5a13c93
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449925"
---
# <a name="report-as-finished-from-the-job-card-device"></a>從工作卡裝置報告為完成

[!include [banner](../includes/banner.md)]

工作人員使用工作卡裝置的 **報告進度** 頁面以報告生產作業已完成的數量。 本主題介紹如何設定各個選項，來建立工作人員使用此頁面報告完工入庫的方法以及接下來要執行的事項。 選項包括：

- 控制是否以及如何將報告為完工入庫的數量加入庫存中。
- 控制在報告完工入庫時是否以及如何產生和套用批號。
- 控制在報告完工入庫時是否以及如何產生和套用序號。
- 控制是否以及如何向牌照報告完工入庫。

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>控制是否將報告為完工入庫的數量加入庫存中

若要控制是否以及如何將最後一項作業中報告為完工入庫的數量加入庫存中，請按照下列步驟操作。

1. 移至 **產品控制 \> 設定 \> 製造執行 \> 生產訂單預設值**。
1. 在 **報告為完成** 索引標籤，將 **線上更新已完成的報告** 欄位設定為下列其中一個值：

    - **否** – 在最後一項作業報告數量時，不會將數量加入庫存中。 生產訂單的狀態永遠不會改變。
    - **狀態 + 數量** – 生產訂單的狀態將更改為 *報告為完成*，並且數量將報告為完工入庫。
    - **數量** – 數量將報告為完工入庫，但生產訂單的狀態永遠不會改變。
    - **狀態** – 只有生產訂單的狀態改變。 在最後一項作業報告數量時，不會將數量加入庫存中。

> [!NOTE]
> 如果報告為完工入庫的作業未定義為最後一項作業，則不會在庫存中追蹤數量。 但是，這些數量可用於查看進度。 它們也可以包含在規則中，協助控制工作人員是否可以在達到前一項目作業報告數量的定義閾值之前開始下一項目作業。 您可以在 **生產訂單預設值** 頁面的 **數量驗證** 索引標籤中定義這些規則。

有關如何使用 **生產訂單預設值** 頁面的詳細資訊，請參閱[製造執行中的生產參數](production-parameters-manufacturing-execution.md)。

## <a name="report-batch-controlled-items-as-finished"></a>將批次控制品項報告為完工入庫

工作卡裝置支援三種報告批次品項的案例。 這些案例既適用於進階倉庫流程支援的品項，也適用於進階倉庫流程不支援的品項。

- **手動指派的批號** - 工作人員輸入自訂批號。 此批號可能來自系統未知的外部來源。
- **預定義批號** - 在生產訂單發佈到工作卡裝置之前，工作人員在系統自動產生的批號清單中選擇一個批號。
- **固定批號** - 工作人員不輸入或選擇批號。 反而，系統會在生產訂單發佈前自動為其指派批號。


### <a name="enable-the-feature-on-your-system"></a>在系統中啟用此功能

要使您的工作卡裝置在報告完工入庫期間接受批號，您必須使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)啟用以下功能 (按此順序)：

1. 工作卡裝置中報告進度對話方塊的改良式使用者體驗
1. 啟用可在從工作卡裝置報告為完工入庫時輸入批號和序列號

### <a name="configure-products-that-require-batch-number-reporting"></a>設定需要報告批號的產品

若要使產品支援任何可用的批次控制案例，請按照下列步驟操作：

1. 請前往 **產品資訊管理 \> 產品 \> 已發佈的產品**。
1. 選取要設定的產品。
1. 在 **管理庫存** FastTab 中，在 **批號群組** 欄位，選擇為支援您的案例而設定的追蹤編號群組。

> [!NOTE]
> 預設情況下，如果批號未指派給批次控制產品，工作卡裝置將在報告完工入庫期間提供手動輸入批號。

以下部分介紹如何設定追蹤編號群組，以支援報告批次品項的三種案例。

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>設定讓工作人員可以手動指派批號的追蹤編號群組

若要允許手動指派批號，請按照以下步驟設定追蹤編號群組。

1. 移至 **庫存管理 \> 設定 \> 維度 \> 追踪編號群組**。
1. 建立或選擇要設定的追踪編號群組。
1. 在 **一般** FastTab 中，將 **手動** 選項設定為 **是**。

    ![手動批號的追踪編號群組。](media/tracking-number-group-manual.png "手動批號的追踪編號群組")

1. 根據需要設定其他值，然後選擇此追踪編號群組作為要使用此案例之已發佈產品的批號群組。

使用此案例時，工作卡裝置內 **報告進度** 頁面提供的 **批號** 欄位是一個文字方塊，工作人員可以在其中輸入任何值。

![含有手動批號欄位的報告進度頁面。](media/job-card-device-batch-manual.png "含有手動批號欄位的報告進度頁面")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>設定提供預定義批號清單的追蹤編號群組

若要提供預定義批號清單，請按照以下步驟設定追蹤編號群組。

1. 移至 **庫存管理 \> 設定 > 維度 \> 追踪編號群組**。
1. 建立或選擇要設定的追踪編號群組。
1. 在 **一般** FastTab 上，將 **僅限庫存交易** 選項設為 **是**。
1. 使用 **按數量** 欄位根據您輸入的值按數量分割批號。 例如，您有一個十件產品的生產訂單，並且 **按數量** 欄位設定為 *2*。 在這種情況下，將在生產訂單建立時為其指派五個批號。

    ![預定義批號的追踪編號群組。](media/tracking-number-group-predefined.png "預定義批號的追踪編號群組")

1. 根據需要設定其他值，然後選擇此追踪編號群組作為要使用此案例之已發佈產品的批號群組。

使用此案例時，工作卡裝置內 **報告進度** 頁面提供的 **批號** 欄位是一個下拉式清單，工作人員必須在其中選擇預定義值。

![含有預定義批號清單的報告進度頁面。](media/job-card-device-batch-predefined.png "含有預定義批號清單的報告進度頁面")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>設定自動指派批號的追蹤編號群組

如果應在沒有工作人員輸入的情況下自動指派批號，請按照以下步驟設定追蹤編號群組。

1. 移至 **庫存管理 \> 設定 \> 維度 \> 追踪編號群組**。
1. 建立或選擇要設定的追踪編號群組。
1. 在 **一般** FastTab 上，將 **僅限庫存交易** 選項設為 **否**。
1. 將 **手動** 選項設置為 **否**。

    ![固定批號的追踪編號群組。](media/tracking-number-group-fixed.png "固定批號的追踪編號群組")

1. 根據需要設定其他值，然後選擇此追踪編號群組作為要使用此案例之已發佈產品的批號群組。

使用此案例時，工作卡裝置內 **報告進度** 頁面提供的 **批號** 欄位將顯示一個值，但工作人員不能進行編輯。

![含有固定批號的報告進度頁面。](media/job-card-device-batch-fixed.png "含有固定批號的報告進度頁面")

## <a name="report-serial-controlled-items-as-finished"></a>將序號控制品項報告為完工入庫

工作卡裝置支援三種案例來報告序號控制品項。 這些案例既適用於進階倉庫流程支援的品項，也適用於進階倉庫流程不支援的品項。

- **手動指派的序號** - 工作人員輸入自訂序號。 此序號可能來自系統未知的外部來源。
- **預定義序號** - 在生產訂單發佈到工作卡裝置之前，工作人員在系統自動產生的序號清單中選擇一個序號。
- **固定序號** - 工作人員不輸入或選擇序號。 反而，系統會在生產訂單發佈前自動為其指派序號。

### <a name="enable-the-feature-on-your-system"></a>在系統中啟用此功能

要使您的工作卡裝置在報告完工入庫期間接受序號，您必須使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)啟用以下功能 (按此順序)：

1. 工作卡裝置中報告進度對話方塊的改良式使用者體驗
1. 啟用可在從工作卡裝置報告為完工入庫時輸入批號和序列號

### <a name="configure-products-that-require-serial-number-reporting"></a>設定需要報告序號的產品

若要使產品支援任何可用的序號控制案例，請按照下列步驟操作：

若要啟用每個案例，請按照以下步驟操作。

1. 請前往 **產品資訊管理 \> 產品 \> 已發佈的產品**。
1. 選取要設定的產品。
1. 在 **管理庫存** FastTab 中，在 **序號群組** 欄位，選擇為支援您的案例而設定的追蹤編號群組。

> [!NOTE]
> 預設情況下，如果序號未指派給序號控制產品，工作卡裝置將在報告完工入庫期間提供手動輸入序號。

以下部分介紹如何設定追蹤編號群組，以支援報告序號控制品項的三種案例。

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-serial-number"></a>設定讓工作人員可以手動指派序號的追蹤編號群組

若要允許手動指派序號，請按照以下步驟設定追蹤編號群組。

1. 移至 **庫存管理 \> 設定 \> 維度 \> 追踪編號群組**。
1. 建立或選擇要設定的追踪編號群組。
1. 在 **一般** FastTab 中，將 **手動** 選項設定為 **是**。

    ![追蹤編號群組頁面、序號。](media/tracking-number-group-manual-serial.png "追蹤編號群組頁面、序號")

1. 根據需要設定其他值，然後選擇此追踪編號群組作為要使用此案例之已發佈產品的序號群組。

使用此案例時，工作卡裝置內 **報告進度** 頁面提供的 **序號** 欄位是一個文字方塊，工作人員可以在其中輸入任何序號。 輸入值後，它會加到序號清單中。 在此清單中，工作人員可以執行以下操作：

- 若要將序號標記為已報廢，請選擇對應列的 **報廢** 按鈕。 系統將提示工作人員提供 **錯誤原因**。
- 若要刪除序號，請選擇對應列的 **刪除** 按鈕。

![含有手動序號欄位的報告進度頁面。](media/job-card-device-serial-manual.png "含有手動序號欄位的報告進度頁面")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-serial-numbers"></a>設定提供預定義序號清單的追蹤編號群組

若要提供預定義序號清單，請按照以下步驟設定追蹤編號群組。

1. 移至 **庫存管理 \> 設定 \> 維度 \> 追踪編號群組**。
1. 建立或選擇要設定的追踪編號群組。
1. 在 **一般** FastTab 上，將 **僅限庫存交易** 選項設為 **是**。
1. 使用 **按數量** 欄位以按數量一分割序號。

    ![預定義序號的追踪編號群組。](media/tracking-number-group-predefined-sn.png "預定義序號的追踪編號群組")

1. 根據需要設定其他值，然後選擇此追踪編號群組作為要使用此案例之已發佈產品的序號群組。

使用此案例時，工作卡裝置內 **報告進度** 頁面提供的 **序號** 欄位是一個下拉式清單，工作人員必須在其中選擇預定義值。

![含有預定義序號清單的報告進度頁面。](media/job-card-device-serial-predefined.png "含有預定義序號清單的報告進度頁面")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-serial-numbers"></a>設定自動指派序號的追蹤編號群組

如果應在沒有工作人員輸入的情況下自動指派序號，請按照以下步驟設定追蹤編號群組。

1. 移至 **庫存管理 \> 設定 \> 維度 \> 追踪編號群組**。
1. 建立或選擇要設定的追踪編號群組。
1. 在 **一般** FastTab 上，將 **僅限庫存交易** 選項設為 **否**。
1. 將 **手動** 選項設置為 **否**。

    ![固定序號的追踪編號群組。](media/tracking-number-group-fixed-sn.png "固定序號的追踪編號群組")

1. 根據需要設定其他值，然後選擇此追踪編號群組作為要使用此案例之已發佈產品的序號群組。

使用此案例時，工作卡裝置內 **報告進度** 頁面提供的 **序號** 欄位將顯示一個值，但工作人員不能進行編輯。 此案例僅在為數量為一件的序號控制品項建立生產訂單時有用。

![含有固定序號的報告進度頁面。](media/job-card-device-serial-fixed.png "含有固定序號的報告進度頁面")

## <a name="report-as-finished-to-a-license-plate"></a>報告為已完工入庫到牌照

進階倉庫流程可以使用牌照維度來追蹤為此目的設定的倉庫位置庫存。 在這種情況下，工作人員報告完工入庫數量時需要牌照號碼。

### <a name="enable-license-plate-reporting-and-label-printing"></a>啟用牌照報告和標籤列印

若要使用本節中介紹的功能，您必須使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)啟用以下功能 (按此順序)：

1. *報告為已完成的牌照新增到工作卡裝置*<br>(從 Supply Chain Management 版本 10.0.21 開始，此功能為預設開啟。 從 Supply Chain Management 版本 10.0.25 開始，此功能為必要。)
1. *在工作卡裝置中報告為完成時啟用自動生成牌照號碼*<br>(從 Supply Chain Management 版本 10.0.25 開始，此功能為必要。)
1. *從工作卡裝置列印標籤*<br>(從 Supply Chain Management 版本 10.0.25 開始，此功能為必要。)

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>設定報告為已完工入庫到牌照

若要控制工作人員在報告完工入庫數量後是應該重用現有牌照還是產生新牌照，請按照以下步驟操作。

1. 前往 **產品控制 \> 設定 \> 製造執行 \> 設定裝置的作業卡**。
2. 為每個裝置設定以下選項：

    - **產生牌照** – 將此選項設為 **是**，可在每次報告完工入庫產生新牌照。 如果應在每次報告完工入庫使用現有牌照，則設定為 **否**。
    - **列印標籤** – 如果工作人員必須在每次報告完工入庫列印牌照標籤，將此選項設為 **是**。 如果不需要標籤，則設定為 **否**。 

![為裝置頁面設定工作卡。](media/config-job-card-raf.png "為裝置頁面設定工作卡")

> [!NOTE]
> 若要設定標籤，則移至 **Warehouse Management \> 設定 \> 文件路徑 \> 文件路徑**。 如需詳細資訊，請參閱[啟用牌照標籤列印](../warehousing/tasks/license-plate-label-printing.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]