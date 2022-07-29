---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年三月 3 日)
description: 本文說明 Microsoft Dynamics 365 Human Resources 於 2020 年三月3 日新增或更改的功能。
author: andreabichsel
ms.date: 03/03/2020
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
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2fea153f7d532b25d7866f852875453ca3e4fc49
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452007"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年三月 3 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.2955。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>Dataverse 解決方案現在開放進行下列更改：

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

3.  尋找您希望升級的環境。 環境應對應到人力資源 **關於** 表單中，**Common Data Service 資訊** 專區的 **環境名稱**。

4.  選取環境以檢視環境細節。

5.  在最上方的動作列中，選取 **管理解決方案**。 新瀏覽器視窗將打開並瀏覽到您環境脈絡的 **Dynamics 365 系統管理中心**。

6.  請在 **解決方案** 清單，選取 **Dynamics 365 Human Resources 錨點**。

7.  選取 **升級** 套用最新的解決方案。

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a>請假登記資料實體的匯入問題 (406082)

您現在可以將員工註冊到相同類型的新請假計劃，只要新註冊日期晚於先前計劃已到過期的註冊日期。

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a>DMF 的 401k payrollWorkerEnrolledBenefitDetail 實體匯出提撥率的問題 (420700)

此項更改改正 **payrollWorkerEnrolledBenefitDetail** 實體的匯出功能，反映目前雇主的提撥值。

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a>簡化版的 Worker 表單搜尋產生寫明必須填寫個人欄位的訊息 (402525)

當您搜尋員工時，您將不再收到一則寫明您必須填寫 **個人** 欄位的訊息。

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a>須注意的是欄位值不會在新增更多技能表單上轉譯 (380134)

此項更改會改正當您個人化 Employee 自助服務中的 **新增更多技能** 表單時，遭遇的問題。

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a>轉調員工時，多項固定薪酬計劃不會到期 (389466)

隨著這項更改，舊職位的所有有效固定薪酬記錄將在轉任日期當天到期。

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