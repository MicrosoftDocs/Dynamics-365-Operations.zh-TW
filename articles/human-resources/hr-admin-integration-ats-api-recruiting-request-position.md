---
title: 招募要求職位
description: 本主題說明 Dynamics 365 Human Resources 招募要求職位實體。
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
ms.openlocfilehash: 24ea00c13030d09fb9cda02950ac7b79bfe0d03d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452136"
---
# <a name="recruiting-request-position"></a>招募要求職位


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 招募要求職位實體。

實際名稱：mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>描述

說明針對招聘要求填補的一個或多個職位。 新增職位到招募要求是選擇性的。 職位的屬性是唯讀，因為招募要求上的職位屬性不應與職位主記錄上的不同。 如果需要更改屬性，應在新增職位到招募要求前在職位主記錄上完成。

### <a name="json-representation"></a>JSON 呈現
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **招募要求職位實體識別碼**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | 唯讀<br>必要 |    系統產生的招募要求職位記錄識別碼。 |
| **招募要求識別碼**<br>mshr_recruitingrequestid<br>*字串* | 一次性寫入<br>必要 | 使用者可讀的唯一招募要求識別碼。 |
| **招募要求識別碼值**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmrecruitingrequestentity entity 實體的 mshr_hcmrecruitingrequestentityid | 系統產生職位要指派的招募要求識別碼。 |
| **職位 ID**<br>mshr_positionid<br>*字串* | 一次性寫入<br>必要 | 使用者可讀的唯一職位識別碼。 |
| **職位識別碼值**<br>_mshr_fk_position_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmpositionv2entity entity 的 mshr_hcmpositionv2entityid | 系統產生的職位識別碼。 |
| **描述**<br>mshr_description<br>*字串* | 唯讀<br>必要 | 職位說明。 |
| **職位類型識別碼**<br>mshr_positiontypeid<br>*字串* | 唯讀<br>選擇性 | 使用者可讀的此職位唯一的職位識別碼。 |
| **職位類型識別碼值**<br>_mshr_fk_positiontype_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmpositiontypeentity 實體的 mshr_hcmpositiontypeentityid | 系統產生的此職位唯一的職位識別碼。 |
| **狀態**<br>mshr_status<br>*RecruitingRequestPositionStatus* 選項集合 | 讀/寫<br>必要 | 招募職位要求的狀態。 |
| **部門編號**<br>mshr_departmentnumber<br>*字串* | 唯讀<br>選擇性<br> | 職位的部門編號。 |
| **部門識別碼值**<br>_mshr_fk_department_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_omdepartmententity 實體的 mshr_omdepartmententityid | 系統產生職位唯一的部門識別碼。 |
| **職位回報識別碼**<br>mshr_reportstopositionid<br>*字串* | 唯讀<br>必要 | 招募職位在組織階層中回報職位的使用者可讀識別碼。 |
| **職位回報識別碼值**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmpositionv2entity entity 的 mshr_hcmpositionv2entityid | 系統產生招募職位回報的職位識別碼。 |
| **人員回報編號**<br>mshr_reportstopersonnelnumber<br>*字串* | 唯讀<br>必要 | 被錄用候選人將回報的背景工作角色的背景工作角色識別碼。 |
| **背景工作角色回報識別碼值**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmworkerbaseentity 實體的 mshr_hcmworkerbaseentityid | 系統產生被錄用候選人將回報的背景工作角色識別碼。 |
| **財務維度**<br>mshr_financialdimension<br>*字串* | 唯讀<br>選擇性 | 指派給職位的財務維度 (例如成本中心)。 財務維度是針對每個法人實體的每個職位指派。 維度中定義的成本中心可透過 mshr_dimattributeomcostcenterentity 實體存取。 |
| **資料區識別碼**<br>mshr_dataareaid<br>*字串* | 讀/寫<br>選擇性 | 指明招募要求職位的法人實體 (公司)。 |
| **資料區識別碼值**<br>_mshr_dataareaid_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：cdm_company 實體的 cdm_companyid | 系統產生的 GUID 值，用來辨別招募要求職位的法人實體 (公司)。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 招募要求值和職位識別碼併列，作為另一種辨別唯一記錄的方法。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
