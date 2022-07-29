---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年七月 23 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年七月23 日新增或更改的功能。
author: andreabichsel
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1dd8ab95d37c2fbc5d7453fadeae043677c30160
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452061"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年七月 23 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3416。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a>刪除職位的財務維度動作無法如預期成功 (445476)

現在從某個職位移除維度等於是從 Dataverse 移除那些相同職位。

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a>不在階層結構的職位顯示無效職位 (397257)

無效職位 (持續期間已到期)，不再以 **不在階層結構的職位** 顯示在職位階層結構中。 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a>資料管理框架 (DMF) 匯入 LeaveEnrollmentEntity 和 HcmWorkerEntity 之間發生的驗證造成資料載入緩慢 (442324)

此次發行版本的更改提高 **LeaveEnrollmentEntity** 的效能。

## <a name="unable-to-personalize-in-organization-administration-447490"></a>無法在組織管理中個人化 (447490)

此項更改讓您現在可以個人化 **組織管理** 中的連結。

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

客戶可以處理一間公司或一項請假和缺勤計劃的累計項目。 本項功能針對請假年數或請假累計政策不同的客戶提供累計流程的 Clarity。 更多資訊，請參閱[每間公司或每項請假計劃的累計請假數](hr-leave-and-absence-accrue.md)。

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

## <a name="platform-changes"></a>平台變動

平台更新 10.0.十二月(36)

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]