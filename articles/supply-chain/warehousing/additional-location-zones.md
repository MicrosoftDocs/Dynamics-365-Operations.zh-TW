---
title: 其他位置區域
description: 本主題概述已新增到 Microsoft Dynamics 365 Supply Chain Management 的新位置區域。
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: dd9e97cabe5e3d3bdc261a7280930b73eb8e1419
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450039"
---
# <a name="additional-location-zones"></a>其他位置區域

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management 中提供了三個新的區域欄位。 倉庫經理可以使用它們來定義其他倉庫組織或佈局。 可以手動設定新區域欄位，也可以使用 **位置設定** 精靈。 它們可用於任何使用到「位置」資料表的查詢或篩選。

使用區域欄位不需要額外的設定。

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>打開或關閉其他位置區域功能

從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。 系統管理員可以在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區中搜尋 *其他位置區域* 功能，以開啟或關閉這項功能。

## <a name="use-location-zones"></a>使用位置區域

1. 前往 **Warehouse Management\>設定\>倉庫\>位置設定精靈**。
2. 設定以下值：

    - 請在 **倉庫** 欄位，選取 _62_。
    - 在 **區域識別碼** 欄位，選擇 _樓層_。
    - 在 **其他區域1** 欄位，選取 _揀貨區1_。
    - 在 **其他區域2** 欄位，選取 _揀貨區1_。
    - 在 **位置設定檔識別碼** 欄位，選取 _樓層_。

3. 選取 **樓層** 明細。
4. 在 **起始號碼** 欄位，輸入 _1_。 在 **終止號碼** 欄位，輸入 _3_。
5. 選取 **通道** 明細。
6. 在 **起始號碼** 欄位，輸入 _1_。 在 **終止號碼** 欄位，輸入 _5_。
7. 選取 **建立**。
8. 您會收到訊息，表示已新增新位置。 選取 **顯示訊息** 按鈕查看訊息。
9. 移至 **倉庫管理 \> 設定 \> 倉庫 \> 位置**。 新位置出現在列表中，並且所有區域欄位都可用（即現有區域欄位和新的其他區域欄位）。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]