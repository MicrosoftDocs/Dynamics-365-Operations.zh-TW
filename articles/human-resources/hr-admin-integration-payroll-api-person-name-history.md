---
title: 個人名字歷史
description: 本主題提供 Dynamics 365 Human Resources 裡個人名字歷史實體的細節和範例查詢。
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d87803b6ae0ada3ed2de6e4e7da5ffa57bf22eec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452070"
---
# <a name="person-name-history"></a>個人名字歷史


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的個人名字歷史實體。

實際名稱：mshr_dirpersonnamehistoricalentity。

### <a name="description"></a>描述

本實體提供有關預訂人員名字歷史的資訊。

> [!IMPORTANT] 
> **名字**、**中間名**、**姓氏**、**NameValidFrom** 和 **NameValidTo** 欄位在工資單員工實體上不再提供。 它們已被移除，確保只有一個日期有效的資料來源支援此實體。

## <a name="properties"></a>屬性

| 屬性</br>**實際名稱**</br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **名字**</br>mshr_firstname</br>*字串* | 唯讀 | 第一個名字。 |
| **姓氏前綴詞**</br>mshr_lastnameprefix</br>*字串*) | 唯讀 | 姓氏前綴詞。 |
| **姓氏**</br>mshr_lastname</br>*字串*) | 唯讀 | 姓氏。 |
| **中間名字**</br>mshr_middlename</br>*字串*) | 唯讀 | 中間名字。 |
| **失效日期**</br>mshr_validto</br>*字串*) | 唯讀 | 名字失效的日期。 |
| **合作對象編號**</br>mshr_partynumber</br>*字串* | 唯讀 | 使用者可讀，系統產生的唯一個人識別碼。 |
| **主要領域**</br>mshr_primaryfield</br>*字串* | 唯讀 | 記錄的唯一識別碼 |
| **個人名字歷史實體識別碼**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | 系統產生的 | 系統產生的全域唯一識別碼 (GUID) 值用來辨別唯一的記錄。 |

## <a name="relations"></a>關係

| 屬性值 | 相關實體 | 瀏覽屬性 | 集合物件類型 |
| --- | --- | --- | --- |
| 不適用 | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | 不適用 | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>工資單員工的範例查詢

**要求**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**回應**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>也請參閱

[工資單整合 API 簡介](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
