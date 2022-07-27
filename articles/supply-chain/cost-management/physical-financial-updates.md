---
title: 實體與財務更新
description: 本主題概述哪些交易類型會增加或減少庫存數量。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c7b354a7524a6e96da8e2a9eeca0d4f21b9fb0a6d515620ab3fe446425af17c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446826"
---
# <a name="physical-and-financial-updates"></a>實體與財務更新

[!include [banner](../includes/banner.md)]

本主題概述哪些交易類型會增加或減少庫存數量。 

可在 Dynamics 365 Supply Chain Management 中對庫存交易進行實體更新與財務更新。 某些類型的實體和財務交易會增加庫存數量，而其他類型的交易會減少數量。

## <a name="physical-increases"></a>實體增加
過帳實體交易後，交易記錄的狀態為 **已收到**。 以下交易會視為實體增加：

-   採購訂單收據
-   銷售訂單裝箱單退回
-   將生產訂單報告為完成
-   生產訂單揀料單上的副產品

## <a name="financial-increases"></a>財務增加
財務收款交易過帳時，增加數量的交易記錄狀態為 **已購買**。 以下交易會視為財務增加：

-   廠商發票
-   退貨的銷售訂單發票
-   生產訂單成本核算
-   正數量庫存日記帳，如變動、損益、盤點、物料清單和轉移

## <a name="transactions-that-increase-quantity"></a>增加數量的交易
增加數量的交易會按移動平均成本價過帳。 計算的移動平均成本價格是以追蹤其財務的每個庫存維度的每個交易成本為基礎。 如需移動平均成本價的相關資訊，請參閱[移動平均成本價](running-average-cost-price.md)。

## <a name="transactions-that-decrease-quantity"></a>減少數量的交易
當過帳減少數量的交易時，會使用計算後的移動平均成本價，無論與該庫存關聯的庫存模型如何。 減少數量的交易在過帳之前不得標記至另一個交易。 如果實體現有庫存變為負數，則會使用在 **品項** 頁面上為品項定義的庫存成本。 

> [!NOTE]
> 如果啟用了多地點功能，則在 **預設訂單設定** 頁面上此成本將會改成為地點定義的庫存成本。

## <a name="physical-issues-vs-financial-issues"></a>實體發貨與財務發貨
過帳實體發貨交易後，交易記錄的狀態為 **已扣除**。 以下交易會視為實體發貨：

-   生產訂單揀料單日記帳
-   銷售訂單裝箱單
-   採購訂單裝箱單退回

過帳財務交易後，交易記錄的狀態為 **已售出**。 以下交易會視為財務發貨：

-   結束生產訂單
-   銷售訂單發票
-   廠商發票退回
-   負數量庫存日記帳，如變動、損益、盤點、物料清單和轉移

減少數量的交易會按移動平均成本價過帳。 因此，需要庫存結轉程序，才能根據指派給每個品項的庫存模型，將發貨交易結算到收貨交易。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]