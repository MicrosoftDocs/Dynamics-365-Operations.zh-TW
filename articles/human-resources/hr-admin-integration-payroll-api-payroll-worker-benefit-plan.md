---
title: 工資單背景工作角色福利計劃
description: 本主題提供 Dynamics 365 Human Resources 裡工資單背景工作角色福利計畫實體細節和範例查詢。
author: marcelbf
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1805f7efaf2efc48d5996776f3aa27d75606886f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452451"
---
# <a name="payroll-worker-benefit-plan"></a>工資單背景工作角色福利計劃


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 工資單背景工作角色計畫實體。

實際名稱：mshr_payrollworkerbenefitplanentities。

### <a name="description"></a>描述

本實體提供有關預訂背景工作角色福利計畫的資訊。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人編號**</br>mshr_personnelnumber</br>*字串* | 唯讀</br>必要 | 員工的唯一個人編號。 |
| **法人實體識別碼**</br>mshr_legalentityID</br>*字串* | 唯讀 | 指定法人實體 (公司)。 |
| **期間識別碼**</br>mshr_periodid</br>*字串* | 唯讀 | 期間的識別碼。 |
| **計劃識別碼**</br>mshr_planid</br>*字串* | 唯讀 | 計畫的識別碼。 |
| **涵蓋範圍選項**</br>mshr_coverageoptionid</br>*字串* | 唯讀 | 涵蓋範圍選項的辨識。 |
| **扣減開始日期**</br>mshr_deductionstartdatetime</br>*日期時間位移* | 唯讀 | 扣減開始日期。 |
| **扣減結束日期**</br>mshr_deductionenddatetime</br>*日期時間位移* | 唯讀 | 扣減結束日期。 |
| **狀態**</br>mshr_status</br>*[福利員工計畫狀態選項集合](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | 唯讀 | 福利計畫狀態。 |
| **生效日期**</br>mshr_validfrom</br>*日期時間位移* | 唯讀 | 此記錄的生效時間。 |
| **失效日期**</br>mshr_validto</br>*日期時間位移* |  唯讀 | 此記錄的到期時間。 |
| **計劃類型識別碼**</br>mshr_plantypeid</br>*字串* | 唯讀 | 計畫類型的識別碼。 |
| **計劃類型碼**</br>mshr_plantypecode</br>*[福利計劃類型涵蓋選項集合](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | 唯讀 | 計畫類型的辨識。 |
| **支付期數**</br>mshr_payperiod</br>*整數* | 唯讀 | 代表福利提供者或僱主支付各筆的支付期數。 本項金額將用來計算員工的年度福利薪資金額。 |
| **員工金額**</br>mshr_amountemployee</br>*十進位* | 唯讀 | 員工金額或百分比。 |
| **雇主金額**</br>mshr_amountemployer</br>*十進位* | 唯讀 | 雇主金額或百分比。 |
| **主要領域**</br>mshr_primaryfield</br>*字串* | 系統產生的 | 主要領域。 |
| **背景工作角色識別碼值** </br>_mshr_fk_worker_id_value</br>*GUID* | 外部索引鍵：mshr_hcmworkerbaseentity 實體的 mshr_hcmworkerbaseentityid。 | 系統產生的唯一背景工作角色識別碼。 |
| **期間識別碼值**</br> _mshr_fk_period_id_value</br>*GUID* | 外部索引鍵：mshr_benefitperiodentity 實體的 mshr_benefitperiodentityid。 | 系統產生的唯一期間識別碼。 |
| **計劃識別碼值**</br> _mshr_fk_plan_id_value</br>*GUID* | 外部索引鍵：mshr_benefitplanentity 實體的 mshr_benefitplanentityid。 | 系統產生的唯一計畫識別碼。 |
| **計畫類型識別碼值**</br> _mshr_fk_plantype_id_value</br>*GUID* | 外部索引鍵：mshr_benefitplantypeentity 實體的 mshr_benefitplantypeentityid。 | 系統產生的唯一計畫識別碼。 |
| **涵蓋範圍選項識別碼值**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | 外部索引鍵：mshr_benefitcoverageoptionentity 實體的 mshr_benefitcoverageoptionentityid。 | 系統產生的唯一計畫識別碼。 |
| **工資單背景工作角色福利計劃實體識別碼值**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | 唯讀 </br> 系統產生的 | 系統產生的唯一記錄識別碼。 |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>工資單背景工作角色福利計劃的範例查詢

**要求**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**回應**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
