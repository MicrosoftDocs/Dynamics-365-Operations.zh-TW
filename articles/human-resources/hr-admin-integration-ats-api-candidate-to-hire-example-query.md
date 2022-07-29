---
title: 聘雇候選人的範例查詢
description: 本主題提供 Dynamics 365 Human Resources 裡針對候選人聘雇實體的範例查詢。
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
ms.openlocfilehash: edb8687b9dae0afc1bc15a3a5c197e14e7e8cf1e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452535"
---
# <a name="example-query-for-candidate-to-hire"></a>聘雇候選人的範例查詢


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題提供 Dynamics 365 Human Resources 裡針對候選人聘雇實體的範例查詢。

本主題舉例示範如何使用 *深度插入* 在單 API 操作中建立新候選人記錄的所有明細。 更多有關深度插入的資訊，請參閱[一次操作中建立相關實體記錄](/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation)。

**mshr_hcmcandidatetohireentity** 實體因為與 **mshr_dirpersonity** 實體的關聯性而顯得獨一無二。 **mshr_hcmcandidatetohireentity** 的很多屬性 (例如，**mshr_firstname**、**mshr_姓氏** 和 **mshr_birthdate**) 是從 **mshr_dirpersonenity** 記錄衍生而來。 如果您將新候選人記錄張貼到 **mshr_hcmcandidatetohireentity** 而不使用深度插入，您可以直接在 **mshr_hcmcandidatetohireentity** 記錄上定義這些屬性值。 **mshr_dirpersonity** 關聯記錄是使用屬性的定義值藉由隱含的方式建立。 接著您可以將任何其他相關實體記錄 (例如技能或教育) 建立成單獨的 API 呼叫。

然而，如果您想使用深度插入在一次操作中建立所有相關實體，則請務必在蜂巢式操作等級上定義  **mshr_dirpersonity** 實體。

本範例顯示如何在單 API 操作中使用深度插入的三個蜂巢層級建立候選人記錄、關聯人員記錄及人員的技能和教育。

> [!NOTE]
> 本範例不包括每個 API 實體的所有屬性。 它已先基於示範的目的簡易化。

**要求**

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

**回應**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>也請參閱

[申請人追蹤系統整合 API 簡介](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
