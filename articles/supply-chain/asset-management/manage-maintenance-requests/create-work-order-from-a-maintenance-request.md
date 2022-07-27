---
title: 依據維護要求建立工單
description: 本主題說明如何在資產管理中依據維護要求建立工單。
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1c69ad91e931475dd4c8e5a126190e867bd193f881ad58525c1d2ac8997c972a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446745"
---
# <a name="create-work-orders-from-maintenance-requests"></a>依據維護要求建立工單

[!include [banner](../../includes/banner.md)]

 


建立維護要求後，即可輕鬆將之轉換成工單。 本主題說明最快速的方法來處理維護要求、同時更新多個維護要求，以及同時為多個維護要求建立工單。 在 **作用中維護要求** 或 **我的功能位置維護要求** 頁面上，您也可一次處理一個維護要求，並將其轉換成工單。

> [!NOTE]
> 每個維護要求只能與一個工單建立關聯。 然而，多個維護要求可納入一份工單，即使這些維護要求有不同資產也沒問題。

1. 選擇 **資產管理** \> **一般** \> **維護要求** \> **所有維護要求**。
2. 依據維護要求建立工單前，您必須至少要為此維護要求選擇維護作業類型，以及維護作業類型變體和技術等相關資訊。 在網格檢視中，您可輕鬆更新維護要求資訊。
3. 準備好建立工單時，請選擇維護要求以將其納入。

    - 若您選擇數個維護要求來轉換成一份工單，則必須先設定 **資產** 欄位和 **維護作業類型** 欄位，之後才能建立工單。
    - 若您選擇一個維護要求來轉換成一份工單，只需要先設定 **資產** 欄位，即可建立工單。 然而，建立工單時，您可在 **建立工單** 對話方塊中，選擇維護作業類型 (及相關的維護作業類型變體和技術資訊)。

4. 選擇 **工單**。
5. 在 **建立工單** 對話方塊中，請設定欄位，然後選擇 **確定**。

    訊息列可能會通知您新工單已建立。

    此外，建立維護要求的工單時，若相關的資產包含在保固協議中，訊息欄也會通知您此保固協議。

6. 選擇 **資產管理** \> **一般** \> **工單** \> **所有工單**，然後開啟新的工單。

    ![開啟新的工單。](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]