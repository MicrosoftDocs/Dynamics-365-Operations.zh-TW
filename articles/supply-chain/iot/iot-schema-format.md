---
title: IoT 中樞訊息的結構描述格式
description: 本主題說明應如何設計可在 IoT 智慧中使用的訊息結構描述。
author: tonyafehr
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b24a6e14182baa91299abad0da2987b2dca92601
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449454"
---
# <a name="schema-formats-for-iot-hub-messages"></a>IoT 中樞訊息的結構描述格式

[!include [banner](../../includes/banner.md)]

本主題說明應如何設計可在 IoT 智慧中使用的訊息結構描述。

## <a name="message-requirements"></a>訊息要求

以下規則適用於 IoT 智慧中的訊息監控：

+ 訊息結構描述必須採用 JavaScript 物件標記法 (JSON) 格式。
+ 一個 UNIX **時間戳記** 屬性，其中值以毫秒 (ms) 表示，必須存在於 Microsoft Azure IoT 中樞訊息之中。
+ 只有訊息消息包含案例設定定義的所有屬性時，才會追蹤訊息。 例如，如果您定義 **識別碼**、**時間戳記** 和 **值** 屬性，將監控以下訊息。

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    此訊息不受監控，因為 **值** 屬性遺失。

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ IoT 智慧會忽略未在案例設定中定義的訊息屬性。 例如，如果您定義 **識別碼**、**時間戳記** 和 **值** 屬性，IoT 智慧將監控所有以下訊息。

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ IoT 智慧會以無訊息方式忽略與案例設定條件不符的訊息。
+ 您可以定義和使用多種類型的訊息結構描述。
+ 並非必須定義每種類型的訊息結構描述。 僅必須定義將用於 IoT 智慧案例的結構描述。

## <a name="id-value-pair-schema"></a>識別碼值配對結構描述

識別碼值配對是 IoT 智慧訊息結構描述的常見模式。 使用識別碼值配對，您可以確保您的訊息結構描述在所有案例中都是相同的。 例如，這裡有一條 **設備停機時間** 或 **生產延遲** 案例的訊息。

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

這裡有一條 **產品品質** 案例的訊息。

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

前面的兩條訊息都包含 **識別碼** 和 **值** 屬性。 **識別碼** 值可以在案例設定期間於 **訊號資料值** 資料表之中對應。 對於 **設備停機時間** 案例，您將對應 **IoTInt.Machine1225.PartOut** 值。 對於 **產品品質** 案例，您將對應 **IoTInt.Machine1225.Temperature** 值。

更多資訊請參閱 [Azure IoT 中樞文件](/azure/iot-hub/)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]