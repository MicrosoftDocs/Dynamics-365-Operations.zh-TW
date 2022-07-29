---
title: 個人身份證號碼
description: 本主題說明 Dynamics 365 Human Resources 的個人身份證號碼實體。
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
ms.openlocfilehash: 0991f5b2e17e64e23f78b346c451f7c43bc20378
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452313"
---
# <a name="person-identification-number"></a>個人身份證號碼


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的個人身份證號碼實體。

實際名稱：mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>描述

本實體說明候選人的身份證號碼。 它促使 API 使用者將身份證號碼，像社會安全號碼或護照號碼，寫入候選人記錄。 身份證號碼印在背景工作角色記錄上，但不在候選人記錄上。 整合應用程式會將值寫入人力資源資料庫，但建立候選人的背景工作角色記錄之前，這些數字在人力資源看不到。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人身份證號碼實體識別碼**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | 唯讀<br>必要<br>系統產生 | 唯一的個人身份證號碼記錄主要識別碼。 |
| **項目類型**<br>mshr_entrytype<br>*字串* | 讀-寫<br>可選項目 | 參考身份證號碼輸入類型的任意值。 |
| **描述**<br>mshr_description<br>*字串* | 讀-寫<br>可選項目 | 識別碼編號的描述。 |
| **到期日**<br>mshr_expirationdate<br>*日期時間* | 讀-寫<br>可選項目 | 身份證號碼或關聯文件到期的日期。 |
| **是主要**<br>mshr_isprimary<br>*mshr_noyes 選項集合* | 讀-寫<br>可選項目 | 定義身份證號碼是否為此辨別類型的個人主要記錄。 |
| **識別碼編號**<br>mshr_identificationnumber<br>*字串* | 讀-寫<br>必要 | 識別碼編號。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 讀-寫<br>必要 | 擁有身份證號碼的合作對象 (個人) 識別碼。 |
| **個人識別碼**<br>_mshr_fk_person_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_dirpersonentity 實體的 mshr_dirpersonentityid | 合作對象 (個人) 的唯一識別碼。 |
| **辨別類型識別碼**<br>mshr_identificationtypeid<br>*字串* | 讀-寫<br>必要 | 身份證號碼的類型。 |
| **辨別類型識別碼值**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_hcmidentificationtypeentity 實體的 mshr_hcmidentificationtypeentityid | 系統產生的唯一辨別類型識別碼。 |
| **核發機構識別碼**<br>mshr_issuingagencyid<br>*字串* | 讀-寫<br>可選項目 | 核發身份證號碼的機構或組織。 |
| **核發機構識別碼值**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | 唯讀<br>可選項目<br>外部索引鍵：mshr_hcmissuingagencyentity 實體的 mshr_hcmissuingagencyentityid | 系統產生的唯一核發身份證號碼的機構識別碼。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 預計當作實體記錄識別碼的欄位。 合作對象編號、辨別類型識別碼和身份證號碼組合。 |
| **核發日期**<br>mshr_issuedate<br>*日期* | 讀-寫<br>可選項目 | 核發身份證號碼的日期。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
