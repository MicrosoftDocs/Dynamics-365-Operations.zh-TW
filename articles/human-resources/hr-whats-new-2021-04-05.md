---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年四月 5 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年四月5 日新增或更改的功能。
author: marcelbf
ms.date: 04/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d91ef244f8dd48baf65f5633357a7d81a68f84621b20d39d4e0ee771283a2bab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451896"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年四月 5 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4074。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 限制員工編輯商業聯絡人細節 | [限制員工編輯商業聯絡人細節](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [限制個人資訊的編輯](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 550852 | **核准** 按鈕不以 **審核** 表單設定的必填欄位驗證。 | 當您將 **審核** 表單欄位設定為必填欄位，並且發佈經理角色的更改，此表單未如預期驗證。 |
| 559564 | 聘雇狀態已終止的使用者，在歷史背景工作角色更改固定薪酬的動作執行上會出錯。 | 已離職員工薪酬的背景工作角色動作會出錯。 待員工的聘雇狀態終止後，背景工作角色終止前的升職動作會出錯。 |
| 560074 | 雇用類別下拉式清單並未篩選 **背景工作角色類型**，並且顯示員工和承包商類別。 | **員工** 表單上的 **雇用類別** 下拉式清單應根據員工的背景工作角色類型顯示員工或承包商類別。 |
| 567388 | 新建立員工的若干資訊不會立即與 Dataverse 中的 **cdm_worker** 資料表同步。 | 建立新員工記錄時，新記錄會與 Dataverse 中的 **cdm_worker** 表單同步，但並非所有屬性都會納入 Dataverse 記錄。 |
| 563837 | 人力資源顯示畫面尚未開放使用的功能。 | 不適用人力資源的幾項功能顯示在功能管理中。 這些功能現在已經從人力資源開放啟用的功能清單刪除。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 經理為其員工輸入的技能可由工作流程自動核准 | 即將推出。 |
| 平台更新 10.0.17 (41) | 平台更新 10.0.17 排程與下次 2021 年四月 19 日的發行版本一起推出。 更多資訊，請參閱 [財務和營運應用程式版本 10.0.17 的平台更新 (2021 年四月)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md)。 |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]