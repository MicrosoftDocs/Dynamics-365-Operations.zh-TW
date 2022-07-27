---
title: 用於服務的內部資產
description: 本主題介紹如何使用 Microsoft Dynamics 365 Field Service 為客戶資產和內部資產提供服務。
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 8048a99951eea3fbae34e56c1b444c75ad3d199d
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460452"
---
# <a name="in-house-assets-for-servicing"></a>用於服務的內部資產

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Field Service 旨在為客戶資產提供服務。 Dynamics 365 Supply Chain Management 的資產管理旨在維護內部資產。 這兩個應用程式的整合讓您可以使用 Field Service 為客戶資產和內部資產提供服務。 您還可以根據函數位置或階層對資產進行分類，並詳細追蹤服務。

如需相關資訊，請參閱[整合 Dynamics 365 Field Service 和 Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration)。

## <a name="templates"></a>範本

內部資產包括一組在資料交流期間協同工作的核心表對應，如下表所示。

| 財務和營運應用程式 | Customer Engagement 應用程式 | 描述 |
|-----------------------------|-----------------------------------|-------------|
[資產管理資產生命週期模型](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[資產管理資產生命週期狀態](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[資產管理資產類型](mapping-reference.md#124) | msdyn_customerassetcategories | |
[資產管理資產](mapping-reference.md#125) | msdyn_customerassets | |
[資產管理機能位置生命週期模型](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[資產管理機能位置生命週期狀態](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[資產管理機能位置類型](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[資產管理機能位置](mapping-reference.md#136) | msdyn_functionallocations | |
[資產管理製造商](mapping-reference.md#153) | msdyn_manufacturers | |
[資產管理模型](mapping-reference.md#154) | msdyn_models | |
[資產管理保固](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
