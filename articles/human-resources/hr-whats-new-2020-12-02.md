---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年十二月 2 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年十二月 2 日新增或更改的功能。
author: marcelbf
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e02586ad3e6b4428f2ba826851db6ebc3172bdf1760b483032f5159e7864a81
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451929"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年十二月 2 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.3788。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 經理可以提交職位招募要求 | [經理會針對職缺提交招募要求](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [新增招募要求](./hr-personnel-recruit.md#add-a-recruiting-request) |
| 人事管理中強化的求職者設定檔 | [人事管理中強化的求職者設定檔](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [新增或編輯求職者設定檔](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| 啟用與招募提供商的簡化整合 | [啟用與招募提供商的簡化整合](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [招募工作求職者](./hr-personnel-recruit.md) |
| Manager 自助服務中的自訂連結 | [經理自助服務中的自訂連結](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [經理自助服務中的自訂連結](./hr-employee-manager-self-service-custom-links.md) |


### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 | 描述 |
| --- | --- | --- |
| 514087 | BenefitEligibilityProcessResult 應包括處理所使用的 datetime。 | BenefitEligibity 處理結果現在包括上次處理遺漏的 datetimestamp。 |
| 526903 | 當 **自動選取被指定者** 在 **人力資源共用參數** 開啟時，家屬的福利註冊計畫失敗。 | 此次修正 **自動選取被指定者** 選項針對預設被指定者開啟時，家屬福利註冊計畫失敗的問題。 |
| 521922 | **顯示無細節缺勤** 參數在團隊缺勤行事曆顯示休假要求的細節。 | 當 **請假和缺勤參數** 中的 **顯示無細節缺勤** 設定為 **是**，請假類型、請假類型顏色和日期細節會顯示在團隊缺勤行事曆。 此問題已獲得解決，現在請假類型不會顯示，並且預設請假類型顏色 (深藍色) 用在團隊缺勤行事曆上的所有請假類型。 |
| 527316 | Job、Position 和 Worker 通知的標題更改尚未同步。 | Title 關係之前已新增到 Job、Position 和 Worker 實體。 此關係的同步適用從 Human Resources 同步到 Dataverse，但不適用來自 Dataverse 的通知。 此問題已獲得解決。 |
| 512275 | 從 **請假和缺勤參數** 移除顏色選項。 | 現在顏色已在請假類型定義，**請假和缺勤參數** 不再需要顏色選項，因此被移除。 |
| 437112 | 員工職位指派期間的誤導性錯誤訊息文字。 | 更新僱用背景工作角色並試圖指派背景工作角色到非有效職位時的錯誤訊息。 更新後的訊息 **指定的職位截至雇用開始日期止是無效的。請檢查此職位的持續期間。** |
| 527816 | **休假** 頁的效能問題。 | **休假** 頁的效能已經改善。 |
| 523158 | BenefitPeriodMigrationUpgrade 和 BenefitPlanMigrationUpgrade 現在並未執行。 | 修正福利遷移工作 **時期** 和 **計劃** 相關問題未適度執行的問題。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| Microsoft Teams 中的人力資源 App | [在 Microsoft Teams 中的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)<br>[管理 Teams 的請假要求](hr-teams-leave-app.md) |
| 強化的工作流程要求與核准 | [組織和人事管理工作流程體驗強化](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [指派我的清單中，職位 Work 項目配置選項](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| 與 LinkedIn 人才中心的整合 | [與 LinkedIn 人才中心的整合](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [整合 LinkedIn 人才中心](./hr-admin-integration-linkedin.md) |
|經理請假的跨公司視圖 | [員工為經理請假的跨公司視圖](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [配置請假和缺勤參數](./hr-leave-and-absence-parameters.md) |
|額外提供對請假餘數的深入解析| [額外提供對請假餘數的深入解析](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [管理員工請假](./hr-leave-and-absence-manage-employee-leave.md) |
| 經理可以提交職位招募要求 | [經理會針對職缺提交招募要求](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [新增招募要求](./hr-personnel-recruit.md#add-a-recruiting-request) |
| 人事管理中強化的求職者設定檔 | [人事管理中強化的求職者設定檔](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [新增或編輯求職者設定檔](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| 啟用與招募提供商的簡化整合 | [啟用與招募提供商的簡化整合](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [招募工作求職者](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>即將推出

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]