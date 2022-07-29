---
title: 申請人追蹤系統整合 API 簡介
description: 本主題說明 Dynamics 365 Human Resources 申請人追蹤系統 (ATS) 整合 API。
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e16c781a6e51c57db8ae76dcfe0d28ec709428eb
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452601"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>申請人追蹤系統整合 API 簡介


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 申請人追蹤系統 (ATS) 整合 API。 API 原本意圖是在 Dynamics 365 Human Resources 與合作的 ATS 之間啟用簡化後的整合功能。

![ATS 整合流程。](media/hr-admin-integration-ats-api-introduction-flow.png)

當錄用經理建立招募要求時，整合的體驗會從人力資源開始。 啟動要求後，ATS 會提取要求的細節建立招募專案。 接著它按照招募管線選取和錄用候選人擔任這些職位。 最後，ATS 藉由將選取的候選人記錄傳送到人力資源完成往返的整合動作。 於是候選人記錄可經歷更多到職驗證和工作流程建立員工記錄。

為了啟用整合功能，人力資源新增組成部份如下：

1.  建立招募要求的功能。
2.  展開後的候選人設定檔和相關工作流程。
3.  整合 API 扛開全新的整合應用程式功能。

更多有關設定和使用招募要求及候選人功能的資訊，請參閱[招募求職者](hr-personnel-recruit.md)。

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

這個 API 內建於 Microsoft Dataverse 中 (前身為 Common Data Service)。 與此 API 的所有 RESTful 互動都是透過使用 OData 的 Microsoft Dataverse Web API 進行。 此 API 是 Dataverse Web API 的子集合。 Dataverse Web API 定義如驗證、SLA、批次、同時控制和錯誤處理等特性。

更多有關 Microsoft Dataverse Web API 一般資訊，請參閱：

- [何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)
- [使用 Microsoft Dataverse Web API](/powerapps/developer/data-platform/webapi/overview)
- [Microsoft Dataverse 開發人員指引](/powerapps/developer/data-platform)

上述文件包括使用 Dataverse Web API 和 API 的開發人員指引，例如[管理身份驗證](/powerapps/developer/data-platform/webapi/authenticate-web-api)、[執行操作](/powerapps/developer/data-platform/webapi/perform-operations-web-api)、[搭配 API 使用 Postman](/powerapps/developer/data-platform/webapi/use-postman-web-api) 和[使用追蹤修訂或 Delta Tokens](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)。

### <a name="option-sets"></a>選項集合

本文件描述的 ATS 整合 API 資料模型包括提供與實體屬性相關聯的列舉值選項集合。 有關搭配 Dataverse Web API 選項集合的詳細資訊，請參閱[使用 Web API 建立與更新選項集合](/powerapps/developer/data-platform/webapi/create-update-optionsets)。 選項集合由每個 Dataverse 環境定義。

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Dataverse 人力資源虛擬資料表

ATS 整合 API 端點使用 Microsoft Dataverse 虛擬資料表平台功能。 預設情況下不會針對人力資源環境佈署虛擬資料表及其關聯的 API 端點，進而促使組織判定將為環境揭露的 OData 端點。 若要使用 API，必須針對環境產生人力資源實體的虛擬資料表。 

關於針對 API 產生虛擬資料表的資訊，請參閱[配置 Dataverse 虛擬資料表](./hr-admin-integration-common-data-service-virtual-entities.md)。

## <a name="data-model"></a>資料模型

資料模型以兩大主要實體為中心：

- **RecruitingRequest** 代表向 ATS 提出要求招募一個或多個空缺職位。有關範例查詢，請參閱[招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)。
- **CandidateToHire** 代表已接受職位要約的候選人詳細資料。 **個人** 代表身為候選人的個別人士。 個人在公司可以擔任多個角色，例如候選人、背景工作角色、員工或承包商。 有關範例查詢，請參閱[候選人錄用的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)。

下圖說明 API 內的關係。 目前幾種類型有人力資料預先存在實體的外部索引鍵，未納入這裡的說明。 本文件提供招募整合方案的具體資訊。 然而適用 Dynamics 365 Human Resources 的 Dataverse Web API 也可能攸關您的整合。 例如，您可能也需要這裡尚未定義的背景工作角色、工作、職位或其他實體的詳細資料。 當中許多實體會在外部索引鍵關係或導航屬性中引用。

![ATS 整合 API 資料模型。](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>招募要求和相關實體及選項集合

範例查詢： 

- [招募要求的範例查詢](hr-admin-integration-ats-api-recruiting-request-example-query.md)

實體：

- [招募要求](hr-admin-integration-ats-api-recruiting-request.md)
- [招募要求職位](hr-admin-integration-ats-api-recruiting-request-position.md)
- [招募要求技能](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [招募要求教育](hr-admin-integration-ats-api-recruiting-request-education.md)
- [招募要求位置](hr-admin-integration-ats-api-recruiting-request-location.md)

選項集合：

- [工作免責狀態](hr-admin-integration-ats-api-job-exempt-status.md)
- [招募要求職位狀態](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [招募要求狀態](hr-admin-integration-ats-api-recruiting-request-status.md)
- [監管工作類別](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>候選人錄用和相關實體及選項集合

範例查詢：

- [聘雇候選人的範例查詢](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

實體：

- [準員工](hr-admin-integration-ats-api-candidate-to-hire.md)
- [個人](hr-admin-integration-ats-api-person.md)
- [個人教育](hr-admin-integration-ats-api-person-education.md)
- [個人專業經驗](hr-admin-integration-ats-api-person-professional-experience.md)
- [個人地址](hr-admin-integration-ats-api-person-address.md)
- [合作對象聯絡方式](hr-admin-integration-ats-api-party-contact.md)
- [個人技能](hr-admin-integration-ats-api-person-skill.md)
- [評等級別](hr-admin-integration-ats-api-rating-level.md)
- [個人證書](hr-admin-integration-ats-api-person-certificate.md)
- [證書類型](hr-admin-integration-ats-api-certificate-type.md)
- [個人篩選](hr-admin-integration-ats-api-person-screening.md)
- [篩選類型](hr-admin-integration-ats-api-screening-types.md)
- [個人身份證號碼](hr-admin-integration-ats-api-person-identification-number.md)

選項集合：

- [申請人整合結果](hr-admin-integration-ats-api-applicant-integration-result.md)
- [空白是否](hr-admin-integration-ats-api-blank-yes-no.md)
- [完成狀態](hr-admin-integration-ats-api-completion-status.md)
- [聯絡類型](hr-admin-integration-ats-api-contact-type.md)
- [教育學分基礎](hr-admin-integration-ats-api-education-credit-basis.md)
- [性別](hr-admin-integration-ats-api-gender.md)
- [婚姻狀態](hr-admin-integration-ats-api-marital-status.md)
- [一年當中的月份](hr-admin-integration-ats-api-months-of-year.md)
- [否是](hr-admin-integration-ats-api-no-yes.md)
- [期間單位](hr-admin-integration-ats-api-period-unit.md)
- [篩選頻率](hr-admin-integration-ats-api-screening-frequency.md)
- [篩選頻率來源](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [技能等級類型](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>也請參閱

[招募求職者](hr-personnel-recruit.md)<br>
[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)<br>
[使用 Microsoft Dataverse Web API](/powerapps/developer/data-platform/webapi/overview)<br>
[使用 Web API 建立和更新選項集合](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
