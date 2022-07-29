---
title: 配置與 Finance 的整合
description: 本主題說明 Dynamics 365 Human Resources和 Dynamics 365 Finance 之間的整合。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0a2c5dd0ce97f33f5f8b65c801fbc15dfc65e8d4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452088"
---
# <a name="configure-integration-with-finance"></a>配置與 Finance 的整合


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



若要整合 Dynamics 365 Human Resources 和 Dynamics 365 Finance，您可以使用 [Data Integrator](/powerapps/administrator/data-integrator) 裡 Human Resources to Finance 範本。 Human Resources to Finance 範本啟用工作、職位和背景工作角色的資料流。 此範本允許資料從人力資源流入 Finance，但不允許資料從 Finance 流入人力資源。

![Human Resources to Finance 的整合流。](./media/hr-admin-integration-finance-flow.png)

Human Resources to Finance 解決方案提供的資料同步類型如下：

- 維護人力資源工作並從人力資源同步到 Finance
- 維護人力資源職位和職位指派並從人力資源同步到 Finance
- 維護人力資源的就業並從人力資源同步到 Finance
- 維護人力資源背景工作角色及其地址並從人力資源同步到 Finance

## <a name="system-requirements-for-human-resources"></a>人力資源系統要求

整合解決方案需要下列的 Human Resources and Finance 版本： 

- Dataverse 上的 Dynamics 365 Human Resources
- Dynamics 365 Finance 7.2 版本及更新版本

## <a name="template-and-tasks"></a>範本和工作

存取 Human Resources to Finance 範本。

1. 打開 [Power Apps 系統管理中心](https://admin.powerapps.com/)。 

2. 選取 **專案**，然後選取右上角的 **新專案**。 針對您希望在 Finance 整合的每個法人實體建立新專案。

3. 選取 **人力資源 (人力資源 Dataverse 到 Finance)** 將記錄從人力資源同步到 Finance。

此範本使用下列基本任務將記錄從人力資源同步到 Finance：

- **工作職能到薪酬工作職能**
- **部門到營運單位**
- **工作類型到薪酬工作類型**
- **工作到工作**
- **工作到工作細節**
- **職位類型到職位類型**
- **工作職位到基本職位**
- **工作職位到職位細節**
- **工作職位到職位持續時間**
- **工作職位到職位階層結構**
- **背景工作角色到背景工作角色**
- **就業到就業**
- **就業到就業細節**
- **職位背景工作角色指派到職位背景工作角色指派**
- **背景工作角色地址到背景工作角色通訊地址 V2**

## <a name="template-mappings"></a>範本測繪

在下列範本測繪資料表中，任務名稱包含每個應用程式使用的實體。 來源 (人力資源) 在左側，目的地 (Finance) 在右側。

### <a name="job-functions-to-compensation-job-function"></a>工作職能到薪酬工作職能

| Dataverse 資料表 (來源) | Finance 實體 (目的地) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job 函數名稱)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | 說明   (說明)                 |

### <a name="departments-to-operating-unit"></a>部門到營運單位

| Dataverse 資料表 (來源)           | Finance 實體 (目的地) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | 姓名 (姓名)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>工作類型到薪酬工作類型

| Dataverse 資料表 (來源)   | Finance 實體 (目的地) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | 說明   (說明)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>工作到工作

| Dataverse 資料表 (來源)                           | Finance 實體 (目的地)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | 說明   (說明)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>工作到工作細節

| Dataverse 資料表 (來源)                             | Finance 實體 (目的地) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name   (工作類型 (工作類型名稱))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name   (工作職能 (工作職能名稱)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (生效日期)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (失效日期)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (預設全職等職)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>職位類型到職位類型

| Dataverse 資料表 (來源)       | Finance 實體 (目的地) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | 說明   (說明)                 |
| cdm_classification   (cdm_classification) | 分類   (分類)           |

### <a name="job-positions-to-base-position"></a>工作職位到基本職位

| Dataverse 資料表 (來源)           | Finance 實體 (目的地) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (工作職位編號) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>工作職位到職位細節

| Dataverse 資料表 (來源)              | Finance 實體 (目的地)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber  (工作職位編號)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name   (工作 (名稱))                                        | JOBID (JOBID)                                    |
| cdm_description   (cdm_description)                                        | 說明   (說明)                       |
| cdm_departmentid.cdm_departmentnumber   (部門 (部門編號)) | DEPARTMENTNUMBER   (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name   (職位類型 (名稱))                     | POSITIONTYPEID   (POSITIONTYPEID)                 |
| cdm_avaialableforassignment   (可以指派)                 | AVAILABLEFORASSIGNMENT   (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom   (生效日期)                                            | VALIDFROM   (VALIDFROM)                           |
| cdm_validto (失效日期)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent   (全職等職)                           | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>工作職位到職位持續時間

| Dataverse 資料表 (來源)             | Finance 實體 (目的地) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (工作職位編號)   | POSITIONID (POSITIONID)                      |
| 計算啟動 (計算啟動) | VALIDFROM (VALIDFROM)                        |
| 計算退休 (計算退休) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>工作職位到職位階層結構

| Dataverse 資料表 (來源)        | Finance 實體 (目的地) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (工作職位編號)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (生效日期)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (失效   日期)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>背景工作角色到背景工作角色
| Dataverse 資料表 (來源)           | Finance 實體 (目的地)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate   (cdm_birthdate)               | BIRTHDATE   (BIRTHDATE)                           |
| cdm_gender   (cdm_gender)                     | GENDER (GENDER)                                   |
| cdm_primaryaddress   (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL   (PRIMARYCONTACTEMAIL )      |
| cdm_primarytelephone   (cdm_primarytelephone) | PRIMARYCONTACTPHONE   (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity   (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK   (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity   (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER   (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity   (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN   (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl   (cdm_websiteurl)             | PRIMARYCONTACTURL   (PRIMARYCONTACTURL)           |
| cdm_firstname   (cdm_firstname)               | 名字 (名字)                           |
| cdm_middlename   (cdm_middlename)             | MIDDLENAME   (MIDDLENAME)                         |
| cdm_lastname   (cdm_lastname)                 | 姓氏 (姓氏)                               |
| cdm_workernumber   (cdm_workernumber)         | PERSONNELNUMBER   (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | WORKERTYPE   (WORKERTYPE)                         |
| cdm_state   (cdm_state)                       | WORKSTATUS   (WORKERSTATUS)                       |

### <a name="employments-to-employment"></a>就業到就業

| Dataverse 資料表 (來源)                             | Finance 實體 (目的地) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)     |
| cdm_workertype   (cdm_workertype)                               | WORKERTYPE   (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>就業到就業細節

| Dataverse 資料表 (來源)                             | Finance 實體 (目的地)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE)   |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)       |
| cdm_validfrom   (生效日期)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (失效   日期)                                        | VALIDTO (VALIDTO)                             |
| cdm_workerstartdate   (cdm_workerstartdate)                     | WORKERSTARTDATE   (WORKERSTARTDATE)           |
| cdm_lastdateworked   (cdm_lastdateworked)                       | LASTDATEWORKED   (LASTDATEWORKED)             |
| cdm_transitiondate   (cdm_transitiondate)                       | TRANSITIONDATE   (TRANSITIONDATE)             |
| cdm_employerunitofnotice   (cdm_employerunitofnotice)           | EMPLOYERUNITOFNOTICE   (EMPLOYERUNITOFNOTICE) |
| cdm_workerunitofnotice   (cdm_workerunitofnotice)               | WORKERUNITOFNOTICE   (WORKERUNITOFNOTICE)     |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)               |
| cdm_employernoticeamount   (cdm_employernoticeamount)           | EMPLOYERNOTICEAMOUNT   (EMPLOYERNOTICEAMOUNT) |
| cdm_workernoticeamount   (cdm_workernoticeamount )              | WORKERNOTICEAMOUNT   (WORKERNOTICEAMOUNT)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>職位背景工作角色指派到職位背景工作角色指派

| Dataverse 資料表 (來源)                             | Finance 實體 (目的地)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_jobpositionnumber   (工作職位編號)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom   (生效日期)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (失效日期)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>背景工作角色地址到背景工作角色通訊地址 V2

| Dataverse 資料表 (來源)                             | Finance 實體 (目的地)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSLOCATIONROLES   (ADDRESSLOCATIONROLES) |
| cdm_line1   (cdm_line1)                                         | ADDRESSSTREET   (ADDRESSSTREET)               |
| cdm_city (cdm_city)                                             | ADDRESSCITY   (ADDRESSCITY)                   |
| cdm_stateorprovince   (cdm_stateorprovince)                     | ADDRESSSTATE   (ADDRESSSTATE)                 |
| cdm_postalcode   (cdm_postalcode)                               | ADDRESSZIPCODE(ADDRESSZIPCODE)                |
| cdm_countryregion   (cdm_countryregion)                         | ADDRESSCOUNTRYREGION(ADDRESSCOUNTRYREGION)    |
| cdm_addressnumber   (cdm_addressnumber)                         | ADDRESSLOCATIONID(ADDRESSLOCATIONID)          |
| cdm_ispreferred   (cdm_ispreferred)                             | ISPRIMARY   (ISPRIMARY)                       |
| cdm_county   (cdm_county)                                       | ADDRESSCOUNTYID(ADDRESSCOUNTYID)              |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSDESCRIPTION(ADDRESSDESCRIPTION)        |

## <a name="integration-considerations"></a>整合考量因素

從人力資源到 Finance 的整合根據識別碼符合記錄。 如果記錄符合，Data Integrator 會以人力資源值覆寫 Finance 資料。 然而如果邏輯上這些是不同的記錄，而且相同識別碼是在人力資源或 Finance 根據各別編號順序產生，則可能發生問題。

這個問題可能發生在 **背景工作角色** 身上，它使用 **人事編號** 和 **職位** 配對。 工作不使用編號順序。 於是，如果人力資源和 Finance 的工作識別碼相同，則人力資源資料會覆寫 Dynamics 365 Finance 資訊。 

為了預防識別碼重覆的問題，您可以在[編號順序](/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json)上新增前綴詞，或在其怹系統範圍以外的編號順序上設定起始編號。 

用在背景工作角色地址的位置識別碼並不是編號順序的一部分。 將背景工作角色從人力資源部整合到 Finance 時，如果 Finance 已經存在背景工作角色地址，可能因此建立重覆的地址記錄。 

下圖顯示 Data Integrator 的範本測繪範例。 

![範本測繪。](./media/IntegrationMapping.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
