---
title: 移動平均後援成本序列
description: 本主題提供與 Microsoft Dynamics 365 Supply Chain Management 中移動平均計算後援成本序列相關的資訊。
author: AndersGirke
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: d91b3b4b8d49e59aa03d62f4dd101b5a1ec18c41
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448089"
---
# <a name="moving-average-fallback-cost-sequence"></a>移動平均後援成本序列

[!include [banner](../includes/banner.md)]

計算庫存成本的一種方法就是使用 _移動平均_。 每個庫存項目最多可以與三個成本值相關聯：

- **最後發貨**–在庫存變為負數之前指派的最後一個發貨成本
- **使用中成本**–在成本計算版本中啟用的最後成本
- **項目價格** – 為已發佈產品指定的成本

為了決定在移動平均計算中應使用這些成本值中的哪一個，系統使用 _後援成本序列_ 來建立值的偏好順序。 如果偏好的成本值不可用，系統會使用下一個偏好值，依此類推。

在舊版本的 Microsoft Dynamics 365 Supply Chain Management 中，系統使用固定的後援成本序列 (_最後發貨 – 使用中成本 – 項目價格_)。 在 10.0.11 版本中，這個序列仍然是預設序列。 但是，您也可以開啟一項功能，讓您在三個可用的後援成本序列中選擇。 此功能對於經常使用負數庫存值的組織特別有用。

若要讓後援成本序列的選擇器可供使用，您 (或管理員) 必須使用 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)開啟名為 _移動平均後援成本序列_ 的功能。

若要為移動平均計算選取後援成本順序，請執行以下步驟。

1. 開啟 **參數** 頁面。
2. 在 **庫存會計** 索引標籤的 **移動平均** 區段中，將 **後援成本序列** 欄位設定為以下其中一個值：

    - **最後發貨 – 使用中成本 – 項目價格** – 此序列是預設序列。 如果 _移動平均後援成本序列_ 功能未開啟，則會使用同一個序列。
    - **使用中成本 – 最後發貨**
    - **使用中成本 – 項目價格** – 如果組織使用的業務流程其庫存經常為負數，同時交易量很高，組織可能會遇到效能問題。 此設定可以幫助緩解這些效能問題。

![庫存會計參數。](media/inventory-accounting-parameters.png "庫存會計參數")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]