---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年六月 22 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年六月22 日新增或更改的功能。
author: marcelbf
ms.date: 06/22/2021
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
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 897c25df96017c5be1ae789027d178ca6b3ccc0410b4f65c7d2557b39e840134
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451893"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年六月 22 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4258。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 通知待業功能的背景工作角色使用者 - 當開啟進階存取以及功能管理的 **檢視所有待業中的背景工作角色** 已經停用，橫幅將在背景工作角色待業表單中顯示。 橫幅將引導使用者開啟 **檢視所有待業中的背景工作角色** 功能。 | 不適用| [待業中的背景工作角色](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| 福利管理資格規則的自訂欄位支援 | [資格處理的自訂欄位支援](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[配置資格規則](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| 請假累計交易稽核中 | 不適用 | [請假累計交易稽核中](hr-leave-and-absence-accrue.md)|
| 請假和缺勤工作流程體驗提升 | [請假和缺勤工作流程體驗提升](https://go.microsoft.com/fwlink/?linkid=2147528) | [要求休假](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 583052 | 收到意見反應的使用者可以編輯收到的意見反應 | 當員工收到績效日記帳的意見反應時選取 **新增外部連結**，表單會變成可編輯狀態，允許員工編輯他們已經收到的績效意見反應。 |
| 522281 | 在薪酬管理中的薪酬結構圖格上選取員工人數會造成結果不正確| 現在從薪酬工作區向下切入薪酬計劃時，會顯示正確的員工人數。 |
| 580683 | 指派給員工和經理角色的使用者無法連結注釋或更新績效日誌 | 指派給員工和經理角色的使用者無法連結注釋或更新績效日誌。 使用者收到錯誤訊息，"無法在績效日記帳分錄 (HcmPerfJournal) 建立記錄。 安全性政策權限遭到駁回。" |
| 583077 | 請假和缺勤公司行事曆中，員工的出生日期顯示的日期不正確 | 用戶將可以在請假和缺勤公司行事曆檢視員工的正確出生日期。 |
| 586996 | 當存取權限限制在單一公司時，跨公司請假檢視功能會造成餘數空白 | 啟用跨公司請假視圖功能後，使用者可以正確檢視員工的未來請假餘數。 |
| 581014 | 檢視未來餘數時，啟用跨公司請假和缺勤視圖功能會造成錯誤 | 使用者在跨公司請假視圖功能啟用情況下，檢視未來請假餘數時的錯誤已經修正。 |
| 509404 | Department Headcount 分析不考慮部門之間員工的流動情況。 | 當員工從一個部門遷移到另一個部門時，如果當年度的職位細節已經到期，則部門人數資料不會反映該名員工切換過來的舊部門。 |
| 584851 | 福利信用額度比例規則 "無" 未曾提供信用額度 |彈性信用額度比例規則 "無" 造成員工福利期間的信用額度為零，不論他們何時被錄用。 此問題已經修正，因此如果員工在福利期開始前被錄用，他們應該收到彈性信用全額，反之如果是福利期開始後才錄用，則沒有。 |
| 584897 | 重複 "使用基本外部功能" 職責會造成錯誤 | 試圖複製 "使用基本外部功能" 職責時，使用者會收到錯誤訊息 "找不到識別碼為 UserDefinedAppHostDialogView 的對象"。 |
| 575692 | 待核定背景工作角色無法使用累計請假和缺勤數 | 請假和缺勤累計數可以在啟用 **簡化員工輸入** 時，對未來的錄用員工執行。 |
| 580110 | 新增公司到工資單整合會重設整合，以便使用所有實體，即使選項設定為不重新整理專案亦然 | 如果客戶已經移除實體或更改工資單整合的資料專案，並且設定防止自動重新整理專案的選項，則新增公司到整合會忽略設定並重新整理專案。  |
| 584518 |註冊福利處理效能問題 | 此 BUG 解決舊版福利註冊過程中的效能問題。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 平台更新 10.0.19 (43) | 平台更新 10.0.19 排程與 2021 年六月 28 日的服務版本一起推出。 更多資訊，請參閱 [財務和營運應用程式版本 10.0.19 的平台更新 (2021 年六月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19)。 |
|  服務年資切換 | 本功能提供選項，可使用不同日期計算在 **簡化員工輸入** 表單和 **人員** 表單顯示的服務年資。  這將在人力資源參數開放使用。 |
|  啟用缺勤經理管理請假 | [啟用缺勤經理管理請假](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  特定請假類型的授權附件 | 此功能讓系統管理員授權在提交特定請假類型的請假要求時，預計新增的附件。 |
|  配置每個請假類型的請假單位 | 此功能讓系統管理員能為每種請假類型配置請假單位 (小時或天)。  |
| 使員工被標記為準備支付 | [使員工被標記為準備支付](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
