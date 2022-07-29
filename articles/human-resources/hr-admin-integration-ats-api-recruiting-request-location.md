---
title: 招募要求位置
description: 本主題說明 Dynamics 365 Human Resources 招募要求位置實體。
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
ms.openlocfilehash: 4dbc676e25c1ec24350607b10787924b0738e102
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452529"
---
# <a name="recruiting-request-location"></a>招募要求位置


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 招募要求位置實體。

實際名稱：mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>描述

位置清單定義為招募員工將在錄用時工作的位置。 這些是橫跨法人實體建立的位置。

### <a name="json-representation"></a>JSON 呈現

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **位置識別碼**<br>mshr_locationid<br>*字串* | 一次性寫入<br>必要 | 系統產生使用者可讀的招募位置識別碼。 |
| **招募要求位置**<br>mshr_recruitingrequestlocationid<br>*字串* | 一次性寫入<br>必要 | 使用者定義的唯一招募位置識別碼。 |
| **招募要求位置實體識別碼**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | 唯讀<br>必要 | 系統產生的唯一招募要求位置記錄識別碼。 |
| **描述**<br>mshr_description<br>*字串* | 讀/寫<br>必要 | 位置的說明。 |
| **國家/地區識別碼**<br>mshr_countryregionid<br>*字串* | 唯讀<br>選擇性 | 指明候選人擁有公民身份的國家或地區。 |
| **國家/地區識別碼值**<br>_mshr_fk_countriregion_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：mshr_logisticsaddresscountryregionentity 的 mshr_logisticaddresscountryregionentityid | 系統產生的唯一地址所在國家/地區識別碼。 |
| **ZipCode**<br>mshr_zipcode<br>*字串* | 唯讀<br>選擇性 | 郵遞區號。 |
| **街道**<br>mshr_street<br>*字串* | 唯讀<br>選擇性 | 街道地址。 |
| **城市**<br>mshr_city<br>*字串* | 唯讀<br>選擇性 | 城市。 |
| **狀態**<br>mshr_state<br>*字串* | 唯讀<br>選擇性 | 州或省份。 |
| **縣市**<br>mshr_county<br>*字串* | 唯讀<br>選擇性 | 縣轄市。 |
| **電話**<br>mshr_telephone<br>*字串* | 讀/寫<br>選擇性 | 此處位置的電話號碼。 |
| **電子郵件**<br>mshr_email<br>*字串* | 讀/寫<br>選擇性 | 電子郵件地址。 |
| **InternetAddress**<br>mshr_internetaddress<br>*字串* | 讀/寫<br>選擇性 | 位置網站 URL。 |
| **資料區識別碼**<br>mshr_dataareaid<br>*字串* | 讀/寫<br>選擇性 | 指定法人實體 (公司)。 |
| **資料區識別碼值**<br>_mshr_dataareaid_id_value<br>*GUID* | 唯讀<br>選擇性<br>外部索引鍵：cdm_company 實體的 cdm_companyid | 系統產生辨別法人實體 (公司) 的 GUID 值。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
