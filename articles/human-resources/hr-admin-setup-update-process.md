---
title: 更新流程
description: Microsoft Dynamics 365 Human Resources 是針對應用程式和平台變更提供持續性、非觸控式服務更新的軟體即服務 (Saas)。
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2af1f710ca010041bd684bca8ecfa6f20ac30d46
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452049"
---
# <a name="update-process"></a>更新流程

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Microsoft Dynamics 365 Human Resources 是提供持續性、非觸控式服務更新的軟體即服務 (Saas)。 這些更新包含應用程式和平台變更，時常提供服務的關鍵改善，包括法規更新。

## <a name="update-policy"></a>更新政策

更新版會重覆發行到所有環境。 人力資源根據 [Microsoft Lifecycle 政策](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy)支援，提供一致性及可預測的支援開放指南。

## <a name="release-cadence"></a>發行節奏 

人力資源更新自動套用在所有環境。 人力資源提供兩種發行類型：

- **服務更新**：每兩週更新一次，包括錯誤修復和新功能。 服務更新也包括發行時適用的平台更新。 若要了解平台更新的發行時間點構想，請參閱[資料表 3：平台發行版本](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases)。 雙週更新橫跨全球各地區分階段推出。 更多有關雙週更新資訊，請參閱[Dynamics 365 Human Resources 新面貌或新轉變](hr-admin-whats-new.md)。

    除非另行說明，否則所有支援的資料中心每兩週更新一次。 美國、澳洲、歐洲、英國、亞洲和加拿大地區納入雙週更新一次的範圍。 

- **Dataverse 解決方案更新**：這些更新依照需求大約每六週發生一次。 它們包括新實體和對 Dataverse 既有的實體的變動。 這些更新版發行到雙週更新區域，一般需要大約六週的時間在所有資料中心複製。 解決方案更新可能與雙週服務更新一致或不一致。

> [!NOTE]
> 解決方案更新一經發行，即可在所有資料中心使用。 如果您不希望等待更新版自動複製，您可以在任何資料中心的任何環境手動套用這些更新。

必要時，人力資源也提供修復程式如下：

- **修訂 (Hotfix)** ：與雙週服務更新發行版本一起或分開發生的錯誤修復

- **緊急修復**：主動和被動修補 Hotfix 本質上獨立，會包括配置專用或變更程式碼以解決直播網站問題，以及與雙週服務更新版本分開發生

版本在內部環境審查、測試和驗證。 待建構簽字認可後，它們接著會部署到實際執行環境。

## <a name="release-cadence-exceptions-in-2021"></a>2021 年發行節奏異常

為了考慮年節假期，2021 年 11 月和 12 月的發行時間表如下：

- 11 月發行：11 月 1 日 - 11 月 14 日
- 12 月發行：11 月 29 日 - 12 月 12 日
 
雙週發行節奏將在 2022 年 1 月 10 日照常恢復。

## <a name="communications"></a>通訊

您可以在下列位置找到人力資源的工作項目以及我們已經發行的部份：

- [Dynamics 365 Human Resources 發展藍圖](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Dynamics 365 Release 計畫](/dynamics365/release-plans/)

- [Dynamics 365 Human Resources 新面貌或新轉變](hr-admin-whats-new.md)

- [Lifecycle Services (LCS) 的問題搜尋](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (限平台發行錯誤專用)

- [人力資源部落格](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [人力資源 Yammer 社群](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>在沙箱環境預覽功能

您可以先在沙箱環境驗證預覽功能，然後再到實際執行環境啟用它們。 更多有關啟用功能資訊，請參閱[功能管理概觀](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。

所有新功能的預覽期維持在至少 30 天，典型期間為 30-60 天。 主要功能一般在每年預覽期後的 10 月和 4 月開放使用。 只要您在功能管理工作區看到新功能，即可開啟它們。 某些功能可能預設開啟。

偶爾一體化功能會預設開啟無法關閉 (例如，功能管理工作區)。

一旦功能普及化，它就能在實際執行環境開啟或關閉。 功能管理工作區指出預覽功能將成為必備功能的時間點。 這個日期通常是 10 月 1 日或 4 月 1 日，方便對齊半年發行計劃。 您不能關閉強制性功能。 直到它變成強制性功能之前，您都可以在所有環境開啟和關閉。

我們強烈建議在沙箱或試用環境預覽功能。 最好將目前的實際執行環境或資料庫拷貝版建立到沙箱環境，如此您就能利用您的資料取得新功能的完整體驗。

更多有關佈建沙箱環境的資訊，請參閱[佈建人力資源專案](hr-admin-setup-provision.md)。 若要移除測試環境，請參閱[移除執行個體](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment)。 

## <a name="report-bugs"></a>回報錯誤

在測試預覽功能或嘗試新功能時，您可能會發現無法如預期工作的項目。 請透過 [Microsoft Dynamics 365 支援](https://dynamics.microsoft.com/support/)回報任何錯誤。

## <a name="see-also"></a>也請參閱

[Dynamics 365 和 Power Platform 發行計劃](/dynamics365/release-plans)</br>
[Dynamics 365 人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[軟體生命週期政策](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]