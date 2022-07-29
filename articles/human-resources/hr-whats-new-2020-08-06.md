---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年八月 06 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2020 年八月06 日新增或更改的功能。
author: andreabichsel
ms.date: 08/06/2020
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
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dbcf854330b7c5ba6ca812a5aed384584c05ce8d
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452028"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年八月 06 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題說明 Dynamics 365 Human Resources 新增或更改的功能。 更改適用組建編號 8.1.3444。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="platform-update-1001236-is-now-available"></a>平台更新 10.0.12(36) 現在問市

更多資訊，請參閱 [財務與營運應用程式版本 10.0.12 的平台更新 (2020 年八月)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12.md)。

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>用在福利管理的資料管理框架 (DMF) 實體
 
福利管理實體發行中。 DMF 實體允許您匯入和匯出資料，輕鬆配置福利管理。 福利管理範本將開放用來移動資料。 範本按照順匯出和匯入資料，尊重資料的依從性。 更多資訊，請參閱：

- [DMF 實體支援](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support)在 Dynamics 365 2020 發行版本第一波計劃
- [資料管理概觀](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>Claire 建立用來購買和銷售請假要求的工作流程 (446557)

更多資訊，請參閱：

- [允許員工買賣請假](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave)在 Dynamics 365 2020 發行版本第 2 波計劃
- [管理買賣請假政策](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [買賣請假](./hr-employee-self-service-buy-sell-leave.md)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>背景工作角色地址 V2 實體具備限制性的跨法人實體存取權 (459126)

隨著這項更改，**背景工作角色郵寄地址 V2** 實體將根據給使用者的法人實體存取權限制。

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>工作流程電子郵件超連結無法打開相關考核 (437398)

當您使用預留位置打開考核工作流程的績效考核時，電子郵件產生的超連結現在會打開選取的記錄。

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>買賣請假的新實體 (473180)

資料管理框架實體現在可用來買賣請假。 更多資訊，請參閱[資料管理概觀](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)。

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>檢視記錄資訊和使用進階篩選條件時，使用者可以存取其他員工的記錄 (472490)

隨著這項更改，Employee 自助服務使用者在使用員工自助服務時，只能存取自己的記錄。 更改篩選選項的同時檢視記錄資訊不再公開其他資料。

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>人事管理分析包括已離職背景工作角色記錄 (382893)

隨著此次發行版本，人事管理分析現在只包括在職員工。 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>無法為員工處理加薪 (473125)

這項更改允許您在更改新加薪的生效日期時輸入加薪。

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>考核工作流程可以多次啟動 (467541)

隨著這項更改，您只能啟動一次績效考核工作流程。 經理的狀態不再顯示開始考核的選項。

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>取消已核准的請假要求時，請假要求工作流程以錯誤結束 (472063)

此次發行版本中，當您取消已核准的請假要求，要求狀態不再保持已核准，而工作流程將會繼續。

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>從範本建立新考核時，系統建議已離職的背景工作角色 (460624)

隨著這項更改，從範本建立新考核時，已離職的背景工作角色不再開放使用。 您不能為僱用日期之外的員工建立考核。

## <a name="position-hierarchy-circular-reference-detection-415879"></a>職位階層結構循環參考偵測 (415879)

隨著這項更改，職位階層結構循環參考偵測只限於單一時間點。 您可以針對不同日期執行循環參考偵測，驗證報表結構不執行循環參考。

## <a name="buy-and-sell-leave"></a>買賣請假 

一些組織提供允許員工購買或銷售他們請假的福利。 這道流程徒往是手動管理。 此功能自動管理人力資源部門的政策和要求。 它簡化請假管理流程並有助於消除錯誤。 更多資訊，請參閱：

- [允許員工買賣請假](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave)在 Dynamics 365 2020 發行版本第 2 波計劃
- [管理買賣請假政策](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [買賣請假](./hr-employee-self-service-buy-sell-leave.md)

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

## <a name="in-preview"></a>預覽中

### <a name="mandatory-fields"></a>必填欄位

您可以借助人力資源個人化功能將欄位設為必填欄位。 此功能需要 **已儲存的視圖**。 更多有關已儲存視圖的資訊，請參閱：

- [已儲存的視圖 - 全面開放使用](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)在 Dynamics 365 2020 發行版本第 2 波計劃
- [建構完整利用已儲存視圖的表單](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Teams 的人力資源應用程式

員工可以在 Microsoft Teams 內部檢視和要求下班時間。 他們可以 Bot 互動、建立請假要求。 更多資訊，請參閱：

- [Microsoft Teams 的員工請假和缺勤經驗](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams)在 Dynamics 365 2020 發行版本第一波計劃
- [Teams 的人力資源應用程式](./hr-admin-teams-leave-app.md)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF 實體開放用在累計暫停

DMF 實體現在開放用在累計暫停。

## <a name="coming-soon"></a>即將推出

## <a name="checklist-entities-included-in-dataverse"></a>核對清單實體納入 Dataverse

到職、離職、調動和業務流程核對清單實體將很快在 Dataverse 開放使用。

## <a name="known-issues"></a>已知問題

**功能管理** 工作區可能顯示全面開放使用時，作為預覽功能停用的功能。 下面是顯示不正確狀態的全面開放使用功能清單。 

1.  福利管理
2.  案例管理
3.  資料庫記錄 (稽核中)
4.  針對一間公司或一項計劃的請假累計
5.  請假和缺勤累計暫停
6.  餘數調整原因代碼和評論意見
7.  買賣請假
8.  請假和缺勤行事曆
9.  請假結轉規則
10. 請假累計稽核中
11. 請假累計刪除
12. 請假累計進位
13. 在單一請假計劃配置多種請假類型
14. 更新休假強化功能
15. 使用員工的 FTE 進行累計
16. 跨公司薪酬視圖
17. 列印績效考核
18. 請假累計假期改正

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]