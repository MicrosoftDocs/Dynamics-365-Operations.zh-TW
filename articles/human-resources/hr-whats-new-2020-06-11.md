---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年六月 11 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年六月11 日新增或更改的功能。
author: andreabichsel
ms.date: 06/16/2020
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
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f7e8f2b158f3d3274fee87f94c69c599380f2e2c06cf0bd2284f963d46d81c02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451914"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年六月 11 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.3316。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>簡化的員工表單偶爾會造成子系表單關閉 (X) 按鈕停止工作 (442369)

當新 **背景工作角色** 表單已經啟用時，關閉 (**X**) 按鈕偶爾對子系表單無效。 此問題是間歇性問題。 您可以在離開並返回表單後關閉表單。 例如，您可以選取左側的功能表項目，然後回頭瀏覽 **背景工作角色** 表單並且接著關閉。 本週的發行版本解決這項問題。 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>背景工作角色個人聯絡人實體不匯出父系關係類型的個人聯絡人

此次發行版本中，**背景工作角色個人聯絡人** 實體匯出所有關係類型。

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>HcmPositionWorkerAssignmentV2Entity 預設應該是 Ceridian 工資單整合包的一部分 (448506)

這項更改將 **HcmPositionWorkerAssignmentV2Entity** 納入 Ceridian 工資單整合包。

## <a name="in-preview"></a>預覽中

## <a name="database-logging"></a>資料庫記錄

資料庫記錄功能允許您判定預計監視的資料表和欄位。 它也讓您判定應該觸發追蹤修訂的事件。 您可以使用資料庫記錄功能查看隨時間進行的更改。 更多資訊，請參閱 [Configure 和管理資料庫記錄](hr-admin-database-logging.md)。

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

## <a name="new-platform-capabilities"></a>新平台功能 

您將可以藉由使用個人化功能使欄位成為必填。 本項功能將要求您啟用 **儲存的視圖**。

## <a name="configure-the-name-of-employee-self-service"></a>配置 Employee 自助服務的名稱

人力資源參數將開放使用新選項，更新 Employee 自助服務工作區的名稱為 Self 服務。 

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]