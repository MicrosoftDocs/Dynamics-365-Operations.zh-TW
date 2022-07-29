---
title: 工資單背景工作角色地址
description: 本主題提供 Dynamics 365 Human Resources 裡工資單背景工作角色地址實體的細節和範例查詢。
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 70e42cbf657a28327699d927731edd36de7c4a64
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452580"
---
# <a name="payroll-worker-address"></a>工資單背景工作角色地址


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 工資單背景工作角色地址實體。

實際名稱：mshr_payrollworkeraddressentity。

### <a name="description"></a>描述

本實體提供預訂員工的工資單居住位置和工資單工作位置。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人編號**</br>mshr_personnelnumber</br>*字串* | 唯讀 | 員工的唯一個人編號。 |
| **位置識別碼**</br>mshr_locationidbr>*字串* | 唯讀 | 地址識別碼。 |
| **住所地址**</br>mshr_islivedinaddressbr </br> *[mshr_NoYes 選項集合](hr-admin-integration-payroll-api-no-yes.md)* | 唯讀 | 指出員工居住地址的值。 |
| **工作地址** </br> mshr_isworkedinaddressbr </br>*[mshr_NoYes 選項集合](hr-admin-integration-payroll-api-no-yes.md)* | 唯讀 | 指出員工工作地址的值。 |
| **國家/地區**</br>mshr_countryregionid</br>*字串* | 唯讀</br>必要 | 為地址定義的國家或地區。 |
| **郵遞區號**</br>mshr_zipcode<br>*字串* | 唯讀 | 為員工定義的身份證號碼。 |
| **街道**</br>mshr_street</br>*字串* | 唯讀 | 為地址定義的街道。 |
| **城市**</br>mshr_city</br>*字串* | 唯讀 | 為地址定義的城市。 |
| **狀態**</br>mshr_state</br>*字串* | 唯讀 | 為地址定義的州或省份。 |
| **縣市**</br>mshr_county</br>*字串* | 唯讀 | 為地址定義的郡縣。 |
| **生效日期**</br>mshr_postaladdressvalidfrom</br>*日期時間位移* | 唯讀 | 地址的生效日期。 |
| **失效日期**</br>mshr_postaladdressvalidto</br>*日期時間位移* | 唯讀 | 地址的失效日期。 |
| **主要領域**</br>mshr_primaryfield</br>*字串* | 唯讀 | 主要領域。 |
| **工資單背景工作角色地址識別碼**</br>mshr_payrollworkeraddressentityid</br>*GUID* | 系統產生的 | 系統產生的全域唯一識別碼 (GUID) 值用來辨別唯一的地址。 |

## <a name="relations"></a>關係

| 屬性值 | 相關實體 | 瀏覽屬性 | 集合物件類型 |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

## <a name="example-query"></a>範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**回應**

```json
{
    "mshr_personnelnumber": "000041",
    "mshr_locationid": "000000538",
    "mshr_islivedinaddress": 200000001,
    "mshr_isworkedinaddress": 200000000,
    "mshr_countryregionid": "USA",
    "mshr_zipcode": "99025",
    "mshr_street": "6543 Cypress Ave",
    "mshr_city": "Tacoma",
    "mshr_state": "WA",
    "mshr_county": "KING",
    "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
    "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
    "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
    "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
