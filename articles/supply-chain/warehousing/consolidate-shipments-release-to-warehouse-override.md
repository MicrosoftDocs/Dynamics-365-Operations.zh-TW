---
title: 貨件整合原則被覆寫時整合貨件
description: 本主題介紹一個案例，其中一或多個銷售明細必須從發佈到倉庫頁面手動發佈到倉庫，並且必須在發佈之前覆寫系統定義的貨件整合原則。
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 606f370277b67a65612d81916f4fcc93ca47224e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448698"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden"></a>貨件整合原則被覆寫時整合貨件

[!include [banner](../includes/banner.md)]

本主題介紹一個案例，其中一或多個銷售明細必須從 **發佈到倉庫** 頁面手動發佈到倉庫，並且必須在發佈之前覆寫系統定義的貨件整合原則。 例如，如果通常不與未結貨件合併的訂單，必須與未結貨件整合，則可能需要覆寫貨件整合原則。

在此案例中，您將建立一組銷售訂單，然後在將訂單發佈到倉庫之前覆寫預設的貨件整合原則。

## <a name="make-demo-data-available"></a>設定示範資料為可用

本主題中的案例引用了為 Microsoft Dynamics 365 Supply Chain Management提供的標準示範資料中所包含的值和記錄 。 如果您想在練習時使用此處提供的值，請務必在安裝了示範資料的環境中工作，並在您開始之前將法律實體設定為 **USMF**。

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>設定貨件合併原則和產品篩選條件

此處描述的案例假設您已經開啟了該功能，並在[配置貨件整合原則](configure-shipment-consolidation-policies.md)中完成練習，並建立了其中描述的原則和其他記錄。 在繼續此案例之前，請務必完成這些練習。

## <a name="create-the-sales-orders-for-this-scenario"></a>為此案例建立銷售訂單

1. 前往 **應收帳款 \> 訂單 \> 所有銷售訂單**，並建立三個具有以下設定的相同銷售訂單：

    - **客戶帳戶：** *US-002*

1. 新增具有以下設定的訂單行：

    - **品項編號：** *A0001* (沒有指派 **代碼 4** 篩選條件的項目)
    - **數量：** *1.00*

1. 選擇 **庫存 \> 保留**，然後於動作窗格選擇 **保留批號** 以保留訂單明細。

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>從發佈到倉庫頁面發佈銷售訂單

按照以下步驟，在向倉庫發佈期間覆寫貨件整合原則。

1. 前往 **倉庫管理 \> 發佈到倉庫 \> 發佈到倉庫**。
1. 在上窗格中，選擇您為此案例建立的第一個銷售訂單。
1. 選擇 **新增** 將明細加入向倉庫的發佈。 請注意，下窗格套用 *預設* 貨件整合原則。
1. 在下窗格中，選擇 **選擇新的貨件整合原則**。
1. 選擇允許與相同原則的其他未結貨件整合的原則。 例如，選擇 *CustomerOrderNo* 原則。
1. 選擇 **發佈到倉庫**。
1. 選擇您為此案例建立的第二個和第三個銷售訂單。
1. 選擇 **新增** 將明細加入向倉庫的發佈。 請注意，下窗格套用 *預設* 原則。
1. 選擇第二個明細，然後在 **選擇新的貨件整合原則** 欄位，選擇 *CustomerOrderNo* 原則。
1. 為兩個明細選擇 **發佈到倉庫**。

## <a name="verify-the-shipments"></a>驗證貨件

兩批貨件應該已經建立：

- 第一個貨件包含兩個明細，是使用 *CustomerOrderNo* 貨件整合原則。
- 第二個貨件包含一個明細，是使用 *預設* 貨件整合原則。

請按照以下步驟查看已建立的貨件。

1. 前往 **倉庫管理 \> 運送 \> 所有運送**。
1. 尋找並選擇所需的貨件。
1. 在 **貨件整合原則** 欄位，查看建立貨件時使用的整合原則。

## <a name="additional-resources"></a>其他資源

- [貨件整合原則](about-shipment-consolidation-policies.md)
- [配置貨件整合原則](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]