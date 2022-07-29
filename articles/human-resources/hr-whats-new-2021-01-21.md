---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年一月 21 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年一月21 日新增或更改的功能。
author: marcelbf
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 02f0b0664dcb78d20c2719b4377dcc6047f2bf3392225f1cf9c166a1073ecd59
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451911"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年一月 21 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)。


## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.3866。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 平台更新 10.0.16(40) | -- | [財務和營運應用程式版本 10.0.16 的平台更新 (2021 年二月)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16.md) |
| 強化的工作流程要求與核准 | [組織和人事管理工作流程體驗強化](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [指派我的清單中，職位 Work 項目配置選項](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| 1095-C 表單、1095-B 表單和舊版福利中的電子報表平價醫療法案 (ACA) 法令遵循更新 | -- | -- | 
| 福利管理現在支援美國法人實體的 ACA 法令遵循報告 | -- | [在福利管理中產生 ACA 報表](hr-benefits-management-aca-reports.md) |
| 福利管理現在揭露福利費率分層和福利費率雙層實體  | -- | -- |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 533079 | 當我們試著查看減扣項目時，出現 "表單調用不正確" 的瀏覽錯誤。 | 已修正藉由 **截止日期** 視圖查看福利減扣項目的錯誤。 |
| 543641 | 郵遞區號不填寫在電子報表上。  | 已修正當涵蓋範疇代碼為 M 到 Q 時，郵遞區號未出現在 ACA 福利管理電子報表的內部 BUG。 |
| 542815 | Employee 自助服務的個人聯絡人畫面控制項允許員工查看其他人的個人聯絡人。 | 已修正 Employee 自助服務個人聯絡人 **編輯** 表單限制查詢的程度無法保證只檢索一位個人聯絡人，允許使用者使用鍵盤快速鍵檢視其他人的聯絡人。 |
| 536157 | 因調用 IsVirtualEntityPackageInstalled() 緣故，無法打開系統管理的 **Microsoft Dataverse 整合** 頁面。 | 問題防止 **Microsoft Dataverse 整合** 頁面載入人力資源。 |
| 533079 | 當我們試著查看減扣項目時，出現 "表單調用不正確" 的瀏覽錯誤。 | 已修正在福利管理的 **扣減** 表單來視 **截止日期** 時發生的錯誤。 |
| 537264 | 求職者記錄缺少 **個人資訊** 快速索引標籤。 | 求職者的個人資訊現在開放求職者記錄使用。 |
| 537267 | **專業經驗** 不會顯示在內部求職者記錄上。 | **專業經驗** 快速索引標籤現在顯示在內部求職者記錄上。 之前，如果求職者是內部員工，**專業經驗** 由 **雇用歷程** 替代，指出求職者在組織內的雇用歷程。 兩者都適用，並且內部求職者必須顯示。 |
| 537067 | 不顯示 **允許聯絡雇主**。 | **允許聯絡雇主** 控制項新增到求職者記錄的 **編輯職業經歷** 窗格。 |
| 525957 | **求職者狀態** 在完成轉移後，不會更新內部求職者。 | 當轉移完成時 (**轉移背景工作角色到新職位指派** 頁選取 **更改職位** 或 **繼續** 按鈕)，求職者記錄上的 **狀態** 必須更改為 **已錄用**。 |
| 537051 | 印度盧比和土耳其里拉的貨幣符號無法正確同步到 Dataverse | 印度盧比和土耳其里拉的符號現在已正確同步到 Dataverse。 |
| 534846 | 資料管理必須啟用招募資料表。 | 資料管理現在啟用針對招募要求和求職者建立的新資料表。 這允許為資料表啟用追蹤修訂功能，連帶啟用 OData 在 Dataverse 虛擬資料表上的追蹤修訂功能。 |
| 533474 | 修正 Microsoft.SqlServer.XEvent.dll 缺少參考的問題。 | Microsoft.SqlServer.XEvent.dll 的組合語言載入異常防堵 Dataverse 在某些環境設定虛擬資料表。 |
| 481122 | **人員** 工作區顯示退休職位。 | 退休職位在 **人員** 工作區顯示為職缺。 退休職位不再顯示。 | 
| 541978 | 新增主要電子郵件地址到 BaseWorker 實體。 | 這項更改新增背景工作角色的主要電子郵件地址到 HcmWorkerBaseEntity。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| Microsoft Teams 中的人力資源 App | [在 Microsoft Teams 中的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)<br>[管理 Teams 的請假要求](hr-teams-leave-app.md) |
| 與 LinkedIn 人才中心的整合 | [與 LinkedIn 人才中心的整合](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [整合 LinkedIn 人才中心](./hr-admin-integration-linkedin.md) |
| 經理請假的跨公司視圖 | [員工為經理請假的跨公司視圖](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [配置請假和缺勤參數](./hr-leave-and-absence-parameters.md) |
|額外提供對請假餘數的深入解析| [額外提供對請假餘數的深入解析](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [管理員工請假](./hr-leave-and-absence-manage-employee-leave.md) |
| 經理可以提交職位招募要求 | [經理會針對職缺提交招募要求](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [新增招募要求](./hr-personnel-recruit.md#add-a-recruiting-request) |
| 人事管理中強化的求職者設定檔 | [人事管理中強化的求職者設定檔](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [新增或編輯求職者設定檔](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| 啟用與招募提供商的簡化整合 | [啟用與招募提供商的簡化整合](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [招募工作求職者](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>即將推出
| 功能 | 詳細資料​​ |
| --- | --- |
| 福利註冊的電子郵件確認 | 本功能將提供選項，方便他們核定 Employee 自助服務中的福利註冊體驗時，傳送確認電子郵件給員工。 更多資訊，請參閱[配置每間公司的福利管理參數](hr-benefits-setup-parameters-per-company.md)。 |
| 經理為其員工輸入的技能可由工作流程自動核准 | 即將推出。 |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)。

## <a name="terminology-updates-for-microsoft-dataverse"></a>Microsoft Dataverse 專門術語更新

自 2020 年十一月起生效，Common Data Service 已重新命名為 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)。 請參閱在 Power Apps 部落格的[官宣](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/)了解更多資訊。 Dataverse 的若干專門術語已經隨著這項名稱更改動作更新。 例如，*實體* 即為現在的 *資料表*，而 *欄位* 就是現在的 *欄位*。 更多資訊，請參閱[專門術語更新](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)。

此次發行版本中，Dynamics 365 Human Resources 整合 Dataverse 的相關專門術語已在整個應用程式更新，反映這些更改。 例如，**Common Data Service 整合** 表單現在是 **Microsoft Dataverse 整合**。

了解更多有關 Dynamics 365 Human Resources 整合 Microsoft Dataverse，請參閱[配置Microsoft Dataverse 整合](./hr-admin-integration-common-data-service.md)和[配置 Microsoft Dataverse 虛擬資料表](./hr-admin-integration-common-data-service-virtual-entities.md)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]