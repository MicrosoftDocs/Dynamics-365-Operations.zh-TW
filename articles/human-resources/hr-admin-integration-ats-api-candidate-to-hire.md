---
title: 準員工
description: 本主題說明 Dynamics 365 Human Resources 的準員工實體。
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
ms.openlocfilehash: ef76a84c8a4edd1d209b976fc4c65a16cd020e96
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452409"
---
# <a name="candidate-to-hire"></a>準員工


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 的準員工實體。

實際名稱：mshr_hcmcandidatetohireentity

## <a name="description"></a>描述

本實體提供用在 Dynamics 365 Human Resources 建立背景工作角色的候選人細節。 它用來讀取所有候選人記錄並且建立內部和外部候選人記錄，允許您為新候選人建立個人細節。

當您建立將成為系統新人記錄的外部候選人記錄時，您不得定義您會貼文新候選人記錄的合作對象 (個人) 編號。 新個人實體記錄會隨著新候選人記錄建立。

當您建立內部候選人記錄 (公司已有本職位候選人的員工記錄) 時，請為候選人記錄上 mshr_partynumber 屬性已經存在於記錄的合作對象 (個人) 編號定義，而不是定義會被用來建立新個人記錄的個人資訊 (例如姓名、性別或出生日期)。

## <a name="json-representation"></a>JSON 呈現

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
        }
```

## <a name="properties"></a>屬性

| 屬性<br>**實際名稱**<br>**_類型_** | 使用 | 描述 |
| --- | --- | --- |
| **準員工實體識別碼**<br>mshr_hcmcandidatetohireentityid<br>GUID | 唯讀<br>必要<br>系統產生 | 系統產生的唯一實體記錄識別碼。 |
| **候選人識別碼**<br>mshr_candidateid<br>字串 | 唯讀<br>必要<br>系統產生 | 唯一的實體識別碼。 |
| **合作對象編號**<br>mshr_partynumber<br>字串 | 唯讀<br>必要 | 候選人個人記錄的合作對象 (個人) 編號。 |
| **個人識別碼值**<br>_mshr_fk_person_id_value<br>GUID | 唯讀<br>必要<br>外部索引鍵：mshr_direpersonentity 的 mshr_dirpersonentityid | 系統產生的唯一候選人合作對象 (個人) 記錄識別碼。 |
| **合作對象類型**<br>mshr_partytype<br>mshr_dirpartytype 選項集合 | 唯讀<br>必要 | 記錄的合作對象類型，如 mshr_dirpartytype 選項集合中的定義。 本實體類型將一直是 “個人”。 |
| **招募要求識別碼**<br>mshr_recruitingrequestid<br>字串 | 一次性寫入<br>選擇性 | 參考此候選人圓滿達成的招募要求。 |
| **招募要求識別碼值**<br>_mshr_fk_recruitingrequest_id_value<br>GUID | 讀/寫<br>選擇性<br>外部索引鍵：mshr_hcmrecruitingrequestentity 的 mshr_hcmrecruitingrequestentityid | 系統產生的唯一候選人圓滿達成招募要求識別碼。 |
| **職位 ID**<br>mshr_positionid<br>字串 | 讀/寫<br>選擇性 | 正被考慮的候選人職位識別碼。 |
| **職位識別碼值**<br>_mshr_fk_position_if_value<br>GUID | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmpositionv2entity 的 mshr_hcmpositionv2entityid | 系統產生正被考慮的候選人職位識別碼。 |
| **名字**<br>mshr_firstname<br>字串 | 讀/寫<br>必要 | 候選人名字。 |
| **中間名**<br>mshr_middlename<br>字串 | 讀/寫<br>選擇性 | 候選人中間名。 |
| **姓氏前綴詞**<br>mshr_lastnameprefix<br>字串 | 讀/寫<br>選擇性 | 候選人姓氏前綴詞。 |
| **姓氏**<br>mshr_lastname<br>字串 | 讀/寫<br>選擇性 | 候選人姓氏。 |
| **性別**<br>mshr_gender<br>mshr_hcmpersongender 選項集合 | 讀/寫<br>選擇性 | 候選人性別。 |
| **生日**<br>mshr_birthdate<br>日期時間 | 讀/寫<br>選擇性 | 候選人出生日期。 |
| **公民身分國碼 (地區碼)**<br>mshr_citizenshipcountrycode<br>字串 | 讀/寫<br>選擇性 | 指明候選人擁有公民身份的國家/地區。 有效的國碼在 mshr_logisticaddresscountryregionentity。 |
| **退伍軍人身份識別碼**<br>mshr_veteranstatusid<br>字串 | 讀/寫<br>選擇性 | 指明候選人的退伍軍人身份。 |
| **退伍軍人身份識別碼值**<br>_mshr_fk_veteranstatus_id_value<br>GUID | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmveteranstatusentity 的 mshr_hcmveteranstatusentityid | 系統產生的唯一退伍軍人身份實體記錄識別碼。 |
| **兵役開始日期**<br>mshr_militaryservicestartdate<br>日期時間 | 讀/寫<br>選擇性 | 候選人服兵役的開始日期。 |
| **兵役結束日期**<br>mshr_militaryserviceenddate<br>日期時間 | 讀/寫<br>選擇性 | 候選人服兵役的屆滿日期。 |
| **專家狀態已停用**<br>mshr_isdisabledveteran<br>mshr_noyes 選項集合 | 讀/寫<br>選擇性 | 指明候選人是否已有停用的退伍軍人身份。 |
| **可用日期**<br>mshr_availabilitydate<br>日期時間 | 讀/寫<br>選擇性 | 候選人可以到職的最早日期。 |
| **願意搬家**<br>mshr_iswillingtorelocate<br>mshr_noyes 選項集合 | 讀/寫<br>選擇性 | 指明候選人是否願意為此職位搬家。 |
| **附註**<br>mshr_comments<br>字串 | 讀/寫<br>選擇性 | 招募人員或錄用經理預計採用的評論意見。 |
| **應用程式整合結果**<br>mshr_applcantintegrationresult<br>mshr_applicantintegrationresult 選項集合 | 讀/寫<br>必要 | 候選人在攸關整合的招募流程中的狀態。 |
| **不錄用原因代碼識別碼**<br>mshr_donothirereasoncodeid<br>字串 | 讀/寫<br>選擇性 | 當狀態 (應用程式整合結果) 設定為 “不錄用” 時可選擇提供的原因代碼。 |
| **原因代碼識別碼值**<br>_mshr_fk_reasoncode_id_value<br>GUID | 唯讀<br>選擇性<br>外部索引鍵：mshr_hcmreasoncodeentity 實體的 mshr_hcmreasoncodeentityid | 系統產生的唯一 **不僱用** 原因代碼識別碼。 |
| **資料區識別碼**<br>mshr_dataareaid<br>字串 | 讀/寫<br>選擇性 |  指定法人實體 (公司)。 |
| **資料區識別碼值**<br>_mshr_dataareaid_id_value<br>GUID | 唯讀<br>選擇性<br>外部索引鍵：cdm_company 實體的 cdm_companyid | 系統產生辨別法人實體 (公司) 的 GUID 值。 |

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>
[聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
