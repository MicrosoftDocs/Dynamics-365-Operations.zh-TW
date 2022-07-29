---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年四月 19 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年四月19 日新增或更改的功能。
author: marcelbf
ms.date: 04/19/2021
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
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadad34be31f6522654bc3af47a4f71695dcc5fea7f0b3e760ff26d79d88eb4c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451881"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年四月 19 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4113。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 平台更新 10.0.17 (41) | -- | [財務和營運應用程式版本 10.0.17 的平台更新 (2021 年四月)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| 福利管理表單中的自訂欄位支援 | [福利管理中的自訂欄位支援](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [福利管理概觀](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 552164 | **員工自助服務 > 公開課程** 上的 **已儲存視圖** 不適用包含議程的課程 | 如果開放課程 (ESS) 上使用已儲存視圖，並且其中一門課程隨附議程，則此視圖將不再顯示該門課程的多行資料 |
| 560614 | **福利 > 生活事件選項** 顯示工具提示文件和代碼行為中的差異。 | 已在 **生活事件選項** 更新工具提示為顯示正確行為。 |
| 560616 | **福利 > 生活事件選項** 可在背景工作角色福利計劃中編輯，但更改不受影響。 | 已更新生活事件選項行為，切換為根據各個工具提示文件的相依選項啟用或停用。 |
| 565054 | **進階存取** 開啟時，無法檢視 **待業中的背景工作角色** 清單內容。 | 此次發行版本修正 **進階存取** 功能已開啟的位置和時間點，只有系統管理員才能檢視 **待業中的背景工作角色** 清單內容。 因為此次修正是安全性更改，您將需要加入功能管理。 本功能一旦開啟後，對表單有存取權的這些角色將會看到內容，即便進階存取功能已開啟。 更多資訊，請參閱[待業中的背景工作角色](hr-personnel-workers-without-employment.md)。 |
| 570586 | 當該名背景工作角色在所有請假計劃中的最新交易之前，僱用結束，請假要求驗證就會失敗。 | 僱用結束後，請假要求驗證不會因為員工請假交易而失敗。|
| 570783 | 啟用與停用人力資源共用參數中跨公司請假功能會改變受僱於單間公司員工在請假要求中看到的內容。 | 如果啟用或停用該參數，受僱於一家公司的員工在要求休假方面是看不到任何變動的。 |
| 572343 | 當啟用跨公司請假檢視功能時，不會顯示必要的原因代碼。 | 當啟用跨公司請假功能時，原因代碼現在會如預期顯示。 |
| 573676 | 無法新增 **期間** 到 **福利管理 > 連結 > 福利計劃**。 | 已修正 **期間** 無法在既有的 **福利計劃** 表單上新增或更新的 BUG。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 請假和缺勤工作流程體驗提升 | [請假和缺勤工作流程體驗提升](https://go.microsoft.com/fwlink/?linkid=2147528) | [要求休假](hr-employee-self-service-request-time-off.md)|
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 經理為其員工輸入的技能可由工作流程自動核准 | 即將推出。 |
| 平台更新 10.0.18 (42) | 平台更新 10.0.18 排程與 2021 年五月 17 日的服務版本一起推出。 更多資訊，請參閱[財務和營運應用程式版本 10.0.18 的平台更新 (2021 年五月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18)。 |
| 自訂福利管理資格規則中的欄位支援  | [資格處理的自訂欄位支援](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
