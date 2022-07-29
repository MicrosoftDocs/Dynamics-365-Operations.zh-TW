---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年十月 5 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年十月 5 日新增或更改的功能。
author: marcelbf
ms.date: 10/05/2021
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
ms.search.validFrom: 2021-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 206c7f590b495278b7899271db0e83b3a4da3edc
ms.sourcegitcommit: 42bd701179e664947b6eafcd1804c83a5e64abcb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2021
ms.locfileid: "8451962"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-5-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年十月 5 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Microsoft Dynamics 365 Human Resources 中全新、已更改或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4485。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
|---|---|---|
| 平台更新 10.0.21 (45) | -- | [財務和營運應用程式版本 10.0.21 的平台更新 (2021 年十月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21) |


### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能會更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 | 描述 |
|---|---|---|
| 598896 | 員工只有已完成登記才會顯示員工數額 | **Employee 自助服務** 頁面上不顯示員工福利金額。 **福利自助服務** 頁面上顯示員工金額。  |
| 613440 | 無法從 **資料管理** 匯出資料 | 在 **資料管理** 匯出專案資料時，匯出意外失敗。 |
| 618327 | 福利對帳單結案期間和未來期間會顯示在 **報表參數** 頁面 | 瀏覽到 **Employee 自助服務** 的 **福利對帳單** 時，**報表參數** 頁面顯示 **預計包括的記錄** 和 **後台執行** FastTab。 這些專區已經移除。|
| 618326 | 顯示在 **Employee 自助服務** 福利對帳單的 **報表參數** 頁面不正確| 瀏覽到 **福利對帳單報表** 目標頁面時，使用者可以選取已經結案或未來日期的福利計劃期間，因此造成頁面空白。 只有目前的福利計劃期間應該顯示在清單內。 |

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
|使用 **GER 報表目的地** 傳送電子郵件報表時出錯 | 福利對帳單可以設定為在 **GER 報表目的地** 頁面上使用電子郵件參數。 完成設定並列印報表時，使用者將收到格式錯誤訊息，並且不會傳送福利對帳單。|

## <a name="feature-management-changes"></a>功能管理更改

| 功能 | 描述 |
|---|---|
|效能日記帳擴大報表視圖 | 此次發行版本將預計啟用本功能。 |

## <a name="coming-soon"></a>即將推出

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

| 功能 | 詳細資料​​ |
|---|---|
| 平台更新 10.0.22 (46) | 平台更新 10.0.22 的推出排程在與 2021 年十一月 1 日的服務版本一同開始。 更多資訊，請參閱[財務和營運應用程式版本 10.0.22 的平台更新 (2021 年十一月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22)。 |



## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
