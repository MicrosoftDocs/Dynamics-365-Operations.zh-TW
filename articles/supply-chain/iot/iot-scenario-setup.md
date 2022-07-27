---
title: IoT 智慧的案例設定
description: 本主題說明如何在 Microsoft Dynamics 365 Supply Chain Management 為 IoT 智慧設定案例。
author: tonyafehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: tfehr
ms.custom: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b8e8c65cebe64f86dcf158668e8a4f5600c158a1
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449460"
---
# <a name="scenario-setup-for-iot-intelligence"></a>IoT 智慧的案例設定

[!include [banner](../../includes/banner.md)]

本主題說明如何在 Microsoft Dynamics 365 Supply Chain Management 為 IoT 智慧設定案例。 在設定案例之前，您必須[設定 Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md)。

在本主題中，您將設定 **設備停機時間** 案例，以便在機器停機時在 Supply Chain Management 中產生通知。 該主題還顯示要如何設定 **產品品質** 案例，以便在項目屬性超出指定範圍時產生通知，以及如何設定 **生產延遲** 案例，以便在生產輸送量低於閾值時產生通知。

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>在 Supply Chain Management 中設定設備停機案例

**設備停機時間** 案例將 **PartOut** 訊號對應至機器警報閾值。 只有在針對機器選取該案例，並且在 Supply Chain Management 設定為 **運作中** 時，才會監控機器。 如果機器上次收到 **PartOut** 的時間超過警報閾值，就會觸發 **機器停機** 通知。 如果機器仍在運行，則 **機器運作** 通知就會在收到下一個 **PartOut** 訊號時觸發。 如果一台機器停機 30 分鐘，就會觸發一個新的 **機器停機** 通知。

**設備停機時間** 案例具有以下相依性：

+ 只有生產訂單在對應的機器上運行時才能觸發警報。
+ 表示對應機器 **PartOut** 的訊號必須傳送到 IoT 中樞，並且必須包含唯一的屬性名稱。
+ 一個 UNIX **時間戳記** 屬性，其中值以毫秒 (ms) 表示，必須存在於 Azure IoT 中樞訊息之中。

若要設定案例，請按照以下步驟操作。

1. 登入 Supply Chain Management。
2. 啟用 IoT 智慧功能旗標。 更多資訊，請參閱[功能管理概觀](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。
3. 設定計量。 如需相關資訊，請參閱[如何設定計量](iot-metrics-setup.md#configure-metrics)。
4. 前往 **生產控制 \> 設定 \> IoT 智慧 \> 案例管理**。
6. 在 **設備停機時間** 圖格選擇 **設定** 以開啟設定精靈。

   精靈的第一頁是 **設備感應器結構描述定義** 頁。 在此頁面上，您的目標是在 Supply Chain Management 中設定結構描述，使其與 IoT 中樞訊息的 JavaScript 物件標記法 (JSON) 格式相符。 可以定義多個訊息結構描述。 詳細資訊請參閱 [IoT 中樞訊息的結構描述格式](iot-schema-format.md)。 在此範例中，訊息承載包含一批具有以下格式的訊息。

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. 在資料表中新增列，並設定以下值：

    1. 設定 **結構描述名稱** 欄位為 **識別碼**。
    2. 設定 **結構描述路徑** 欄位為 **/payload\[\*\]/id**。
    3. 設定 **說明** 欄位為 **訊息識別碼**。

8. 在資料表中新增另一個列，並設定以下值：

    1. 設定 **結構描述名稱** 欄位為 **時間戳記**。
    2. 設定 **結構描述路徑** 欄位為 **/payload\[\*\]/timestamp**。
    3. 設定 **說明** 欄位為 **訊息時間戳記**。

9. 在資料表中新增另一個列，並設定以下值：

    1. 設定 **結構描述名稱** 欄位為 **值**。
    2. 設定 **結構描述路徑** 欄位為 **/payload\[\*\]/value**。
    3. 設定 **說明** 欄位為 **訊息值**。

    > [!NOTE]
    > 您不必定義訊息中的所有屬性。 僅定義您需要的屬性。 在前面的步驟中，您沒有為 **根時間戳記** 建立列。 **根時間戳記** 的路徑將是 **/timestamp**。

10. 選擇 **下一步** 前往 **設備感應器結構描述對應** 頁面。
11. 在 **設備資源識別碼** 列的 **結構描述名稱** 欄位中選擇 **識別碼**。
12. 在 **UTC 時間** 列的 **結構描述名稱** 欄位中選擇 **時間戳記**。
13. 在 **零件產生訊號碼** 列的 **結構描述名稱** 欄位中選擇 **值**。
14. 選擇 **下一步** 前往 **設備資源識別碼設定** 頁面。
15. 按照以下步驟將 IoT 中樞訊息的值對應到 Supply Chain Management 資源：

    1. 在 **訊號資料值** 資料表添加一個新列。 在 **值** 欄位輸入 **IoTInt.Machine1225.PartOut**。 此值來自 IoT 中樞訊息的 JSON **id** 屬性。
    2. 選擇 **儲存**。
    3. 在 **業務記錄對應** 資料表選擇 **新增**。 **業務記錄類型** 欄位的預設值是自動填入的，您不必變更它。
    4. 在 **業務記錄** 欄位，選擇從中發送訊號值的 Supply Chain Management 機器資源。
    5. 選擇 **儲存**。
    6. 重複這些步驟以便為 **Machine1226** 新增新的業務記錄對應。 您可以將多個訊號資料值對應到 Supply Chain Management 中的單個記錄。

16. 使用 **已選擇** 欄以選擇要處理的機器。 您不必定義所有訊號值，也不必選擇所有機器。
17. 選擇 **下一步** 前往 **零件產生訊號設定** 頁面。
18. 在 **訊號資料值** 資料表新增列，並將 **值** 欄位設定為 **真**。 此值來自 IoT 中樞訊息的 JSON **值** 屬性。 您可以根據案例的需要新增任意數量的值。
19. 選擇 **儲存**。
20. 選擇 **下一步** 前往 **設備停機時間閾值** 頁面。 列出的機器是之前對應到訊號值的機器。 在此頁面上，您將定義一個閾值來確定機器是否停機。 例如，如果您將閾值設置為 **10**，如果 10 分鐘沒有從機器收到 **PartOut** 訊號，Supply Chain Management 將會產生通知。
21. 選擇 **下一步** 前往 **啟用案例** 頁面。 設定選項以啟用案例。
22. 選擇 **完成**。

案例設定現已完成。 IoT 智慧將自動開始處理 IoT 中樞訊息。

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>在 Supply Chain Management 中設定產品品質案例

**產品品質** 案例會在項目屬性超出指定範圍時產生通知。 例如，感應器將每個項目的重量發送到 IoT 中樞。 如果項目太重或太輕，則會在 Supply Chain Management 中產生通知。

**產品品質** 案例具有以下相依性：

+ 只有在生產訂單在對應的機器上運行，並生產具有對應批次屬性的產品時，才能觸發警報。
+ 表示批次屬性的訊號必須傳送到 IoT 中樞，並且必須包含唯一的屬性名稱。
+ 一個 UNIX **時間戳記** 屬性，其中值以毫秒 (ms) 表示，必須存在於 IoT 中樞訊息之中。

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>在 Supply Chain Management 中設定生產延遲案例

**生產延遲** 案例會在生產輸送量低於閾值時產生通知。 在這種情況下，會為每個生產的品項傳送 **PartOut** 訊號至 IoT 中樞。 在 Supply Chain Management 中，訂單延遲是根據生產訂單排定運行的時間量、應生產的品項數、作業已運行的時間量，以及接收的 **PartOut** 數計算。 如果作業的 **PartOut** 訊號數低於閾值，就會產生延遲通知。

**生產延遲** 案例具有以下相依性：

+ 只有生產訂單在對應的機器上運行時才能觸發警報。
+ 表示對應機器 **PartOut** 的訊號必須傳送到 Azure IoT 中樞，並且必須包含唯一的屬性名稱。
+ 一個 UNIX **時間戳記** 屬性，其中值以毫秒 (ms) 表示，必須存在於 IoT 中樞訊息之中。

## <a name="disable-a-scenario"></a>停用案例

若要停用案例，請按照以下步驟操作。

1. 在 Supply Chain Management 中，前往 **生產控制 \> 設定 \> IoT 智慧 \> 案例管理**。
2. 在案例的磚上選擇 **設定**。
3. 選擇 **下一步** 前往最後的精靈頁面。
4. 設定選項以停用案例。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]