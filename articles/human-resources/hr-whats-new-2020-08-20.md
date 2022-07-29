---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年八月 20 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年八月20 日新增或更改的功能。
author: andreabichsel
ms.date: 08/20/2020
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
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a97997212a090f141c7280f7e48fd116a1f31481
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452025"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年八月 20 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3478。 某些標題括號裡的數字意指 Lifecycle Services (LCS) 支援參考的編號。

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>將即將到來和待核定的缺勤請假資訊顯示在 People 工作區的卡片

待核定和即將到來的請假要求選項現在開放在 **People** 工作區的請假和缺勤卡使用。

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>私人欄位預設非屬 Employee 自助服務的 Employee 角色使用 (477106)

當員工透過 Employee 自助服務的 **Personal 資訊** 頁面新增地址記錄時，**私人** 欄位現在預設為 **是**。  

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>人事管理的準員工 FastTab 顯示不正確的求職者計數 (470110)

**人事管理** 頁面現在可以精確顯示準員工人數。 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>當累計設定為零時，無法輸入已離職員工的病假 (446195)

現在允許對已經確定未來會終止的員工進行請假交易，並且累計設定為零。 請假交易可以輸入到員工的終止日期為止。 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>新增自訂欄位到新 Worker 表單會停用 Manage 請假動作窗格的欄位 (473314)

如果自訂欄位已新增到新 **背景工作角色** 表單，**Manage 請假** 中，**背景工作角色** 表單上的動作窗格選項將不再停用。

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>標示請假欄位為必填欄位會允許在未輸入任何留言時，提交請假要求 (473543)

留言欄位現在是必填欄位，請假要求尊重這項設定。 必填欄位是預覽功能。

### <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF 實體開放用在累計暫停

DMF 實體現在開放用在累計暫停。

## <a name="in-preview"></a>預覽中

### <a name="mandatory-fields"></a>必填欄位

您可以借助人力資源個人化功能將欄位設為必填欄位。 此功能需要 **已儲存的視圖**。 更多有關已儲存視圖的資訊，請參閱：

- [已儲存的視圖 - 全面開放使用](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)在 Dynamics 365 2020 發行版本第 2 波計劃
- [建構完整利用已儲存視圖的表單](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Teams 的人力資源應用程式

員工可以在 Microsoft Teams 內部檢視和要求下班時間。 他們可以 Bot 互動、建立請假要求。 更多資訊，請參閱：

- [Microsoft Teams 的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams)在 Dynamics 365 2020 發行版本第一波計劃
- [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)

## <a name="coming-soon"></a>即將推出

### <a name="human-resources-app-in-teams-preview-features"></a>Teams 預覽功能的人力資源 App
 
-  **通知**：請假要求的提交者和核准者將在 Teams 的人力資源應用程式接獲通知。 核准者將能核准或駁回請假要求，如果要求被核准或駁回，提交者將接獲通知。
 
- **經理休假行事曆**：經理將可以在行事曆視圖查看下屬的已核准和待核定休假申請。 本視圖讓您輕鬆了解團隊成員何時下班。

### <a name="checklist-entities-included-in-dataverse"></a>核對清單實體納入 Dataverse

到職、離職、調動和業務流程核對清單實體將很快在 Dataverse 開放使用。

## <a name="known-issues"></a>已知問題

**功能管理** 工作區可能顯示全面開放使用時，作為預覽功能停用的功能。 下面是顯示不正確狀態的全面開放使用功能清單。 

- 福利管理
- 案例管理
- 資料庫記錄 (稽核中)
- 針對一間公司或一項計劃的請假累計
- 請假和缺勤累計暫停
- 餘數調整原因代碼和評論意見
- 買賣請假
- 請假和缺勤行事曆
- 請假結轉規則
- 請假累計稽核中
- 請假累計刪除
- 請假累計進位
- 在單一請假計劃配置多種請假類型
- 更新休假強化功能
- 使用員工的 FTE 進行累計
- 跨公司薪酬視圖
- 列印績效考核
- 請假累計假期改正

### <a name="benefit-plan-employee-entity"></a>福利計劃員工實體 

我們最近發現兩個關於 **BenefitsPlanEmployee** 實體的問題。 匯入背景工作角色註冊時，**涵蓋範疇代碼** 和 **計劃類型代碼** 會設定不正確。 此問題造成員工福利計劃在 **Worker 福利計劃** 表單和 Employee 自助服務中的 **Open 招募** 表單不正確顯示。 此問題也會影響員工在 Employee 自助服務中選取計劃的能力。 目前沒有解決方法。 我們以高優先級修正工作看待，將在下一次發行版本中推出修正程式。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]