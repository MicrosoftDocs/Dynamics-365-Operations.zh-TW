---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年五月 20 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年五月20 日新增或更改的功能。
author: marcelbf
ms.date: 05/20/2021
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
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4519e90e19d0652f855999d1a73ca64777b53b53465d6065987afc1cf2494187
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451884"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年五月 20 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4189。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 平台更新 10.0.18 (42) | -- | [財務和營運應用程式版本 10.0.18 的平台更新 (2021 年五月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| 人力資源 Microsoft Teams 應用程式現在支援半天定義和單日分割功能 | -- | [管理 Teams 的請假要求](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 583776 | 員工大量註冊請假計劃導致發生重覆記錄錯誤 | 此 BUG 已在最新版本修正，並且應該成功處理大規模請假計劃註冊局面。 |
| 582263 | 無法立即執行所有背景工作角色的生命事件處理 | 當生活事件處理的 **背景工作角色** 欄位預留空白時，所有背景工作角色皆將處理。 |
| 558383 | 如果未選取預設被指定者，主要受益人不會標記為 100% | BUG 已修正，使用者只需要選取主要受益人切換即可。|
| 509404 | Department Headcount 分析並不考慮部門之間員工的流動情況 |分析已經更新到包括部門之間的員工調動狀況|
| 579420 | 網格中的凍結欄位應該尚未開放使用 | 人力資源尚未開放使用的 **網格中凍結欄位** 功能，已經在功能管理列為開放使用。 此項功能已經從預計啟用功能清單移除。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 自訂福利管理資格規則中的欄位支援 | [資格處理的自訂欄位支援](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[配置資格規則](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 請假和缺勤工作流程體驗提升 | [請假和缺勤工作流程體驗提升](https://go.microsoft.com/fwlink/?linkid=2147528) | [要求休假](hr-employee-self-service-request-time-off.md)|
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md)|
| 請假累計交易稽核中 | - | [請假累計交易稽核中](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
|  啟用缺勤經理管理請假 | [啟用缺勤經理管理請假](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
