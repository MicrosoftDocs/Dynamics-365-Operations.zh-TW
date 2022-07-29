---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年十月 22 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年十月 22 日新增或更改的功能。
author: jcart1106
ms.date: 10/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b36354b14faf59aacb4a619dfb6f243335e6a297
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452052"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年十月 22 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。 更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.3680。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 平台更新 10.0.14(38) | -- | [財務和營運應用程式版本 10.0.14 的平台更新 (2020 年十一月)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14.md) |
| 組織和人事管理工作流程體驗強化 | [組織和人事管理工作流程體驗強化](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [指派我的清單中，職位工作項目配置選項](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號| 問題  | 描述|
| --- | --- | --- |
| 437922 | 使用 DMF 實體匯入 FMLA Hours 會造成唯讀的錯誤。 | 使用 FMLA Hours 實體匯入與 FMLA 案例關聯的時數失敗。 我們新增邏輯確保匯入的時數不超過案例剩餘的時數。 |
| 512019 | 不正確的 **上期結轉** 金額。 | 在 **休息時間** 頁面上，更改 **截止日期** 到下一個會計期間的第一天會顯示不正確的 **年假** 類型 **最後結轉** 金額。 它現在顯示正確金額。 |
| 458639 | **背景工作角色聯絡人** 實體不支援更改追蹤模式。 | 我們更新 **背景工作角色聯絡人** 實體，以便您可以在自己的資料庫 (BYOD) 方案使用。|
| 505347 | 當啟用簡化背景工作角色功能時，培訓經理可以為員工提交請假要求。 | 人力資源助理和人力資源經理以外的角色不得為員工提交休假要求。 |
| 513490 | 福利管理記錄：針對無涵蓋範疇選項的計劃新增記錄。 | 我們已經啟用 **無涵蓋範疇選項計劃** 的記錄結果。 它們現在顯示在 **處理結果** 資料表，並且正確排序和顯示在最上方。 |
| 517021 | 如果 **計劃類型** 的各類型都有一項註冊，就無法選取 **計劃類型** 代碼相同的多項計劃。 | 我們更改選取計劃的限制，只允許一次註冊。 現在限制在 **計劃類型代碼** 等級而不是 **計劃類型**。 這項更改允許像 HSA 和 FSA 的計劃，皆屬相同類型，但您可以給它們分開的 **計劃類型代碼**。 如此一來，您便能在相同註冊期間選擇兩者。 |
| 444791 | 當薪酬計畫開啟 **限制存取** 功能時，就無法在 Employee 自助服務檢視薪酬。 | 在 Employee 自助服務 **薪酬** 卡中，如果員工註冊一項計劃，其已開啟 **限制存取** 功能並指派給特定角色，則目前薪酬金額和增加佔比會顯示 "0"。 我們己經解決這個問題，因此員工和經理始終可以查看自己及其下屬的薪酬細節。 |
| 457542 | 課程結束後更新課程細節不會同時更新參加課程的員工的相同資訊。 | 現在，當您關閉、重新打開課程後更改課程細節時，員工資訊會適度更新。 |
| 515342 | 無法透過 **CDSLeaveRequestDetailEntity** 插入資料。 未找到公司或公司不存在。 | 您現在可以使用 **CDSLeaveRequestDetailEntity** 插入資料。 |
| 514743 | 使用 Microsoft Exchange 時，**電子郵件參數** 表單出錯。 | 當電子郵件提供商設定為 **交易商** 時，**電子郵件參數** 頁會顯示 "無法載入檔案或組譯碼..." 的訊息。 此次修正也允許 **電子郵件參數** 頁面如預期載入和儲存。 |


## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| Microsoft Teams 中的人力資源 App | [在 Microsoft Teams 中的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)<br>[管理 Teams 的請假要求](hr-teams-leave-app.md) |
| 強化的工作流程要求與核准 | [組織和人事管理工作流程體驗強化](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [指派我的清單中，職位 Work 項目配置選項](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Dataverse 中的人力資源虛擬實體 | [擴大 Dataverse 中的 Dynamics 365 Human Resources 核心資料](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [配置 Dataverse 虛擬實體](hr-admin-integration-common-data-service-virtual-entities.md) |
| 與 LinkedIn 人才中心的整合 | [與 LinkedIn 人才中心的整合](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [整合 LinkedIn 人才中心](./hr-admin-integration-linkedin.md) |
| Manager 自助服務中的自訂連結 | [經理自助服務中的自訂連結](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [經理自助服務中的自訂連結](./hr-employee-manager-self-service-custom-links.md) |

## <a name="coming-soon"></a>即將推出

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)。


## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]