---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年二月 12 日)
description: 本文說明 Microsoft Dynamics 365 Human Resources 於 2020 年二月 12 日新增或更改的功能。
author: andreabichsel
ms.date: 02/07/2020
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
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ac274cc18ddb3392fb118dcc1df7813cbc5b8293
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452046"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-12-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年二月 12 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.2867。 某些標題括號裡的數字意指 Microsoft Dynamics Lifecycle Services (LCS) 裡的支援編號。

## <a name="existing-entities-compfixedempls-and-hcmpersonimage-should-be-accessible-from-odata-414178"></a>既有實體 CompFixedEmpls 和 HcmPersonImage 應可從 OData 存取 (414178)

隨著本週發行版本的問市，**CompFixedEmpls** 和 **HcmPersonImage** 實體現在已經公開並透過 ODAta 使用。

## <a name="delete-employment-from-dataverse-doesnt-work-when-employment-details-arent-active-403193"></a>當雇用細節無效時，無法從 Dataverse 刪除雇用 (403193)

此項更改現在允許有效雇用細節不存在時，透過 Dataverse 刪除雇用。

## <a name="course-registration-workflow-changes-status-to-complete-and-errors-after-second-approval-409749"></a>課程註冊工作流程在第二次核准後，將狀態更改為已完成和有錯誤 (409749)

課程註冊工作流程已更新為允許多名核准者。

## <a name="in-preview"></a>預覽中

下列預覽功能在 2020 年二月 3 日推出：

- **請假和缺勤預覽功能**  - 更多資訊，請參閱[請假和缺勤預覽功能](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)。

- **福利管理預覽功能**- 更多資訊，包括已知問題，請參閱[福利管理概觀](hr-benefits-management-overview.md)。

## <a name="coming-soon"></a>即將推出

### <a name="platform-update-32"></a>平台更新 32 

平台更新 32 即將推出。 [這裡探究更多有關平台更新 32 的資訊](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md)。

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

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]