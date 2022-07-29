---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年五月 14 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年五月14 日新增或更改的功能。
author: andreabichsel
ms.date: 05/14/2020
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
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb4693f3c856e7abcc39cbd658183d01ec98a066
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452064"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年五月 14 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3244。 某些標題括號裡的數字意指 Lifecycle Services (LCS) 支援參考的編號。

## <a name="platform-changes"></a>平台變動

本週的發行版本包括平台更改。 更多資訊，請參閱 [財務和營運應用程式版本 10.0.10 的平台更新 (2020 年五月)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34.md)。 此次發行版本包括 BUG 修正和已儲存視圖的更改。
 
## <a name="ensure-dataverse-picklists-are-consistent-with-leave-enums-436343"></a>確保 Dataverse 挑選清單與 Leave 列舉項目一致 (436343)

Dataverse 挑選清單現在與 Leave 列舉項目一致。

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>允許使用者根據要求數額配置請假要求工作流程 (300044)

使用者可以根據要求數額配置請假要求工作流程。
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>啟用進階安全性時，新背景工作角色表單透過檢視功能表公開資料 (403185)

此次發行版本改正啟用進階存取，以及其他公司的背景工作角色可以存取時，如何跨法人實體檢視背景工作角色的方式。

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>允許針對單一計劃或單一公司執行請假累計 (318844)

隨著這項更改，您可以為公司或計劃執行累計功能。
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>在已註冊背景工作角色表單顯示職位的全職等效 (FTE) (414658)

當請假類型啟用 FTE 選項時，來自背景工作角色職位的 FTE 值判定背景工作角色的累計費率。 本欄位現在納入 **已註冊背景工作角色** 表單和 **大規模註冊** 對話。

## <a name="add-leave-balance-expiration-batch-job-431266"></a>新增請假餘數到期批次工作 (431266)

現在開放每日執行的新批次工作。 當到期日期變成當日時，它減少剩餘的請假餘數。

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>使用背景工作角色個人聯絡人實體匯出員工的個人聯絡人動作，不會連帶匯出父系關係類型的個人聯絡人 (345893)

**背景工作角色個人聯絡人** 資料實體 (在 DMF 的 **HcmPersonalContactPersonEntity** 和 OData 的 **個人聯絡人**) 無法匯出 **父系** 關係類型的個人聯絡人。 此問題已針對這項更改後建立的個人聯絡人修正。 既有的 **父系** 個人聯絡人類型將在之後的發行版本中修正。

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>當標記為請假和缺勤並且啟用簡化的員工表單時，原因代碼會顯示在不同的方案中 (434163)

當您啟用簡化的員工輸入時，此項更改將原因代碼限制為僅限請假和缺勤代碼。

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>預覽功能指派請假計劃給未來的員工顯示錯誤 (433555)

此項更改改正當請假計劃指派兩種請假類型，並且您試圖指派員工時的錯誤。

## <a name="getting-started-banner-appears-for-all-users-441731"></a>所有使用者出現開始橫幅 (441731)

隨著這項更改，非系統管理員或資料管理管理員的使用者會隱藏開始橫幅。 

## <a name="the-dataverse-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>Dataverse 背景工作角色地址實體在人力資源中的日期時間生效日期方面，有不同的工作方式 (425071)

此項更改根據地址的日期，保持特定方案的地址資訊對齊。

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>無法新增附件到已核准的請假要求 (425407)

隨著本週的發行版本，您可以新增附件到已核准的請假要求，不必更改請假要求。

## <a name="in-preview"></a>預覽中

## <a name="leave-suspension"></a>請假暫停

您可以暫停員工在人力資源的請假和缺勤。 暫停請假會停止選取請假類型的請假累計。 如果累計處理之後發生暫停，暫停請假會對員工的請假餘數按比例調整。 更多資訊，請參閱[暫停請假](hr-leave-and-absence-suspend-leave.md)。

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>更新使用者體驗為指出累計已經暫停 (429550)

使用者體驗現在指出計劃的累計已經暫停。

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>暫停特定請假類型的累計請假 (272447)

此次發行版本中，HR 可以針對無薪請假輸入請假要求的員工，建立暫停累請假的規則。 無薪假可以為類型，但不是必要選項。 您可以暫停以另一個請假類型為主的任何請假。

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>DMF 實體開放用於累計暫停 (429549)

DMF 實體現在開放用在累計暫停。

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>新增原因代碼到累計暫停 (429547)

原因代碼已經新增到累計暫停。

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>開始從人力資源參數過渡到請假和缺勤參數

此次發行版本開始結合人力資源參數和請假與缺勤參數。

## <a name="carry-forward-rules"></a>結轉規則

您可以針對轉移結轉調整的結轉餘數指明結轉假期類型。 例如，如果員工結轉 10 天，您可以為那 10 天選取不同的請假類型。 更多資訊，請參閱[配置請假和缺勤類型](hr-leave-and-absence-types.md)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]