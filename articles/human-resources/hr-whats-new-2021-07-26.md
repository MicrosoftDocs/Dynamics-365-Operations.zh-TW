---
title: Dynamics 365 Human Resources 的新面貌或新轉變 2021 年七月 26 日
description: 本主題說明 Microsoft Dynamics 365 Human Resources 於 2021 年七月26 日新增或更改的功能。
author: marcelbf
ms.date: 07/12/2021
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
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 810511c42cd690579d8c8b6ebcc17b0cf7fcb9eb2b999822dc2226fabd127cc6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451905"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 2021 年七月 26 日

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Dynamics 365 Human Resources 中全新、已變更或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [ Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括下列新功能和 BUG 修正。 更改適用組建編號 8.1.4384。

### <a name="new-features"></a>新功能

下列功能隨著此次發行版本全面開放。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 平台更新 10.0.20 | -- | [財務和營運應用程式版本 10.0.20 的平台更新 (2021 年八月)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 |  描述 |
| --- | --- | --- |
| 600422 | 準備付款的工資單地址驗證失敗。 | 驗證已經更新為只要求一處 '工資單居住地' 類型的地址和一處 '工資單工作地點' 類型的地址。 |
| 601226 | 資料整合問題：工資單匯出專案沒有全部發送選項 | 整合 Ceridian DayForce 的工資單是在做增量發送，而不是完全發送。 Ceridian 需要永遠完全重新整理。 此問題現在已經修正，資料匯出專案的實體將不再轉為增量發送。 |
| 602272 | 新增到 Employee Self Service 工作區的圖格現在遺失，圖格再也無法新增進去 | 我們已經修正 Employee 自助服務的個人化問題。 新圖格可以新增到視圖中，使用者將可以看見任何既有的個人化設定 |
| 600711 | 針對全天請假要求啟用半天定義選取欄位 | 此問題現在已經修正，而只有在員工選取已經啟用的半天定義 (半天為選取的金額值) 的請假類型時才會啟用半天定義欄位 |
| 602208 | 顯示小時而不是天的累計費率單位 | 此問題現在已經修正。 **休假** 表單將顯示 **累計費率** 欄位的正確請假單位 (小時或天)。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開啟或關閉功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
| --- | --- | --- |
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |
| 啟用簡化的工資單整合 (工資單整合 API) | [啟用與工資單提供商的簡化整合](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [工資單整合 API](hr-admin-integration-payroll-api-introduction.md)|
|  啟用缺勤經理管理請假 | [啟用缺勤經理管理請假](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | 隨著此次發行版本，我們正在更新缺勤經理工作區視圖。 更多資訊，請參閱[配置缺勤經理角色](https://go.microsoft.com/fwlink/?linkid=2168107)。|
|  配置每個請假類型的附件要求 | [配置每個請假類型的附件要求](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[配置請假和缺勤類型](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  配置每個請假類型的請假單位 | [配置每個請假類型的請假單位](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[配置請假和缺勤類型](https://go.microsoft.com/fwlink/?linkid=2168215)|
| 使員工被標記為準備支付 | [使員工被標記為準備支付](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [準備支付](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>即將推出

關於已計劃功能的完整清單和排程的發行版本，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

## <a name="see-also"></a>也請參閱

[人力資源的新面貌或新轉變](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 年發行版本第 2 波概觀](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[更新流程](hr-admin-setup-update-process.md)</br>
[管理功能](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
