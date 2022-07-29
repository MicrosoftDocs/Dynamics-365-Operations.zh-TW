---
title: 個人
description: 本主題說明 Dynamics 365 Human Resources 個人實體。
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
ms.openlocfilehash: 728e383be44949ec7f1e51feb5157c61679b3e7b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452478"
---
# <a name="person"></a>個人


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 個人實體。

實際名稱：mshr_dirpersonentity

### <a name="description"></a>描述

本實體為候選人的個別人士提供個人資訊。

## <a name="json-representation"></a>JSON 呈現

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **個人實體識別碼**<br>mshr_dirpersonentityid<br>*GUID* | 唯讀<br>必要<br>系統產生 | 系統產生的唯一實體記錄識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>*字串* | 唯讀<br>必要<br>系統產生 | 使用者可讀，系統產生的唯一個人識別碼。  |
| **姓名**<br>mshr_name<br>*字串* | 唯讀<br>必要 | 欄位值是名字、中間名、姓氏前綴詞和姓氏按照定義的順序在 **名稱序列顯示為** 欄位中併列。 |
| **名稱別名**<br>mshr_namealias<br>*字串* | 讀/寫<br>選擇性 | 可為個人提供的名稱別名。 |
| **姓名**<br>mshr_knownas<br>*字串* | 讀/寫<br>選擇性 | 如果典型上就是指另一個名字，那麼可以用於個人的名字。 |
| **語言識別碼**<br>mshr_languageid<br>*字串* | 讀/寫<br>選擇性 | 個人主要語言的語言識別碼，以 ISO 639-1 格式定義。 |
| **通訊錄**<br>mshr_addressbooks<br>*字串* | 讀/寫<br>選擇性 | 個人可以被指派的通訊錄。 已針對組織設定的通訊錄就列在 mshr_diraddressbooksentity 實體中。 |
| **紀念日**<br>mshr_anniversaryday<br>*Int* | 讀/寫<br>選擇性 | 個人週年紀念日的日期。 |
| **週年紀念月**<br>mshr_anniversarymonth<br>*mshr_monthsofyear 選項集合* | 讀/寫<br>選擇性 | 個人週年紀念月的日期。 |
| **週年紀念年份**<br>mshr_anniversaryyear<br>*Int* | 讀/寫<br>選擇性 | 個人週年紀念年份的日期。 |
| **生日**<br>mshr_birthday<br>*Int* | 讀/寫<br>選擇性 | 個人的生日的日期。 |
| **出生月**<br>mshr_birthmonth<br>*mshr_monthsofyear 選項集合* | 讀/寫<br>選擇性 | 個人生日日期當月。 |
| **出生年**<br>mshr_birthyear<br>*Int* | 讀/寫<br>選擇性 | 個人生日日期當年度。 |
| **子女姓名**<br>mshr_childrennames<br>*字串* | 讀/寫<br>選擇性 | 個人子女姓名的字串。 不需要分隔。 |
| **性別**<br>mshr_gender<br>*mshr_hcmpersongender 選項集合* | 讀/寫<br>選擇性 | 個人性別。 |
| **嗜好**<br>mshr_hobbies<br>*字串* | 讀/寫<br>選擇性 | 個人嗜好。 |
| **縮寫**<br>mshr_initials<br>*字串* | 讀/寫<br>選擇性 | 個人姓名的首字母。 |
| **婚姻狀態**<br>mshr_maritalstatus<br>*mshr_hcmpersonmaritalstatus 選項集合* | 讀/寫<br>選擇性 | 個人婚姻狀態。 |
| **拼音名字**<br>mshr_phoneticfirstname<br>*字串* | 讀/寫<br>選擇性 | 個人名字的拚音發音。 |
| **拼音姓氏**<br>mshr_phoneticlastname<br>*字串* | 讀/寫<br>選擇性 | 個人姓氏的拚音發音。 |
| **拼音中間名**<br>mshr_phoneticmiddlename<br>*字串* | 讀/寫<br>選擇性 | 個人姓氏的拚音發音。 |
| **個人字尾**<br>mshr_personalsuffix<br>*字串* | 讀/寫<br>選擇性 | 個人的個人後綴詞。 mshr_dirnameaffixentity 實體中的有效值，其中 mshr_type 為後綴詞 (200000001)。 |
| **個人稱謂**<br>mshr_personaltitle<br>*字串* | 讀/寫<br>選擇性 | 個人的個人頭銜。 mshr_dirnameaffixentity 實體中的有效值，其中 mshr_type 為頭銜 (200000000)。
| **專業後綴詞**<br>mshr_professionalsuffix<br>*字串* | 讀/寫<br>選擇性 | 專業後綴詞。 |
| **專案職銜**<br>mshr_professionaltitle<br>*字串* | 讀/寫<br>選擇性 | 專案職銜。 |
| **完整的主要地址**<br>mshr_fullprimaryaddress<br>*字串* | 讀/寫<br>選擇性 | 個人完整主要地址，主要地址欄位的併列。 |
| **地址城市**<br>mshr_addresscity<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在城市。 在 mshr_logisticsaddresscityentity 實體中設定。 |
| **地址所在國家/地區**<br>mshr_addresscountryregionid<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在國家/地區。 mshr_logisticsaddresscountryregionentity 實體中的有效值。 |
| **地址所在國家/地區 ISO 代碼**<br>mshr_addresscountryregionisocode<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在國家/地區的 ISO 代碼。 |
| **地址所在縣市**<br>mshr_addresscounty<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在縣市。 在 mshr_logisticsaddresscountyentity 實體中設定。 |
| **地址所在區名**<br>mshr_addressdistrictname<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在區別。 在 mshr_logisticsaddressdistrictentity 實體中設定。 |
| **地址所在緯度**<br>mshr_addresslatitude<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在緯度。 |
| **地址位置識別碼**<br>mshr_addresslocationid<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在位置的唯一識別碼。 mshr_logisticspostaladdresslocationcdsentity 實體的有效值。 |
| **位置地址角色**<br>mshr_addresslocationroles<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址的位置角色。 在 mshr_logisticslocationrolecdsentity 實體中設定。 |
| **地址所在經度**<br>mshr_addresslongitude<br>*字串* |  讀/寫<br>選擇性 | 個人主要地址所在經度。 |
| **地址所在州別**<br>mshr_addressstate<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在州別。 在 mshr_logisticsaddressstateentity 實體中設定。 |
| **街道地址**<br>mshr_addressstreet<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址所在街道地址。 |
| **地址有效來源**<br>mshr_addressvalidfrom<br>*日期* | 讀/寫<br>選擇性 | 個人主要地址有效的日期。 |
| **地址效期截止日**<br>mshr_addressvalidto<br>*日期* | 讀/寫<br>選擇性 | 個人主要地址有效截止日期。 |
| **地址郵遞區號**<br>mshr_addresszipcode<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址的郵寄通訊代碼。 在 mshr_logisticsaddresspostalcodeentity 實體中設定。 |
| **地址是私人的**<br>mshr_addressisprivate<br>*mshr_noyes 選項集合* | 讀/寫<br>選擇性 | 判定個人主要地址是否與組織中的其他人共享。 |
| **地址描述**<br>mshr_addressdescription<br>*字串* | 讀/寫<br>選擇性 | 個人主要地址說明。 |
| **主要連絡的電子郵件**<br>mshr_primarycontactemail<br>*字串* | 讀/寫<br>選擇性 | 個人主要電子郵件地址。 |
| **主要連絡的電子郵件說明**<br>mshr_primarycontactemaildescription<br>*字串* | 讀/寫<br>選擇性 | 針對主要電子郵件地址提供的說。 |
| **主要連絡的電子郵件是 IM**<br>mshr_primarycontactemailisim<br>*mshr_noyes 選項集合* | 讀/寫<br>選擇性 | 判定主要電子郵件地址是否可用於即時訊息。 |
| **主要連絡的電子郵件目的**<br>mshr_primarycontactemailpurpose<br>*字串* | 讀/寫<br>選擇性 | 主要電子郵件地址用途。 在 mshr_logisticslocationroleentity 實體中設定。 |
| **主要連絡傳真**<br>mshr_primarycontactfax<br>*字串* | 讀/寫<br>選擇性 | 主要傳真號碼。 |
| **主要連絡的傳真說明**<br>mshr_primarycontactfaxdescription<br>*字串* | 讀/寫<br>選擇性 | 針對主要傳真號碼提供的說明。 |
| **主要連絡的傳真說明**<br>mshr_primarycontactfaxextension<br>*字串* | 讀/寫<br>選擇性 | 主要傳真號碼的分機。 |
| **主要連絡的傳真目的**<br>mshr_primarycontactfaxpurpose<br>*字串* | 讀/寫<br>選擇性 | 主要傳真號碼的用途。 在 mshr_logisticslocationroleentity 實體中設定。
| **主要連絡電話**<br>mshr_primarycontactphone<br>*字串* | 讀/寫<br>選擇性 | 主要電話號碼。 |
| **主要連絡的電話說明**<br>mshr_primarycontactphonedescription<br>*字串* | 讀/寫<br>選擇性 | 針對主要電話號碼提供的說明。 |
| **主要連絡電話的分機**<br>mshr_primarycontactphoneextension<br>*字串* | 讀/寫<br>選擇性 | 主要電話號碼的分機。 |
| **主要連絡電話是手機**<br>mshr_primarycontactphoneismobile<br>*mshr_noyes 選項集合* | 讀/寫<br>選擇性 | 判定主要電話號碼是否為手機。 |
| **主要連絡電話的目的**<br>mshr_primarycontactphonepurpose<br>*字串* | 讀/寫<br>選擇性 | 主要電話號碼的用途。 在 mshr_logisticslocationroleentity 實體中設定。 |
| **主要連絡電報**<br>mshr_primarycontacttelex<br>*字串* | 讀/寫<br>選擇性 | 主要電報號碼。 |
| **主要連絡電報的說明**<br>mshr_primarycontacttelexdescription<br>*字串* | 讀/寫<br>選擇性 | 針對個人主要電報號碼提供的說明。 |
| **主要連絡電報的目的**<br>mshr_primarycontacttelexpurpose<br>*字串* | 讀/寫<br>選擇性 | 個人主要電報號碼的用途。 在 mshr_logisticslocationroleentity 實體中設定。 |
| **主要連絡 URL**<br>mshr_primarycontacturl<br>*字串* | 讀/寫<br>選擇性 | 主要 URL。 |
| **主要連絡的 URL 說明**<br>mshr_primarycontacturldescription<br>*字串* | 讀/寫<br>選擇性 | 針對個人主要 URL 提供的說明。 |
| **主要連絡 URL 的目的**<br>mshr_primarycontacturldescription<br>*字串* | 讀/寫<br>選擇性 | 個人主要 URL 的用途。 在 mshr_logisticslocationroleentity 實體中設定。 |
| **主要連絡的 Facebook**<br>mshr_primarycontactfacebook<br>*字串* | 讀/寫<br>選擇性 | 主要 Facebook 帳戶。 由使用者識別碼辨別。 |
| **主要連絡的 Facebook 說明**<br>mshr_primarycontactfacebookdescription<br>*字串* | 讀/寫<br>選擇性 | 針對個人主要 Facebook 帳戶提供的說明。 |
| **主要聯絡的 Facebook 是私人的**<br>mshr_primarycontactfacebookisprivate<br>*mshr_noyes 選項集合* | 讀/寫<br>選擇性 | 判定是否其他人可看見主要的 Facebook 帳戶。 |
| **主要連絡的 Facebook 目的**<br>mshr_primarycontactfacebookpurpose<br>*字串* | 讀/寫<br>選擇性 | 個人主要 Facebook 帳戶的用途。 在 mshr_logisticslocationroleentity 實體中設定。 |
| **主要連絡的 LinkedIn**<br>mshr_primarycontactlinkedin<br>*字串* | 讀/寫<br>選擇性 | 主要的 LinkedIn 帳戶。 由使用者名稱辨別。 |
| **主要連絡的 LinkedIn 說明**<br>mshr_primarycontactlinkedindescription<br>*字串* | 讀/寫<br>選擇性 | 針對個人主要 LinkedIn 帳戶提供的說明。 |
| **主要聯絡的 LinkedIn 是私人的**<br>mshr_primarycontactlinkedinisprivate<br>*mshr_noyes 選項集合* | 讀/寫<br>選擇性 | 判定個人主要 LinkedIn 帳戶資訊是否與其他用戶共享。 |
| **主要連絡的 LinkedIn 用途**<br>mshr_primarycontactlinkedinpurpose<br>*字串* | 讀/寫<br>選擇性 | 個人主要 LinkedIn 帳戶的用途。 在 mshr_logisticslocationroleentity 實體中設定。 |
| **主要連絡的推特**<br>mshr_primarycontacttwitter<br>*字串* | 讀/寫<br>選擇性 | 個人的主要推特帳戶。 由 @username 辨別。 |
| **主要連絡的推特說明**<br>mshr_primarycontacttwitterdescription<br>*字串* | 讀/寫<br>選擇性 | 針對個人主要推特帳戶提供的說明。 |
| **主要聯絡的推特是私人的**<br>mshr_primarycontacttwitterisprivate<br>*mshr_noyes 選項集合* | 讀/寫<br>選擇性 | 判定個人主要推特帳戶資訊是否與其他用戶共享。 |
| **主要連絡的推特用途**<br>mshr_primarycontacttwitterpurpose<br>*字串* | 讀/寫<br>選擇性 | 個人主要推特帳戶的用途。 在 mshr_logisticslocationroleentity 實體中設定。 |
| **合作對象類型**<br>mshr_partytype<br>*字串* | 讀/寫<br>選擇性 | 個人的合作對象類型。 候選人始終為 **個人**。 |
| **名稱順序顯示為**<br>mshr_namesequencedisplayas<br>*字串* | 讀/寫<br>選擇性 | 個人姓名屬性併列以形成姓名 (mshr_name) 屬性值的順序。 |
| **名字**<br>mshr_firstname<br>*字串* | 讀/寫<br>必要 | 個人名字。 |
| **中間名**<br>mshr_middlename<br>*字串* | 讀/寫<br>選擇性 | 個人中間名。 |
| **姓氏前綴詞**<br>mshr_lastnameprefix<br>*字串* | 讀/寫<br>選擇性 | 個人姓氏的前綴詞。 |
| **姓氏**<br>mshr_lastname<br>*字串* | 讀/寫<br>選擇性 | 個人的姓氏。 |
| **電子位置識別碼**<br>mshr_electroniclocationid<br>*字串* | 讀/寫<br>選擇性 | 個人的電子位置識別碼。 |
| **地址時區**<br>mshr_addresstimezone<br>*Int* | 讀/寫<br>選擇性 | 個人主要地址所在時區。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
