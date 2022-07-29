---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年三月 24 日)
description: 本文說明 Microsoft Dynamics 365 Human Resources 於 2020 年三月24 日新增或更改的功能。
author: andreabichsel
ms.date: 03/24/2020
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
ms.search.validFrom: 2020-03-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dec2f270f53968292ec25cca43c216f26cfc8087
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452016"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-24-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年三月 24 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.3073。 某些標題括號裡的數字意指 Lifecycle Services (LCS) 支援參考的編號。

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>人力資源環境現在限制以更新過的授權為主 (394595)

Lifecycle Services (LCS) 中各個專案的環境數量限制已經更改。 之前的限制是兩個環境。 現在您可以在 LCS 針對人力資源建立的實際執行和沙箱環境數量限制，以更新後的授權為主。 您現在可以根據購買的授權數量，針對每個 LCS 專案建立數量恰如所需的環境。 2020 年二月 1 日更新的新授權允許客戶購買額外的環境。 更多有關額外環境的授權要求資訊，請參閱 [Dynamics 365 授權指引](https://dynamics.microsoft.com/pricing/#HumanResources)。

## <a name="platform-changes"></a>平台變動

- 整頁應用程式 (預覽) - 此預覽功能要求您啟用已儲存的視圖功能，允許透過儀表板將 Power Apps 和協力廠商應用程式新增為整頁體驗。

- 已儲存的視圖 (預覽) - 本預覽功能啟用已儲存的視圖，明顯強化個人化子系統功能。 此功能允許使用者每一頁擁有多套已命名的個人化。 您也可以向資訊安全角色發佈視圖。

- 最佳化 "其中之一" 的篩選體驗 - 此功能造就最佳化 "其中之一" 的篩選體驗，讓輸入多個篩選值更加容易，具有移除個別或所有篩選值的更簡單機制，以及篩選值更精巧、直覺式視覺效果的境界。

- 推薦欄位 - 使用者往往需要新增欄位到格線或頁面。 處理如此多的可用欄位會很困難。 有別於搜尋冗長清單，此功能讓系統根據其他使用者最常在類似方案新增的內容顯示一套推薦的欄位。

- 格線中的相黏預設動作 - 此功能確保格線中的預設動作是連結格線中的特定欄位，不論是否移動或隱藏該欄位。

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-multiple-leave-type-feature-on-419635"></a>無法調整計劃中，累計並未以 "多種請假類型" 功能建立的請假餘數 (419635)

隨著這項更改，您可以調整請假計劃中，已借助功能管理中啟用多種請假類型 (預覽) 功能建立的餘數。

## <a name="in-preview"></a>預覽中

下列預覽功能在 2020 年二月 3 日即已問市：

- **請假和缺勤預覽功能**  - 更多資訊，請參閱[請假和缺勤預覽功能](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)。

- **福利管理預覽功能**- 更多資訊，包括已知問題，請參閱[福利管理概觀](hr-benefits-management-overview.md)。

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
| 新 **標題** 實體 | <ul><li>已新增 **標題**</li></ul>新 **職銜** 實體納入 Dataverse，但這次不是參考 **工作職位** 或 **工作** 實體。 |

> [!NOTE]
> 職位和雇用的財務維度提供從人力資源到 Dataverse 更新的單向整合。 財務維度更新目前無法從 Dataverse 同步到人力資源。

在接下來的幾週內，這些實體更改將開放所有環境使用。 若要手動安裝最新版的 Dataverse 人力資源解決方案：

1.  請前往 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com)。

2.  選取 **環境**。

3.  尋找您希望升級的環境。 環境應對應到人力資源 **關於** 表單中，**Common Data Service 資訊** 專區的 **環境名稱**。

4.  選取環境以檢視環境細節。

5.  在最上方的動作列中，選取 **管理解決方案**。 新瀏覽器視窗將打開並瀏覽到您環境脈絡的 **Dynamics 365 系統管理中心**。

6.  請在 **解決方案** 清單，選取 **Dynamics 365 Human Resources 錨點**。

7.  選取 **升級** 套用最新的解決方案。

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint 預覽功能在一些環境行不通

如果儲存在 SharePoint 的文件預覽行不通，請嘗試下列步驟：

1. 驗證管理使用者帳戶的電子郵件是否與使用者記錄相關聯。 您可以在 **使用者** 頁面檢視這項資訊。 如果電子郵件尚未設定，您需要使用 OData Excel 增益集新增電子郵件和提供商。 電子郵件地址預設不在 Excel 設計範圍。 您將需要編輯 Excel 設計、新增所有欄位、套用和重新整理。 一旦完成這些步驟，您就可以更新管理帳戶。

2. 待管理帳戶有關聯的電子郵件帳號後，使用管理員憑據登入人力資源。

3. 存取 SharePoint 的附件開始文件預覽。

4. 使用可存取附件的另一個使用者帳戶登入並驗證預覽是否如預期運作。

## <a name="coming-soon"></a>即將推出

## <a name="new-production-release-cadence"></a>新實際執行發行版本節奏

自四月起，人力資源的版本節奏將從每週更新轉為兩週更新。 為了確保對齊安全部署實務作法，並維持服務穩定性和可靠性的高標準，將改為每兩週推出全部區域部署服務更新版本的流程。 額外測試和監視將準備好驗證流程中各階段的部署成效。 更多發行版本節奏的資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

## <a name="known-issues"></a>已知問題

## <a name="employment-detail-entity"></a>雇用細節實體

**雇用細節** 實體已經更新下列欄位：**支付頻率**、**雇用類別識別碼**、**雇用類型**、**雇用類型識別碼** 和 **福利雇用狀態**。 這些欄位的設定資料得依照功能管理啟用的福利管理才能操作。 這些欄位不應該在 **雇用細節** 實體中填寫或更新，因為它將造成匯入期間的錯誤。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]