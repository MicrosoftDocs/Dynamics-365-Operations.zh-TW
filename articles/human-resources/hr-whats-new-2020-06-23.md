---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年六月 25 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年六月23 日新增或更改的功能。
author: andreabichsel
ms.date: 06/25/2020
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
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a89c0febbe2e4adca1508f106ffa7b84b5f14e2c
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452001"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年六月 23 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3347。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>當已離職員工的註冊到期時，請假類型、餘數和金額在 Leave 註冊表單全部清除 (444867)

現在選取 **請假類型**、**餘數** 和 **金額** 值時會維護而不是清除。

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>啟用新功能 (針對一間公司或一項計劃的 Leave 累計) 時的預測餘數不正確 (456553)

現在啟用一間公司或一項計劃的請假累計功能時，會顯示正確預測的餘數。

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>關係造成重複性瀏覽屬性的實體 (456486)

此次發行版本改正多實體瀏覽屬性 (關係) 的問題。 偵測到重複關係。 這些狀況都已經改正。
 
## <a name="cross-company-comments-on-performance-review-455536"></a>對於績效考核的跨公司意見 (455536)

隨著此次修正，現在可以在績效考核上看見跨公司意見。 這項更改改正不同公司針對相同績效考核輸入的考核人員意見視圖。
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>顯示薪酬管理資料的不一致 (432562)

現在，Manager 自助服務已經維持一致性的薪酬視圖。 依照您如何瀏覽到背景工作角色的 **薪酬細節** 方式，薪酬資料現在會一致性顯示給經理。
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>固定薪酬計劃的生效日期預設為今天日期 (411994)

薪酬開始日期現在是以指派給員工職位的開始日期為準。

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>請假和缺勤表單在表單打開時，停用半天定義 (452607)

隨著這項更改，**啟用半天定義** 將啟用到存在新請假交易為止。 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>無法透過 Excel 發佈到 HcmDiscussionEntity；TotalRatingScore 欄位錯誤 (453899)

您現在可以使用 Excel 活頁簿設計器的 **HCMDiscussionEntity** 更新 **TotalRatingScore** 欄位。

## <a name="in-preview"></a>預覽中

## <a name="database-logging"></a>資料庫記錄

資料庫記錄功能允許您判定預計監視的資料表和欄位。 它也讓您判定應該觸發追蹤修訂的事件。 您可以使用資料庫記錄功能查看隨時間進行的更改。 更多資訊，請參閱 [Configure 和管理資料庫記錄](hr-admin-database-logging.md)。

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

客戶可以處理一間公司或一項請假和缺勤計劃的累計項目。 本功能針對請假年數或請假累計政策不同的客戶提供清晰的累計流程。 更多資訊，請參閱[每間公司或每項請假計劃的累計請假數](hr-leave-and-absence-accrue.md)。

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

## <a name="configure-the-name-of-employee-self-service"></a>配置 Employee 自助服務的名稱

**人力資源參數** 將開放新選項更新 Employee 自助服務工作區的名稱為 Self 服務。

## <a name="checklist-entities-included-in-dataverse"></a>核對清單實體納入 Dataverse

到職、離職、調動和業務流程核對清單實體將很快在 Dataverse 內開放使用。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]