---
title: 招募要求教育
description: 本主題說明 Dynamics 365 Human Resources 招募要求教育實體。
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
ms.openlocfilehash: 9fe1a99debac3dc784ba82b711143337d4077be0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452310"
---
# <a name="recruiting-request-education"></a>招募要求教育


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 招募要求教育實體。

實際名稱：mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>描述

說明 RecruitingRequest 的教育要求。

### <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **招募要求教育實體 ID**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | 唯讀<br>必要 | 系統產生的唯一招募要求教育記錄識別碼。 |
| **招募要求 ID**<br>mshr_recruitingrequestid<br>*字串* | 一次性寫入<br>必要 | 使用者可讀的唯一相關招募要求識別碼。 |
| **招募要求識別碼值**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmrecruitingrequestentity 的 mshr_hcmrecruitingrequestentityid | 系統產生的唯一相關招募要求識別碼。 |
| **教育程度 ID**<br>mshr_educationlevelid<br>*字串* | 一次性寫入<br>必要 | 所需的教育程度。 |
| **教育程度識別碼**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmeducationlevelentity 的 mshr_hcmeducationlevelentityid | 系統產生的唯一所需教育程度識別碼。 |
| **教育程度說明**<br>mshr_educationleveldescription<br>*字串* | 唯讀<br>必要 | 技能所需程度描述。 |
| **教育學科 ID**<br>mshr_educationdisciplinedescription<br>*字串* | 一次性寫入<br>必要 | 教育學科領域。 |
| **教育學科識別碼值**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmeducationdisciplineentity 的 mshr_hcmeducationdisciplineentityid | 系統產生的唯一教育學科領域識別碼。 |
| **教育學科說明**<br>mshr_educationdisciplinedescription<br>字串 | 唯讀<br>必要 | 教育學科領域說明。 |
| **資料區 ID**<br>mshr_dataareaid<br>*字串* | 讀/寫<br>可選項目 | 指定法人實體 (公司)。|
| **資料區識別碼值**<br>_mshr_dataareaid_id_value<br>*GUID* | 唯讀<br>可選項目<br>外部索引鍵：cdm_company 實體的 cdm_companyid | 系統產生辨別法人實體 (公司) 的 GUID 值。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 招募要求值、教育程度 ID 和教育學科 ID 併列，作為另一種辨別唯一記錄的方法。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
