---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年九月 26 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年九月 26 日新增或更改的功能。
author: jcart1106
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8b0260c4d1bafe271a08336ceed7dc3742f1d590
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452013"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年九月 26 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。 更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2020 年發行版本第 2 波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.3589-hf.3。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放：

- **平台更新 10.0.13 現在已經問市**：更多更新資訊，請參閱 [財務和營運應用程式版本 10.0.13 的平台更新 (2020 年十月)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13.md)。

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快提供您這項資訊。 本主題可能已更新為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 | 描述 |
| --- | --- | --- |
| 469495 | 更新預設財務維度格線和對話方塊 | 財務維度格線和對話方案在整個人力資源更新。 |
| 474887 | 請假要求工作項目在手動決定中打開錯誤的連結 | 當工作流程配置包含手動決策時，從 **指派給我的工作項目** 瀏覽到請假要求時打開錯誤的連結，顯示目前使用者建立的空白表單或請假要求，而不是指派給他們用在手動決策的請求。 |
| 474962 | 請假和缺勤參數實體欄位標籤不明 | 請假和缺勤參數實體標籤已更新為更清晰。 |
| 481401 | 當累計日期基礎在累計開始日期之後以及月末時，累計處理動作會暫停 | 當累計日期基礎在累計開始日期之後以及月末時，累計處理會更新為不會延遲。 |
| 447167 | 到期記錄清單包括無效背景工作角色 | **人事管理** 的 **到期記錄** 索引標籤包括無效背景工作角色。 現在它只包括有效背景工作角色。 |
| 486840 | 從 **指派給我工作項目** 打開的缺勤請假要求是錯的 | 從 **指派給我的工作項目** 選取缺勤的請假要求不再打開指派給目前使用者的最近請假要求。 |
| 506868 | Dataverse **標題** 欄位未針對 **工作職位** 實體設定 | **工作** 和 **工作職位** 實體中的 **標題** 欄位顯示為未指定。 此時顯示 **標題** 欄位。 |
| 430359 | 無法存取已指派經理和員工角色的離職清單任務 | 如果背景工作角色只有員工或經理角色，已明訂未來雇用狀態終止日期者無法存取他們的清單任務。 現在，只有員工或經理角色的使用者可以存取明訂未來終止日期的離職任務。 |
| 458102 | 新員工建立時，不會在 **背景工作角色工資單資訊** 實體上出現 | 新員工納入背景工作角色工資單資訊實體中，不必在匯出實體之前打開員工的工資單資訊。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| Microsoft Teams 中的人力資源 App | [在 Microsoft Teams 中的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)<br>[管理 Teams 的請假要求](hr-teams-leave-app.md) |
| 強化的工作流程要求與核准 | [組織和人事管理工作流程體驗強化](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [指派我的清單中，職位 Work 項目配置選項](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>即將推出

下列新功能排程未來的發行版本中發佈：

- [經理自助服務中的自訂連結](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2019 年發行版本第二波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)。

## <a name="additional-resources"></a>其他資源

[人力資源的新面貌或新轉變](hr-admin-whats-new.md) 
[Dynamics 365 Human Resources 2020 發行版本第二波概觀](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[更新流程](hr-admin-setup-update-process.md)
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]