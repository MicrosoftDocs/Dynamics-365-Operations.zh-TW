---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年七月 08 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年七月8 日新增或更改的功能。
author: andreabichsel
ms.date: 07/08/2020
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
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a574436bc7762fbee722af8be2f923d18d01e5b
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451989"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年七月 8 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3382。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="database-logging"></a>資料庫記錄

資料庫記錄功能允許您判定預計監視的資料表和欄位。 它也讓您判定應該觸發追蹤修訂的事件。 您可以使用資料庫記錄功能查看隨時間進行的更改。 更多資訊，請參閱 [Configure 和管理資料庫記錄](hr-admin-database-logging.md)。

## <a name="configure-the-name-of-employee-self-service"></a>配置 Employee 自助服務名稱

您現在可以在 **人力資源參數** 將 **Employee 自助服務** 工作區名稱更改為 **Self 服務**。 更多資訊，請參閱[更改 Employee 自助服務工作區名稱](hr-employee-self-service-workspace-name.md)

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>超出期間以外的福利管理開放註冊存取權限

此次發行版本已修正員工可能在註冊期間以外或沒有生活事件情況下，存取福利公開註冊的錯誤。 所以，如果您需要在 Employee 自助服務中示範開放註冊，您必須將開放註冊日期調整為今天 (或更早)，使其可以存取。 您可以在 **福利管理 > 規則和選項期間** 下方更改此項設定。

## <a name="email-employee-enrollment-confirmation"></a>電子郵件員工註冊確認

您現在可以在員工完成福利選取後，傳送電子郵件給他們。 您可以傳送預設訊息或使用組織電子郵件範本。 這些設定皆在 **人力資源參數 > 福利管理** 下方。

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>取消的請假仍會在 People 工作區上即將到來的休假中出現 (441358)

取消的請假在 **People** 工作區的請假卡上不再顯示為即將到來的休假。

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>無法在 PositionV2 實體使用部門實體屬性 (456486)

您現在可以新增部門，不必建立重覆關係。

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>PayrollWorkerEnrolledBenefitDetailEntity 應該只將計算的欄位用在退休計劃 (459779)

匯出 **PayrollWorkerEnrolledBenefitDetailEntity** 實體時，匯出會同時判定是否應該根據費率表使用計算的欄位或是使用支援表上的 **ContributionAmountCur** 欄位。 資料實體使用的邏輯是在應用程式正常不使用情況下使用費率表。 此邏輯造成實體匯出此欄位並傳回零值，因為沒有計算費率表，而產品不允許客戶指定一個。
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>Personnel 管理和 Employee 自助服務中的捷克語翻譯讓人困惑 (400276)

此次發行版本改正 **公司產品型錄**、**下一個註冊課程**、**工作** 和 **職位** 的翻譯。
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>WorkCalendarEmployment 資料表並未啟用已建立和修改的系統欄位 (460171)

已建立和修改的系統欄位現在在人力資源的 **WorkCalendarEmployment** 資料表啟用。
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>Hire 的空值參考例外情況以及針對未來員工新增細節 (455475)

此次發行版本改正當您使用 **Hire 和新增細** 選項錄用員工時，簡化員工輸入的錯誤 (空值參考)。

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a>Dataverse 背景工作角色實體進行的更改不會反映在人力資源 (455652)

針對下列 Dataverse 的 **背景工作角色** 實體欄位進行的更改現在將在人力資源顯現：

- **居家工作**
- **資歷日期**
- **週年紀念日**
- **原始錄用日期**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>正確的薪酬等級預設不以指派給該職位的工作為主 (394136)

隨著此項更改，正確的薪酬等級預設是以 **薪酬計劃指派****職位細節** 和 **開始日期** 的 **生效日期** 記錄為主。

## <a name="in-preview"></a>預覽中

## <a name="mandatory-fields"></a>必填欄位 

您現在可以借助人力資源個人化功能將欄位設為必填欄位。 此功能需要 **已儲存的視圖**。

## <a name="human-resources-application-in-teams"></a>Teams 的人力資源應用程式

員工可以在 Microsoft Teams 內部檢視和要求下班時間。 他們可以 Bot 互動、建立請假要求。 更多資訊，請參閱 [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)。 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>用在福利管理的資料管理框架 (DMF) 實體
 
福利管理實體發行中。 DMF 實體允許您匯入和匯出資料，輕鬆配置福利管理。 福利管理範本將開放用來移動資料。 範本按照順匯出和匯入資料，尊重資料的依從性。

## <a name="buy-and-sell-leave"></a>買賣請假 

一些組織提供允許員工購買或銷售他們請假的福利。 這道流程徒往是手動管理。 此功能自動管理人力資源部門的政策和要求。 它簡化請假管理流程並有助於消除錯誤。 更多資訊，請參閱：

- [管理買賣請假政策](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [買賣請假](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>針對一間公司或一項計劃的請假累計

客戶可以處理一間公司或一項請假和缺勤計劃的累計項目。 本功能針對請假年數或請假累計政策不同的客戶提供累計流程的 Clarity。 更多資訊，請參閱[每間公司或每項請假計劃的累計請假數](hr-leave-and-absence-accrue.md)。

## <a name="add-attachments-to-time-off-requests"></a>新增附件到休假要求

新增附件到已核准的請假要求能力對目前的 COVID-19 環境很關鍵。 員工現在可以新增這些附件。 他們也可以更深入解析如何更新請假要求。 更多資訊，請參閱[新增附件到既有的要求](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request)。

## <a name="add-reason-code-to-accrual-suspensions"></a>新增原因代碼到累計暫停 

原因代碼已經新增到累計暫停。

## <a name="carry-forward-rules"></a>結轉規則 

您可以針對轉移結轉調整的結轉餘數指明結轉假期類型。 例如，如果員工結轉 10 天，您可以為那 10 天選取不同的請假類型。 更多資訊，請參閱[配置請假和缺勤類型](hr-leave-and-absence-types.md)。

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>暫停特定請假類型的請假累計

您可以針對無薪請假輸入請假要求的員工，建立暫停請假累計規則。 無薪假可以為類型，但不是必要選項。 您可以暫停以另一個請假類型為主的任何請假。

## <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF 實體開放用在累計暫停 

DMF 實體現在開放用在累計暫停。

## <a name="coming-soon"></a>即將推出

## <a name="checklist-entities-included-in-dataverse"></a>核對清單實體納入 Dataverse

到職、離職、調動和業務流程核對清單實體將很快在 Dataverse 開放使用。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]