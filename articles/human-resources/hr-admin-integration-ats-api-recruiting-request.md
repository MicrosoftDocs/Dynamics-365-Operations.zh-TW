---
title: 招募要求
description: 本主題說明 Dynamics 365 Human Resources 招募要求實體。
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
ms.openlocfilehash: a1f160d828c8fe5babb96d39afd911052767f67b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452469"
---
# <a name="recruiting-request"></a>招募要求


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 招募要求實體。

實際名稱：mshr_hcmrecruitingrequestentity

### <a name="description"></a>描述

說明招聘工作的要求。

### <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **招募要求識別碼**<br>mshr_recruitingrequestid<br>*字串* | 唯讀<br>必要<br>系統產生 | HR 應用程式中顯示要求的使用者可讀唯一識別碼。 編號順序。 |
| **招募要求實體識別碼**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | 唯讀<br>必要<br>系統產生 | 系統產生 GUID 值用來辨別唯一的招募要求。 |
| **資料區識別碼**<br>mshr_dataareaid<br>*字串* | 讀/寫<br>選擇性<br> | 指明招募要求的法人實體 (公司)。 |
| **資料區識別碼值**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | 唯讀<br>選擇性<br>外部索引鍵：cdm_company 實體的 cdm_companyid | 系統產生的 GUID 值，用來辨別招募要求的法人實體 (公司)。 |
| **錄用經理人事編號**<br>mshr_hiringmanagerpersonnelnumber<br>*字串* | 讀/寫<br>選擇性 | 與本招募要求有關聯的錄用經理人事編號。 |
| **錄用經理識別碼值**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmworkerbaseentity 實體的 mshr_hcmworkerbaseentityid | 系統產生 GUID 值用來辨別與招募要求有關聯的經理。 |
| **招募合作對象編號**<br>mshr_recruiterpartynumber<br>*字串* | 讀/寫<br>選擇性 | 針對要求選取招募人員的個人 (合作對象) 識別碼。 |
| **招募人員識別碼值**<br>_mshr_fk_recruiter_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_dirpersonentity 實體的 mshr_dirpersonentityid | 系統產生 GUID 值用來辨別與招募要求有關聯的招募人員。 |
| **狀態**<br>mshr_status<br>*RecruitingRequestStatus* 選項集合 | 讀/寫<br>必要<br> | 指明招募要求的狀態。 |
| **描述**<br>mshr_description<br>*字串* | 讀/寫<br>必要 | 說明要求。 |
| **招募要求位置識別碼**<br>mshr_recruitingrequestlocationid<br>*字串* | 讀/寫<br>選擇性 | 使用者可讀的唯一與本要求有關聯的工作位置識別碼。 |
| **招募位置識別碼值**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmrecruitingrequestlocationentity 實體的 mshr_hcmrecruitingrequestlocationentityid | 系統產生 GUID 值用來辨別針對要求選取的招募要求位置。 |
| **附註**<br>mshr_comments<br>*字串* | 讀/寫<br>選擇性 | 關於錄用經理和招聘人員使用要求的評論意見。 |
| **職務識別碼**<br>mshr_jobid<br>*字串* | 一次性寫入<br>必要 |   使用者可讀的唯一與本要求有關聯，所有職位共享的工作識別碼。 |
| **工作識別碼值**<br>_mshr_fk_job_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmjobentity 實體的 mshr_hcmjobentityid | 系統產生的唯一與招募要求有關聯，所有職位共享的工作識別碼。 |
| **職銜識別碼**<br>mshr_titleid<br>*字串* | 唯讀<br>必要 | 使用者可讀的唯一與本要求有關聯的工作職銜識別碼。 |
| **職銜識別碼值**<br>_mshr_fk_title_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmtitleentity 實體的 mshr_hcmtitleid | 系統產生的唯一針對招募要求選取的工作職銜識別碼。 |
| **工作職能識別碼**<br>mshr_jobfunctionid<br>*字串* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmjobfunctionentity 實體的 mshr_jobfunctionid | 使用者可讀的唯一與本要求有關聯的工作職能識別碼。 |
| **預設全職等效**<br>mshr_defaultfulltimeequivalency<br>*雙倍* | 唯讀<br>必要 | 工作全職等效值，其中 1.0 代表全職背景工作角色。 |
| **監管工作類別**<br>mshr_regulatoryjobcategory<br>*監管工作類別* 選項集合 | 唯讀<br>選擇性 | 針對工作選取工作職能的 EEO 工作類別。 HcmRegulatoryJobCatetory (mshr_hcmregulatoryjobcategory) 選項集合包括的有效值。 |
| **工作類型識別碼**<br>mshr_jobtypeid<br>*字串* | 唯讀<br>選擇性 | 與本職位有關聯的工作類型。 工作類型是使用者定義值，可在 mshr_hcmjobtypeentity 實體使用。 |
| **工作類型識別碼值**<br>_mshr_fk_jobtype_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmjobtypenentity 實體的 mshr_hcmjobtypeentityid | 系統產生的唯一針對招募要求工作有關聯的工作類型識別碼。 |
| **責任制狀態**<br>mshr_exemptstatus<br>*JobExemptStatus* 選項集合 | 唯讀<br>選擇性 | 以工作類型為主的 FLSA 免責狀態。 |
| **預估開始日期**<br>mshr_estimatedstartdate<br>*日期* | 讀/寫<br>必要 | 候選人會開始工作的預估日期。 |
| **外部說**<br>mshr_externaldescription<br>*字串* | 讀/寫<br>選擇性 | 候選人面向的工作/職位說明。 | 
| **報酬低門檻**<br>mshr_compensationlowthreshold<br>*雙倍* | 讀/寫<br>選擇性 | 報酬等級的較低界限。 |
| **報酬控制點**<br>mshr_compensationcontrolpoint<br>*雙倍* | 讀/寫<br>選擇性 | 報酬等級的控制點。 |
| **報酬高門檻**<br>mshr_compensationhighthreshold<br>*雙倍* | 讀/寫<br>選擇性 | 報酬等級的較高界限。 |
| **薪資等級**<br>mshr_compensationlevelid<br>*字串* | 讀/寫<br>選擇性 | 工作的報酬等級。 工作可以設定具有多個報酬等級。 本屬性指明為針對本要求選取的工作報酬等級。 |
| **工作報酬識別碼**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmjobcompensationentity 實體的 mshr_hcmjobcompensationentityid | 系統產生的唯一與此招募要求工作有關聯的報酬等級識別碼。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
