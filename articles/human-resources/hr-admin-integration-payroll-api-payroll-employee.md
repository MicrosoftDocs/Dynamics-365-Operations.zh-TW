---
title: 工資單員工
description: 本主題提供 Dynamics 365 Human Resources 裡工資單員工實體細節和範例查詢。
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
ms.openlocfilehash: e853a8a5730d397f253c8ce3a330794594dfd907
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452457"
---
# <a name="payroll-employee"></a>工資單員工


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 工資單員工實體。

實際名稱：mshr_payrollemployeeentity。

### <a name="description"></a>描述

本實體提供有關員工的資訊。 您必須先設定[工資單整合參數](hr-admin-integration-payroll-api-parameters.md)才能使用本實體。

>[!IMPORTANT] 
>**名字**、**中間名**、**姓氏**、**NameValidFrom** 和 **NameValidTo** 欄位在本實體上不再提供。 這確保本實體只獲得生效日期當天的資料來源支援。
>這些欄位將在平台更新 43 發行的 **DirPersonNameHistoricalEntity** 開放使用。 從 **PayrollEmployeeEntity** 到 **DirPersonNameHistoricalEntity** 存在 OData 關係。 

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **法人實體識別碼**</br>mshr_legalentityid</br>*字串* | 唯讀 | 指定法人實體 (公司)。 |
| **個人編號**</br>mshr_personnelnumber</br>*字串* | 唯讀 | 員工的唯一個人編號。 |
| **雇用開始日期**</br>mshr_employmentstartdate</br>*日期時間位移* | 唯讀 | 員工雇用的開始日期。 |
| **雇用結束日期**</br>mshr_employmentstartdate</br>*日期時間位移* | 唯讀 |員工雇用的結束日期。  |
| **生日**</br>mshr_birthdate</br>*日期時間位移* | 唯讀 | 員工出生日期。 |
| **性別**</br>mshr_gender</br>[mshr_hcmpersongender 選項集合](hr-admin-integration-payroll-api-gender.md) | 唯讀 | 員工性別。 |
| **雇用類型**</br>mshr_employmenttype</br>[mshr_hcmemploymenttype 選項集合](hr-admin-integration-payroll-api-hcmemploymenttype.md) | 唯讀 | 雇用類型。 |
| **辨識類型識別碼**</br>mshr_identificationtypeid</br>*字串* |唯讀 | 為員工定義的辨識類型。 |
| **身份證號碼到**</br>mshr_identificationnumber</br>*字串* | 唯讀 |為員工定義的辨識號碼。 |
| **準備支付**</br>mshr_readytopay</br>[mshr_noyes 選項集合](hr-admin-integration-payroll-api-no-yes.md) | 唯讀 | 指出員工是否被標示為準備付款。 |
| **工資單員工實體識別碼**</br>mshr_payrollemployeeentityid</br>*GUID* | 系統產生的 | 系統產生的全域唯一識別碼 (GUID) 值用來辨別唯一的員工。 |

## <a name="relations"></a>關係

|屬性值 | 相關實體 | 瀏覽屬性 | 集合物件類型 |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | mshr_FK_HcmEmploymentDetailEntity_PayrollEmployee |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | mshr_FK_HcmWorkerBaseEntity_PayrollEmployee |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | mshr_FK_HcmWorkerBankAccountEntity_PayrollEmployee |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>工資單員工的範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
```

**回應**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
