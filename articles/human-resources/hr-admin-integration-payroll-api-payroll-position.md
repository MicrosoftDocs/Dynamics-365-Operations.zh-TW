---
title: 工資單職位詳細資料
description: 本主題提供 Dynamics 365 Human Resources 裡工資單職位實體的細節和範例查詢。
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
ms.openlocfilehash: 2bbb234d2f51391ea65e3d6153d6cee250f3c6dc
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452586"
---
# <a name="payroll-position"></a>工資單職位


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 工資單職位實體。

實際名稱：mshr_payrollpositionentity。

### <a name="description"></a>描述

本實體提供預訂員工職位相關資訊。

實際名稱：mshr_payrollpositionentity。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **職位 ID**</br>mshr_positionid</br>*字串* | 唯讀 | 職位識別碼。 |
| **付款週期識別碼**</br>mshr_paycycleid</br>*字串* | 唯讀 | 在職位上定義的付款週期。 |
| **年度標準時數**</br>annualregularhours</br>*十進位* | 唯讀 | 職位上定義的年度標準工作時數。 |
| **由法人實體支付**</br>paidbylegalentity</br>*字串* | 唯讀 | 在職位上定義負責核發支付款項的法人實體。 |
| **失效日期**</br>validto</br>*日期時間位移* | 唯讀 | 職位細節的失效日期。 |
| **生效日期**</br>validfrom</br>*日期時間位移* | 唯讀 | 職位細節的生效日期。 |
| **主要領域**</br>mshr_primaryfield</br>*字串* | 系統產生的 | 主要領域。 |
| **工資單職位細節實體識別碼**</br>payrollpositiondetailsentityid</br>*Guid* | 必要</br>系統產生的。 | 系統產生的全域唯一識別碼 (GUID) 值用來辨別唯一的職位。 |

## <a name="relations"></a>關係

| 屬性值 | 相關實體 | 瀏覽屬性 | 集合物件類型 |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | 不適用 |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | 不適用 |

## <a name="example-query"></a>範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**回應**

```json
{
    "mshr_positionid": "000276",
    "mshr_paycycleid": "w",
    "mshr_annualregularhours": 3000,
    "mshr_paidbylegalentity": "USMF",
    "mshr_validfrom": "2021-03-14T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_primaryfield": "000276 | 3/14/2021",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
