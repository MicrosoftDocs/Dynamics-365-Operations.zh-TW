---
title: 個人篩選
description: 本主題說明 Dynamics 365 Human Resources 的個人篩選實體。
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
ms.openlocfilehash: 5129348f928fd709a5fabe73917522799a2d47e0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452220"
---
# <a name="person-screening"></a>個人篩選


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的個人篩選實體。

實際名稱：mshr_hcmpersonscreeningentity

## <a name="description"></a>描述

本實體說明候選人已經通過或必須通過的篩選。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人篩選實體 ID**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | 唯讀<br>必要<br>系統產生 | 唯一個人篩選記錄主要識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 讀/寫<br>必要 | 與候選人關聯的合作對象 (個人) 編號。 |
| **個人識別碼**<br>_mshr_fk_person_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_dirpersonentity 的 mshr_dirpersonentityid | 系統產生的合作對象 (個人) 實體記錄識別碼。 |
| **篩選類型 ID**<br>mshr_screeningtypeid<br>*字串* | 讀/寫<br>必要<br>外部索引鍵：ScreeningType | 人力資源定義的篩選類型識別碼。 |
| **篩選類型識別碼**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmscreeningtypeentity 的 mshr_hcmscreeningtypeentityid | 系統在關聯實體產生的篩選類型識別碼。 |
| **必要項目**<br>mshr_requiredby<br>*日期時間* | 讀/寫<br>可選項目 | 需要完成篩選的日期。 |
| **狀態**<br>mshr_status<br>*mshr_hcmcompletionstatus 選項集合*<br>讀/寫<br>必要 | 提供候選人的篩選狀態。 |
| **完成日期**<br>mshr_completeddate<br>*日期時間* | 讀/寫<br>可選項目 | 篩選完成的日期。 |
| **附註**<br>mshr_note<br>*字串* | 讀/寫<br>可選項目 | 錄用經理和招募人員專用注釋。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
