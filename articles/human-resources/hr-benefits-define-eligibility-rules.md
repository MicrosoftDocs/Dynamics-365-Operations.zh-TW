---
title: 定義福利資格規則和政策
description: 本主題說明建立福利資格規則和政策，然後指派規則給福利的方式。
author: twheeloc
ms.date: 08/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: c2595e40f6f9d1f75a94a3339735cc06bdabd14a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452379"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>定義福利資格規則和政策


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明建立福利資格規則和政策，然後指派規則給福利的方式。  

## <a name="create-benefit-eligibility-policy-rule-type"></a>建立福利資格政策規則類型

1. 請前往 **人力資源>福利>資格>福利資格政策規則類型**。
2. 選取 **新增**。
3. 請在 **規則名稱** 欄位中輸入值。
4. 在 **描述** 欄位中輸入一值。
5. 請在 **查詢名稱** 欄位中選取下拉式按鈕開啟查閱功能。
6. 請在清單選取已選取行的連結。
7. 選取 **儲存**。
8. 關閉頁面。

## <a name="benefit-eligibility-policy"></a>福利資格政策

1. 請前往 **人力資源>福利>資格>福利資格政策**。
2. 選取既有的福利政策。
3. 請在清單選取已選取行的連結。
4. 切換展開 **政策組織** 區段。 您可以新增或刪除要納入政策的任何組織。
5. 展開或摺疊 **原則規則** 區段。
6. 請在清單找出之前建立的政策規則。
7. 按一下 **建立原則規則**。
8. 請在 **生效日期** 欄位輸入您希望政策生效的日期。
    * 設定生效結束日期可讓您變更未來政策規則，如此一來，您就不必在希望這些變更生效時返回政策。  
9. 必要時將 where 子句新增到 **新增條件** 欄位。
    * 例如，如果您希望規則只適用銷售經理，您可以建立 where 子句表示：職位說明等於銷售經理。 您可以在規則中一起新增多個 where 子句。  
10. 選取 **確定**。
11. 關閉頁面。

## <a name="assign-rule-to-benefit"></a>指派規則給福利

1. 前往 **人力資源>福利>福利**。
2. 在清單中，尋找並選取所需的記錄。
3. 請在清單選取已選取行的連結。
4. 展開或收合 **資格規則** 區段。
5. 選取 **編輯**。
6. 請在 **資格** 欄位中選取規則。
7. 請在 **規則類型** 欄位選取您之前建立的規則。
9. 請在清單選取已選取行的連結。
10. 選取 **儲存**。
11. 關閉表單。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
