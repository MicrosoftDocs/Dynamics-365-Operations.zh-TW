---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年九月 6 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年九月 6 日新增或更改的功能。
author: marcelbf
ms.date: 09/06/2021
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
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2add53b4b014cb65caacff03bf175078d2b70d8f
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2021
ms.locfileid: "8451956"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年九月 6 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Microsoft Dynamics 365 Human Resources 中全新、已更改或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4443。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
|---|---|---|
| 啟用缺勤經理管理請假 | [啟用缺勤經理管理請假](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | 此次發行版本中，我們正在更新缺勤經理工作區視圖。 更多資訊，請參閱[配置缺勤經理角色](https://go.microsoft.com/fwlink/?linkid=2168107)。 |
| 配置每個請假類型的附件要求 | [配置每個請假類型的附件要求](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [配置請假和缺勤類型](https://go.microsoft.com/fwlink/?linkid=2168108) |
| 配置每個請假類型的請假單位 | [配置每個請假類型的請假單位](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [配置請假和缺勤類型](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能會更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 | 描述 |
|---|---|---|
| 610128 | 使用 HcmDiscussionOverallCommentEntity 時發佈資料時出錯 | 當資料從 Excel 活頁簿發佈到 HcmDiscussionOverralCommentEntity 實體時，會發生下列錯誤："找不到 HcmTopicOverrall 類型的資料來源記錄。" |
| 589073 | EEO-1 報表計數 "非特定" 和 **性別** 欄位為 "女性" 值的空白值。 | 如果 **性別** 欄位未指定 **男性**，EEO-1 報表會產生 **女性** 的預設值。 |
| 589617 | 當使用者角色僅限於特定法人實體時，不會出現休假卡餘數、開放購買和開放銷售餘數。 | 如果使用者 (員工角色) 僅限於特定的法人實體，餘數不會正確顯示在 **休假餘數** 卡和 **開放購買** 及 **開放銷售** 欄位。 |
| 604310 | 當使用者沒有指派的缺勤階層結構時，應隱藏缺勤經理索引標籤。 | 以預訂的法人實體而言，**缺勤經理** 索引標籤應該隱藏在自助服務入口網站中，除非已經啟用跨公司參數並且至少一個缺勤階層結構與使用者相關聯。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開關功能方式的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
|---|---|---|
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md) |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 使員工被標記為準備支付 | [使員工被標記為準備支付](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [準備支付](/dynamics365/human-resources/hr-compensation-payroll) |
| 資料中的自訂欄位 |[資格處理中的自訂欄位支援](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [使用資格處理中的自訂欄位](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>即將推出

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

| 功能 | 詳細資料​​ |
|---|---|
| 平台更新 10.0.21 (45) | 平台更新 10.0.21 的推出排程在與 2021 年十月 4 日的服務版本一同開始。 更多資訊，請參閱[財務和營運應用程式版本 10.0.21 的平台更新 (2021 年十月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21)。 |
| 福利對帳單 | 用在檢視員工目前福利選取項目的福利對帳單。 更多細節，請參閱發行版本文件中的[福利對帳單](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement)。 |

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
