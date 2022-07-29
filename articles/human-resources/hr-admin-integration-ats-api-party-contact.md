---
title: 合作對象聯絡方式
description: 本主題說明 Dynamics 365 Human Resources 的合作對象聯絡方式實體。
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
ms.openlocfilehash: fca72cb73ef46a4eeee27d43e22254373a425a36
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452316"
---
# <a name="party-contact"></a>合作對象聯絡方式


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的合作對象聯絡方式實體。

實際名稱：mshr_dirpartycontactentities

## <a name="description"></a>描述

本實體說明候選人的聯絡資訊，包括電話、電子郵件和社交媒體帳戶。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **合作對象聯絡方式實體識別碼**<br>mshr_dirpartycontactentityid<br>*字串* | 唯讀<br>必要 | 系統產生的唯一實體記錄識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 讀/寫<br>必要 | 關聯合作對象 (個人) 記錄識別碼。 |
| **個人識別碼值**<br>_mshr_fk_person_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_dirpersonentity 的 mshr_dirpersonentityid | 系統產生的合作對象 (個人) 實體記錄識別碼。 |
| **位置識別碼**<br>mshr_locationid<br>*字串* | 讀/寫<br>必要 | 地址記錄的位置識別碼。 在 mshr_logisticspostaladdresslocationcdsentity 實體中設定。 |
| **描述**<br>mshr_description<br>*字串* | 讀/寫<br>必要 | 聯絡方式細節說明 |
| **類型**<br>mshr_type<br>*mshr_logisticselectronicaddressmethodtype 選項集合* | 讀/寫<br>必要 | 聯絡方式詳細類型。 |
| **國碼 (地區碼)**<br>mshr_countryregioncode<br>*字串* | 讀/寫<br>選擇性 | 地址的國家或地區。 |
| **定位器**<br>mshr_locator<br>*字串* | 讀/寫<br>選擇性 | 聯絡方式細節。 例如，如果類型是 **電子郵件地址**，則本欄位會包含候選人的電子郵件地址。 |
| **定位器擴充**<br>mshr_locatorextension<br>*字串* | 讀/寫<br>選擇性 | 定位器擴充。 例如，如果類型是 **電話**，則本屬性會包含電話號碼分機。 |
| **是行動電話**<br>mshr_ismobile<br>*mshr_noyes 選項集合* | 讀/寫<br>必要 | 指明電話是否為手機號碼。 |
| **是即時訊息**<br>mshr_isinstantmessage<br>*mshr_noyes 選項集合* | 讀/寫<br>必要 | 指明電話是否啟用即時傳訊功能。 |
| **是主要**<br>mshr_isprimary<br>*mshr_noyes 選項集合* | 讀/寫<br>必要 | 判定聯絡方式類型的主要聯絡方式。 每個聯絡方式類型必須只有一筆主要記錄。 |
| **是私人**<br>mshr_isprivate<br>*mshr_noyes 選項集合* | 讀/寫<br>必要 | 辨別此地址是否是個人的私人地址。 |
| **目的**<br>mshr_purpose<br>*字串* | 讀/寫<br>選擇性 | 聯絡方式的目的/角色細節。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 當作實體記錄的主要識別碼欄位。 合作對象編號、類型、說明和定位器組合。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
