---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年三月 8 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年三月8 日新增或更改的功能。
author: marcelbf
ms.date: 03/08/2021
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
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 133cfffadabade8f7770b4853e14b769c5b961370546e3104d6db26bc0c6331a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451875"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年三月 08 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4017。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 經理請假的跨公司視圖 | [員工為經理請假的跨公司視圖](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [配置請假和缺勤參數](./hr-leave-and-absence-parameters.md) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 486611 | 缺勤的請假會在啟用 **停用所有行事曆上的請假** 功能時，顯示在請假行事曆 | 如果啟用 **停用所有行事曆上的請假**，請假和缺勤行事曆強化功能啟用時，即不再顯示請假資訊。|
| 508972 | Leave and Absence Bank Transaction 實體遺漏註冊的驗證 | 使用 Leave and Absence Bank Transaction 實體時，無法再匯入尚未註冊到計劃的員工。 |
| 554854 | 如果與使用者選項的預設法人實體不同，更新 Employment 實體的行事曆會出錯 | 如果與使用者選項的預設法人實體不同，使用 Employment 實體更新員工的行事曆就不會再出錯。 |
| 558347 | 載入起始頁時會出現 "無法在表單配置 (FormRunConfiguration) 建立記錄"。 | 載入起始頁時，個人化會出現 "無法在表單配置 (FormRunConfiguration) 建立記錄" 的錯誤。 |
| 557327 | 福利管理工作區：格線上方會出現縫隙。 | 福利工作區中的資料表格線邊框上方意外出現縫隙的使用者體驗問題已經修正。 |
| 557334 | 福利管理工作區：**期間** 選取下拉式方塊應該只出現在 **總結** 索引標籤 | 福利 **期間** 選取下拉式清單現在只在 **總結** 索引標籤在福利工作區有效，且不在 **處理結果** 和 **連結** 專區時才會出現。 |
| 557336 | 福利管理工作區：圖格視圖的 **開放已核定計劃的註冊** 文字遭到截斷 | 將圖格視圖的文字更改為 **已核定計劃...開放註冊**，避免截斷必要的上下文。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 限制員工編輯商業聯絡人細節 | [限制員工編輯商業聯絡人細節](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [限制個人資訊的編輯](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>即將推出

| 功能 | 詳細資料​​ |
| --- | --- |
| 經理為其員工輸入的技能可由工作流程自動核准 | 即將推出。 |

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 1 波概觀](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]