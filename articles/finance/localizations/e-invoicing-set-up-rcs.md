---
title: 設定 Regulatory Configuration Service (RCS)
description: 本主題說明如何設定 Regulatory Configuration Service (RCS)。
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 33aab6f0a482ce3d90a7e9828015a8e7bebb7827
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451728"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>設定 Regulatory Configuration Service (RCS)

[!include [banner](../includes/banner.md)]

本主題說明如何設定 Regulatory Configuration Service (RCS)。

## <a name="turn-on-globalization-features"></a>開啟 Globalization 功能

1. 登入您的 RCS 帳戶。
2. 請選取 **功能管理** 圖格。
3. 請在 **功能管理** 工作區，在清單中選取 **全球功能**，然後選取 **立即啟用**。

**全球化功能** 工作區的圖格現在應該出現在主 RCS 儀表板上。

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>為與電子開票的 RCS 整合設定參數

1. 在 **全球化功能** 工作區的 **相關設定** 區段中，選擇 **電子報表參數**。
2. 在 **電子開票** 索引標籤的 **服務端點 URI** 欄位，為您的 Microsoft Azure 地理位置輸入適當的服務端點，如下表所示。

    | 資料中心 Azure 地理位置 | 服務端點 URI |
    |----------------------------|----------------------|
    | 美國              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | 歐洲                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | 英國             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | 亞洲                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | 日本                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. 確認 **應用程式識別碼** 欄位設定為 **0cdb527f-a8d1-4bf8-9436-b352c68682b2**。 此值是固定值。 確保僅輸入了全域唯一識別碼 (GUID)，並且該值不包含任何其他符號，例如空格、逗號、句點或引號。
4. 在 **LCS 環境識別碼** 欄位，輸入 Microsoft Dynamics Lifecycle Services (LCS) 環境的識別碼。 此值是對您將用於電子開票服務的 Finance 或 Supply Chain Management 環境的參考。 要取得您的識別碼，請登入 [LCS](https://lcs.dynamics.com/)，打開您的專案，然後在 **管理環境** 索引標籤的 **環境詳細資料** 區段，查看 **環境識別碼** 欄位。

    > [!IMPORTANT]
    > 如果電子開票增益集安裝在 LCS 中的多個 Finance 或 Supply Chain Management 環境中，請一律使用最近安裝的環境的環境識別碼。 如果您決定在新環境中安裝增益集，設定並使用電子發票功能後，將 RCS 中的 **LCS 環境識別碼** 欄位更新為最新值。

5. 請選取 **儲存**，然後關閉此頁。

## <a name="configuration-providers"></a>設定提供者

您可以使用設定提供者來區分電子開票流程中使用的電子報表 (ER) 設定的負責人和負責人全球化功能。 對於 Microsoft 提供並在全域存放庫中發佈的所有全球化功能，設定提供者設定為 **Microsoft** (`http://microsoft.com`)。

您只能調整屬於活動設定提供者的 ER 設定和全球化功能。 您可以使用這些設定和功能作為範本來建立屬於活動設定提供者的設定和功能，以便您可以調整它們。

首先，建立設定提供者。 然後將其中一個設定為使用中。 你不能將 **Microsoft** 設定提供者設定為使用中。

### <a name="create-a-configuration-provider"></a>建立設定提供者

1. 在 **電子報表** 工作區的 **相關連結** 區段，選擇 **設定提供者**。
2. 選取 **新增**。
3. 在 **名稱** 欄位中，輸入設定提供者的唯一名稱。
4. 在 **網址** 欄位中，輸入設定提供者的唯一 URL。
5. 請選取 **儲存**，然後關閉此頁。

### <a name="select-a-configuration-provider-as-active"></a>將設定提供者選取為使用中

1. 在設定提供者清單中，選擇要設定為使用中的設定提供者。
2. 選取 **設定為使用中**。

## <a name="import-er-configurations-from-the-global-repository"></a>從全域存放庫匯入 ER 設定

1. 在 **電子報表** 工作區的 **相關連結** 區段，選擇 **設定提供者**。
2. 在設定提供者清單中，選取 **Microsoft**，然後選取 **存放庫**。
3. 選擇 **全域**，然後在動作窗格上選擇 **開啟**。
4. 匯入以下 ER 模型：

    - **客戶發票內容模型**
    - **發票模型**
    - **會計文件** (對於巴西案例，如果需要)
    - **回應訊息模型**

5. 如果 **發票模型對應** 沒有自動匯入，則請匯入。
6. 關閉頁面。
