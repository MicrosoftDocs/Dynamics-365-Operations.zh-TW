---
title: 招募要求狀態
description: 本主題說明 Dynamics 365 Human Resources 招募要求狀態選項集合。
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
ms.openlocfilehash: d845179077fc2e04dfb3bd05eaa70b0a2a016121
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452307"
---
# <a name="recruiting-request-status"></a>招募要求狀態


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 招募要求狀態選項集合。

實際名稱：mshr_hcmrecruitingrequeststatus

此列舉項目提供 RecruitingRequest 狀態值的選項集合。

| 值 | 標籤 | 描述 |
| --- | --- | --- |
| 200000000 | 草稿 | 這項要求目前只是草稿，尚未準備好進行積極招募。 |
| 200000001 | 檢閱中 | 這項要求已經提交，正被傳送給工作流程核准。 僅用於工作流程啟用時。 |
| 200000002 | 擱置中 | 這項要求正等待工作流程的動作。 僅用於工作流程啟用時。 |
| 200000003 | 已取消 | 這項要求已經取消。 僅用於工作流程啟用時。 |
| 200000004 | 拒絕 | 這項要求已遭到拒絕。 僅用於工作流程啟用時。 |
| 200000005 | 使用中 | 任何工作流程皆已完成並獲得核准，而這項要求已準備好進行積極招募。 |
| 200000006 | 已結案 | 招聘要求已經關閉。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
