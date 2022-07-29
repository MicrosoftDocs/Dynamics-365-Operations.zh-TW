---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年九月 16 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年九月 16 日新增或更改的功能。
author: jcart1106
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cd3424db6bf918b4041f6d12e5d840bc3a8dfef7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452019"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年九月 16 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3557。 某些功能旁邊括號裡的數字意指 Lifecycle Services (LCS) 支援參考的編號。

## <a name="included-in-this-release"></a>納入此次發行版本中

-  [儲存的視圖 - 一般可用性](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- 更多資訊，請參閱[已儲存的視圖](../fin-ops-core/fin-ops/get-started/saved-views.md)。 

- **職位動作** 表單有更新後的維度格線和新對話 (469495)。

- 如果你在 **人力資源共用參數** 中的 **進階存取** 設定 **限制存取背景工作角色資訊** 為是，福利表單現在只會顯示適當的背景工作角色 (393384)。

- **WorkCalendar** 實體中的新行事曆產生選項 (477055)：<br>- 預設結束時間<br>- 預設開始時間<br>- 是星期五工作日<br>- 是星期一工作日<br>- 是星期六工作日<br>- 是星期日工作日<br>- 是星期四工作日<br>- 是星期二工作日<br>- 是星期三工作日<br>- 工作行事曆假日識別碼

- **LeaveBankTransactionV1** 實體現在包括原因代碼 (477823)。

- 您現在可以儲存任務記錄 (492923)。

- 資料現在已經從 **HCMWorkerContactEntity** 成功發佈 (427620)。

- **薪酬** 快速索引標籤如今在 **Worker 動作** 表單中顯示承包商背景工作角色類型 (482494)。

- 如果您設定 **固定薪酬**，**等級** 和 **計劃** 欄位現在是必填欄位。 如果您預留這些欄位空白，會顯示錯誤訊息 (482497)。

- **福利** 中的 **計劃類型** 欄位現在是下拉式清單 (488768)。

- 如果從人力資源刪除自訂欄位，系統管理員現在會接獲通知 (481408)。

- 終止員工流程期間，人力資源的行為如預期一般，在顯示為鎖定後不會更改選取的公司 (479877)。 

- 經理無法再透過個人化新增數字欄位 (485317)。

- 經理無法再從到期的身份識別編號移除資料範圍篩選條件 (485321)。

- 當 **Reports to** 欄位空白時，滑鼠停在職位上方時仍會顯示職位細節 (433328)。

- 員工現在可以在 Employee 自助服務中檢視福利計劃資訊 (481676)。

- 員工現在可以查看所有註冊的課程 (429048)。

- 您現在可以限制 **專業證書** 頁的檢視選項。 您可以按照背景工作角色狀態和背景工作角色類型限制檢視選項為目前法人實體 (451501)。 


## <a name="in-preview"></a>預覽中

### <a name="human-resources-app-in-teams"></a>Teams 的人力資源應用程式

員工可以在 Microsoft Teams 內部檢視和要求下班時間。 他們可以 Bot 互動、建立請假要求。 更多資訊，請參閱：

- [Microsoft Teams 的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams)在 Dynamics 365 2020 發行版本第一波計劃
- [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md) 在人力資源文件中

### <a name="human-resources-app-in-teams-preview-features"></a>Teams 預覽功能的人力資源 App
 
-  **通知**：請假要求的提交者和核准者將在 Teams 的人力資源應用程式接獲通知。 核准者可以核准或駁回休假要求。 如果要求被核准或遭到駁回，提交者將接獲通知。 更多資訊，請參閱：
   - [Microsoft Teams 的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams)在 Dynamics 365 2020 發行版本第二波計劃
   - [在 Teams 啟用人力資源應用程式的通知功能](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) 在人力資源文件中
   - [針對個別使用者打開或關閉 Teams 通知功能](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users)在人力資源文件中
   - [Teams 通知](./hr-teams-leave-app.md#respond-to-teams-notifications)在人力資源文件中
   - [檢視您的團隊的請假行事曆](./hr-teams-leave-app.md#view-your-teams-leave-calendar)在人力資源文件中
 
- **經理休假行事曆**：經理可以在行事曆視圖查看下屬的已核准和待核定休假申請。 本視圖讓您輕鬆了解團隊成員何時下班。 更多資訊，請參閱：
   - [Microsoft Teams 的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams)在 Dynamics 365 2020 發行版本第二波計劃
   - [檢視您的團隊的請假行事曆](./hr-teams-leave-app.md#view-your-teams-leave-calendar)在人力資源文件中

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>指派我的清單中，職位 Work 項目配置選項 (477004)

現在開放使用新選項來定位出，位於儀表板右手邊欄位的 **指派我的工作項目** 清單。 隨著這項更改，所有工作項目和待辦事項清單都會顯示在相同區域。 憑藉在功能管理開啟 **預覽 - 工作流程體驗強化** 功能，來啟用此功能。 更多有關開啟預覽功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

本功能也推動人事動作表單中出現的工作流程選項。 工作流程選項也出現在動作快速索引標籤上方，方便快速存取。 更多資訊，請參閱： 

- [組織和人事管理工作流程體驗強化](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements)在 Dynamics 365 2020 發行版本第二波計劃

![指派我的工作項目。](./media/hr-workflow-work-items-assigned-to-me.png)

![工作流程項目快速存取。](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a>請假和缺勤行事曆

此次發行版本包括請假和缺勤行事曆的其他行事曆選項。 更多資訊，請參閱[檢視團隊和公司行事曆](./hr-employee-self-service-calendar.md)。

## <a name="coming-soon"></a>即將推出

### <a name="checklist-entities-included-in-dataverse"></a>核對清單實體納入 Dataverse

到職、離職、調動和業務流程核對清單實體將很快在 Dataverse 開放使用。

### <a name="benefits-management-reason-codes"></a>福利管理原因代碼

福利管理原因代碼將很快結合人力資源的既有原因代碼。 如果您在福利管理建立超過 15 個字元的原因代碼，您必須在福利管理的 **原因代碼** 清單，更改原因代碼名稱為 15 個字元或更少。 待您更新名稱後，原因代碼將出現在人事管理中既有原因代碼表單下方。 此項更改將在未來開放使用，不影響既有功能。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
