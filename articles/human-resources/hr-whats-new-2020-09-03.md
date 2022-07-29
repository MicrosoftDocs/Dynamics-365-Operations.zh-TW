---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年九月 03 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年九月 3 日新增或更改的功能。
author: andreabichsel
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d1cc3a64e6c345df7727f5ca7336821388c9dbcf
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452055"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年九月 3 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3504。 某些標題括號裡的數字意指 Lifecycle Services (LCS) 支援參考的編號。

更多有關人力資源即將推出的功能資訊，請參閱 [Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)。 更多有關人力資源更新流程的資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

## <a name="in-this-release"></a>此次發行版本中

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>整個人力資源的新預設財務維度格線和對話型態 (469495)

財務維度的新型態現在開放下列領域使用：

- 職位動作 (表單：**HcmPositionActionDetail**)
- 工資單收入代碼 (表單：**PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>如果未啟用請假和缺勤行事曆強化功能，登錄項不會出現在公司請假行事曆 (484406)

此次發行版本改正請假登錄項未顯示在公司請假行事曆的問題。 只有在功能管理選項 **請假和缺勤行事曆強化功能** 未啟用時，才會出現此問題。

### <a name="benefitplanemployeeentity-issue-467597"></a>BenefitPlanEmployeeEntity 問題 (467597)

此次發行版本改正 **BenefitsPlanEmployee** 實體的問題。 匯入背景工作角色註冊時，**涵蓋範疇代碼** 和 **計劃類型代碼** 現在會正確設定。 此問題造成員工福利計劃在 **Worker 福利計劃** 表單和 Employee 自助服務的 **Open 招募** 表單不正確顯示。

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>電子檔案 1094-C 以 XML 格式輸出遺漏的字母 (435190)

此項更改改正 1094-C 輸出檔案在提交給 IRS 時遺漏所需字元的問題。

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>對應到固定薪酬表單的員工變動薪酬資料表 (476117)

此項更改對齊固定薪酬欄位和固定薪酬表單。 變動薪酬欄位現在只開放搭配變動薪酬表單。

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>如果請假類型的最低餘額為負數，可在註冊前允許請假要求 (469917)

此項更改禁止在註冊計劃前輸入請假要求，即使註冊的最低餘數為負數。 您只能在計劃有效時輸入或提交要求。

### <a name="document-templates-dont-download-457279"></a>不下載文件範本 (457279)

隨著這項更改，您現在可以下載所有文件範本。 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>資料顯示為欄位標題，而不是薪酬計劃報表的支付費率欄位的各行 (476077)

分析報告現在顯示正確的 **支付費率** 資訊。

## <a name="in-preview"></a>預覽中

### <a name="human-resources-application-in-teams"></a>Teams 的人力資源應用程式

員工可以在 Microsoft Teams 內部檢視和要求下班時間。 他們可以 Bot 互動、建立請假要求。 更多資訊，請參閱：

- [Microsoft Teams 的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams)在 Dynamics 365 2020 發行版本第一波計劃
- [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md) 在人力資源文件中

### <a name="human-resources-app-in-teams-preview-features"></a>Teams 預覽功能的人力資源 App
 
-  **通知**：請假要求的提交者和核准者將在 Teams 的人力資源應用程式接獲通知。 核准者將可以核准或駁回休假要求。 如果要求被核准或遭到駁回，提交者將接獲通知。 更多資訊，請參閱：
   - [Microsoft Teams 的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams)在 Dynamics 365 2020 發行版本第二波計劃
   - [在 Teams 啟用人力資源應用程式的通知功能](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) 在人力資源文件中
   - [針對個別使用者打開或關閉 Teams 通知功能](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users)在人力資源文件中
   - [Teams 通知](./hr-teams-leave-app.md#respond-to-teams-notifications)在人力資源文件中
   - [檢視您的團隊的請假行事曆](./hr-teams-leave-app.md#view-your-teams-leave-calendar)在人力資源文件中
 
- **經理休假行事曆**：經理將可以在行事曆視圖查看下屬的已核准和待核定休假申請。 本視圖讓您輕鬆了解團隊成員何時下班。 更多資訊，請參閱：
   - [Microsoft Teams 的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams)在 Dynamics 365 2020 發行版本第二波計劃
   - [檢視您的團隊的請假行事曆](./hr-teams-leave-app.md#view-your-teams-leave-calendar)在人力資源文件中

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>指派我的清單中，職位 Work 項目配置選項 (477004)

現在開放使用新選項來定位出，位於儀表板右手邊欄位的 **指派我的工作項目** 清單。 隨著這項更改，所有工作項目和待辦事項清單都會顯示在相同區域。 憑藉在功能管理開啟 **預覽 - 工作流程體驗強化** 功能，來啟用此功能。 更多有關開啟預覽功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

本功能也推動人事動作表單中出現的工作流程選項。 工作流程選項也出現在動作快速索引標籤上方，方便快速存取。 更多資訊，請參閱： 

- [組織和人事管理工作流程體驗強化](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements)在 Dynamics 365 2020 發行版本第二波計劃

![指派我的工作項目。](./media/hr-workflow-work-items-assigned-to-me.png)

![工作流程項目快速存取。](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a>即將推出

### <a name="checklist-entities-included-in-dataverse"></a>核對清單實體納入 Dataverse

到職、離職、調動和業務流程核對清單實體將很快在 Dataverse 開放使用。

### <a name="benefits-management-reason-codes"></a>福利管理原因代碼

福利管理原因代碼將很快結合人力資源的既有原因代碼。 如果您在福利管理建立超過 15 個字元的原因代碼，您必須在福利管理的 **原因代碼** 清單，更改原因代碼名稱為 15 個字元或更少。 待您更新名稱後，原因代碼將出現在人事管理中既有原因代碼表單下方。 這項更改將在未來開放使用，不影響既有的功能。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
