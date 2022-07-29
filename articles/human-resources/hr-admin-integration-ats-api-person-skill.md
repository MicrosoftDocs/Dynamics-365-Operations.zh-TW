---
title: 個人技能
description: 本主題說明 Dynamics 365 Human Resources 的個人技能實體。
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
ms.openlocfilehash: c37001c82be34e802835515db86f7ab29e6735bf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452217"
---
# <a name="person-skill"></a>個人技能


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的個人技能實體。

實際名稱：mshr_hcmpersonskillentity

## <a name="description"></a>描述

本實體說明候選人的技能。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人技能實體識別碼**<br>mshr_hcmpersonskillentityid<br>*GUID* | 唯讀<br>必要 | 系統產生的唯一實體記錄識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 讀/寫<br>必要 |   關聯合作對象 (個人) 記錄識別碼。 |
| **個人識別碼值**<br>_mshr_fk_person_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_dirpersonentity 的 mshr_dirpersonentityid | 系統產生的合作對象 (個人) 實體記錄識別碼。 |
| **認證單位**<br>mshr_certifier<br>*字串* | 讀/寫<br>選擇性 | 認證本技能的背景工作角色人員編號。 |
| **認證單位識別碼值**<br>_mshr_fk_certifier_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmworkerentity 的 mshr_hcmworkerentityid | 系統產生唯一認證技能的背景工作角色記錄識別碼。 |
| **技能識別碼**<br>mshr_skillid<br>*字串* | 讀/寫<br>必要 | 人力資源定義的技能識別碼。 |
| **技能識別碼值**<br>_mshr_fk_skill_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmskillentity 的 mshr_hcmskillentityid | 系統產生的唯一選取技能識別碼。 |
| **多年經驗**<br>mshr_yearsofexperience<br>*十進位* | 讀/寫<br>選擇性 | 候選人在本技能的多年經驗。 |
| **評等識別碼**<br>mshr_ratingid<br>*字串* | 讀/寫<br>必要 | 評等量表類型。 本實體值為 **技能**。 |
| **等級類型**<br>mshr_leveltype<br>*mshr_hrmskillleveltype 選項集合* | 讀/寫<br>必要 | 指派給技能的等級類型分類。 |
| **等級識別碼**<br>mshr_levelid<br>*字串* | 讀/寫<br>必要 | 候選人對本項技能的評等級別識別碼。 |
| **評等級別識別碼值**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmratinglevelentity 的 mshr_hcmratinglevelentityid | 系統產生的評等級別識別碼。 |
| **等級日期**<br>mshr_leveldate<br>*日期時間* | 讀/寫<br>必要 | 候選人技能的評分日期。 |
| **評等級別檢驗人員**<br>mshr_ratinglevelexaminer<br>*字串* | 讀/寫<br>選擇性 | 評等候選人的背景工作角色人員編號。 |
| **評等級別檢驗人員識別碼值**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmworkerentity 的 mshr_hcmworkerentityid | 系統產生檢驗候選人技能程度的背景工作角色識別碼。 |
| **已查核**<br>mshr_verified<br>*mshr_noyes 選項集合* | 讀/寫<br>必要 | 指示已評鑑的技能程度是否已經查核過。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 預計當作實體記錄識別碼的欄位。 合作對象編號、等級類型、技能識別碼和等級日期組合。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
