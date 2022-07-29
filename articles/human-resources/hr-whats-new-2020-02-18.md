---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年二月 18 日)
description: 本文說明 Microsoft Dynamics 365 Human Resources 於 2020 年二月18 日新增或更改的功能。
author: andreabichsel
ms.date: 02/18/2020
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
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9cce93aab902a8ca269cf22e1999716fe49f3ed8
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452043"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年二月 18 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.2903。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="platform-update-32"></a>平台更新 32 

平台更新 32 現在已經問市。 更多資訊，請參閱 [財務與營運平台更新 32 (2020 年二月) 新增或更改的功能](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md)。

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>在簡化的員工表單中更改視圖選項時須記住搜尋值 (383833)

新 **背景工作角色** 表單現在會在您更改視圖選項和套用更改時，記住搜尋值。

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>預覽功能的薪酬管理摘要圖塊重新轉向到錯誤表單 (401861)

現在，固定和變動薪酬管理圖格在新 **背景工作角色** 表單顯示正確的記錄。 只套用在簡化的員工表單預覽功能。 您可以在 **功能管理** 啟用此預覽功能。 更多資訊，請參閱[管理功能](hr-admin-manage-features.md)。

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a>Dataverse 中的若干請假要求記錄的空白狀態欄位 (414915)

此項更改改正當請求要求的 **狀態** 欄位設定為 **審核** 時，在 Dataverse 出現的問題。 Dataverse 現在反映狀態。

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>技能落差分析只可能適用指派的工作 (411390)

現在您可以對人力資源定義的任何工作進行技能落差分析。

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a>系統貨幣未從 Dataverse 同步到新環境的人力資源 (418011)

Dataverse 系統貨幣現在可以同步到人力資源。

## <a name="in-preview"></a>預覽中

- [請假和缺勤預覽功能](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [福利管理預覽功能](hr-benefits-management-overview.md)

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

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]