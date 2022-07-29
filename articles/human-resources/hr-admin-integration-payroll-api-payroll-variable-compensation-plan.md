---
title: 工資單變動薪酬計畫
description: 本主題提供 Dynamics 365 Human Resources 裡工資單變動薪酬計畫實體細節和範例查詢。
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f2f057fb0f492efd08674b3bbeef9f3fec3d7be0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452454"
---
# <a name="payroll-variable-compensation-plan"></a>工資單變動薪酬計畫


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 工資單變動薪酬計畫實體。

### <a name="description"></a>描述

本實體提供按員工預設職位指派的變動薪酬計劃。

實際名稱：mshr_payrollvariablecompensationawardentity。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人編號**</br>mshr_personnelnumber</br>*字串* | 唯讀 | 員工的唯一個人編號。  |
| **獎項日期**</br>mshr_awarddate</br>*日期時間位移* | 唯讀 | 獎項的日期。 |
| **獎項類型**</br>mshr_awardtype</br>*[mshr_HrmCompVarAwardEmplType 選項集合](hr-admin-integration-payroll-api-award-type.md)* | 唯讀 | 針對變動薪酬計劃定義的獎項類型。 |
| **貨幣**</br>mshr_unitcurrencycode</br>*字串* | 唯讀 |為變動薪酬計劃定義的貨幣。   |
| **固定薪酬計劃識別碼**</br>mshr_fixedplanid</br>*字串* | 唯讀 | 充當獎項計算依據的固定薪酬計劃。 |
| **單位值**</br>mshr_awardamount</br>*十進位* | 唯讀 | 單位的值 |
| **流程類型**</br>mshr_processtype</br>*[mshr_hrmCompProcessType 選項集合](hr-admin-integration-payroll-api-process-type.md)* | 唯讀 | 流程類型。 |
| **變動薪酬計畫類型**</br>字串</br>*mshr_typeid* | 唯讀 | 變動薪酬計劃的類型。 |
| **變動薪酬計畫識別碼**</br>字串</br>*mshr_planid* | 唯讀 | 變動薪酬計劃的識別碼。 |
| **單位數量**</br>十進位</br>*mshr_numberofunits* | 唯讀 | 獎項的單位數。 |
| **主要領域**</br>mshr_primaryfield</br>*GUID* | 唯讀</br>系統產生的。 | |
| **工資單變動薪酬計畫實體**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | 系統產生的 | 系統產生用來辨別唯一薪酬計畫的 GUID 值。 |

## <a name="relations"></a>關係 

|屬性值 | 相關實體 | 瀏覽屬性 | 集合物件類型 |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_VariableCompAward |
| _mshr_fk_fixedcomp_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedComp_id | mshr_FK_PayrollFixedCompensationPlanEntity_VariableCompAward |

## <a name="example-query"></a>範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000046'
```

**回應**

```json
{
    "mshr_personnelnumber": "000046",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_unitvalue": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_numberofunits": 1500,
    "mshr_primaryfield": "000046 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000666-0000-0000-daff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a4-0000-0000-0d00-005001000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
