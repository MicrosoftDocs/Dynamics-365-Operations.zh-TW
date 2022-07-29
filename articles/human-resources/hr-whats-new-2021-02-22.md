---
title: 'Dynamics 365 Human Resources 的新面貌或新轉變 2021 二月 22 日 '
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年二月22 日新增或更改的功能。
author: marcelbf
ms.date: 02/22/2021
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
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 379a902489bdccdfa3490a830cc3b0bbf7639e7f0b62079a3ff3a999b0a7c412
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451878"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 二月 22 日 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.3988。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 適用 Microsoft Teams 的 Dynamics 365 Human Resources App | [在 Microsoft Teams 中的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)<br>[管理 Teams 的請假要求](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 529994 | 修改 **背景工作角色** 表單上的 **號稱** 欄位不會觸發 Dataverse 更新 | 修正 **號稱** 欄位在 **背景工作角色** 表單上更新時，Dataverse 不更新的問題。 |
| 532651 | Compensation 分析 PBI 報表在計算所有公司的計量時不使用貨幣轉換功能 | 修正 Compensation 分析 PBI 報表未正確做貨幣轉換的問題。 |
| 552226 | 生活事件處理針對單一生活事件數次關閉和重新打開計劃  | 修正員工在多法人實體中及發生生活事件時，為員工所在的各法人實體產生生活事件記錄的問題。 處理生活事件時，務必選取要處理的法人實體。 不過處理邏輯並不侷限於此法人實體。 它反而處理所有法人實體，並且關閉和重新打開選取法人實體的計劃。 此項動作是在相同法人實體數次處理的生活事件，導致受到生活事件影響的各個計劃數次關閉/重新打開。 |
| 518064 | 當一人以上標記為預設被指定者時，合格計劃只選取一名家屬 | 修正多名預設被指定者未自動選入合格計畫的問題。 您現在也可以為個人聯絡人指定主要受益人。 多名受益人時，主要受益人在合格計劃列為 100%。 |
| 552365 | 待升級到平台更新 40 後，攜帶您自己的資料庫 (BYOD) 匯出作業失敗 | 修正平台更新 40 套用到環境後，BYOD 匯出檔案失敗的問題。 |
| 547123 | 限制儀表板上，待辦事項清單查詢的任務數量 | 待辦事項清單顯示的任務數量現在限制為 15 件，以便修正嘗試載入過多任務造成的效能問題。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 經理請假的跨公司視圖 | [員工為經理請假的跨公司視圖](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [配置請假和缺勤參數](./hr-leave-and-absence-parameters.md) |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 限制員工編輯商業聯絡人細節 | [限制員工編輯商業聯絡人細節](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [限制個人資訊的編輯](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 經理為其員工輸入的技能可由工作流程自動核准 | 即將推出。 |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="terminology-updates-for-microsoft-dataverse"></a>Microsoft Dataverse 專門術語更新

自 2020 年十一月起生效，Common Data Service 已重新命名為 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)。 請參閱在 Power Apps 部落格的[官宣](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/)了解更多資訊。 Dataverse 的若干專門術語已經隨著這項名稱更改動作更新。 例如，*實體* 即為現在的 *資料表*，而 *欄位* 就是現在的 *欄位*。 更多資訊，請參閱[專門術語更新](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)。

此次發行版本中，Dynamics 365 Human Resources 整合 Dataverse 的相關專門術語已在整個應用程式更新，反映這些更改。 例如，**Common Data Service 整合** 表單現在是 **Microsoft Dataverse 整合**。

了解更多有關 Dynamics 365 Human Resources 整合 Microsoft Dataverse，請參閱[配置Microsoft Dataverse 整合](./hr-admin-integration-common-data-service.md)和[配置 Microsoft Dataverse 虛擬資料表](./hr-admin-integration-common-data-service-virtual-entities.md)。

## <a name="updates-to-service-deployment"></a>服務部署更新

自 2021 年二月 22 日發行版本開始，我們正在調整我們的區域服務更新部署。 調整將包括輪換全球區域收取人力資源服務更新的順序，以及更新階段之間等候時間的修改。 這些更改讓我們更符合安全部署實務做法 (SDP)，改善服務穩定性、品質和支援性。

我們將繼續遵守為期兩週的部署節奏。 不過，客戶可能注意到，更新通常套用他們人力資源環境的時間點是兩週週期的不同天，有別於以前的發行版本。

更多有關服務更新流程資訊，請參閱[更新流程](./hr-admin-setup-update-process.md)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]