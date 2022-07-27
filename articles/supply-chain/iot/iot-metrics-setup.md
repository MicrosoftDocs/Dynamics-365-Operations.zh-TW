---
title: 為 IoT 智慧設定計量
description: 本主題介紹如何為 IoT 智慧設定計量。
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
ms.openlocfilehash: 85db0211c32ad4e27c3a9a65d2c74c5a39687f9c
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449472"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>為 IoT 智慧設定計量

[!include [banner](../../includes/banner.md)]

## <a name="configure-metrics"></a>設定計量

如果您想在 Microsoft Dynamics 365 Supply Chain Management 查看時間序列圖表，您必須按照以下步驟設定計量。

1. 複製 Redis 快取的連接字串：

    1. 在 Azure 入口網站中前往 Redis 快取。
    2. 前往 **設定** \> **存取金鑰**。
    3. 複製 **主連接字串** 欄位之中的值。

2. 在 Supply Chain Management 中，前往 **生產控制 \> 設定 \> IoT 智慧 \> 案例參數**。
3. 在 **案例參數** 頁面，在 **Redis 計量儲存連接字串** 欄位的 **時間序列** 索引標籤，貼上您之前複製的連接字串。 此步驟使 Azure IoT 中樞的計量能夠在 Supply Chain Management 中視覺化。 您將值貼到欄位中時會顯示為 **\*\*\*\*\*\***。

    > [!NOTE]
    > 您更新 Redis 快取連接字串時，您還必須更新此欄位。

4. 前往 **生產控制 \> 查詢和報告 \> IoT 智慧 \> 計量金鑰**。
5. 在 **計量金鑰** 頁面選擇 **更新**。
6. 在 **更新計量金鑰** 對話方塊，請注意於欄位選取 **在背景執行**。 選擇 **確定**。

檢索 Redis 快取中的所有計量金鑰，並將其新增到 **計量金鑰** 清單。 計量值不會出現，直到您[啟用案例](iot-scenario-setup.md)為止。

## <a name="configure-the-resource-status-time-series"></a>設定資源狀態時間序列

如欲設定 **資源狀態** 時間序列，請按照以下步驟操作。

1. 在 Supply Chain Management 中，前往 **生產控制 \> 製造執行 \> 資源狀態**。
2. 在 **資源狀態** 頁面選擇 **設定**。
2. 在 **設定** 對話方塊的 **資源** 清單中，選擇要監控的項目。
3. 選擇 **編輯** 按鈕用於 **時間序列 1**。
4. 在 **選擇時間序列** 對話方塊中，在格線中選擇一個計量。 (您也可以使用 **更新計量金鑰** 連結以從此對話方塊更新計量金鑰。)
5. 選擇 **確定**，返回 **設定** 對話方塊。
6. 輸入顯示名稱。
7. 在 **顯示資料來源** 欄位選擇時間範圍。
8. 選擇 **確定**。

隨即顯示圖表。

## <a name="delete-a-metric-key"></a>刪除計量金鑰

1. 在 Supply Chain Management 前往 **生產控制 \> 查詢和報告 \> IoT 智慧 \> 計量金鑰**。
2. 在 **計量金鑰** 頁面，選擇要刪除的計量金鑰。
3. 選擇 **刪除**。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]