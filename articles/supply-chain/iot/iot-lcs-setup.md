---
title: 在 LCS 安裝 IoT 智慧增益集
description: 本主題說明如何在 Microsoft Dynamics Lifecycle Services (LCS) 安裝 IoT 智慧增益集。
author: tonyafehr
ms.date: 07/07/2020
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
ms.openlocfilehash: ebf11b55f1034b9a84dda9ada77c2f1b7f587a58
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449457"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>在 LCS 安裝 IoT 智慧增益集

[!include [banner](../../includes/banner.md)]

本主題說明如何在 Microsoft Dynamics Lifecycle Services (LCS) 安裝 IoT 智慧增益集。 請注意，增益集不能安裝在示範/試用環境中。 在安裝增益集之前，您必須[建立 Azure 資源](iot-azure-setup.md)。

## <a name="set-up-the-lcs-environment"></a>設定 LCS 環境

1. 開啟 LCS，然後前往您的 Microsoft Dynamics 365 Supply Chain Management 環境。
2. 向下捲動至 **環境增益集** 區段。
3. 選擇 **安裝新的增益集**，以顯示已為環境啟用的增益集清單。
4. 在 **選擇要安裝的增益集** 對話方塊選擇 **IoT 智慧**。
5. 在 **設定增益集** 對話方塊提供 IoT 中樞和 Redis 快取的詳細資訊。 您可以在您於[建立 Azure 資源](iot-azure-setup.md)之中建立的金鑰保存庫找到所需的值。

    + **租用戶識別碼** – 在 Azure 入口網站中前往金鑰保存庫，然後在左側功能窗格中選擇 **概述**，並複製 **目錄識別碼** 值。 將該值貼到 **設定增益集** 對話方塊。
    + **IoT 事件中樞相容的端點金鑰保存庫 URI** – 前往金鑰保存庫，然後在左側功能窗格中選擇 **概述**，並複製 **DNS 名稱** 值。 將該值貼到 **設定增益集** 對話方塊。
    + **IoT 事件中樞相容的端點秘密名稱** – 前往金鑰保存庫，然後在左側功能窗格中選擇 **秘密**，並複製儲存 IoT 中樞的事件中樞連接字串的秘密名稱。 將該值貼到 **設定增益集** 對話方塊。
    + **Redis 快取金鑰保存庫 URI** – 前往金鑰保存庫，然後在左側功能窗格中選擇 **概述**，並複製 **DNS 名稱** 值。 將該值貼到 **設定增益集** 對話方塊。
    + **Redis 快取端點秘密名稱** – 前往金鑰保存庫，然後在左側功能窗格中選擇 **秘密**，並複製儲存 Redis 快取的事件中樞連接字串的秘密名稱。 將該值貼到 **設定增益集** 對話方塊。

6. 選擇核取方塊以接受條款和條件。
7. 選擇 **安裝**。
8. 將出現一個訊息方塊，指出「已成功觸發增益集進行安裝」。 選擇 **確定**。

LCS 設定現已完成。 下一步是[設定情境](iot-scenario-setup.md)。

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>解除安裝增益集

1. 在 Supply Chain Management 中[停用情境](iot-scenario-setup.md#disable-a-scenario)。
2. 在 LCS 中，前往您的 Supply Chain Management 環境詳細資訊。
3. 向下捲動至 **環境增益集** 區段。
4. 為 IoT 智慧增益集選擇 **解除安裝**。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]