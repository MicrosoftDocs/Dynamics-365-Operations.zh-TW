---
title: IoT 智慧首頁
description: 本主題提供 IoT 智慧相關資訊的連結。
author: tonyafehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: intro-internal
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b6c179052cdb9d1ca808d9cba089163bde0d5d5
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449466"
---
# <a name="iot-intelligence-home-page"></a>IoT 智慧首頁

[!include [banner](../../includes/banner.md)]

> [!IMPORTANT]
> 此功能目前僅在以下國家/地區可用：
>
> - US (美國)
> - EU (歐盟)
> - AU (澳洲)
> - CA (加拿大)
> - UK (英國)

IoT 智慧是 Microsoft Dynamics 365 Supply Chain Management 的增益集。 其中將物聯網 (IoT) 訊號與 Supply Chain Management 中的資料整合，以產生可操作的深入解析。

IoT 智慧支援以下情境：

+ **生產延遲** – 此情境將實際週期與規劃週期進行比較。 生產未按時程進行時，Supply Chain Management 會通知您，以便您進行干預盡可能提高營運效率並避免訂單延遲。
+ **設備停機** – 此情境將測量的連續運作時間與使用者定義的參數進行比較。 超過中斷閾值時，Supply Chain Management 會通知您，以便您可以採取行動，例如重新安排生產工單或建立維護工單。
+ **產品品質** – 此情境將感應器讀數 (例如濕度和溫度) 與使用者定義的品質指標進行比較。 出現偏差時，Supply Chain Management 會通知您，以便您進行干預以維持品質標準並盡可能減少浪費。

下圖顯示了 Azure IoT 中樞、IoT 智慧和 Supply Chain Management 的互動。

![IoT 中樞、IoT 智慧和 Supply Chain Management。](media/iot_intelligence.png)

## <a name="setup"></a>設定

您無需編寫任何程式碼即可設定 IoT 智慧。 以下是基本步驟。

1. [設定 Azure 資源](iot-azure-setup.md) – 建立一個 IoT 中樞、一個 Redis 快取，以及一個可從 Supply Chain Management 存取的金鑰保存庫。
2. [IoT 中樞的訊息結構描述格式](iot-schema-format.md) – 設定您的裝置以將訊息傳送到 IoT 中樞，並定義 JavaScript 物件標記法 (JSON) 訊息格式。
3. 在功能管理中，啟用 IoT 智慧功能旗標。 
4. [在 Microsoft Dynamics Lifecycle Services (LCS) 安裝 IoT 智慧增益集](iot-lcs-setup.md) – 在 LCS 安裝增益集，並設定 Azure 秘密。
5. [設定指標](iot-metrics-setup.md) – 在 Supply Chain Management 中設定指標。
6. [案例設定](iot-scenario-setup.md) – 在 Supply Chain Management 中設定情境。

## <a name="tracking-and-maintenance"></a>追蹤和維護

+ [在 Dynamics 365 Supply Chain Management 監控情境](iot-management.md#monitor-scenarios)
+ [停用案例](iot-scenario-setup.md#disable-a-scenario)
+ [解除安裝增益集](iot-lcs-setup.md#uninstall-addin)
+ [修改正在執行的 IoT 智慧案例](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [模擬選項](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]