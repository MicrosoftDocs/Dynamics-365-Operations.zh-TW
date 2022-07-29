---
title: 無法在 Power Apps 管理中心建立環境
description: 本主題說明如果管理員無法在 Microsoft Power Apps 管理中心建立環境時的作法。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 937b372fa95c8076666aed14c2b34b12e8029c4d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452385"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>無法在 Power Apps 管理中心建立環境


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**問題**

- 租使用者/環境管理員無法在 Microsoft Power Apps 管理中心建立環境。
- 使用者沒有獲得建立環境的授權。

**解決方案**

請確定租使用者管理員已經指派有效的 Power Apps P2 授權給建立環境的使用者。 下列 Microsoft Dynamics 服務計劃提供建立環境的權限：

| 整體產品庫存單位 (SKU)       | Power Apps P2 服務計劃  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Dynamics 365 Power Apps |
| Microsoft Dynamics 365 計劃 Enterprise Edition | Dynamics 365 Power Apps |

請注意，各種 Microsoft Office SKU 也提供權利，加上單機板 Power Apps 計劃 2 SKU。 重點是這些 SKU 其中一個必須存在。

1. 請前往 [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments)。
2. 按照[提供人力資源](/dynamics365/unified-operations/talent/provisioning-talent)的說明建立環境。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
