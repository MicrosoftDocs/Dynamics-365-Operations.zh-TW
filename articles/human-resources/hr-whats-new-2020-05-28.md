---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年五月 28 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年五月28 日新增或更改的功能。
author: andreabichsel
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 624201841b512b01daf94d13e3d9fe7c381f5c11b328d57e22fbd73e1066bf88
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451899"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年五月 28 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3287。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>當您啟用各請假計劃多種類型時，LeaveRequest 實體無法運作 (447498)

隴著這項更改，**LeaveEnrollmentV2Entity** 現在已經開放用於改正啟用多個請假類型時發生的錯誤。

## <a name="batch-contention-reduction-feature-preview-446619"></a>減少批次競用功能 (預覽版) (446619)

當您啟用本功能時，您可以預期在選取任務和完成工作時，減少批次框架資料表的阻塞。

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>UpdateConflict 同時儲存背景工作角色可防止編輯 People 裡的記錄 (427915)

此項更改改正新增背景工作角色、更新地址資訊和更改語言喜好時的錯誤。 這個唯一的方案所顯示的錯誤會指出無法更新的記錄。 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>無法新增附件到已核准的請假要求重新提交 (425407)

此項更改現在允許附件到已核准的請假要求。

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>使用者可以按不同的法人實體形式輸入員工薪酬 (409529)

此項更改停用薪酬選項，防止意外輸入錯誤法人實體的薪酬記錄。

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>當您轉調員工，且背景工作角色職位指派日期比職位持續期間早時會出錯 (429402)

此時轉調員工的錯誤訊息已經更新到更能貼切說明改正問題需要的更改。

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>Employee 自助服務福利登記的附件功能
 
現在，您可以在福利登記流程中，針對員工登記的每項計劃新增附件。 接著您可以檢視 **背景工作角色登記的福利** 表單內的附件。

## <a name="in-preview"></a>預覽中

## <a name="human-resources-application-in-teams"></a>Teams 的人力資源應用程式

員工可以在 Microsoft Teams 內部檢視和要求下班時間。 他們可以 Bot 互動、建立請假要求。 更多資訊，請參閱 [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)。 

## <a name="leave-suspension"></a>請假暫停

您可以暫停員工在人力資源的請假和缺勤。 暫停請假會停止選取請假類型的請假累計。 如果累計處理之後發生暫停，暫停請假會對員工的請假餘數按比例調整。 更多資訊，請參閱[暫停請假](hr-leave-and-absence-suspend-leave.md)。

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>更新使用者體驗為指出累計已經暫停 (429550)

使用者體驗現在指出計劃的累計已經暫停。

## <a name="coming-soon"></a>即將推出

## <a name="database-logging-in-preview-in-june"></a>資料庫記錄 (六月預覽版)

資料庫記錄功能允許您判定應該監視的資料表和欄位。 它也讓您判定應該觸發追蹤修訂的事件。 查詢功能可用來查看這些隨著時間演變的變動。

## <a name="buy-and-sell-leave-in-preview-june-1"></a>買賣請假 (六月 1 日預覽版)

一些組織提供允許員工購買或銷售他們請假的福利。 這道流程徒往是手動管理。 本功能提供更自動化的方式管理人力資源部門的政策和要求，並且在簡化請假管理流程時，有助於消弭錯誤。 更多資訊，請參閱：

- [管理買賣請假政策](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [買賣請假](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>用在福利管理的資料管理框架 (DMF) 實體
 
福利管理實體發行中。 DMF 實體允許匯入和匯出資料，輕鬆配置福利管理。 福利管理範本也可開放用來移動資料。 範本依序匯出和匯入資料，尊重資料的依從性。

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>新增原因代碼到累計暫停 (六月 1 日)

原因代碼已經新增到累計暫停。

## <a name="carry-forward-rules-june-1"></a>結轉規則 (六月 1 日)

您可以針對轉移結轉調整的結轉餘數指明結轉假期類型。 例如，如果員工結轉 10 天，您可以為那 10 天選取不同的請假類型。 更多資訊，請參閱[配置請假和缺勤類型](hr-leave-and-absence-types.md)。

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>暫停特定請假類型的累計請假 (六月 1 日)

此次發行版本中，HR 可以針對無薪請假輸入請假要求的員工，建立暫停累請假的規則。 無薪假可以為類型，但不是必要選項。 您可以暫停以另一個請假類型為主的任何請假。

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>DMF 實體開放用於累計暫停 (六月 1 日)

DMF 實體現在開放用在累計暫停。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]