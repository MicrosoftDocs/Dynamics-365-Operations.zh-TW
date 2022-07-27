---
title: 透過倉儲管理相關工作進行庫存異動
description: 移動庫存時，您可以決定允許哪些倉庫工作人員移動保留的庫存。
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d996886a90037f288e839c54c8c9d932cabb21f19f2aef1552ca82b192c96a51
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446847"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>透過倉儲管理相關工作進行庫存異動

[!include [banner](../includes/banner.md)]

移動庫存時，您可以決定允許哪些倉庫工作人員移動保留的庫存。 您可以因此彈性管理受管制的倉庫，禁止工作人員為已建立的揀料工作選擇新的揀料地點。 這項功能還允許倉庫主管決定經驗不足的工作人員能執行哪些作業。

在這類情況下，彈性管理倉庫工作人員的日常作業能帶來很大助益：

## <a name="scenario-1"></a>情況 1

某家公司有個相對較小的收貨區，其中堆滿了待收起的棧板和箱子。 由於預計當天會送來大量貨物，因此收貨員決定將一些棧板移動到次要入庫暫存區來清理收貨區。

## <a name="scenario-2"></a>情況 2

一位經驗豐富的倉庫工作人員發現可以將倉庫品項集中存放到一個位置，而不是將分開存放到附近的三個位置，但每個位置的存放數量很少。 工作人員希望將每個位置的品項移到同一位置和同一牌照來合併數量。

## <a name="scenario-3"></a>情況 3

棧板放置於某個暫存位置等待裝運，例如 BAYDOOR01 附近的 STAGE01。 然而，由於計劃改變，貨車預定到達 BAYDOOR04。 裝運員發現這一點後，需要確保卡車不必等候從 STAGE01 裝載。 裝運員決定將運送的品項從 STAGE01 移至更接近新目的地的 STAGE04。

### <a name="current-limitations"></a>目前限制

您可以移動的保留作業僅限於銷售訂單、轉移訂單發出、轉移訂單接收、訂購單和補貨作業。

為了避免拆分工作明細，您無法移動品項。 這代表，如果您有一項位於位置 Loc1 的 100 件品項 A 的工作明細，您將無法僅將 30 件品項 A 從該處移到另一個位置。 這將導致現有工作明細分成 30 和 70 項，因為現在位置不同。

如果是暫存情況，將貨物移動來源或目的地的牌照設為工單目標 LP，就只會移動整個 LP，因此不會拆分目標 LP。

目前僅支援臨時移動。 這代表您無法透過移動範本行動裝置選單項目來移動保留庫存。

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>為個別工作人員設定保留庫存移動權限

針對允許移動保留庫存的工作人員，在 **倉庫管理 \> 設定 \> 工作人員** 下選取 **允許移動與工作相關的庫存**。  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
