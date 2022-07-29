---
title: 休假要求
description: 本主題提供 Dynamics 365 Human Resources 裡休假要求實體細節和範例查詢。
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f14c143a59553786fe85284c128cec80905810b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452382"
---
# <a name="leave-request"></a>休假要求


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 休假要求實體。

### <a name="description"></a>描述

本實體提供休假要求的資訊。

實際名稱：mshr_essleaverequestentity。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **要求識別碼**</br>mshr_requestid</br>*字串* | 唯讀 | 要求識別碼。 |
| **休假類型識別碼**</br>mshr_leavetypeid</br>*字串* | 唯讀 | 休假類型識別碼。 |
| **日期**</br>mshr_leavedate</br>*日期時間位移* | 唯讀 | 休假要求的日期。 |
| **金額**</br>mshr_amount</br>*十進位* | 唯讀 | 休假要求金額。 |
| **半天型**</br>mshr_halfdaydefinition</br>*mshr_LeaveHalfDayDefinition 選項集合* | 唯讀 | 半天假類型。 |
| **註解**</br>mshr_comment</br>*字串* | 唯讀 | 要求留言。 |
| **狀態**</br>mshr_status</br>*mshr_status 選項集合* | 唯讀 | 要求的狀態。 |
| **日期**</br>mshr_requestdate</br>*日期時間位移* | 唯讀 | 要求的日期。 |
| **個人編號**</br>mshr_personnelnumber</br>*字串* | 唯讀 | 員工的唯一個人編號。 |
| **原因代碼識別碼**</br>mshr_reasoncodeid</br>*字串* | 唯讀 | 原因代碼識別碼。 |
| **資料區識別碼**</br>mshr_dataareaid</br>*字串* | 唯讀 | 指定法人實體 (公司)。 |
| **主要領域**</br>mshr_primaryfield</br>*GUID* | 唯讀</br>系統產生的 | |
| **休假類型實體**</br>mshr_essleaverequestentityid</br>*GUID* | 系統產生的 | 系統產生用來辨別唯一休假要求的 GUID 值。 |

## <a name="example-query"></a>範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**回應**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
