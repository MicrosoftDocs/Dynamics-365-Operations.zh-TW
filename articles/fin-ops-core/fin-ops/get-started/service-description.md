---
title: 財務和營運應用程式的服務說明
description: 本主題提供財務和營運應用程式的服務說明。
author: tomhig
ms.date: 01/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: 85f82a863f0bde4c0414760fa2477651242538f2
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2022
ms.locfileid: "8460582"
---
# <a name="service-description-for-finance-and-operations-apps"></a>財務和營運應用程式的服務說明

[!include[banner](../includes/banner.md)]

財務和營運應用程式是企業資源規劃 (ERP) 軟體即服務 (SaaS) 產品，其基於並用於 [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/)。 財務和營運應用程式服務為組織提供支援其獨特需求並幫助他們適應不斷變化的業務環境的 ERP 函數，而無需他們管理基礎設施。 財務和營運應用程式可以包括以下一個或多個解決方案領域：

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

這些應用程式與[商業智慧](/power-bi/fundamentals/power-bi-service-overview)、[基礎結構](https://azure.microsoft.com/global-infrastructure/)、[計算](/azure/service-fabric/service-fabric-overview)和[資料庫服務](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/)一起，使組織能夠執行產業專用的營運業務流程。 在其實作合作夥伴的支援下，客戶確定最適合其獨特業務流程的商務應用程式邏輯設定。 函數和業務流程可以透過以下解決方案之一或組合來擴增或擴展：

- 內建[個人化體驗](personalize-user-experience.md)
- [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md)工具
- [Visual Studio](https://visualstudio.microsoft.com) - 基於[財務和營運應用程式軟體開發套件 (SDK)](../../dev-itpro/dev-tools/developer-home-page.md)和[Azure DevOps組建自動化](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure)
- [AppSource](https://appsource.microsoft.com/partners) 的獨立軟體廠商 (ISV) 解決方案

根據需求，客戶選取他們的解決方案。 他們與實作合作夥伴一起使用 [Microsoft Dynamics Lifecycle Services (LCS)](../../dev-itpro/lifecycle-services/lcs.md) 中提供的工具和最佳做法來定義、開發和測試他們的解決方案。 有四種常見情況：

- 標準財務和營運應用程式「立即可用」設定 (無擴充函數)
- 包含一個或多個 ISV 解決方案的財務和營運應用程式設定
- 包含一個或多個客戶專用擴充函數的財務和營運應用程式設定
- 財務和營運應用程式設定，包括客戶專用的擴充函數和一個或多個 ISV 解決方案的組合

組織可以透過簡單、透明的訂閱模式輕鬆新增使用者和業務流程來比對其業務成長。 如需相關資訊，請參閱[Dynamics 365 認證指南](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)。

## <a name="operating-model"></a>作業模型

財務和營運應用程式的作業模型定義了客戶、實作合作夥伴和 Microsoft 在整個服務生命週期中的特定角色和責任。 如需相關資訊，請參閱[雲端營運和服務](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md)。

### <a name="customer-activities"></a>客戶活動

客戶與他們的合作夥伴和 [Microsoft FastTrack](/dynamics365/fasttrack/) 一起遵循 [Dynamics 365 實作指南](https://community.dynamics.com/365/dynamics-365-fasttrack/p/dynamics365implementationguide)、[Success by Design](/dynamics365/fasttrack/success-by-design-overview) 架構以及 [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md) 中提供的工具和最佳做法範本來實作他們的解決方案。 常見的活動包括：

- 使用者身分識別和安全性管理
- 定義、開發和營運業務流程
- 定義、開發、測試和營運擴充函數
- 監控和管理非生產部署
- 管理應用程式更新和驗證擴充函數
- 管理 ISV 解決方案和第 3 方整合

### <a name="microsoft-responsibilities"></a>Microsoft 責任

Microsoft 透過在 Microsoft SaaS 訂閱中部署、主動監視和服務客戶沙箱和實際執行環境來管理財務和營運應用程式服務。 這種管理包括配置所需的系統基礎結構來執行服務並主動與客戶就服務的健康狀況進行溝通。 責任包括：

**基礎結構管理**
- 安全性和隔離
- 作業系統和虛擬化
- 伺服器、儲存和網路
- 資料中心電源、網路、冷卻

**應用程式平台管理**
- 24/7 應用程式監控和通知
- 診斷、平台更新、修補程式、服務更新
- 應用程式路由、負載平衡、站台複寫
- 環境佈建和管理
- 資料庫管理、高可用性 (HA)/災害復原 (DR)、規模、營運
- 計算部署、擴大、縮小

## <a name="system-configuration"></a>系統設定

財務和營運應用程式根據交易量和使用者負載進行縮放。 每個客戶實作都會產生一個獨特的解決方案，該解決方案由以下元素組成：

- **資料構成** – 一組獨特的參數，用於控制行為、組織配置、主資料結構 (如財務和庫存維度) 以及交易追蹤的細微性。
- **擴充函數和設定** – 使用代碼擴充函數、ISV 解決方案和獨特設定的擴充函數機制，包括工作流程、整合和報表設定。
- **使用模式** – 線上和批次使用的獨特組合，以及與上游和下游系統整合以實現統一資料流程的能力，以及基於客戶在其業務流程中使用的資訊檢視表的差異化能力。

Microsoft 設定大小可處理交易量和使用者並行的客戶實際執行環境。 Microsoft 負責以下工作：

- 根據客戶在 [LCS 訂閱估算器](../../dev-itpro/lifecycle-services/subscription-estimator.md)中的分析資訊，正確配置實際執行環境的資源
- 持續監控和診斷實際執行環境的服務可用性
- 使用財務和營運應用程式分析和解決系統效能問題

若要確保為高效能設定實作，客戶必須完成以下工作：

- 在 [LCS 訂閱估算器](../../dev-itpro/lifecycle-services/subscription-estimator.md)中提供有關財務和營運應用程式實作的準確使用資訊。
- 為效能和規模構建和測試擴充函數。
- 適當地測試資料設定的效能。
- 透過在上線前進行[效能測試](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018)來確保可擴展性。

## <a name="onboarding-and-implementation"></a>上線和實作

下表顯示了典型的上線和實作事件。

| 要求 | 預期的 Microsoft 動作 | 預期的客戶/實作合作夥伴動作 |
|---|---|---|
| 初始報價購買 | LCS 專案是在購買報價後根據客戶觸發的事件建立的。 | 透過企業協議 (EA) 或雲端解決方案提供者 (CSP) [商業流程](before-you-buy.md)。 合作夥伴為客戶建立租使用者 (如果適用)。 |
| 附加元件購買 | 授與客戶存取在實作期間選取的附加元件的權限。 | 不適用 |
| 實作規劃與分析 | 提供 LCS 中的相關工具，如[商業流程建模工具 (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md)和[與 Azure DevOps 的互操作性](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md)。 | 做專案規劃，設定 Azure DevOps，完成系統上線，並設定管理員帳戶。 |

如需相關資訊，請參閱[上線實作專案](../imp-lifecycle/onboard.md)。

## <a name="globalization"></a>全球化

財務和營運應用程式由全球多個 Azure 區域提供服務。 財務和營運應用程式提供支援不同國家/地區和母語的函數。 如需相關資訊，請參閱[本地化和監管功能](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features)。

### <a name="countryregion-specific-considerations"></a>國家/地區特定的注意事項

- 與需要本地資料駐留的法國實體開展業務的受監管行業或商業組織的客戶應查看[法國的財務和營運應用程式](../../dev-itpro/deployment/france-local-deployment.md)。
- 在中國開展業務的客戶應查看 [Azure 中國手冊](/azure/china/) 和 [21Vianet 在中國營運的財務和營運應用程式](../../dev-itpro/deployment/china-local-deployment.md)。
- 在俄羅斯展開業務的客戶應查看[俄羅斯個人資料本地化法](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia)。

### <a name="general-data-protection-regulation-gdpr"></a>一般資料保護規定 (GDPR)

對於財務和營運應用程式，Microsoft 會充當處理器。 作為資料處理者，財務和營運應用程式提供流程和功能，幫助客戶遵守作為資料控制器的 GDPR 義務。 如需相關資訊，請參閱 [GDPR 概述](../../dev-itpro/gdpr/gdpr-guide.md)。

## <a name="environment-and-data-management"></a>環境和資料管理

本節介紹服務中發生的一些典型環境和資料管理事件。

### <a name="environment-and-data-management-events-for-production-instances"></a>生產執行個體的環境和資料管理事件

LCS 提供[自助工具](../../dev-itpro/deployment/infrastructure-stack.md)和[資料庫移動操作](../../dev-itpro/database/dbmovement-operations.md)用於執行環境和資料管理工作。 這裡有些範例：

**事件：**[請求生產執行個體](../imp-lifecycle/prepare-go-live.md#requesting-the-production-environment)

- 完成[上線檢查清單](../imp-lifecycle/prepare-go-live.md)，並將其送出給 [Microsoft FastTrack](/dynamics365/fasttrack/) 團隊。
- 在您請求生產執行個體之前完成[LCS 訂閱估算器](../../dev-itpro/lifecycle-services/subscription-estimator.md)。
- 完成 [LCS 方法論](../../dev-itpro/lifecycle-services/create-methodology.md)中規定的所有實作工作。

**事件：**[將沙箱資料庫複製到生產執行個體](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- 為模擬上線或實際上線切換執行。

**事件：**[維護模式](../../dev-itpro/sysadmin/maintenance-mode.md)

1. 打開 LCS 中的維護模式 。
2. 完成所需的維護。
3. 關閉 LCS 中的維護模式 。

### <a name="environment-and-data-management-events-for-non-production-instances"></a>非生產執行個體的環境和資料管理事件

LCS 提供[自助佈建](../../dev-itpro/deployment/infrastructure-stack.md)和[資料庫移動操作](../../dev-itpro/database/dbmovement-operations.md)用於執行環境和資料管理工作。 這裡有些範例：

**事件：**[部署新的沙箱執行個體](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- 確保所有必需的執行個體都已[規劃](../imp-lifecycle/environment-planning.md)，並且已購買適用的附加優惠。
- 在 LCS 中執行部署過程。
- 完成 LCS 檢查清單中規定的所有工作。
    
>[!NOTE]
>開發沙箱環境是一個虛擬機器 (VM)，它會[部署到客戶的 Azure 訂閱](../../dev-itpro/dev-tools/access-instances.md)並由客戶管理。

**事件：**[將黃金設定資料庫從沙箱複製到生產](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- 為模擬上線或實際上線切換執行。

**事件：**[將生產時間點備份恢復到非生產執行個體](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- 執行 LCS 中的[重新整理資料庫](../../dev-itpro/database/database-refresh.md)選項。
- 複製後：透過指令碼刪除或混淆敏感資料，調整特定環境的應用程式設定 (例如整合端點)，以及啟用或新增使用者。 請注意，這些更改是透過套用[資料封裝](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package)進行的。

**事件：**[非生產執行個體資料庫時間點還原](../../dev-itpro/database/database-point-in-time-restore.md)

- 接受該過程無法復原。
- 在 LCS 中執行階段間點還原作業。

**事件：** 將第 2 層沙箱資料庫複製到開發沙箱以進行故障排除和[偵錯](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)

- 在第 2 層沙箱環境的 LCS 中執行資料庫匯出作業。
- 在開發環境中匯入和更新資料庫。

## <a name="data-backup-and-retention"></a>資料備份和保留

SaaS 訂閱中的財務和營運應用程式環境資料庫受自動備份保護。 對於實際執行環境，自動備份會保留 28 天，除非 Microsoft 進行復原。 對於沙箱 (第 2 層以上) 環境，它們會保留 7 天。 如果在任何計畫性維護更新期間發生故障，則可以復原實際執行環境。

如需自動備份的相關資訊，請參閱[自動備份 - Azure SQL 資料庫和 SQL 受控執行個體](/azure/azure-sql/database/automated-backups-overview?tabs=single-database)。

## <a name="service-activity-responsibilities"></a>服務活動責任

下表描述了該服務的一些典型案例和活動。 它還指示 Microsoft、客戶或 Microsoft 和客戶是否都對這些活動負責。

| 活動 | Microsoft 的責任 | 客戶的責任 |
|---|---|---|
| **佈建初始租使用者** | | |
| 使用訂閱估算器工具調整 LCS 中的預計負載，並請求佈建特定環境。 | | X |
| 佈建所有生產執行個體和非生產執行個體。 | X | |
| 驗證已部屬的生產執行個體和非生產執行個體。 | | X |
| **服務更新** | |
| 將服務更新應用於指定的非生產和生產執行個體。 | X | |
| 手動將 LCS 中的服務更新應用到沙箱執行個體。 定義、開發、測試更新，並將代碼更新包提供回 LCS。 | | X |
| 請求和安排擴充函數更新應用於生產執行個體。 | | X |
| 在應用任何更新之前，為生產執行個體建立代碼和資料備份。 | X | |
| 如果發生任何故障，請將生產執行個體復原到代碼和資料備份。 | X | |
| **資料管理 (備份、恢復和更新)** | | |
| 備份資料庫。 | X | |
| 確定高可用性和災害復原方案。 | X | |
| 監控生產執行個體資料庫的效能。 | X | |
| 調整生產執行個體資料庫的效能。 | X | |
| 對非生產執行個體執行生產執行個體資料庫時間點重新整理作業。 | | X |
| **更新基礎結構** | | |
| 安排定期基礎結構更新。 | X | |
| **擴大和縮減 (使用者、儲存和執行個體)** | | |
| 購買額外的使用者和非生產附加元件。 | | X |
| 更新 LCS 訂閱估算器工具中的使用更改。 | | X |
| 回報影響服務使用的任何重大效能問題。 | | X |
| 主動管理適用服務所需的資源。 | X | |
| 調查和解決事件。 | X | |
| **安全性 (使用者存取)** | | |
| 為使用者提供對服務的存取權限。 | | X |
| 為透過 LCS 部署的執行個體的管理和操作提供 LCS 專案存取權限。 | | X |
| **監控生產執行個體** | | |
| 全天候監控生產執行個體。 | X | |
| 主動通知客戶涉及生產執行個體的事件。 | X | |
| **管理和監控非生產執行個體** | | |
| 使用 LCS 管理非生產執行個體。 | | X |
| 監控非生產執行個體。 | | X |

## <a name="service-update-strategy"></a>服務更新策略

按照[軟體生命週期原則](../../dev-itpro/migration-upgrade/versions-update-policy.md)，財務和營運應用程式遵循 Microsoft [現代生命週期原則](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy)，其中涵蓋持續服務和支援的產品。 

Microsoft 每年在以下幾個月發佈八項財務和營運應用程式應用服務更新：

- 一月
- 二月
- 四月
- 5 月
- 七月
- 八月
- 十月
- 十一月

>[!NOTE]
>4 月和 10 月是主要功能發佈浪潮。 客戶最多可以連續三個更新周期暫停單個服務更新。

如需相關資訊，請查看下列主題：

- [One Version 服務更新概述](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [透過 LCS 設定服務更新](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [透過 LCS 暫停服務更新](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [透過 LCS 取得有關服務更新的通知](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [用於驗證服務更新的回歸測試工具](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Dynamics 365 發展藍圖和發佈波次](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>安全和管理存取

對財務和營運應用程式實際執行環境的管理存取受到嚴格控制和記錄。 客戶資料根據 [Microsoft 線上服務條款](https://www.microsoft.com/licensing/terms/productoffering)進行處理。 

### <a name="customer-administrative-access"></a>客戶管理權限

客戶的租使用者管理員可以存取生產執行個體或非生產執行個體，如下表所述：

| 環境類型 | 目的 | 客戶存取層級 |
|---|---|---|
| **非生產**<br>第 1 層沙箱 | 客戶為開發、展示或培訓目的而部署的非實際執行環境。 | 第 1 層沙箱 (也稱為雲端託管環境) 是客戶管理的 VM，從 LCS 部署到客戶的 Azure 訂閱。 由於它是客戶 Azure 訂閱中的 VM，因此客戶可以透過遠端桌面對環境進行完全管理存取。 |
| **非生產**<br>第 2 層 (或更高) 沙箱 | 客戶為使用者驗收測試、整合測試、培訓、登台或任何其他預生產場景部署的非實際執行環境。 | 第 2 層和更高級別的沙箱部署到財務和營運應用程式SaaS 訂閱。 透過[即時存取](../../dev-itpro/database/database-just-in-time-jit-access.md)授予對與非實際執行環境關聯的 Azure SQL 資料庫的存取權限。 不提供遠端桌面存取。 |
| **生產** | 當專案[準備好初始上線](/imp-lifecycle/environment-planning.md#production-system-readiness)時，將部署實際執行環境。 | 將實際執行環境部署到 SaaS 訂閱。 所有存取都透過瀏覽器、服務端點或 LCS。 |

### <a name="microsoft-administrative-access"></a>Microsoft 管理存取

下表顯示了不同 Microsoft 管理員的不同存取級別：

| 管理員 | 客戶資料 |
|---|---|
| Operations 回應團隊<br>(僅限關鍵人員) | 透過支援票證授予存取權限。 存取被稽核並限制在支援活動的持續時間內。 |
| Microsoft 客戶支援服務 (CSS) | 無直接存取權限。 客戶可以使用螢幕分享與支援人員一起偵錯問題。 |
| 工程 | 無直接存取權限。 Operations 回應團隊可以使用螢幕分享與工程部門一起偵錯問題。 |
| Microsoft 的其他人 | 無存取權限。 |

## <a name="monitoring"></a>監控

Microsoft 投資了一個廣泛的工具集來監視和診斷客戶的生產執行個體。 Microsoft 每週 7 天、每天 24 小時監控客戶的實際執行環境。 如需相關資訊，請參閱[生產支援和監控](../imp-lifecycle/production-support-monitoring.md)。

| Microsoft 責任 | 客戶責任 |
|---|---|
| <ul><li>監控服務的可用性。</li><li>透過執行狀況指標和監視程序持續監控和提醒關鍵組件，例如應用程式對象伺服器 (AOS)、批次處理、資料匯入/匯出架構 (DIXF)、Commerce 和 Management Reporter。</li><li>監控由基礎結構服務 (例如 Azure Active Directory\[Azure AD\] 和 Azure SQL)。</li><li>如果 Microsoft 確定單一流程或批次處理作業導致異常，則該進程或作業將在與客戶溝通後終止。</li></ul> | <ul><li>監控可能導致函數和效能問題的應用程式設定和擴充函數的更改。</li><li>必須使用監控工具來診斷應用程式錯誤。 使用這些工具來診斷使用者報表的效能異常。</li><li>如果系統上的預期負載超出預計的峰值使用量，請通知 Microsoft。</li><li>如果生產執行個體中沒有適用的服務，客戶可以使用 LCS 回報[生產中斷](../../dev-itpro/lifecycle-services/report-production-outage.md)。</li></ul> |

透過 LCS 線上送出支援請求，客戶使 Microsoft 能夠以最有效和最高效的方式提供快速和深入的技術專業知識。 儘管提供電話選項，但僅當線上選項無法使用時才應使用。 如需相關資訊，請參閱[電話支援選項](/power-platform/admin/support-overview.md?toc=/dynamics365/fin-ops-core/dev-itpro/toc.json&bc=/dynamics365/breadcrumb/toc.json#is-there-a-phone-number-i-can-call-to-contact-support)。

## <a name="incident-management"></a>事件管理

Microsoft 根據嚴重性級別回應和修復事件。 在對事件進行初步評估時，以及在獲得更多關於影響和範圍的資訊時，Microsoft 的事件嚴重性級別可以改變。 如果事件得到緩解，則事件嚴重性保持不變。

如需嚴重性級別的相關資訊，請參閱[此嚴重性資料表](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request)。

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>透過高可用性和災害復原實現商務持續性 

Microsoft 在 Azure 區域範圍內發生中斷時為財務和營運應用程式的生產執行個體提供商務持續性和災害復原。 如需相關資訊，請參閱[商務持續性和災害復原](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md)。

- **高可用性** – HA 函數提供了防止因 Azure 資料中心中的單個節點故障而導致停機的方法。 每個服務的雲端架構都使用計算層的 Azure 可用性集來防止單點故障事件。 資料庫的 HA 是透過[Azure SQL 高可用性功能 ](/azure/azure-sql/database/high-availability-sla)提供。
- **災害復原** – [ Azure 災害復原功能](/azure/best-practices-availability-paired-regions)可保護每項服務免受廣泛影響整個 Azure 資料中心的中斷。 以下是一部分功能：

    - 用於主資料庫 (業務資料庫) 的 Azure SQL 主動異地複寫。
    - 其他 Azure 區域中 Azure Blob 儲存體 (包含文件附件) 的異地冗餘副本。
    - Azure SQL 和 Azure Blob 儲存體複寫的次要區域。

主資料儲存支援複寫。 因此，每個服務的組件 (例如 Management Reporter 和實體儲存) 都使用來自主資料庫的轉換資料。 必須在設定復原站台並啟動服務後產生此資料。 客戶代碼構件和復原的資料儲存用於重新部署站台。 重新部署使計算節點的狀態複寫以及網路和其他組件能夠使用復原的資料儲存來設定輔助站台。 如果使用災害復原來恢復客戶的生產執行個體，Microsoft 和客戶將滿足他們的[事件管理](service-description.md#incident-management)責任。

透過系統和組織控制 (SOC) 稽核定期檢查 Microsoft 的災害復原計畫和程序。 這些合規性稽核證明了 Microsoft DR 的技術和程序流程，包括 Dynamics 365 Finance 和 Operations 應用程式。 [SOC 合規性](/compliance/regulatory/offering-soc-2)稽核報表和所有其他合規報表皆可在[Microsoft 信任中心合規性產品](/compliance/regulatory/offering-home)上找到。

| Microsoft 職責 | 客戶責任 |
|---|---|
| 部署主要生產執行個體時，Microsoft 在 Azure 配對資料中心佈建輔助環境。 如需相關資訊，請參閱[商務持續性和災害復原 (BCDR)：Azure 配對區域](/azure/best-practices-availability-paired-regions)。 | 無 |
| Microsoft 在部署主要生產執行個體時啟用 Azure SQL 和 Azure Blob 儲存體的異地冗餘。 | 無 |
| Microsoft 在 Azure SQL 資料庫上啟用自動備份。 | 無 |
| <p>發生中斷時，Microsoft 確定是否必須為客戶執行故障轉移，以及是否會丟失資料。 根據中斷的性質和時間，客戶可能會遇到長達 15 分鐘的資料丟失。 | 如果發生資料丟失，客戶可能必須提供書面簽字以觸發故障轉移。 |
| 發生故障轉移時，適用的服務以受限模式工作。 在故障轉移模式下無法觸發更新維護。 | 客戶不能在故障轉移模式下請求包部署或其他常規維護請求。 |
| 當資料中心開始執行階段，Microsoft 會故障回復到主要 Azure 區域中的生產執行個體。 恢復正常作業。 | 客戶可能必須在故障回復到主要 Azure 區域中的生產執行個體時簽核。 |

## <a name="finance-and-operations-support-offerings"></a>財務和營運應用程式支援產品

在提供財務和營運應用程式服務的市場中可以獲得技術支援。 [支援經驗](../../dev-itpro/lifecycle-services/lcs-support.md)在 LCS 或財務和營運應用程式中提供。 這裡有些範例：

- LCS 中的[問題搜尋](../../dev-itpro/lifecycle-services/issue-search-lcs.md)
- 財務和營運應用程式[支援整合的技術](../../dev-itpro/lifecycle-services/support-experience.md)
- LCS 中的[雲端運算支援](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md)

Microsoft 為財務和營運應用程式客戶提供三種支援計畫：頂級、專業直接支援以及訂閱中包含的支援。 每個計畫的支援級別不同。 下表顯示了三個計畫的比較。

| 支援功能 | 頂級 | 專業直接支援 | 訂閱 |
|---|---|---|---|
| 無限次中斷/修復事件送出 | 是 | 是 | 是 |
| 透過 LCS 全天候 24/7 存取 | 是 | 是 | 是 |
| 事件回應時間 | 不到一小時 | 不到一小時 | 下一個工作天 |
| 諮詢時數 | 集區是根據合約獲得的。 | 否 | 否 |
| 專門的支援客戶經理 | 是 | 否 | 否 |
| 專門支援工程師 | 根據單獨的協議參與 | 否 | 否 |

如需相關資訊，請參閱[支援總覽](/power-platform/admin/support-overview)。

### <a name="process-to-engage-support"></a>獲得支援的流程

如果發生涉及財務和營運應用程式的事件，客戶可以透過 LCS 向 Microsoft 送出支援票證。 CSS 根據客戶的支援計畫和 CSS 指定的事件嚴重性來處理事件。

### <a name="service-level-agreement"></a>服務等級合約

Microsoft 承諾每月提供 99.9% 的服務可用性。 如果 Microsoft 未達到和維持服務等級協定 (SLA) 中所述的適用服務的服務級別，則客戶可能有資格獲得抵免該服務每月服務費的一部分。 如需如何啟動服務信用的相關資訊，請參閱[SLA](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services)。

## <a name="important-resources"></a>重要資源

- **[信任中心](https://www.microsoft.com/trust-center)** – 取得有關您財務和營運應用程式資料儲存位置的資訊，以及有關隱私、合規性和安全程序的其他資訊。
- **[許可條款和文件](https://www.microsoftvolumelicensing.com/)** – 快速存取與使用透過 Microsoft 批次許可計畫獲得許可的產品和服務相關的許可條款、條件和補充資訊。
- **[許可條款](https://www.microsoft.com/licensing/product-licensing/)** – 此頁面上的資源定義了您透過 Microsoft 商業許可計畫購買的軟體和線上服務產品的條款和條件。
- **[Microsoft 生命週期原則](/lifecycle/)** – 本頁為產品整個生命週期內的支援可用性提供了一致且可預測的指導方針。
- **[許可指南](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)** – 使用本指南了解有關如何授權 Dynamics 365 的更多資訊。
- **[客戶支援](https://dynamics.microsoft.com/support/)** – 為您的 Dynamics 365 應用程式取得領先業界的支援。
- **[動態 Lifecycle Services](https://lcs.dynamics.com/)** – 管理您的應用程式生命週期，並朝著可預測、可重複、高品質的實作邁進。
- **[Dynamics 365 實作指南](https://aka.ms/D365ImplementationGuideFlip)**- Dynamics 365 實作指南文件經過時間考驗的 Success by Design 原則，並為架構、構建、測試和部署 Dynamics 365 解決方案提供規範性指導。

## <a name="definitions"></a>定義

### <a name="azure-region"></a>[Azure 區域](/azure/availability-zones/az-overview#regions)

存在一個或多個 Azure 資料中心的地理區域。 範例包括美國和歐洲。

### <a name="business-process-modeler-bpm"></a>[商業流程建模工具 (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md)

LCS 中的一種工具，透過使用美國生產力和品質中心 (APQC) 中的財務和營運應用程式支援的業務流程定義，幫助完成給定實作的適合差距分析。

### <a name="cloud-solution-provider"></a>雲端解決方案提供者

屬於 Microsoft Cloud 解決方案提供者 (CSP) 計畫的合作夥伴，可為客戶大規模提供增值雲端服務、支援、一張發票和客戶管理。

### <a name="customer"></a>客戶

使用財務和營運應用程式應用並由 Office 365 中的租使用者表示的商業實體。

### <a name="development-environment"></a>開發環境

用於開發擴充函數的非生產沙箱環境。 客戶從 LCS 將此環境部署到他們自己的 Azure 訂閱。 此環境還可用於展示、培訓或其他測試工作。 它也稱為[第 1 層沙箱](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher)。

### <a name="downtime"></a>停機時間

由於未過期的平台或服務基礎結構出現故障，使用者無法登入或存取其活動租使用者的任何時間段，Microsoft 從自動執行狀況監控和系統記錄中確定。 停機時間不包括計畫停機時間、服務附加功能不可用、由於您對服務的修改而無法存取服務或超出縮放單元容量的時間段。

### <a name="implementation-partner"></a>實作夥伴

客戶選取用於自訂、設定、實作和管理其財務和營運應用程式解決方案的合作夥伴。

### <a name="incident"></a>事件

客戶在使用財務和營運應用程式服務時遇到的問題，他們透過 LCS 送出票證。

### <a name="microsoft-customer-support-services-css"></a>Microsoft 客戶支援服務 (CSS)

致力於為財務和營運應用程式應用提供優質服務的 Microsoft 全球支援小組。

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services (LCS)

財務和營運應用程式生命週期管理的管理入口網站，從試用到實作，再到後期製作管理和支援。 如需更多資訊，請參閱 [Lifecycle Services 資源](../../dev-itpro/lifecycle-services/lcs.md)。

### <a name="non-production-instance"></a>非生產執行個體

客戶用於驗證擴充函數和執行其他開發工作的以下任何服務執行個體：

- **沙箱第 1 層** – 開發者執行個體 (客戶託管)
- **沙箱第 2 層** – 標準驗收測試執行個體
- **沙箱層 3–5** - 附加沙箱

如需第 2 至第 5 層的相關資訊，請參閱[選取正確的第 2 層或更高的環境](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment)。

### <a name="production-instance"></a>生產執行個體

客戶用來管理其「即時」日常交易和商業流程的財務和營運應用程式環境。

### <a name="sandbox-environment"></a>沙箱環境

客戶用於展示、培訓、使用者驗收測試、擴充函數驗證和其他測試工作的非生產環境。

### <a name="service"></a>服務

財務和營運應用程式中包含的任何核心服務。

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>Microsoft 線上服務的服務等級協定 (SLA)

將 SLA 套用至 Microsoft 線上服務。 如需相關資訊，請參閱[服務等級協定](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services)。

### <a name="service-update"></a>服務更新

Microsoft 透過服務更新為財務和營運應用程式環境提供一致的服務。 客戶可以根據自己的業務需求設定自己的服務更新日曆。 如需相關資訊，請參閱 [One Version 服務更新](../../dev-itpro/lifecycle-services/oneversion-overview.md)。

### <a name="success-by-design"></a>[Success by Design](/dynamics365/fasttrack/success-by-design-overview)

該架構透過關鍵階段的一系列評估系統地指導實作，以確保 Dynamics 365 解決方案的最佳架構、安全性、效能和使用者體驗。

### <a name="user"></a>使用者

使用財務和營運應用程式環境並與客戶的租使用者關聯的單人。
