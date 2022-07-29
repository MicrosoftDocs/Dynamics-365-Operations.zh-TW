---
title: Dynamics 365 Human Resources 基礎結構合併常見問答集
description: 本主題回答有關 Microsoft Dynamics 365 Human Resources 與財務和營運應用程式基礎結構合併的常見問題。
author: twheeloc
ms.date: 08/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c022bb15975a1411230d28067a2225c95c0573bf
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452037"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Dynamics 365 Human Resources 基礎結構合併常見問答集

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本主題回答有關 Microsoft Dynamics 365 Human Resources 與財務和營運應用程式基礎結構合併的常見問題。

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>何謂 Dynamics 365 Human Resources 基礎結構合併？

Dynamics 365 Human Resources 是獨立應用程式，使用有別於其他財務和營運應用程式的基礎結構，例如 Dynamics 365 Finance、Dynamics 365 Supply Chain Management、Dynamics 365 Commerce 和 Dynamics 365 Project Operations。 基礎結構合併將 Dynamics 365 Human Resources 帶入與其他財務和營運應用程式的相同基礎結構。

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>基礎結構合併的價值和好處

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>我的組織使用 Dynamics 365 Human Resources 管理旗下人力資源營運。 我們將從這些變動看到什麼好處？

- 這些變動移除 Dynamics 365 的多套人力資源 (HR) 功能導致的困惑。
- 他們同時提供 Microsoft Power Platform 擴充功能以及延伸業務邏輯和功能選項的方式。
- 它們讓 Dynamics 365 Human Resources 和 Application Lifecycle Manageent (ALM) 方面的其他財務和營運應用程式、Microsoft Dynamics Lifecycle Services (LCS)、地理可用性、擴充性之間達成一致。
- 它們讓您善用共用服務和工具，並且幫助降低成本。

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>我的組織使用 Dynamics 365 Finance Human Resources 模組、Supply Chain Management、Commerce 或 Project Operations。 我們將從這些變動看到什麼好處？

已在 Dynamics 365 Human Resources 進行的功能和投資現在將開放 Dynamics 365 Finance 中的人力資源模組使用者使用。 其中一些功能包括請假和缺勤管理、福利管理和任務管理。

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>我會失去目前使用的任何功能或能力嗎？

Dynamics 365 Human Resources 和財務和營運應用程式中的 HR 模組之間將有功能價值平等的情況。 Dynamics 365 Human Resources 將優先類似功能。 更多資訊，請參閱[功能管理概觀](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。

### <a name="will-the-experience-change-for-my-users"></a>我的使用者體驗會因此發生變動嗎？

新的人力資源功能將透過功能管理進行管理。 客戶將決定是否要受理。 某些情況下可能修改功能。 此時將提供文件。

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>如果我是既有的客戶，而且我在財務和營運基礎結構和 Dynamics 365 Human Resources 上同時透過自訂整合功能使用兩個 仂資源模組，這項變動是否會影響到我 ？

Dynamics 365 Human Resources 與 Dynamics 365 Finance 中的人力資源模組之間的自訂整合功能將不再需要。 所有人力資源資料將與其他財務和營運應用程式永駐相同的資料庫。

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>從 Dynamics 365 Human Resources 遷移到財務和營運應用程式

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>我的組織使用 Dynamics 365 Human Resources 管理旗下人力資源營運。 我們必須針對遷移到新體驗計劃什麼？

如果貴組織使用 Dynamics 365 Human Resources 但不使用任何其他財務和營運應用程式，您的人力資源環境將遷移到新基礎結構。 這段遷移流程的大部分將自動化進行。 流程將準備就緒遷移您的資料庫並與新基礎結構同步。

此外，工具將會到位，如此一來，您便能在遷移正式執行環境之前測試遷移流程並驗證您的資料和體驗。

如果貴組織同時使用 Dynamics 365 Human Resources 和其他財務和營運應用程式，您應該計劃更多驗證時間，確保您的資料正確遷移到新環境。 遷移到新基礎結構將把您的人力資源環境中的資料合併您的財務和營運環境。 衝突性資料將需要使用者輸入以便判定應該如何解決衝突。 使用者和管理員將必須管理有衝突的資料測繪，並在正式執行環境遷移之前在沙箱環境中測試遷移。

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>我的組織使用 Dynamics 365 Finance Human Resources 模組、Supply Chain Management、Commerce 或 Project Operations。 我們必須針對遷移到新體驗計劃什麼？

在財務和營運應用程式使用人力資源模組的組織方面，Dynamics 365 Human Resources 的新功能將透過標準的 One Version 更新流程套用到您的環境。 您可以期待在您的環境看到新功能，因為它在每個更新版都能使用。 您可以使用功能管理來開啟新功能，不過您應該計劃驗證這些功能。 請按照您針對驗證環境的其他更新版準備就緒的流程。 更多有關更新套用到財務和營運應用程式的細節，請參閱 [One Version 概觀](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md)。

### <a name="when-will-my-organization-be-migrated"></a>我的組織將在何時遷移？

每個組織的遷移將取決於目前配置和遷移到新基礎結構的準備情況。 這些日期可能有所變動。

- 在財務和營運應用程式使用人力資源模組的組織將收到 Dynamics 365 Human Resources 人力資源功能，這是日常 One Version 更新流程的一部分。 新功能計劃 2022 年 1 月起全面推出。
- 只使用 Dynamics 365 Human Resources 的組織將擁有遷移工具的存取權，藉此在 2022 年年中開始測試與遷移。 遷移到新基礎結構的日期必須是已遷移完成但尚未判定完成的日期。 不過至少是遷移工具開放使用之日後一年。
- 使用 Dynamics 365 Human Resources 與其他財務和營運應用程式的組織將擁有遷移工具的存取權，藉此在 2022 年年中開始測試與遷移。 遷移到新基礎結構的日期必須是已遷移完成但尚未判定完成的日期。 不過至少是遷移工具開放使用之日後一年。

更多有關 Dynamics 365 Human Resources 新功能的資訊，請參閱[人力資源的新面貌或變動](./hr-admin-whats-new.md)。

### <a name="my-organization-has-not-yet-gone-live-on-dynamics-365-human-resources-should-we-go-live-with-the-human-resources-module-in-the-finance-and-operations-apps-or-with-the-dynamics-365-human-resources-app-on-the-legacy-infrastructure"></a>我的組織尚未在 Dynamics 365 Human Resources 上線。 我們應該使用財務和營運應用程式的人力資源模組或舊版基礎結構上的 Dynamics 365 Human Resources 應用程式上線？

必須考慮的重要項目是需要哪些人力資源功能，以及屆時新基礎結構會開放使用的功能。 如果組織需要人事管理的核心功能，則目前在財務和營運應用程式的新基礎結構人力資源模組已經開放使用。 財務和營運應用程式的人力資源模組與 Dynamics 365 Human Resources 應用程式之間的對等功能版預計在 10.0.25 版本開放使用，計劃 2022 年 3 月全面發行。 Teams App 類整合功能和 Dataverse 實體整合將在稍後版本中開放使用。

如果組織人力資源功能需求將在組織上線的時間範圍內，在新基礎結構上開放使用，則財務和營運應用程式的人力資源模組上線可能變得更容易。 這將導致遷移過程更加輕鬆，因為它將是 Dynamics 365 Human Resources 應用程式的標準應用程式升級版，而且客戶已經在新基礎結構上。 如果組織決定在舊基礎結構上的 Dynamics 365 Human Resources 應用程式上線，將需要進行環境遷移才能移到新基礎結構。 這可以藉助新基礎結構上線避免。

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>我正在使用只在 Dynamics 365 Human Resources 開放的新功能 (例如 **請假與缺勤** 和 **福利管理**)。 這些功能現在也會在財務和營運基礎結構的人力資源模組開放使用嗎？

是的，所有 Dynamics 365 Human Resources 模組將在財務和營運應用程式按原狀態運作，並且將有 100% 的功能對等性。 作為這些人力資源功能的客戶使用者整體遷移策略的環節之一，客戶資料將會進行遷移，以便繼續在財務和營運基礎結構上運作。

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>我使用新版 Dynamics 365 Human Resources 福利管理功能。 我已經在財務和營運基礎結構上建製自訂的人力資源整合版，如此一來我便能使用福利資料善用工資單功能。 未來是否需要這些自訂版整合功能？

作為基礎結構合併的一部分，人力資源資料會與其他財務和營運應用程式一起帶入相同的資料庫。 財務和營運應用程式模組之間的整合將不再需要。

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>我的組織使用一個或多個 Dynamics 365 Human Resources ISV 解決方案。 我們的 ISV 解決方案會自動遷移嗎？

每個獨立軟體供應商 (ISV) 解決方案的遷移體驗各有差異，一切依照解決方案的整合方法而定。 Microsoft 將與 ISV 密切合作，確保順利過渡到新基礎結構。

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>我的組織使用 LinkedIn Talent Hub 與 Dynamics 365 Human Resources 的整合版。 基礎架構完成更改後，這個整合版是否繼續運作？

不，遷移到新基礎結構後，LinkedIn Talent Hub 整合版將不會運作。 LinkedIn Talent Hub 整合服務將與舊版 Dynamics 365 Human Resources 基礎結構一起停用。

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>我的組織使用 Teams 的人力資源 App。 基礎結構完成更改後，App 是否繼續運作？

是的，遷移到新基礎結構後，適用 Teams 的人力資源 App 將繼續運作。

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>我的組織已經在 Dynamics 365 Human Resources 配置自訂安全性。 基礎結構完成更改後，我們的自訂安全性是否仍然適用？

是的，自訂安全性配置將納入遷移到基礎結構的資料範圍。

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>我們正在使用 Data 整合器在 Dynamics 365 Human Resources 與財務和營運應用程式之間移動數資料。 目前正在整合的資料會受到怎樣的影響？

目前 Dynamics 365 Human Resources 的人力資源資料會與 Dataverse 同步。 接著可以使用 Data Integrator 與財務和營運應用程式進行單向同步。 遷移到新基礎結構後，人力資源資料將是財務和營運應用程式的在地資料。 Data Integrator 將不再需要在財務和營運應用程式和人力資源之間同步資料。

目前的 Dataverse Human Resources 在地資料表將繼續與新基礎架構的環境資料同。 實體將轉換為支援雙重寫入。 透過 Data Integrator 針對其他 Dynamics 365 App 的這些資料表所配置的任何其他資料整合將繼續按目前配置狀態運作。

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>我們正在使用雙重寫入功能在 Dataverse 與其他財務和營運應用程式之間移動人力資源資料。 目前正在整合的資料將如何受到遷移到新基礎結構動作的影響？

人力資源資料將是新基礎結構上環境中的財務和營運應用程式在地資料。 雙重寫入將用來在新環境和 Dataverse 環境之間移動人力資源資料。

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>我們已經將自訂整合版從 Dynamics 365 Human Resources 建入一套或多套外部系統。 基礎架構完成更改後，我們必須開發新整合功能嗎？

這得依照整合端點而定。 更多有關財務和營運應用程式開放使用的整合技術以及如何選擇最佳整合技術的資訊，請參閱[整合概觀](../fin-ops-core/dev-itpro/data-entities/integration-overview.md)。

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>我們已經擴充 Dynamics 365 Human Resources 的 Dataverse。 這些擴充功能會自動遷移嗎？

如果 Dynamics 365 Human Resources 和將加入新基礎結構環境的財務和營運環境連接相同的 Dataverse 環境，兩套 app 將繼續在遷移後連接相同的 Dataverse 環境。 任何 Dataverse 擴充功能將不需要遷移。

不過如果 Dynamics 365 Human Resources 和目前連接分開獨立的 Dataverse 環境的財務和營運環境，兩個 Dataverse 環境將必須結合，才能連接新基礎結構上的單一環境。 Dataverse 遷移方面，Dataverse 人力資源解決方案標準資料表可連接並與新 Dataverse 環境重覆同步。 Dataverse 環境的任何擴充功能將不會自動遷移，但必須在新環境中重新部署。 我們建議您使用託管解決方案來管理您的 Dataverse 擴充功能。 更多資訊，請參閱[解決方案簡介](/powerapps/developer/data-platform/introduction-solutions)。

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>我們已經配置 Microsoft Power Automate 流程和/或 Microsoft Power Apps 搭配 Dynamics 365 Human Resources。 這些 Microsoft Power Platform 組成元件會在基礎架結構完成更改後遷移並自動運作？

Power Apps、Power Automate 流程和其他 Microsoft Power Platform 客製化與 Dataverse 擴充功能類似。 遷移到新基礎結構後是否自動運作須依照人力資源 App 和財務和營運應用程式是否連接遷移前相同的 Power Apps 環境而定。

如果 App 目前連接相同的 Power Apps 環境，他們將繼續連接遷移到新基礎結構後的 Power Apps 環境。 此時 Power Apps、Power Automate 流程和其他 Microsoft Power Platform 客製化將繼續運作，不必進行任何額外配置。 我們建議您使用託管解決方案來管理您在 Dataverse 上的應用程式擴充功能。 更多資訊，請參閱[解決方案簡介](/powerapps/developer/data-platform/introduction-solutions)。

不過，如果人力資源 App 和財務和營運應用程式連接分開獨立的 Power Apps 環境，它們必須組合成遷移的一部分。 這項任務將要求任何 Power Apps 和其他客製化在新環境重新部署。

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>我們已經啟用 Dynamics 365 Human Resources 的 Dataverse虛擬資料表。 遷移期間這些資料表將會發生什麼情況？

遷移後，如果新基礎結構的環境仍然與目前連接 Dynamics 365 Human Resources 的 Dataverse 環境連接，已在該環境中產生的 Dataverse 虛擬資料表將繼續運作，不必進行任何額外配置。

不過，如果新基礎結構上的環境連接遷移後不同的 Dataverse 環境，虛擬資料表將必須在新的 Dataverse 環境中重新產生。

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>我們已經藉由 Applicant Tracking System (ATS) API、工資單 API、Dynamics 365 Human Resources 的 Dataverse虛擬資料表或 Dataverse Web API 中的其他實體開發整合版。 基礎架構完成更改後，這些整合版是否繼續運作？

遷移後，如果新基礎結構的環境仍然與目前連接 Dynamics 365 Human Resources 的 Dataverse 環境連接，則已經針對  Dataverse Web API 開發的整合版將在遷移完成後繼續運作。

不過，如果新基礎結構的環境連接遷移後不同的 Dataverse 環境，則已經針對 Dataverse Web API 開發的整合版將必須重新配置，才能連接新的  Dataverse 環境。

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>遷移我的環境時會對 Azure 區域造成影響嗎？

預計您的人力資源環境將典型於遷移期間保持在相同的 Azure 區域。 唯一的例外情況是人力資源環境將與不同區域的財務和營運環境合併。 此時人力資源環境將遷移到財務和營運環境的 Azure 區域。

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>我的組織依照 Dynamics 365 Human Resources 中的工作流程用於一個或多個業務流程。 工作流程將會自動遷移嗎？

是的，將遷移工作流程配置、工作流程歷程和目前進行中的工作流程。

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>哪些訓練和資源將開放搭配遷移流程？

將提供完整的文件詳細說明遷移流程的每個步驟。 如影片和研討會在內的額外訓練課程也會依照需求開放使用。

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>我的組織已經在 Dynamics 365 Human Resources 建立 Saved 視圖，改善介面的可用性。 Saved 視圖將會自動遷移嗎？

是的，Saved 視圖將遷移到新基礎結構。

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>我們正在搭配 Dynamics 365 Human Resources 使用 Ceridian。 Ceridian 整合將在基礎架構完成更改後開放使用嗎？ 

與 Ceridian 的整合將遷移到以 Payroll API 為主的整合環境。 目前 Dynamics 365 Human Resources 存在的檔案型整合將不會遷移到財務和營運基礎結構。 更多資訊，請參閱[工資單 API 簡介](./hr-admin-integration-payroll-api-introduction.md)。

### <a name="how-will-the-migration-affect-the-service-update-process"></a>遷移將如何影響服務更新流程？

遷移過後，客戶在 ALM 和服務更新方面將擁有更大的靈活度。 服務更新將不再自動套用人力資源環境。 相反地，此服務將遵照 One Version 服務更新流程和功能。 因此，更新版的配置選項將透過 LCS 提供。 更多資訊，請參閱 [One Version 概觀](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md)。

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>遷移將如何影響我的 Dynamics 365 Human Resources LCS 專案？

遷移到新基礎結構將連帶將您的 Dynamics 365 Human Resources 環境管理移入 LCS 中的財務和營運落實專案。 如果遷移正在使用現有的財務和營運環境合併 Dynamics 365 Human Resources，您的人力資源 LCS 專案將會合併到財務和營運應用程式的 LCS 落實專案。 如果您目前只使用 Dynamics 365 Human Resources，將建立新 LCS 落實專案，並將您既有的人力資源 LCS 專案遷移到新專案。

新專案將與財務和營運應用程式使用相同類型的專案。 它將具有與環境管理相同的特色和功能。 更多資訊，請參閱 [Lifecycle services 資源](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md)。

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>我們已將我們的任務記錄連結到人力資源中的 Business Process Modeler。 Business Process Modeler 將如何遷移並合併到 LCS？

LCS 專案的業務流程庫將遷移到新人力資源 LCS 專案。

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>我的組織目前只使用 Dynamics 365 Human Resources。 目前開放哪些資源可以讓我們在基礎結構完成變更後進一步了解開發能力？

Microsoft Power Platform 擴充選項與財務和營運擴充選項將可同時用於開發。 更多資訊，請參閱 [Develop 和客製化首頁](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md)。

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>我們已經在 Dynamics 365 Human Resources 啟用若干功能。 這些功能將在遷移期間自動啟用嗎？

不論是否在新基礎結構自動啟用，功能將針對各項功能個別判定。 此資訊將納入功能文件。

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>遷移期間我的 BYOD 資料庫會發生什麼情況？

攜帶您自己的資料庫 (BYOD) 的匯入和匯出配置將遷移到新基礎結構。

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>遷移期間我的 Azure Data Lake 會發生什麼情況？

目前針對財務和營運應用程式中的 Azure Data Lake Storage 所配置的任何匯出將在遷移後維持相同配置。

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>我們目前正在使用 Dynamics AX 2012。 目前開放使用的升級工具是否會用來將 AX 2012 的人力資源模組升級到 Dynamics 365 Human Resources？

是。 Dynamics 365 Human Resources 將納入財務和營運應用程式的合併代碼庫和基礎結構。 從 Dynamics AX 2012 升級到 Dynamics 365 Human Resources 將使用升級到財務和營運應用程式最新版本時，相同的升級路徑和工具。

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>我們搭配 Dynamics 365 Human Resources 使用 Document 處理功能。 遷移期間文件將會發生什麼情況？

文件將維持在既有的文件儲存設備。 它們將重新測繪到新基礎結構的環境。

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>遷移後，我們已經在 Dynamics 365 Human Resources 配置的批次工作會發生什麼情況？

適用的批次工作將自動遷移到新基礎結構。

## <a name="licensing-impact"></a>授權影響

此文件不會取代或更換任何涵蓋使用權利的法律文件。

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>我的組織使用 Dynamics 365 Human Resources 管理旗下人力資源營運。 我們的授權或成本會變動嗎？

已經購買 Dynamics 365 Human Resources 授權版的客戶不會受到影響。 這些客戶不必進行授權遷移。 人力資源專屬的額外沙箱庫存單位 (SKU) 將不再適用。 相反地，客戶可以選擇以略低成本購買財務和營運應用程式第 2 層沙箱。 已經購買人力資源沙箱的既有客戶不必額外成本就能遷移到財務和營運應用程式第 2 層沙箱。

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>我的組織使用 Dynamics 365 Finance Human Resources 模組、Supply Chain Management、Commerce 或 Project Operations。 我的授權或成本會變動嗎？

Dynamics 365 App 的既有使用者和單機版 Dynamics 365 Finance、Supply Chain Management、Commerce 和 Project Operations 使用者可以在 2025 年 2 月或目前授權協議到期前存取這些授權的部份人力資源，以較早者為準。 如果它可以幫助您更節省成本，您可以選擇提早遷移到人力資源授權版。 自 2025 年 2 月開始，所有既有的 CSP 和 EA 客戶必須推出 HR 模組並購買人力資源授權版，才能善用財務和營運應用程式帶來的新功能。

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>我的組織搭配 Dynamics 365 Finance、Supply Chain Management、Commerce 或 Project Operations 上線。 我們是否需要購買額外的環境來支援基礎結構合併？

不需要額外環境支援基礎結構更改。

### <a name="where-should-i-go-if-i-have-additional-questions-about-product-licensing"></a>如果我對產品授權有其他問題，應該去哪裡？

如果您有授權上的問題，您可以在 [Biz Apps Hub–D365 定價和授權](https://businessapplications.transform.microsoft.com/resources/pricing-and-licensing?tab=grandfathering) 上找到更多資訊。 如果那裡的資訊對您的問題沒有幫助，請使用 LicenseQ 提出要求。
