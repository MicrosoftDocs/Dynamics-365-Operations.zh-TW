---
title: 預算計劃理由文件
description: 理由文件讓要求預算的人提供說明，以解釋為什麼需要特定預算。
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5eb74b5d2b71372f99dd927ff6e2bee96e199a6f75b3ae920607e5ec37a4241a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450558"
---
# <a name="budget-planning-justification-documents"></a>預算計劃理由文件

[!include [banner](../includes/banner.md)]

理由文件讓要求預算的人提供說明，以解釋為什麼需要特定預算。 

預算計劃範本由預算經理在 Microsoft Word 中建立，並分配給目前的預算計劃流程。 然後預算所有者可以打開範本並根據他們的預算要求在 Word 中自動填入資料。 儲存個人化理由文件並將其附加到預算計劃之前，可以新增更多文字或資料。

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>設定 Microsoft Word 的 Microsoft Dynamics Office 增益集

1.  開啟新的 Microsoft Word 文件。
2.  點擊功能區上的 **插入**，然後點擊 **商店**。
3.  搜尋 Microsoft Dynamics Office 增益集並點擊 **新增**。
4.  在 Word 的右窗格中，點擊 **新增伺服器資訊**。
5.  鍵入或貼上伺服器 URL，然後點擊 **確定**。

##### <a name="define-the-justification-template-in-microsoft-word"></a>在 Microsoft Word 中定義理由範本

1.  登入後，點擊 Microsoft Dynamics  Office 增益集中的 **設計**。
2.  對於標題資訊，請使用 **新增欄位** 按鈕。
3.  選擇實體資料來源 BudgetPlanJustification，然後點擊 **下一步**。 **請注意：** 任何理由文件都需要該實體。 可以使用其他實體，但如果不包含此實體，上傳回 Microsoft Dynamics 365 Finance 將失敗。
4.  在 Word 文件中新增 BudgetPlanName、BudgetPlanPreparer、ResponsibilityCenter 和 DocumentNumber 標籤和值。 **請注意：** 如果需要，您可以使用自己的自訂標籤，而不是標準標籤。
5.  點擊 **完成** 以完成標題區段。
6.  有關預算計劃金額的行等級詳細資料，請點擊 **新增資料表**。
7.  再次選擇實體資料來源 BudgetPlanJustification，然後點擊 **下一步**。
8.  為 EffectiveDate、ScenarioName、AccountDisplayValue 和 AccountingCurrencyExpenseAmount 新增欄位。 **請注意：** 如果可以在各個預算計劃行中新增註解，則可以將其新增到此處的資料表中。
9.  新增任何附加說明以提供給終端使用者，並對文件執行任何必要的格式設定或樣式設定。
10. 將文件儲存到本機電腦並關閉檔案，然後再繼續。

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>設定預算計劃流程以使用理由範本

1.  前往 **預算編製** &gt; **設定** &gt; **預算計劃** &gt; **理由文件範本**。
2.  點擊 **新增** 並瀏覽到您新建立的 Microsoft Word 文件。
3.  輸入範本顯示名稱和描述。 點選 **確定**。
4.  前往 **預算編製** &gt; **設定** &gt; **預算****計劃** &gt; **預算計劃流程**。
5.  選擇應使用理由範本的流程，然後點擊 **編輯**。
6.  在 **理由文件範本** 欄位中，選擇相應的範本並儲存。

##### <a name="edit-and-save-personalized-justification-documents"></a>編輯和儲存個人化的理由文件

1.  建立新的預算計劃或打開現有的預算計劃。
2.  在 **理由** 下拉式功能表中，選擇 **建立新的理由**。
3.  填寫詳細資料後，選擇從 **理由** 下拉式功能表上傳個人化的文件。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]