---
title: 個人專業經驗
description: 本主題說明 Dynamics 365 Human Resources 的個人專業經驗實體。
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
ms.openlocfilehash: 38535b5dd56b3408ea582fbaf1594b7adefcd171
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452481"
---
# <a name="person-professional-experience"></a>個人專業經驗


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的個人專業經驗實體。

實際名稱：mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>描述

本實體說明候選人的專業經驗或工作經歷。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人專業經驗實體識別碼**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | 唯讀<br>必要 | 系統產生的唯一實體記錄識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 讀/寫<br>必要 | 唯一的候選人個人記錄識別碼。 |
| **個人識別碼**<br>_mshr_fk_person_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_dirpersonentity 的 mshr_dirpersonentityid | 系統產生的唯一個人證書實體記錄識別碼。 |
| **雇主職位**<br>mshr_employerposition<br>*字串* | 讀/寫<br>必要 | 候選人受僱期間擔任的職位頭銜。 |
| **雇主名稱**<br>mshr_employername<br>*字串* | 讀/寫<br>必要 | 雇主名稱。 |
| **雇主位置**<br>mshr_employerlocation<br>*字串* | 讀/寫<br>可選項目 | 雇主的位置。 最大長度：60。 沒有定義或要求的特定格式。 |
| **電話**<br>mshr_phone<br>*字串* | 讀/寫<br>可選項目 | 雇主的電話號碼。 |
| **URL**<br>mshr_url<br>*字串* | 讀/寫<br>可選項目 | 雇主網站的 URL。 |
| **開始日期**<br>mshr_startdate<br>*日期時間* | 讀/寫<br>必要 | 候選人就業的開始日期。 |
| **結束日期**<br>mshr_enddate<br>*日期時間* | 讀/寫<br>可選項目 | 候選人就業的結束日期，或著如果候選人仍任職這里，則為 Null。 |
| **允許聯絡雇主**<br>mshr_allowcontactemployer<br>*mshr_hrmblankyesno 選項集合* | 讀/寫<br>可選項目 | 表示候選人是否允許聯絡前雇主。 |
| **附註**<br>mshr_note<br>*字串* | 讀/寫<br>可選項目 | 招募人員或錄用經理使用的注釋。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 當作實體記錄的主要識別碼欄位。 合作對象編號、開始日期、雇主職位和雇主名稱組合。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
