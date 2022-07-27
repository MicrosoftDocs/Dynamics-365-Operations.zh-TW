---
title: 裝運資訊設定
description: 本主題描述如何為 [到岸成本] 模組設定裝運資訊。
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 86350acfd056be2b43fc856e3b76b1632989a804
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449241"
---
# <a name="shipping-information-setup"></a>裝運資訊設定

[!include [banner](../../includes/banner.md)]

本主題描述如何為 **到岸成本** 模組設定裝運資訊。

## <a name="description-of-goods"></a><a name="description-of-goods"></a>貨物描述

貨物描述有助於識別航程、裝運集裝箱或貨物帳頁以及其中的貨物。 您可以在裝運集裝箱標題或帳頁標題上選擇貨物描述。

若要使用商品描述，請移至 **到岸成本 \> 裝運資訊設定 \> 貨物描述**。 您可以在那裡檢視、開啟、建立和刪除貨物描述的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 貨物描述 | 輸入將使用此描述的貨物類型的唯一識別碼名稱/編號。 |
| 描述 | 輸入此類別中的貨物類型的描述。 |

## <a name="vessels"></a><a name="vessels"></a>船舶

船舶是航運公司或代理機構使用的船隻或船舶的唯一名稱。 建立航程時，必須始終為其選擇或輸入船舶。 如果您經常使用相同的船舶，那麼您可以為每個船舶建立船舶記錄來更快、更輕鬆地建立新航程，從而允許使用者從清單中選擇船舶，而不必手動輸入每個船舶的名稱或編號。

若要使用船舶，請移至 **到岸成本 \> 裝運資訊設定\>船舶**。 在那裡，您可以檢視、開啟、建立和刪除船舶的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 船舶 | 輸入將用於在航程中運輸貨物的船舶的唯一識別碼名稱/編號。 |
| 描述 | 輸入船舶的描述。 通常，此描述會確定船舶名稱和裝運公司/代理機構。 |
| 交貨模式 | 選擇船舶使用的交付方式 (例如 _空運_、_海運_ 或 _火車_)。 |

## <a name="exporters"></a>出口商

每個出口商記錄標識廠商或出口商，可以將其定義為航程的廠商。 出口商可以與航程相關聯並用於報告。

若要使用出口商，請移至 **到岸成本 \> 裝運資訊設定 \> 出口商**。 您可以在那裡檢視、開啟、建立和刪除出口商的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 出口商 | 輸入在航程中運輸貨物出口商的唯一識別碼名稱/編號。 |
| 描述 | 輸入出口商的描述。 通常，此描述會確定裝運公司/代理機構的完整名稱。 |

## <a name="commodity-codes"></a>商品代碼

您將使用商品代碼來幫助海關識別和計算航程中貨物的關稅稅率。 您可以在 **已發佈產品** 頁面選擇商品代碼。

若要使用商品代碼，請移至 **到岸成本 \> 裝運資訊設定 \> 商品代碼**。 您可以在那裡檢視、開啟、建立和刪除商品代碼的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 商品代碼 | 輸入此類商品的唯一代碼。 |
| 描述 | 輸入商品類型的描述。 |

## <a name="customs-description"></a>海關描述

海關描述有助於識別用於海關目的的貨物。 您可以在 **已發佈產品** 頁面或訂購單行選擇海關描述。

若要使用海關描述，請移至 **到岸成本 \> 裝運資訊設定 \> 海關描述**。 您可以在那裡檢視、開啟、建立和刪除海關描述的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 海關描述 | 輸入此類海關描述的唯一代碼。 通常，此代碼將是海關主管機關為貨物描述和定性值提供的官方描述。 |
| 描述 | 輸入海關分類的描述。 |
