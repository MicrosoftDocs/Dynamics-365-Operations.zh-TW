---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年七月 12 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年七月 12 日新增或更改的功能。
author: marcelbf
ms.date: 07/12/2021
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
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4ebe5a6ae19d00b94247381c700ff21d31910fcac1968ab4f8a673f89ddd2f0f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451926"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年七月 12 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4353。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
|  服務年資切換 | |本功能在 **簡化員工輸入** 頁和 **人員** 頁提供使用不同日期計算服務年資的選項。  這將在[人力資源參數](/dynamics365/human-resources/hr-setup-parameters)開放使用。 |


### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 595871 | 人力資源中的關於窗格有不正確的 Dataverse 專門術語 | 隨著 Common Data Service 品牌重新定位為 Dataverse，專門術語已在 Microsoft Dynamics 365 Human Resources 資訊窗格更新 (**幫助與支援 > 關於**)。 |
| 598676 | 搭配儲存的視圖使用時，簡化的員工輸入表單覆蓋任務，會因此產生錯誤| **背景工作角色** 頁面上，如果開啟 '簡化員工輸入' 功能，如果 **始終打開編輯** 在已儲存視圖上設定，應用程式可能失敗。 |
| 592344 |職位的背景工作角色薪酬專區應在啟用福利管理時為唯讀狀態 | 背景工作角色薪酬資訊是使用舊版福利功能建立。  啟用福利管理時，這些欄位將是唯讀狀態。 當福利管理開啟並且 HR 共用參數的 **隱藏舊版福利表單** 設定為 **是** 時，**Workers 薪酬** 索引標籤將會隱藏。 |
| 598617 | **HcmDiscussion** 套用個人化時，表單啟動索引標籤會造成無限迴圈 | 當格線與細節視圖的 **始終打開編輯** 皆已開啟時，被覆蓋的任務方法中，啟動索引標籤的代碼會與有關應該有聚焦並建立無限迴圈的個人化控制項衝突。 |
| 593553 | 績效日記帳的日誌日期欄位以 UTC 顯示 | 績效日誌的 **日誌日期** 欄位以 UTC 時區顯示，而不是系統日期設定定義的時區，造成某些時區的日期不正確。 |
| 586930 | 針對績效目標開放的活動打開完全不同的記錄 | 在 '績效日誌延伸報表視圖' 功能在功能管理中啟用時，在 **Employee 自助服務** 中的 **我的團隊** 索引標籤選取績效延伸報表目標會打開員工，而不是選取員工的目標。 |
| 569959 |  HcmPositionWorkerAssignmentV2 實體不指派背景工作角色給職位 | 使用者透過實體新增職位指派記錄並發佈失敗時收到錯誤訊息。 |
| 582259 | VETS 42十二月報表使用 2017 表單而不是 2020 表單 | 更新為 2020 格式。  若要載入新格式，請前往 **報表配置** 並刪除左欄位的 VETS-42 的十二月報表。 請前往 **電子報表 - 儲存庫 - 人力資源** 並選取 **打開**。  選取 **VETS-42 的十二月PDF 印出** 然後選取 **匯入**。|


## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md)|
|  啟用缺勤經理管理請假 | [啟用缺勤經理管理請假](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [配置缺勤經理角色](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  配置每個請假類型的附件要求 | [配置每個請假類型的附件要求](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[配置請假和缺勤類型](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  配置每個請假類型的請假單位 | [配置每個請假類型的請假單位](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[配置請假和缺勤類型](https://go.microsoft.com/fwlink/?linkid=2168215)|
| 使員工被標記為準備支付 | [使員工被標記為準備支付](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [準備支付](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 平台更新 10.0.20 (44) | 平台更新 10.0.20 排程與 2021 年七月 26 日的服務版本一起推出。 更多資訊，請參閱 [財務和營運應用程式版本 10.0.20 的平台更新 (2021 年八月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20)。 |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
