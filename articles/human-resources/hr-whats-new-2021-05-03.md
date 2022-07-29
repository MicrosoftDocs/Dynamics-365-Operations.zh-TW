---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年五月 3 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年五月3 日新增或更改的功能。
author: marcelbf
ms.date: 05/03/2021
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
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1bfbfabc8ba9c41dfd02c205755042f82387f5e09c88722e2503316bc1cf5feb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451902"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年五月 3 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4140。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 建立生活事件時新增資訊列。 | - | 建立生活事件時，資訊列會顯示訊息指出建立的生活事件類型。

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 559312 |  為員工建立固定薪酬計劃時不會顯示等級。 |  當使用者的時區與公司的時區不相符時，無法讀取工作的薪酬等級。 查詢已經更新為根據 UTC 時間擷取。 |
| 573676  | 無法在 **福利計劃** 表單中新增期間。 | 已經更新表單，**福利計劃** 中，**期間** 快速索引標籤下方的 **新增** 按鈕即可啟用。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 請假和缺勤工作流程體驗提升 | [請假和缺勤工作流程體驗提升](https://go.microsoft.com/fwlink/?linkid=2147528) | [要求休假](hr-employee-self-service-request-time-off.md)|
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md)|
| 請假累計交易稽核中 | - | [請假累計交易稽核中](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 平台更新 10.0.18 (42) | 平台更新 10.0.18 排程與 2021 年五月 17 日的服務版本一起推出。 更多資訊，請參閱[財務和營運應用程式版本 10.0.18 的平台更新 (2021 年五月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18)。 |
| 自訂福利管理資格規則中的欄位支援  | [資格處理的自訂欄位支援](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
