---
title: 招募要求職位狀態
description: 本主題說 Dynamics 365 Human Resources 招募要求職位狀態選項集合。
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6a63a95201583fa7b215e221a03715e56b55c11a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452073"
---
# <a name="recruiting-request-position-status"></a>招募要求職位狀態


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說 Dynamics 365 Human Resources 招募要求職位狀態選項集合。

實際名稱：mshr_hcmrecruitingrequestpositionstatus

此列舉項目為 RecruitingRequestPosition 實體中，每個招募要請求職位狀態值提供選項集合。

| 值 | 標籤 | 描述 |
| --- | --- | --- |
| 200000000 | 開啟 | 招募要求中的職位已開放招募。 這並不指出該職位目前沒有有效的指派職位。 招募時此職位可能已有員工任職。 它指出該職位只有在招募要求情況下才會開放招募。 |
| 200000001 | 已徵滿 | 已有背景工作角色獲選指派到該職位。 |
| 200000002 | 已取消 | 此職位的招募要求已經取消。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
