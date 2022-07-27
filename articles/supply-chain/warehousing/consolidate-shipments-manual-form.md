---
title: 使用整合貨件頁面手動整合貨件
description: 本主題介紹一個案例，其中多張訂單發佈到倉庫，之後使用整合貨件頁面進行整合。
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0da98b24b9e0ab1ae19fd353ec226b2e0ab008fe
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448701"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>使用整合貨件頁面手動整合貨件

[!include [banner](../includes/banner.md)]

本主題介紹一個案例，其中多張訂單發佈到倉庫，之後使用 **整合貨件** 頁面進行整合。

## <a name="make-demo-data-available"></a>設定示範資料為可用

本主題中的案例引用了為 Microsoft Dynamics 365 Supply Chain Management提供的標準示範資料中所包含的值和記錄 。 如果您想在練習時使用此處提供的值，請務必在安裝了示範資料的環境中工作，並在您開始之前將法律實體設定為 **USMF**。

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>設定貨件合併原則和產品篩選條件

此處描述的案例假設您已經開啟了該功能，並在[配置貨件整合原則](configure-shipment-consolidation-policies.md)中完成練習，並建立了其中描述的原則和其他記錄。 在繼續此案例之前，請務必完成這些練習。

## <a name="create-the-sales-orders-for-this-scenario"></a>為此案例建立銷售訂單

首先建立您可以使用的銷售訂單集合。 您必須使用按照高級倉庫 (WMS) 流程啟用的倉庫。 除非明確提及不同的倉庫，否則必須為以下各組訂單使用相同的倉庫。

前往 **應收帳款 \> 訂單 \> 所有銷售訂單**，並建立按照以下小節敘述之設定的銷售訂單集合。

### <a name="create-sales-orders-1-and-2"></a>建立銷售訂單 1 和 2

1. 建立具有以下設定的兩個相同的銷售訂單：

    - **客戶帳戶：** *US-007*
    - **集區：** *ShipCons*

1. 新增具有以下設定的訂單行：

    - **品項編號：** *A0001* (沒有指派 **代碼 4** 篩選條件的項目)
    - **數量：** *1.00*

1. 選擇 **庫存 \> 保留**，然後於動作窗格選擇 **保留批號** 以保留訂單明細。

### <a name="create-sales-orders-3-and-4"></a>建立銷售訂單 3 和 4

1. 建立具有以下設定的兩個相同的銷售訂單：

    - **客戶帳戶：** *US-007*
    - **集區：** 將此欄位保留空白。

1. 新增具有以下設定的訂單行：

    - **品項編號：** *A0001* (沒有指派 **代碼 4** 篩選條件的項目)
    - **數量：** *1.00*

1. 選擇 **庫存 \> 保留**，然後於動作窗格選擇 **保留批號** 以保留訂單明細。

## <a name="release-the-orders-to-the-warehouse"></a>將訂單下達到倉庫

按照以下步驟將為此案例建立的各銷售訂單發佈到倉庫。

1. 前往 **應收帳款 \> 訂單 \> 所有銷售訂單**。
1. 尋找並選擇要下達的銷售訂單。
1. 在動作窗格的 **倉庫** 索引標籤上，選擇 **動作 \> 發佈到倉庫** 發佈選定的銷售訂單。
1. 對您為此案例建立的其他所有銷售訂單重複此程序。

## <a name="consolidate-shipments"></a>整合貨件

1. 前往 **倉庫管理 \> 運送 \> 所有運送**。
1. 尋找並選擇在銷售訂單 1 發佈到倉庫時建立的貨件。 (其 **貨件整合原則** 欄位應設為 *訂單集區*。)
1. 在動作窗格上，**運送** 索引標籤中，選擇 **運送 \> 整合貨件**。
1. 驗證建議整合的貨件。 僅應建議整合具有相同原則的一批貨件。
1. 關閉 **貨件整合** 頁面。
1. 尋找並選擇在銷售訂單 3 發佈到倉庫時建立的貨件。 (其 **貨件整合原則** 欄位應設為 *預設*。)
1. 在動作窗格上，**運送** 索引標籤中，選擇 **運送 \> 整合貨件**。
1. 驗證沒有建議整合的貨件。
1. 選擇 **顯示篩選條件**。
1. 在 **篩選條件** 窗格，移除 **訂單編號** 篩選條件，然後選擇 **套用**。
1. 驗證建議整合的貨件。 僅應建議整合具有相同原則的一批貨件。

## <a name="additional-resources"></a>其他資源

- [貨件整合原則](about-shipment-consolidation-policies.md)
- [配置貨件整合原則](configure-shipment-consolidation-policies.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]