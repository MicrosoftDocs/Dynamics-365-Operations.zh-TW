---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年三月 10 日)
description: 本文說明 Microsoft Dynamics 365 Human Resources 於 2020 年三月10 日新增或更改的功能。
author: andreabichsel
ms.date: 03/10/2020
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
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c6e4d93f89721bd722de523fbba7adfd2ee3f786
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452004"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年三月 10 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.2985。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="cant-access-skill-gap-analysis-report-394460"></a>無法存取技能落差分析報告 (394460)

本報告不在 Dynamics 365 Human Resources 支援。 列印 SSRS 報告的功能表項目已移除。

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>存取開始頁面的訊息不正確 (417950)

隨著這項更改，如果您沒有表單的存取權，安全性會隱藏此功能表項目。

## <a name="streamlined-task-maintenance-for-employees-380538"></a>為員工簡化任務維護 (380538)

背景工作角色任務維護表單列出員工在到職、離職、轉調和業務流程的所有任務。 您可以刪除、重新指派或更新任務的狀態。

範例：班傑明馬汀是福利管理員。 員工到職期間，針對班傑明建立任務以便審核新員工的福利選取。 班傑明有過去完成的任務，以及他需要完成的未來任務。 班傑明決定離開公司，因此他的任務需要重新指派或移除。 任務維護表單 (在 **背景工作角色** 表單的動作窗格) 允許重新指派班傑明的所有任務給另一名背景工作角色或就此移除。  

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>Dataverse 解決方案現在開放進行下列更改：

| 描述 | 變更 |
| --- | --- |
| **工作/職位** 實體更改 | <ul><li>已新增 **薪酬區域**</li>|
| 已新增 **職位維度** 實體 | <ul><li>已新增 **財務維度**</li>
| **背景工作角色** 實體更改 | <ul><li>已新增 **名稱順序**</li><li>已新增 **居家工作**</li><li>已新增 **語言**</li><li>已新增 **資歷日期**</li><li>已新增 **週年紀念日**</li><li>已新增 **原始錄用日期**</li></ul> |
| **雇用** 實體更改 | <ul><li>已新增 **財務維度**</li><li>已新增 **終止緣由**</li><li>**終止日期** 改名自 **過渡日期**</li><li>已新增 **試用日期**</li></ul> |
| **背景工作角色地址** 實體更改 | <ul><li>已新增 **街道地址**</li><li>**地址第 1 行**、**地址第 2 行** 和 **地址第 3 行** 已標記為棄用</li></ul> |
| 新變動薪酬設定實體 | <ul><li>**薪酬變動計畫類型**</li><li>**薪酬變動計劃**</li><li>**配股規則**</li><li>**薪酬變動計劃等級**</li></ul> |
| 新 **背景工作角色行事曆雇用** 實體 | <ul><li>已新增 **工作行事曆實體**</li></ul> |
| 新 **工資單職位細節** 實體 | <ul><li>已新增 **工資單職位細節**</li></ul> |
| 新 **標題** 實體 | <ul><li>已新增 **標題**</li></ul> 新 **職銜** 實體納入 Dataverse，但這次不是參考 **工作職位** 或 **工作** 實體。 |

> [!NOTE]
> 職位和雇用的財務維度提供從人力資源到 Dataverse 更新的單向整合。 財務維度更新目前無法從 Dataverse 同步到人力資源。

在接下來的幾週內，這些實體更改將開放所有環境使用。 若要手動安裝最新版的 Dataverse 人力資源解決方案：

1.  請前往 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com)。

2.  選取 **環境**。

3.  尋找您希望升級的環境。 環境應對應到人力資源 **關於** 表單中，**Dataverse 資訊** 專區的 **環境名稱**。

4.  選取環境以檢視環境細節。

5.  在最上方的動作列中，選取 **管理解決方案**。 新瀏覽器視窗將打開並瀏覽到您環境脈絡的 **Dynamics 365 系統管理中心**。

6.  請在 **解決方案** 清單，選取 **Dynamics 365 Human Resources 錨點**。

7.  選取 **升級** 套用最新的解決方案。

## <a name="in-preview"></a>預覽中

下列預覽功能在 2020 年二月 3 日推出：

- **請假和缺勤預覽功能**  - 更多資訊，請參閱[請假和缺勤預覽功能](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)。

- **福利管理預覽功能**- 更多資訊，包括已知問題，請參閱[福利管理概觀](hr-benefits-management-overview.md)。

## <a name="coming-soon"></a>即將推出

### <a name="platform-update-33"></a>平台更新 33

- 整頁應用程式 (預覽) - 此預覽功能要求您啟用已儲存的視圖功能，允許透過儀表板將 Power Apps 和協力廠商應用程式新增為整頁體驗。

- 已儲存的視圖 (預覽) - 本預覽功能啟用已儲存的視圖，是個人化子系統大幅度提升的表現。 此功能允許使用者每一頁擁有多套已命名的個人化。 您也可以向資訊安全角色發佈視圖。

- 最佳化 "其中之一" 的篩選體驗 - 此功能造就最佳化 "其中之一" 的篩選體驗，讓輸入多個篩選值更加容易，具有移除個別或所有篩選值的更簡單機制，以及篩選值更精巧、直覺式視覺效果的境界。

- 推薦欄位 - 使用者往往需要新增欄位到格線或頁面。 處理如此多的可用欄位會很困難。 有別於搜尋冗長清單，此功能讓系統根據其他使用者最常在類似方案新增的內容顯示一套推薦的欄位。

- 格線中的相黏預設動作 - 此功能確保格線中的預設動作是連結格線中的特定欄位，不論是否移動或隱藏該欄位。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]