---
title: 工資單職位工作
description: 本主題提供 Dynamics 365 Human Resources 裡工資單職位工作實體的細節和範例查詢。
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 349479d9e77861b54d879bcfd93f7af0e38cff95
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452589"
---
# <a name="payroll-position-job"></a>工資單職位工作


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 工資單職位工作實體。

### <a name="description"></a>描述

本實體針對預設固定薪酬計劃提供職位和工作之間的關係。

實際名稱：mshr_payrollpositionjobentity。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **職位 ID**</br>mshr_positionid</br>*字串* | 唯讀 | 職位識別碼。 |
| **生效日期**</br>mshr_validto</br>*日期時間位移* | 唯讀 | 職位和工作關係生效的日期。 |
| **失效日期**</br>mshr_validto</br>*日期時間位移* | 唯讀 | 職位和工作關係失效的日期。 |
| **職務識別碼**</br>mshr_jobid</br>*字串* | 唯讀 | 工作識別碼。 |
| **主要領域**</br>mshr_primaryfield</br>*字串* | 系統產生的 | 主要領域。 |
| **工資單職位工作實體 ID**</br>mshr_payrollpositionjobentityid</br>*Guid* | 系統產生的。 | 系統產生的全域唯一識別碼 (GUID) 值用來辨別唯一的工作。 |

## <a name="relations"></a>關係

| 屬性值 | 相關實體 | 瀏覽屬性 | 集合物件類型 |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | 不適用 |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

## <a name="example-query"></a>範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**回應**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
