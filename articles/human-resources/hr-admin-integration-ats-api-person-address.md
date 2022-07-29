---
title: 個人地址
description: 本主題說明 Dynamics 365 Human Resources 的個人地址實體。
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
ms.openlocfilehash: d428c2b1ce69c55fda2e574715021d4763544a6b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452139"
---
# <a name="person-address"></a>個人地址


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的個人地址實體。

實際名稱：mshr_hcmpersonaddressentities

## <a name="description"></a>描述

本實體包含候選人記錄的通訊地址清單。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人地址實體 ID**<br>mshr_hcmpersonaddressentityid<br>*字串* | 唯讀<br>必要 | 系統產生的唯一實體記錄識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 讀/寫<br>必要 | 關聯合作對象 (個人) 記錄識別碼。 |
| **個人識別碼**<br>_mshr_fk_person_id_value<br>*GUID* | 唯讀<br>必要<br>外部索引鍵：mshr_dirpersonentity 的 mshr_dirpersonentityid | 系統產生的合作對象 (個人) 實體記錄識別碼。 |
| **位置識別碼**<br>mshr_locationid<br>*字串* | 讀/寫<br>必要 | 地址記錄的位置識別碼。 在 mshr_logisticspostaladdresslocationcdsentity 實體中設定。 |
| **描述**<br>mshr_description<br>*字串* | 讀/寫<br>必要 | 候選人地址的描述。 |
| **角色**<br>mshr_roles<br>*字串* | 讀/寫<br>必要 | 指派給此地址的角色。 可指派多個角色。 每個角色應該用分號區隔開來。 mshr_logisticslocationroleentity 實體包含的有效值。 |
| **街道**<br>mshr_street<br>*字串* | 讀/寫<br>可選項目 | 街道編號。 |
| **城市**<br>mshr_city<br>*字串* | 讀/寫<br>可選項目 | 地址的鄉鎮市區。 在 mshr_logisticsaddresscityentity 實體中設定。 |
| **狀態**<br>mshr_state<br>*字串* | 讀/寫<br>可選項目 | 地址的狀態。 在 mshr_logisticsaddressstateentity 實體中設定。 |
| **縣市**<br>mshr_county<br>*字串* | 讀/寫<br>可選項目 | 地址的縣市。 在 mshr_logisticsaddresscountyentity 實體中設定。 |
| **郵遞區號**<br>mshr_zipcode<br>*字串* | 讀/寫<br>可選項目 | 地址的郵遞區號。 在 mshr_logisticsaddresspostalcodeentity 實體中設定。 |
| **國家地區識別碼**<br>mshr_countryregionid<br>*字串* | 讀/寫<br>可選項目 | 地址的國家或地區。 |
| **國家/地區識別碼值**<br>_mshr_fk_countriregion_id_value<br>*GUID* | 唯讀<br>可選項目<br>外部索引鍵：mshr_logisticsaddresscountryregionentity 的 mshr_logisticaddresscountryregionentityid | 系統產生的唯一地址所在國家/地區識別碼。 |
| **是主要**<br>mshr_isprimary<br>*mshr_noyes 選項集合* | 讀/寫<br>必要 | 辨別此地址是否為已定義角色的個人主要地址。 |
| **是私人**<br>mshr_isprivate<br>*mshr_noyes 選項集合* | 讀/寫<br>必要 | 辨別此地址是否是個人的私人地址。 |
| **主要領域**<br>mshr_primaryfield<br>*字串* | 唯讀<br>必要 | 當作實體記錄的主要識別碼欄位。 合作對象號碼和位置識別碼組合。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
