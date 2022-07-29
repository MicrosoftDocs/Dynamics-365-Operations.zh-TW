---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年十月 6 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年十月 6 日新增或更改的功能。
author: jcart1106
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ac64218e48d2713b91af1541f94083aef3f815a2
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452040"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年十月 6 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。 更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.3636。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 對請假行事曆額外的深入解析 | [提供請假行事曆視圖額外的深入解析](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [檢視團隊和公司行事曆](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

>[!NOTE]
> 我們的目標是盡快提供您這項資訊。 本主題可能已更新為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 | 描述 |
| --- | --- | --- |
| 448806 | **預設辨識類型** 在 HCM 參數匯出為 **RecID** | 此次對人力資源參數實體的更改新增額外欄位，此欄位顯示 **預設標識類型**。 |
| 492923 | 任務記錄未儲存在 Lifecycle Services (LCS) | 任務記錄現在可以儲存在 LCS。 |
| 429950 | 在職位更改時，固定薪酬的到期日不正確 | 當更改背景工作角色在 **轉調背景工作角色** 頁的職位時，結束薪酬日期設定在職位結束前一天。 薪酬結束日期現在與職位結束日期相同。 |
| 467214 | **帶薪分析** 只在 **支付費率轉換名稱** 設定為 **年度** 時才會顯示 | **年度** 以外的帶薪支付費率名稱不會顯示在 Compensation Analytics。 隨著這項更改，Compensation Analytics 現在使用所有支付費率轉換。 按 **時薪** 或 **薪資** 執行報表時，使用小時以外期間的支付費率轉換皆納入 **薪資** 篩選條件。 唯有 **小時** 期間的支付費率才會納入 **小時** 的篩選條件。 |
| 482464 | 檢視 **考核** 時，**細節** 視圖在您套用篩選條件後，不會更改為格線視圖 | 待套用篩選條件後，考核格線如預期顯示。 |
| 483184 | 當您選取 **分層基礎** 作為 **請假註冊** 記錄的 **調整後開始日期** 時，人力資源不會產生請假累計數額 |**調整後開始日期** 在產生請假累計數額時會填寫和使用。  |
| 509731 | 如果他們申請終止日期後的休假，未來終止背景工作角色的休假要求會造成問題 | 只要要求在終止日期之前，現在就能為未來終止日期的員工提交休假要求。 |
| 510716 | Compensation Analytics 包括適用 **男性平均時薪** 的男性和女性員工 | 在 Compensation Analytics 中，**Compensation Demographic Analysis** 上的 **男性平均時薪** 包括女性平均工資。 現在它只包括男性。 |
| 511348 | 福利自助服務應該只顯示從今天到福利期結束為止，有效的福利計劃 | 到期的福利計劃在 **福利註冊** 頁顯示給員工。 此次修正移除這些計劃。 |
| 512706 | 設定下列欄位為唯讀：<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | 待動作完成後，**新增** 和 **移除** 維度細節的按鈕啟用不正確。 此次的 **職位動作細節** 頁更新版讓動作完成後的欄位無法編輯。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| Microsoft Teams 中的人力資源 App | [在 Microsoft Teams 中的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)<br>[管理 Teams 的請假要求](hr-teams-leave-app.md) |
| 強化的工作流程要求與核准 | [組織和人事管理工作流程體驗強化](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [指派我的清單中，職位 Work 項目配置選項](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Dataverse 中的人力資源虛擬實體 | [擴大 Dataverse 中的 Dynamics 365 Human Resources 核心資料](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [配置 Dataverse 虛擬實體](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>即將推出

下列新功能排程在未來的發行版本：

- **Dataverse 包括的核對清單實體**：到職、離職、調動和業務流程核對清單實體將很快在 Dataverse 開放使用。

- **福利管理原因代碼**：福利管理原因代碼將很快結合人力資源的既有原因代碼。 如果您在福利管理建立超過 15 個字元的原因代碼，您必須在福利管理的 **原因代碼** 清單，更改原因代碼名稱為 15 個字元或更少。 待您更新名稱後，原因代碼將出現在人事管理中既有原因代碼表單下方。 此項更改將在未來開放使用，不影響既有功能。

- **Manager 自助服務中的自訂連結**：為了支援經理，我們正在擴大 Manager 自助服務的功能。 我們正在新增預計在 **我的團隊** 索引標籤上新增自訂連結的功能。此功能類似員工自助服務中，**我的資料索引標籤** 上的自訂連結功能。 更多資訊，請參閱 [經理自助服務自訂連結](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)。

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2019 年發行版本第二波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)。

## <a name="additional-resources"></a>其他資源

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]