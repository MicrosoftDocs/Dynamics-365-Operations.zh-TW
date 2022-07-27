---
title: 監控和管理 IoT 智慧
description: 本主題介紹如何監控和管理 IoT 智慧。
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
ms.openlocfilehash: 8fbd750aa4a316f5e04f3c8622d0847ad9318360
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449463"
---
# <a name="monitor-and-manage-iot-intelligence"></a>監控和管理 IoT 智慧

[!include [banner](../../includes/banner.md)]

本主題介紹如何監控和管理 IoT 智慧。

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>在 Microsoft Dynamics 365 Supply Chain Management 監控案例

您可以從多個位置監控 IoT 智慧處理作業：

+ **模組 \> 生產控制 \> 查詢和報告 \> IoT 智慧 \> 通知** – 檢視未解決的通知清單。
+ **模組 \> 生產控制 \> 查詢和報告 \> IoT 智慧 \> 已關閉通知** – 檢視已解決或關閉的通知。
+ **模組 \> 生產控制 \> 查詢和報告 \> IoT 智慧 \> 計量金鑰** – 檢視 **資源狀態** 時間序列圖表的計量金鑰。
+ **模組 \> 生產控制 \> 製造執行 \> 資源狀態** – 使用 **設定** 對話方塊追蹤特定計量。 如果案例偵測到例外狀況，通知會顯示例外狀況的詳細資訊。
+ **工作區 \> 生產車間管理 \> 通知** – 檢視未解決的通知清單。

## <a name="modify-a-running-iot-intelligence-scenario"></a>修改正在執行的 IoT 智慧案例

案例執行時，您可以進行以下變更：

+ 新增新的感應器結構描述定義。
+ 選擇新的訊號資料值。
+ 取消選擇現有訊號資料值。
+ 新增和對應新的訊號資料值。
+ 更新閾值。

案例執行時，禁止進行以下變更：

+ 刪除或修改已啟用案例當前使用的任何結構描述定義。
+ 變更已啟用案例的選定結構描述路徑。

## <a name="simulation-options"></a>模擬選項

您可以模擬工廠機器訊號。 詳細資訊請參閱下列主題：

+ [將 IoT DevKit AZ3166 連接到 Azure IoT 中樞](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [將 Raspberry Pi 線上模擬器連接到 Azure IoT 中樞 (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [設備模擬解決方案加速器概述](/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]