---
title: 工作免責狀態
description: 本主題說明 Dynamics 365 Human Resources 工作免責狀態選項集合。
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
ms.openlocfilehash: 29d3c4fd37a219b520172c6866c5fec488c698f7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452085"
---
# <a name="job-exempt-status"></a>工作免責狀態


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 工作免責狀態選項集合。

實際名稱：cdm_jobexemptstatus

本列舉項目指明 ELSA 工作免責狀態值選項集合。 這已由既有的 cdm_jobexemptstatus 選項集合提供。

| 值 | 標籤 | 描述 |
| --- | --- | --- |
| 200000000 | 責任制 | 根據 FLSA 指南，此項工作已制訂免責狀態。 |
| 200000001 | 非免責 | 根據 FLSA 指南，此項工作已制訂非免責狀態。 |
| 200000002 | 不適用 | FLSA 狀態指南不適用此項工作。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
