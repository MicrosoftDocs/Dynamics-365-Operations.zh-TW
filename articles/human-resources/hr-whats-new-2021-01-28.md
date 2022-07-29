---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年一月 28 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年一月28 日新增或更改的功能。
author: marcelbf
ms.date: 01/28/2021
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
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 47a15cbab388d98359828561acefb7c110e8d1da3ec489df21ee0496aa3a0730
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451908"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年一月 28 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.3906。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 將福利原因代碼整合到 **人事管理** 工作區 | -- | [設定原因代碼](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。


| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 539456 | 當啟用 **只顯示無細節的缺勤** 參數時，行事曆會以懸停文字形式顯示請假類型。 | 當啟用 **只顯示無細節的缺勤** 選項時，要求的日期現在會懸停顯示。 |
| 528907 | 授予法人實體存取員工角色權限會造成經理無法在 Employee 自助服務的 **我的團隊** 區查看員工的請假餘數活動。 |現在設定此選項會允許經理繼續查看請假餘數活動。 |
| 526280 | HcmWorkerEntity、HcmEmployeeEntity 和 HcmContractorEntity 的權限錯誤。 | 由於 NationalityCountryRegion 欄位的權限錯誤，非系統管理員角色的使用者無法匯出列出的實體。 用戶將繼續需要下列權限匯出此項資訊：HcmWorkerEntityMaintain、HcmWorkerEntityView、HcmEmployeeEntityMaintain、HcmEmployeeEntityMaintain、HcmEmployeeEntityView、HcmContractorEntityMaintain 和 HCMContractorEntityView。 |
| 542147 | **銀行帳號** 和 **路由編號** 欄位在透過 Employee 自助服務新增銀行帳戶時是必填欄位。 | 我們已經修正要求員工在新增銀行帳戶細節時，輸入 **銀行帳號** 和 **路由編號** 欄位的錯誤。 儲存新銀行帳戶資訊時，這些欄位不再為必填欄位。 |
| 543641 | 郵遞區號不在電子報表上填寫。 | 已修正郵遞區號不填寫在 ACA 報表中，涵蓋範圍代碼 L 到 Q 的錯誤。 |
| 545402 | 新增 UserBranding.js 檔案的路由更改內容，以便移除 404 錯誤。 | 使用者在主控台應該再也看不見 404 錯誤。 |

## <a name="in-preview"></a>預覽中   

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| Microsoft Teams 中的人力資源 App | [在 Microsoft Teams 中的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)<br>[管理 Teams 的請假要求](hr-teams-leave-app.md) |
| 經理請假的跨公司視圖 | [員工為經理請假的跨公司視圖](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [配置請假和缺勤參數](./hr-leave-and-absence-parameters.md) |

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 福利註冊的電子郵件確認 | 本功能將提供選項，方便他們核定 Employee 自助服務中的福利註冊體驗時，傳送確認電子郵件給員工。 本功能將於二月 1 日問市。 更多資訊，請參閱[配置每間公司的福利管理參數](hr-benefits-setup-parameters-per-company.md)。 |
| 經理為其員工輸入的技能可由工作流程自動核准 | 即將推出。 |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="terminology-updates-for-microsoft-dataverse"></a>Microsoft Dataverse 專門術語更新

自 2020 年十一月起生效，Common Data Service 已重新命名為 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)。 請參閱在 Power Apps 部落格的[官宣](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/)了解更多資訊。 Dataverse 的若干專門術語已經隨著這項名稱更改動作更新。 例如，*實體* 即為現在的 *資料表*，而 *欄位* 就是現在的 *欄位*。 更多資訊，請參閱[專門術語更新](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)。

此次發行版本中，Dynamics 365 Human Resources 整合 Dataverse 的相關專門術語已在整個應用程式更新，反映這些更改。 例如，**Common Data Service 整合** 表單現在是 **Microsoft Dataverse 整合**。

了解更多有關 Dynamics 365 Human Resources 整合 Microsoft Dataverse，請參閱[配置Microsoft Dataverse 整合](./hr-admin-integration-common-data-service.md)和[配置 Microsoft Dataverse 虛擬資料表](./hr-admin-integration-common-data-service-virtual-entities.md)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]