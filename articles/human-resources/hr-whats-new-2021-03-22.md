---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年三月 22 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年三月22 日新增或變更的功能。
author: marcelbf
ms.date: 03/22/2021
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
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f08dc966353cc612c8145f29e2cd8c303da5b359292a8f928d97f0e0de99585
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451920"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年三月 22 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 變更適用組建編號 8.1.4049。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 強制取消和重設卡住的批次工作選項 (560976) | NA | [重設卡住的批次工作](./hr-admin-troubleshooting-batch-execution.md) |
| 用來建立新福利計劃的 UX 微更新 (419941) | NA | [建立福利計畫](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 554239 | **BusinessProcessTaskAssignment** 資料表相關的實體效能改善 | 藉由新增建議的索引到資料表，改善 **BusinessProcessTaskAssignment** 資料表相關實體的效能。 |
| 566061 | 從夜間同步移除 V2 實體後備代碼 | 移除 Nightly Dataverse同步的 V2 後備代碼。不必再回退並防止篩選同步如預期工作。 這項變更強化 Dataverse 資料同步的一致性。 |
| 538024 | 背景工作角色福利計劃 > 移除結帳時拋出錯誤 | 已修正在背景工作角色福利表單移除福利計劃選項結帳時出現的錯誤。 |
| 557965 | **福利** 工作區：**有效生活事件** 連結在 **連結** 專區應始終看得見 | 已修正 **有效生活事件** 連結在 **連結** 專區看得見，但如果未啟用 **(預覽版) 福利管理工作區** 功能，當嘗試瀏覽著卻拋出錯誤的問題。 更多有關啟用工作區的資訊，請參閱[福利管理工作區](hr-benefits-management-workspace.md)。 |
| 556672 | 當 **簡化員工輸入** 在功能管理中啟用時，無法處理已離職員工的累計項目 | 當員工 **簡化員工輸入** 已在功能管理啟用時，累計請假和缺勤計劃的選項已新增到員工 **工作歷程** 下方的 **更多選項**。 |
| 562656 | **SysRecordChangeLogValidTimeState** 功能表項目應納入安全性權限和 **SystemExternalBasicMaintain** 安全性職責的擴充範圍 | 非系統管理員角色在日期管理器表單上缺少 **檢視變更** 的按鈕。 |
| 505989 | 生活事件處理：由於使用的日期，資格變更未處理正確 | 已修正資格處理的變更須依照職位開始日期，不只依照目前職位的問題。 |
| 562286 | 終止雇用關係的背景工作角色傳送多份 Dataverse 更新版 | 當背景工作角色被終止時，傳送到 Dataverse 的更新操作不只一件，造成同一件變更有兩項更新通知。 如果 Power Automate 流程配置為依照動作給發射鍵，會導致發射鍵多少發射。 |
| 527340 | 打開請假和缺勤註冊時，顯示 "無法呈現的 DateTime" 錯誤 | 選取請假和缺勤註冊時，不再顯示錯誤。 |
| 561663 | 增加群集佈建的等候時間間隔 | 借助群集佈建更新改善基礎設施穩定性和佈建一致性。 |
| 486129 | 無法在 **職位 > 管理變更** 編輯自訂欄位 | 已修正自訂欄位無法在 **職位****管理變更** 索引標籤編輯的問題。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 限制員工編輯商業聯絡人細節 | [限制員工編輯商業聯絡人細節](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [限制個人資訊的編輯](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 經理為其員工輸入的技能可由工作流程自動核准 | 即將推出。 |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]