---
title: 工資單固定薪酬計劃
description: 本主題提供 Dynamics 365 Human Resources 裡工資單固定薪酬計畫實體細節和範例查詢。
author: jcart
ms.date: 08/25/2021
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
ms.openlocfilehash: 14829f18fb5e3adde83e265cd6e70b60e1ff03ac
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452520"
---
# <a name="payroll-fixed-compensation-plan"></a>工資單固定薪酬計劃


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 工資單固定薪酬計畫實體。

### <a name="description"></a>描述

本實體提供按員工預設職位指派的固定薪酬計劃。

實際名稱：mshr_payrollfixedcompensationplanentity。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **計劃識別碼**</br>mshr_planid</br>*字串* | 唯讀 | 指定薪酬計劃。  |
| **個人編號**</br>mshr_personnelnumber</br>*字串* | 唯讀 | 員工的唯一個人編號。 |
| **支付費率**</br>mshr_payrate</br>*十進位* | 唯讀 | 固定薪酬計劃定義的支付費率。 |
| **職位 ID**</br>mshr_positionid</br>*字串* | 唯讀 | 與員工和固定薪酬計劃註冊有關聯的職位識別碼。 |
| **生效日期**</br>mshr_validfrom</br>*日期時間位移* |  唯讀 | 員工固定薪酬的生效日期。  |
| **失效日期**</br>mshr_validto</br>*日期時間位移* | 唯讀 | 員工固定薪酬的失效日期。 |
| **支薪頻率**</br>mshr_payfrequency</br>*字串* | 唯讀 | 預訂支付費率的[薪酬支付頻率](hr-admin-integration-payroll-api-compensation-pay-frequency.md)識別碼。 |
| **貨幣**</br>mshr_currency</br>*字串* | 唯讀 | 為固定薪酬計劃定義的貨幣。 |
| **工資單固定薪酬計劃實體**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | 系統產生的 | 系統產生用來辨別唯一薪酬計畫的 GUID 值。 |

## <a name="relations"></a>關係

|屬性值 | 相關實體 | 瀏覽屬性 | 集合物件類型 |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**回應**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
