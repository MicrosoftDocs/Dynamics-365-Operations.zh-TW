---
title: 休假餘額
description: 本主題提供 Dynamics 365 Human Resources 裡休假餘額實體細節和範例查詢。
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d26d9624ae8d99b208f77d12137262983499c51
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452067"
---
# <a name="leave-balance"></a>休假餘額


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 休假剩額實體。

### <a name="description"></a>描述

本實體提供預訂員工各種休假類型的休假餘額。

實際名稱：mshr_essleavebalanceentities。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人編號**</br>mshr_personnelnumber</br>*字串* | 唯讀 | 員工的唯一個人編號。 |
| **目前餘額**</br>mshr_balanceavailable</br>*十進位* | 唯讀 | 員工目前的餘額。 |
| **類型**</br>mshr_balanceavailable</br>*字串* | 唯讀 | 休假類型識別碼。 |
| **累計費率**</br>mshr_accrualratedescription</br> | 唯讀 | 累計費率。 |
| **上期結轉金額**</br>mshr_lastcarryforwardamount</br>*十進位* | 唯讀 | 上期結轉金額。 |
| **今年取用的**</br>mshr_takenthisyear</br>*十進位* | 唯讀 | 今年取用的休假金額。 |
| **今年總計**</br>mshr_totalthisyear</br>*十進位* | 唯讀 | 今年的總金額。 |
| **資料區識別碼**</br>mshr_dataareaid_id</br>*字串* | 唯讀 | 指定法人實體 (公司)。 |
| **主要領域**</br>mshr_primaryfield</br>*GUID* | 唯讀</br>系統產生的 | |
| **休假類型識別碼**</br>_mshr_fk_leavetype_id_value</br>*GUID* | 唯讀</br>外部索引鍵：mshr_essleavetypeentity entity 的 mshr_essleavetypeentityid  | 休假類型識別碼 |
| **休假餘額實體**</br>mshr_essleavebalanceentityid</br>*GUID* | 系統產生的 | 系統產生用來辨別唯一餘額的 GUID 值。 |

## <a name="example-query"></a>範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**回應**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
