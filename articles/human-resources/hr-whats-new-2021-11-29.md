---
title: Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年十一月 19 日)
description: 本主題說明單機板 Microsoft Dynamics 365 Human Resources 於 2021 年十一月19 日新增或更改的功能。
author: marcelbf
ms.date: 12/03/2021
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
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 618d90f95637002f444b334e16d3fef466dda65e
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "8452691"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Dynamics 365 Human Resources 的新面貌或新轉變 (2021 年十一月 19 日)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明 Microsoft Dynamics 365 Human Resources 中全新、已更改或即將推出的功能。

更多有關我們的更新流程和期程資訊，請參閱[更新流程](hr-admin-setup-update-process.md)。

更多有關新功能及預計全面開放使用日期的資訊，請參閱 [Dynamics 365 Human Resources 2021 年發行版本第 2 波](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

## <a name="in-this-release"></a>此次發行版本中

此次發行版本包括BUG 修正如下。 更改適用組建編號 8.1.4591。

### <a name="bug-fixes"></a>BUG 修正

此次發行版本包括 BUG 修正如下。

> [!NOTE]
> 我們的目標是盡快讓您獲得這項資訊。 我們可能會更新本主題為包括初期公開本主題之後，將 BUG 修正納入建構範圍。

| 問題編號 | 問題 | 描述 |
|---|---|---|
| 626178 | **Manager 自助服務** 的背景工作角色圖格遺漏瀏覽功能 | 此問題現在已經修正。 瀏覽可用來查看 **Manager 自助服務** 中的報表細節。 |
| 632573 | 儲存 **課程** 時沒有驗證錯誤 | 此問題現在已經修正。 以 **最少參與者人數** 大於 0 建立課程時仍然獲准儲存，即使 **最多參與者人數** 為 0 亦然。 |
| 615955 | 建立新招募要求位置時，發生 "**目的** 欄位必須填寫" 的錯誤。 | 建立新招募要求位置的地址時，您會發生 "'目的'欄位必須填寫" 的錯誤。 然而，頁面上的 **目的** 欄位尚未開放使用。 |
| 620797 | **性別** 欄位空白的錯誤會誤導他人 | 當個人聯絡人未輸入性別時，報表顯示 "點選或輕點這裡輸入文字" – 這會誤導他人，因為此欄位根本無法輸入任何內容。 |
| 620800 | 福利對帳單連結已經隱藏 | **Employee 自助服務** 預設無法檢視福利對帳單。  連結已新增到 **連結** 區下方的 **Employee 自助服務** 右側 |
| 629778 | CDS 整合的效能問題。 | 授權相關要求導致的效能問題。 |

## <a name="in-preview"></a>預覽中

下列新功能預覽中。 更多有關開關功能方式的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

| 功能 | 發行版本計劃 | 文件 |
|---|---|---|
| 福利管理工作區 | [福利管理工作區 (預覽版)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [福利管理工作區](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>即將推出
關於計劃功能和排程的發行版本完整清單，請參閱 [Dynamics 365 和產業雲端：2021 年發行版本第 2 波](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
