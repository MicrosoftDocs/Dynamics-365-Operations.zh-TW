---
title: 預算編製首頁
description: 本主題概述了 Microsoft Dynamics 365 Finance 中的預算編製功能元件、預算編製工具和報告功能。
author: panolte
ms.date: 04/29/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "106043"
- intro-internal
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ad0d055702a3801bf9fe9ac3159eba7c297b6f0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451413"
---
# <a name="budgeting-home-page"></a>預算編製首頁

[!include [banner](../includes/banner.md)]

本主題概述了預算編製功能元件、預算編製工具和報告功能。 

## <a name="components-of-budgeting-functionality"></a>預算編製功能的元件

公司的資源計劃週期通常包括計劃、預算編製和預測活動。

[![預算編製功能元件。](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

長期戰略規劃和年度預算規劃的流程透過預算計劃文件獲得支援。 預算計劃文件與 Microsoft Excel 緊密整合。 使用者可以設定無數的貨幣和數量方案，也可以定義預算編製組織層次結構，以支援自上而下和自下而上的預算編製方法。 在應用程式中建立並核准預算後，將預算計劃轉換為預算登記分錄。 預算登記分錄提供了用於維護預算和透過預算代碼保持金額的可追溯性工具。 預算登記分錄可讓您修改原始預算、執行轉移和結轉上一年的預算金額。 根據已建立的預算，公司可以啟用預算控制。 控制等級取決於組織文化和組織的成熟度。 成熟度低的組織可能會「按原樣」保留預算，如果預算未達預期，它們更可能是被動回應，而不是主動採取措施。 其他組織可能會啟用預算控制原則以防止使用者在沒有預算資金時進行採購。

最後，非常成熟的組織可能會建立一種組織文化，讓員工接受有關組織目標的教育，並透過「考慮線上會議而不是出差」之類的原則來實現這些目標。 該應用程式包括一個預算控制框架，讓公司管理層可以選擇硬控制 (防止過帳超出預算) 或軟控制 (使用者將收到超出可用預算資金的警告，但他們可以自行決定如何繼續)。 最後，您可以使用滾動預測。 滾動預測是預算與實際支出的定期比較，用於確定公司在預算方面的執行情況。 滾動預測也用於確定趨勢。 在財務和營運應用程式中，透過預算計劃文件支援滾動預測作為初始規劃活動。 滾動預測可以與即將到來的預算週期的規劃並行執行。

-   [預算編制概觀](basic-budgeting-overview-configuration.md)
-   [預算控制概觀](budget-control-overview-configuration.md)
-   [預算規劃概觀](budget-planning-overview-configuration.md)
-   [職位預測](position-forecasting.md)
-   [預算規劃證明文件](budget-planning-justification-docs.md)
-   [Excel 的預算規劃範本](budget-planning-excel-templates.md)

## <a name="budgeting-tools"></a>預算編製工具
[![預算編製工具。](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

提供了其他規劃和預算編製功能，並與分類帳預算整合。

-   **勞動力預算** – 勞動力預算編製包括職位、薪資群組等方面的詳細預算成本構成計劃。
-   **固定資產預算** – 根據固定資產資訊，您可以計算規劃的折舊並記錄其他與固定資產相關的規劃交易。
-   **專案預算** – 在專案模組中，您可以建立詳細的專案預測。 專案預測將包括有關規劃時間、支出、費用和項目的詳細資料。
-   **需求預測** – 根據歷史交易資料，您可以預估未來的庫存需求並建立需求預測。

有關如何將其他模組中的規劃資料引入預算計劃的資訊，請參閱[預算規劃與其他模組的整合](budget-planning-integration-other-modules.md)。

## <a name="user-interface-and-reporting-capabilities"></a>使用者介面和報告功能
使用者可以直接在客戶端 (透過使用可設定的預算計劃文件頁面) 或透過 Excel 建立預算計劃。 Excel 提供了幾個附加功能。 例如，您可以將外部資料用作預算計劃的來源、進行自訂計算以及使用 Microsoft 資料透視表和圖表。 預算規劃流程中的大部分變數都可以進行設定。 

例如，您可以定義執行預算編製的人員、預算的對象以及具體流程。 儘管您可以使用 Excel 進行預算規劃，但該應用程式仍將作為單一資料來源，幫助防止預算控制問題。 週期性流程可用於將預算的初始資料納入預算計劃。 對於報告，該應用程式提供了一組標準查詢頁面，可讓您查看和分析預算編製資料。 預算計劃資料可以透過[財務報告](../general-ledger/financial-reporting-getting-started.md)存取，單獨的預算計劃方案可在財務報告中顯示為資料行。








[!INCLUDE[footer-include](../../includes/footer-banner.md)]
