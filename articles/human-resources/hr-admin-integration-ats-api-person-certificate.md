---
title: 個人證書
description: 本主題說明 Dynamics 365 Human Resources 的個人證書實體。
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
ms.openlocfilehash: 300bf294bb4b2fadd4c5d3e68e74674a69dd48f2
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452400"
---
# <a name="person-certificate"></a>個人證書


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的個人證書實體。

實際名稱：mshr_hcmpersoncertificateentity

## <a name="description"></a>描述

本實體說明候選人的專業證書。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人證書實體 ID**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | 唯讀<br>必要 | 系統產生的唯一個人證書實體記錄識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 讀/寫<br>必要 | 候選人的合作對象 (個人) ID。 |
| **個人識別碼**<br>_mshr_fk_person_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_dirpersonentity 的 mshr_dirpersonentityid | 系統產生的合作對象 (個人) 實體記錄識別碼。 |
| **證書類型 ID**<br>mshr_certificatetypeid<br>*字串* | 讀/寫<br>必要 |  人力資源定義的證書類型識別碼。 |
| **證書類型識別碼**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | 唯讀<br>必要<br>外部金鑰：mshr_hcmcertificatetypeentity 的 mshr_hcmcertificatetypeentityid | 系統在關聯實體產生的唯一證書類型識別碼。 |
| **開始日期**<br>mshr_startdate<br>*日期時間* | 讀/寫<br>必要 | 簽發證書的日期。 |
| **結束日期**<br>mshr_enddate<br>*日期時間* | 讀/寫<br>可選項目 | 證書將到期的日期。 |
| **附註**<br>mshr_notes<br>*字串* | 讀/寫<br>可選項目 | 錄用經理和招募人員專用注釋。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 |  預計當作實體記錄識別碼的欄位。 合作對象編號、證書類型 ID 和開始日期的組合。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
