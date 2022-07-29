---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年九月 20 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年九月 20 日新增或更改的功能。
author: marcelbf
ms.date: 09/20/2021
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
ms.search.validFrom: 2021-09-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f4fc4768f8c96678b216709f78af6d3ddfd4132
ms.sourcegitcommit: ba8ca42e43e1a5251cbbd6ddb292566164d735dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2021
ms.locfileid: "8451959"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-20-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年九月 20 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Microsoft Dynamics 365 Human Resources 中全新、已更改或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4464。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
|---|---|---|
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md) |
| 使員工被標記為準備支付 | [使員工被標記為準備支付](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [準備支付](/dynamics365/human-resources/hr-compensation-payroll) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能會更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 | 描述 |
|---|---|---|
| 619774 | 編輯地址說明尚未與 Dataverse 即時同步。 | 編輯背景工作角色地址說明時，更新的說明尚未即時與 Dataverse 同步。 **物流位置** 資料表訂閱已經更新可以傳送。 |
| 614603| 當未選取 **背景工作角色人事動作** 參數時，**背景工作角色** 頁面出錯。 | 僱用新背景工作角色或瀏覽到 **背景工作角色** 頁面時，顯示下列錯誤，"必須填寫 **人事動作類型** 欄位"，即使 **人事動作** 已經關閉。 |
| 615367 | **核准的休假** 索引標籤顯示警告並且不正確顯示。 | 如果請假單位設定為 **天**，啟用 **配置每個請假類型的請假單位** 之前，**核准的休假** 索引標籤會顯示無效警告和不正確欄位。 |


## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開關功能方式的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
|---|---|---|
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 資料中的自訂欄位 |[資格處理中的自訂欄位支援](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [使用資格處理中的自訂欄位](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| 福利對帳單 |[福利對帳單](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [福利對帳單](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>福利對帳單已知問題

| 問題 | 描述 |
|---|---|
| **Employee 自助服務** 的福利對帳單 **報表參數** 頁面不正確。 | 瀏覽到 **Employee 自助服務** 的 **福利對帳單** 時，**報表參數** 頁面顯示 **預計包括的記錄** 和 **後台執行** FastTab。  這些需要移除。 |
| 福利對帳單的結案期間和未來期間會顯示在 **報表參數** 頁面。 | 瀏覽到 **福利對帳單報表** 目標頁面時，使用者可以選取已經結案或未來日期的福利計劃期間，因此造成頁面空白。 只有目前的福利計劃期間應該顯示在清單內。 |
|使用 GER 報表目的地傳送電子郵件報表時出錯。 | 福利對帳單可以設定為在 **GER 報表目的地** 頁面內使用電子郵件參數。 完成設定並列印報表時，使用者將收到格式錯誤訊息，並且不會傳送福利對帳單。|


## <a name="coming-soon"></a>即將推出

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

| 功能 | 詳細資料​​ |
|---|---|
| 平台更新 10.0.21 (45) | 平台更新 10.0.21 的推出排程在與 2021 年十月 4 日的服務版本一同開始。 更多資訊，請參閱[財務和營運應用程式版本 10.0.21 的平台更新 (2021 年十月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21)。 |
|效能日記帳擴大報表視圖 | 本功能將在下一次推出時，預設啟用。 |


## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
