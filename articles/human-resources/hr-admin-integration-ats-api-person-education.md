---
title: 個人教育
description: 本主題說明 Dynamics 365 Human Resources 個人教育實體。
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
ms.openlocfilehash: 6334467de488ed24ce684a2a059a5ffd0cf04959
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452082"
---
# <a name="person-education"></a>個人教育


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 個人教育實體。

實際名稱：mshr_hcmpersoneducationentity

## <a name="description"></a>描述

本實體包含候選人的個人教育歷程。 教育與個人記錄連結，使教育能夠除了候選人記錄 (背景工作角色、承包商等) 之外為個人建立的任何其他角色產生關聯。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人教育實體識別碼**<br>mshr_hcmpersoneducationentityid<br>*GUID* | 唯讀<br>必要 | 系統產生的唯一個人教育實體記錄識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 讀/寫<br>必要 | 唯一的候選人合作對象 (個人) 記錄識別碼。 |
| **個人識別碼值**<br>_mshr_fk_person_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_dirpersonentity 的 mshr_dirpersonentityid | 系統產生的唯一候選人個人記錄識別碼。 |
| **學分依據**<br>mshr_creditbasis<br>*mshr_hcmeducationcreditbasis 選項集合* | 讀/寫<br>選擇性 | 教育學位的學分依據。 |
| **學分修畢**<br>mshr_creditscompleted<br>*十進位* | 讀/寫<br>選擇性 | 為教育修畢的學分數。 |
| **獲得的學分**<br>mshr_creditsearned<br>*十進位* | 讀/寫<br>選擇性 | 為正在攻讀的學位教育記錄獲得的學分數。 |
| **需要的學分**<br>mshr_creditsneeded<br>*十進位* | 讀/寫<br>選擇性 | 攻讀中的學位所需學分數。 |
| **描述**<br>mshr_description<br>*字串* | 讀/寫<br>選擇性 | 候選人學位說明。 |
| **教育程度識別碼**<br>mshr_educationlevelid<br>*字串* | 讀/寫<br>選擇性 | 教育程度識別碼。 | 
| **教育程度識別碼值**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmeducationdegreeentity 實體的 mshr_hcmeducationdegreeentityid | 系統產生的教育學位記錄識別碼。 此識別碼為組織提供定義的學位和教育程度。 |
| **教育學科識別碼**<br>mshr_educationdisciplineid<br>*字串* | 讀/寫<br>必要<br>外部索引鍵：EducationDiscipline | 教育學科識別碼。 |
| **教育學科識別碼值**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmeducationdisciplineentity 的 mshr_hcmeducationdisciplineentityid | 系統產生的唯一教育記錄的教育學科識別碼。 |
| **次要重點**<br>mshr_secondaryemphasis<br>*字串* | 讀/寫<br>選擇性 | 獲得學位的次要重點。 |
| **教育機構識別碼**<br>mshr_educationinstitutionid<br>*字串* | 讀/寫<br>選擇性 | 就讀教育機構識別碼。 |
| **教育機構識別碼值**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmeducationinstitutionentity 的 mshr_hcmeducationinstitutionentityid | 系統產生的教育機構識別碼。 |
| **開始日期**<br>mshr_startdate<br>*日期時間* | 讀/寫<br>選擇性 | 獲得學位教育的開始日期。 |
| **結束日期**<br>mshr_enddate<br>*日期時間* | 讀/寫<br>必要 | 核發認證的日期。 |
| **持續時間**<br>mshr_duration<br>*十進位* | 讀/寫<br>選擇性 | 教育記錄的持續時間。 |
| **持續時間單位**<br>mshr_durationunit<br>*mshr_periodunit 選項集合* | 讀/寫<br>選擇性 | 與教育記錄持續時間有關聯的時間單位。 |
| **年級平均學分**<br>mshr_gradepointaverage<br>*十進位* | 讀/寫<br>選擇性 | 學位獲得的年級平均學分。 |
| **年級量表**<br>mshr_gradescale<br>*字串* | 讀/寫<br>選擇性 | 用於年級平均學分的量表。 |
| **附註**<br>mshr_notes<br>*字串* | 讀/寫<br>選擇性 | 招募人員或錄用經理使用的注釋。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 當作實體記錄的另一個主要識別碼欄位。 合作對象編號、教育學科識別碼、教育機構識別碼、教育程度識別碼組合。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
