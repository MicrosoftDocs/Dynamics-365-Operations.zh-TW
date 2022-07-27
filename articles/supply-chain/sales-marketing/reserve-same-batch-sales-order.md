---
title: 為銷售訂單保留相同批次
description: 本文說明如何設定產品以對照單一庫存批次保留庫存。
author: Henrikan
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d4f3ee5d99648155e663c9ad0849b0b9ae3f80e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448923"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>為銷售訂單保留相同批次

[!include [banner](../includes/banner.md)]

本文說明如何設定產品以對照單一庫存批次保留庫存。

相同批次保留可讓您針對單一庫存批次為銷售訂單細項保留庫存。 例如，訂購壁紙的客戶可以要求從相同批次為整個訂單供貨，以避免各捲壁紙不一致。 要將產品設定為使用相同批次保留，以下設定必須在您指派給產品的物料模型群組、追蹤維度群組和儲存維度群組中處於使用中狀態：

- **物料模型群組** – 物料模型群組必須為庫存原則選擇 **保留** 欄位群組中的 **相同批次選擇** 和 **合併要求** 欄位。
- **追蹤維度群組** – 追蹤維度群組必須為批次編號選擇 **依維度劃分的覆蓋範圍計劃** 欄位。
- **儲存維度群組** – 儲存維度群組必須為 **站點** 和 **倉庫** 選擇 **依維度劃分的覆蓋範圍計劃** 欄位。

如果在為相同批次選擇設定的銷售訂單細項上的產品保留庫存，則系統會嘗試保留單一庫存批次中訂購的數量。 還會考慮任何特定的批次屬性要求。 如果無法從單一批次中填滿數量，則將顯示 **相同批次保留衝突** 頁面。 此頁面描述了這些問題以及為繼續保留而採取的措施。 以下情況可能會阻止保留批次：

- 批次處置代碼將銷售的 **封鎖保留** 標記為 **已封鎖**。
- 根據到期日期和任何適用的客戶可銷售天數，該批次已到期。 如果物料的物料模型群組受先到期先出 (FEFO) 日期控制，並且選擇最佳使用日期作為挑選準則，則仍可考慮保留該物料。
- 根據到期日和最佳期限和任何客戶可銷售天數，該批次的保存期限餘天數不足。

對於與啟用了 **使用倉庫管理程序** 的儲存維度群組關聯的物料，您可以使用批次編號庫存維度在庫位維度之上定義的保留階層保留特定的批次編號。 這種類型的預留階層也稱為 *Batch-above \[location\]* 保留階層。 銷售和轉移單細項的 **批次保留** 頁面還可讓您根據可用的批次編號選擇和保留多個細項。 有關使用批次編號維度在庫位之下的保留階層 (*Batch-below \[location\]*) 作業方法的詳細資訊，請參閱[靈活的倉庫級維度保留原則](../warehousing/flexible-warehouse-level-dimension-reservation.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
