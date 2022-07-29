---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年八月 23 日)
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年八月23 日新增或更改的功能。
author: marcelbf
ms.date: 08/23/2021
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
ms.search.validFrom: 2021-08-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 21c9ee0206bd77a8a2ec42501d64e83077baef09
ms.sourcegitcommit: 696796ca5635863850ae9ef16fc1fb0fc46ce8f0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2021
ms.locfileid: "8451950"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-23-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年八月 23 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Microsoft Dynamics 365 Human Resources 中全新、已更改或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4419。

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能會更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 | 描述 |
| --- | --- | --- |
| 594066 | 無法刪除聯絡資訊 | 選取刪除員工的聯絡資訊記錄時，反而會刪除選取記錄以外的聯絡資訊記錄。 |
| 611339 | 新增個人化項目會導致銀行帳戶忽略篩選條件並獲取第一筆記錄 | 新增個人化項目會導致銀行帳戶清單在資料來源查詢功能執行後，執行個人化查詢，進而導致查詢獲取最上方記錄，不論是否正在檢視背景工作角色的細節。 |
| 591806 | 到職截止日期任務計算方法不正確 | 當存在下列情況時，到期日期計算方法不正確：建立的核對清單正在使用時間範圍已經接長的行事曆 (例如從 2005 年到 2050 年)，並且使用者的喜好利用中央標準時間以外的時區。 |   
| 592749 | **Employee 自助服務** 上的請假餘數不正確 | 如果員工受雇於多間法人實體並且啟用跨公司請假視圖功能，則請假餘數可能不正確。 |
| 603133 | 要求休假時出現意外警告 | 要求休假時，在 **數額** 欄位前填寫 **半天** 將導致意外警告。 |
| 606546 | 選取在已核准的休假中看不見的欄位 | 預計選取多項已核准請假要求的勾選方塊並未出現。 |
| 597059 | **請假和缺勤公司行事曆** 看不見背景工作角色 | 如果申請的日期範圍包括他們的請假要求遭到駁回的任何一日，**請假和缺勤公司行事曆** 會看不見背景工作角色。 |


## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開關功能方式的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md)|
| 啟用缺勤經理管理請假 | [啟用缺勤經理管理請假](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | 此次發行版本中，我們正在更新缺勤經理工作區視圖。 更多資訊，請參閱[配置缺勤經理角色](https://go.microsoft.com/fwlink/?linkid=2168107)。 |
| 配置每個請假類型的附件要求 | [配置每個請假類型的附件要求](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[配置請假和缺勤類型](https://go.microsoft.com/fwlink/?linkid=2168108)|
| 配置每個請假類型的請假單位 | [配置每個請假類型的請假單位](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[配置請假和缺勤類型](https://go.microsoft.com/fwlink/?linkid=2168215)|
| 使員工被標記為準備支付 | [使員工被標記為準備支付](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [準備支付](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>即將推出

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

| 功能 | 詳細資料​​ |
| --- | --- |
| 平台更新 10.0.21 (45) | 平台更新 10.0.21 的推出排程在與 2021 年十月 4 日的服務版本一同開始。 更多資訊，請參閱[財務和營運應用程式版本 10.0.21 的平台更新 (2021 年十月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21)。 |

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
