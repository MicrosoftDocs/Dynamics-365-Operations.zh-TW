---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年四月 13 日)
description: 本文說明 Microsoft Dynamics 365 Human Resources 於 2020 年四月13 日新增或更改的功能。
author: andreabichsel
ms.date: 04/13/2020
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
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b5af74329fa741a443932a1007a6c2ef6abd3445
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452031"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2020 年四月 13 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



本文說明在 Dynamics 365 Human Resources 的新增或更改的功能。 更改適用組建編號 8.1.3136。 某些標題括號裡的數字意指 LCS 支援參考的編號。

## <a name="new-production-release-cadence"></a>新實際執行發行版本節奏

隨著本週發行版本的問市，人力資源的版本節奏從每週更新轉為每兩週更新。 為了確保對齊安全部署實務作法，並維持服務穩定性和可靠性的高標準，現在改為每兩週推出全部區域部署服務更新版本的流程。 額外測試和監視已經準備好可以驗證流程中各階段的部署成效。 更多發行版本節奏的資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>指明進位類型後，進位精確度欄位不可編輯 (435616)

隴著這項更改，待您更新 **進位類型** 欄位後，**進位精確度** 欄位即可開放使用。

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>當請假計劃未安排累計期間時，就無法編輯請假登記結束日期 (413628)

您現在可以編輯登記結束日期，不會出現 "必須填寫欄位累計日期基礎" 的錯誤。

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a>雇用實體尚未與 Dataverse 同步 (430834)

此項更改改正新增財務維度後，雇用資料未與 Dataverse 同步的問題。 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>移除 Work Calendar Time 間隔時間實體多重父系 (431775)

本項更改移除 **Work Calendar Time 間隔時間** 實體多重父系。

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>以 CAST 函數操作的篩選條件不適用 OData 調用職位背景工作角色指派實體 (431699)

此項更新包括允許 OData 內的 CAST 函數篩選 **職位背景工作角色指派** 實體的更改。

## <a name="in-preview"></a>預覽中

## <a name="leave-suspension"></a>請假暫停

您可以暫停員工在人力資源的請假和缺勤。 暫停請假會停止選取請假類型的請假累計。 如果累計處理之後發生暫停，暫停請假會對員工的請假餘數按比例調整。 更多資訊，請參閱[暫停請假](hr-leave-and-absence-suspend-leave.md)。

## <a name="carry-forward-rules"></a>結轉規則

您可以針對轉移結轉調整的結轉餘數指明結轉假期類型。 例如，如果員工結轉 10 天，您可以為那 10 天選取不同的請假類型。 更多資訊，請參閱[配置請假和缺勤類型](hr-leave-and-absence-types.md)。

## <a name="known-issues"></a>已知問題

## <a name="employment-details-entity"></a>雇用細節實體

**雇用細節** 實體已經更新為下列欄位：

- **PayFrequency**
- **雇用類別識別碼**
- **雇用類型**
- **雇用類型識別碼**
- **福利雇用狀態**

這些欄位的設定資料得依照 **功能管理** 工作區啟用的福利管理才能操作。 切勿填寫或更新 **雇用細節** 實體的欄位，因為它會導致匯入期間出錯。

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint 預覽功能在一些環境行不通

如果儲存在 SharePoint 的文件預覽行不通，請嘗試下列步驟：

1. 驗證管理使用者帳戶的電子郵件是否與使用者記錄相關聯。 您可以在 **使用者** 頁面檢視這項資訊。 如果電子郵件尚未設定，您需要使用 OData Excel 增益集新增電子郵件和提供商。 電子郵件地址預設不在 Excel 設計範圍。 您將需要編輯 Excel 設計、新增所有欄位、套用和重新整理。 一旦完成這些步驟，您就可以更新管理帳戶。

2. 待管理帳戶有關聯的電子郵件帳號後，使用管理員憑據登入人力資源。

3. 存取 SharePoint 的附件開始文件預覽。

4. 使用可存取附件的另一個使用者帳戶登入並驗證預覽是否如預期運作。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 年發行版本第 2 波概觀](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]