---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年二月 25 日)
description: 本文說明 Microsoft Dynamics 365 Human Resources 於 2020 年二月25 日新增或更改的功能。
author: andreabichsel
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6f8a8795b1af59339e920281ffc46139fb9c45e2
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452010"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年二月 25 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.2927。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>啟用案例管理瀏覽和資料管理框架 (DMF) 實體 (414754)

此預覽功能啟用對案例管理案例的額外瀏覽。 您可以在 **功能管理** 工作區啟用此預覽功能。 這些功能表項目出現在 Dynamics 365 Human Resources 的 **法令遵循** 工作區。 隨著這項更改，人力資源可以存取：

- 所有案例
- 我的案例
- 我的開啟案例
- 我的逾期案例
- 透過工作流程指派給我的案例

除了這些案例的新視圖，**案例細節** DMF 實體也開放使用。

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>在全球通訊錄 bBook 啟用關係定義 (414762)

關係現在在全球通訊錄啟用。 本週發行版本之前，**關係** 事實方塊顯示任何系統定義的關係。 現在您可以在全球通訊錄頁面定義這些關係。

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>當職位存在有效的薪酬記錄時，可以移除 (414568)

隨著這項更改，當您試圖刪除職位，加上背景工作角色有相同職位的有效薪酬記錄時，會出現警告。 發生這種情況時，您必須先更新員工固定薪酬才能移除職位。

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>績效考核工作流程偶爾會新增非屬流程人員的簽字認可 (414171)

這項更改改正額外簽字認可參與者新增到績效考核的問題。

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a>在新 New Worker 對話上選取時，背景工作角色職位指派尚在 Dataverse 建立 (413479)

這項更改改正僱用新背景工作角色和透過 **New 背景工作角色** 對話指派新進員工到職位的問題。 現在職位指派已反映在 Dataverse 上。

## <a name="coming-soon"></a>即將推出

### <a name="updated-dataverse-solution"></a>Dataverse 解決方案更新版

新 Dataverse 解決方案將很快問市，附帶下列更改：

| 描述 | 變更 |
| ----------------------------------------- | --- |
| **工作/職位** 實體更改 | 已新增 **薪酬區域**</br>已新增 **財務維度** |
| **背景工作角色** 實體更改 | 已新增 **名稱順序**</br>已新增 **居家工作**</br>已新增 **語言**</br>已新增 **資歷日期**</br>已新增 **週年紀念日**</br>已新增 **原始錄用日期** |
| **雇用** 實體更改 | 已新增 **財務維度**</br>已新增 **終止緣由**</br>**終止日期** 改名自 **過渡日期**</br>已新增 **試用日期** |
| **背景工作角色地址** 實體更改 | 已新增 **街道地址**</br>**地址第 1 行**、**地址第 2 行** 和 **地址第 3 行** 已標記為棄用 |
| 新變動薪酬設定實體 | **薪酬變動計畫類型**</br>**薪酬變動計劃**</br>**配股規則**</br>**薪酬變動計劃等級** |
| 新 **背景工作角色行事曆雇用** 實體 | 已新增 **工作行事曆實體** |
| 新 **工資單職位細節** 實體 | 已新增 **工資單職位細節** |
| 新 **標題** 實體 | 已新增 **標題**。 新 **標題** 實體將納入人力資源和 Dataverse 之間的同步流程。 它最初不會從 **工作職位** 或 **工作** 實體參考沿用。 |

在接下來的幾週內，這些實體更改將開放所有環境使用。 若要手動安裝最新版的 Dataverse 人力資源解決方案：

1.  請前往 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com)。

2.  選取 **環境**。

3.  尋找您希望升級的環境。 這應該對應到人力資源的 **關於** 表單中，**Common Data Service 資訊** 專區的 **環境名稱**。

4.  選取環境以檢視環境細節。

5.  在最上方的動作列中，選取 **管理解決方案**。 新瀏覽器視窗將打開並瀏覽到您環境脈絡的 **Dynamics 365 系統管理中心**。

6.  請在 **解決方案** 清單，選取 **Dynamics 365 Human Resources 錨點**。

7.  選取 **升級** 套用最新的解決方案。

## <a name="in-preview"></a>預覽中

下列預覽功能在 2020 年二月 3 日即已問市：

- **請假和缺勤預覽功能**  - 更多資訊，請參閱[請假和缺勤預覽功能](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)。

- **福利管理預覽功能**- 更多資訊，包括已知問題，請參閱[福利管理概觀](hr-benefits-management-overview.md)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]