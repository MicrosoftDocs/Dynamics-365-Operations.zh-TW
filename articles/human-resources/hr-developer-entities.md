---
title: Dataverse 資料表
description: Microsoft Dynamics 365 Human Resources 使用 Dataverse 啟用擴充性和整合方案。
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6774fad3543d80d04faacf5960c8037f1734f084
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452271"
---
# <a name="dataverse-tables"></a>Dataverse 資料表


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources 使用 Dataverse 啟用擴充性和整合方案。

> [!NOTE]
> 人力資源實體對應到 Dataverse 資料表。 更多有關 Dataverse (前身為 Common Data Service) 和術語更新的資訊，請參閱[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)

下列 Dataverse 資料表以人力資源實體為基礎開放使用。

## <a name="benefit-tables"></a>福利資料表

| 姓名 | 表格 |
| --- | --- |
| 福利計算週期次數 | cdm_benefitcalculationfrequency |
| 福利計算週期次數支薪期間 | cdm_benefitcalculationfrequencypayperiod |
| 福利計算率 | cdm_benefitcalculationrate |
| 福利計算率詳細資料 | cdm_benefitcalculationratedetail |
| 福利選項 | cdm_benefitoption |
| 福利計劃 | cdm_benefitplan (未啟用自訂欄位支援) |
| 福利類型 | cdm_benefittype |

## <a name="business-process-tasks-tables"></a>商務程序任務資料表

| 姓名 | 表格 |
| --- | --- |
| 業務流程行事曆 | cdm_businessprocesscalendar |
| 業務流程群組指派 | cdm_businessprocessgroupassignment |
| 業務流程文件庫工作群組 | cdm_businessprocesslibrarytaskgroup |
| 業務流程階段 | cdm_businessprocessstage |
| 檢查清單範本標題 | cdm_businessprocesstemplateheader |
| 檢查清單範本工作 | cdm_businessprocesstemplatetask |

## <a name="compensation-tables"></a>薪酬資料表

| 姓名 | 表格 |
| --- | --- |
| 薪資固定計劃 | cdm_compensationfixedplan |
| 薪資方格 | cdm_compensationgrid |
| 薪資等級 | cdm_compensationlevel |
| 支薪頻率次數 | cdm_compensationpayfrequency |
| 薪資參考點設定 | cdm_compensationreferencepointsetup |
| 薪資參考點設定行 | cdm_compensationreferencepointsetupline |
| 薪資地區 | cdm_compensationregion |
| 薪資結構 | cdm_compensationstructure |
| 薪資可變計劃 | cdm_compensationvariableplan |
| 薪資可變計劃等級 | cdm_compensationvariableplanlevel |
| 薪資可變計劃類型 | cdm_compensationvariableplantype |
| 固定薪資事件 | cdm_fixedcompensationevent |
| 配股規則 | cdm_vestingrule |
| 工作者固定薪資 | cdm_workerfixedcompensation |

## <a name="organization-tables"></a>組織資料表

| 姓名 | 表格 |
| --- | --- |
| 部門 | cdm_department |
| 雇用 | cdm_employment |
| 公司 | cdm_company |
| 工作 | cdm_job |
| 職務 | cdm_jobfunction |
| 職位 | cdm_jobposition |
| 職位類型 | cdm_positiontype |
| 職位工作者指派 | cdm_positionworkerassignmentmap |
| 工作職位維度 | cdm_jobpositiondimension|
| 職務類型 | cdm_jobtype |
| 語言 | cdm_language |
| 標題 | cdm_title |

> [!NOTE]
> **職位類型**、**職位背景工作角色指派** 和 **就業** 財務維度單向整合 Dataverse。 財務維度更新目前無法同步 Dataverse 到人力資源。 

## <a name="leave-and-absence-tables"></a>請假和缺勤資料表

| 姓名 | 表格 |
| --- | --- |
| 休假銀行交易 | cdm_leavebanktransaction |
| 休假註冊 | cdm_leaveenrollment |
| 休假計劃 | cdm_leaveplan |
| 休假要求 | cdm_leaverequest |
| 休假要求詳細資料 | cdm_leaverequestdetail |
| 休假類型 | cdm_leavetype |
| 休假類型原因代碼 | cdm_leavetypereasoncode |

## <a name="payroll-tables"></a>工資單資料表

| 姓名 | 表格 |
| --- | --- |
| 支薪週期 | cdm_paycycle |
| 支薪期間 | cdm_payperiod |
| 薪資表薪資代碼 | cdm_payrollearningcode |
| 銀行帳戶撥付 | cdm_bankaccountdisbursement |
| 徵稅地區 | cdm_taxregion |

## <a name="worker-tables"></a>背景工作角色資料表

| 姓名 | 表格 |
| --- | --- |
| 工作人員 | cdm_worker |
| 工作者地址 | cdm_workeraddress |
| 工作者個人詳細資料 | cdm_workerpersonaldetail |
| 工作者個人識別碼編號 | cdm_workerpersonidentificationnumber |
| 工作者個人識別碼類型 | cdm_workerpersonidentificationtype |
| 工作行事曆 | cdm_workcalendar |
| 工作行事曆日 | cdm_workcalendarday |
| 工作行事曆假日 |cdm_workcalendarholiday |
| 工作行事曆假日行 | cdm_workcalendarholidayline |
| 工作行事曆時間間隔 | cdm_workcalendartimeinterval (未啟用自訂欄位支援) |
| 工作者銀行帳戶 | cdm_workerbankaccount |

## <a name="worker-setup-tables"></a>背景工作角色設定資料表

| 姓名 | 表格 |
| --- | --- |
| 專家狀態 | cdm_veteranstatus |
| 種族血統 | cdm_ethnicorigin |
| 原因代碼 | cdm_reasoncode |
| 個人識別碼核發機構 | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>適任度資料表

| 姓名 | 表格 |
| --- | --- |
| 技能類型 | cdm_skilltype |

## <a name="table-relationship-models"></a>資料表關係模型

### <a name="worker"></a>工作人員

![背景工作角色。](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>工作和工作職位

![工作和工作職位。](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>福利

![福利。](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>薪酬

![薪酬。](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>離開

![請假。](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>工作行事曆

![背景工作角色行事曆。](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>也請參閱

[請選擇資料整合技術](hr-admin-integration-choose-technology.md)<br>
[配置 Dataverse 整合](hr-admin-integration-common-data-service.md)<br>
[配置 Dataverse 虛擬資料表](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[人力資源虛擬資料表常見問答集](hr-admin-virtual-entity-faq.md)<br>
[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)<br>
[術語更新](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
