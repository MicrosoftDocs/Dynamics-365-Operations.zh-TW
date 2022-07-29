---
title: 招募要求技能
description: 本主題說明 Dynamics 365 Human Resources 招募要求技能實體。
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
ms.openlocfilehash: 245b9a1ff4f140b9288b79c70820204f3082568b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452472"
---
# <a name="recruiting-request-skill"></a>招募要求技能


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 招募要求技能實體。

實際名稱：mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>描述

說明 RecruitingRequest 的技能要求。

### <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **招募要求技能實體識別碼**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | 唯讀<br>必要 | 系統產生的唯一 **招募要求技能** 記錄識別碼。 |
| **招募要求識別碼**<br>mshr_recruitingrequestid<br>*字串* | 一次性寫入<br>必要 | 使用者可讀的唯一關聯招募要求識別碼。 |
| **招募要求識別碼值**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | 唯讀<br>必要<br> 外部索引鍵：mshr_hcmrecruitingrequestentity entity 實體的 mshr_hcmrecruitingrequestentityid | 系統產生的唯一關聯招募要求識別碼。 |
| **技能識別碼**<br>mshr_skillid<br>*字串*<br> | 一次性寫入<br>必要 | 使用者可讀的唯一必要技能識別碼。 |
| **技能識別碼值**<br>_mshr_fk_skill_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmskillentity entity 的 mshr_hcmskillentityid | 系統產生的唯一必要技能識別碼。 |
| **評等級別識別碼**<br>mshr_ratinglevelid<br>*字串* | 一次性寫入<br>選擇性 | 根據指派給技能的評等模型為工作選取的必要技能等級值。 |
| **評等級別識別碼值**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmratinglevelentity entity 的 mshr_hcmratinglevelentityid | 系統產生的唯一等級識別碼。 |
| **技能描述**<br>mshr_skilldescription<br>*字串* | 唯讀<br>必要 | 技能描述。 |
| **評等級別說明**<br>mshr_ratingleveldescription<br>*字串* | 唯讀<br>選擇性 | 選取技能等級說明。 |
| **資料區識別碼**<br>mshr_dataareaid<br>*字串* | 讀/寫<br>選擇性 | 指定法人實體 (公司)。 |
| **資料區識別碼值**<br>_mshr_dataareaid_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：cdm_company 實體的 cdm_companyid | 系統產生辨別法人實體 (公司) 的 GUID 值。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 招募要求值和技能識別碼併列，作為另一種辨別唯一記錄的方法。 |
| **評等模型識別碼**<br>mshr_ratingmodelid<br>*字串* | 讀-寫<br>必要 | 用來對技能進行評分的評等模型。 |
| **評等模型識別碼值**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmratingmodelentity 實體的 mshr_hcmratingmodelentityid | 系統產生用來對技能評分的唯一識別碼。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
