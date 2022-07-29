---
title: 設定所有公司福利管理和員工自助服務參數
description: 在 Microsoft Dynamics 365 Human Resources 中配置福利管理和員工自助服務參數。
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 822e5b37be7b2d5712d61bf7fb00f40d1692f406
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452283"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>設定所有公司福利管理和員工自助服務參數


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

在 Microsoft Dynamics 365 Human Resources 中設定福利計劃之前，您必須先配置福利管理參數。 這些參數負責設定預設值、原因代碼和其他選項。 

## <a name="configure-general-parameters"></a>配置一般參數

1. 請在 **設定** 下方的 **福利管理** 工作區選取 **人力資源共用參數**。

2. 請在 **福利管理** 索引標籤中指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **國家/地區** | **國家/地區** 欄位負責判定郵遞區號/州的顯示順序。 選取國家/地區會先顯示在下拉式清單。 |
   | **註冊原因代碼** | 選取員工在開放註冊處理期間建立員工計劃時預計使用的預設原因代碼。 |
   | **取消原因代碼** | 取消員工福利計劃時預計使用的原因代碼。 它在取消流程中顯示在對話方塊。 必要時使用者可以變更為 **取消原因代碼**。 |
   | **重新開放原因代碼** | 重新開放員工福利計劃時預計使用的原因代碼。 它在取消流程中顯示在對話方塊。 必要時使用者可以變更為 **重新開放原因代碼**。 | 
   | **生活事件原因代碼** | 生活事件發生時預計使用的原因碼。 |
   | **費率變更原因代碼** | 在費率變更與更新流程中取消和重新開放員工福利計劃時預計使用的原因代碼。 它指明經過費率變更與更新流程所變更的記錄。 |
   | **福利年薪** | 讓您設定員工的 **福利年薪** 金額。 人力資源在判定承保範疇金額時將使用 **福利年薪** 金額，而不是固定年度薪酬金額。 |
   | **具備資格的準員工** | 指明準員工是否具備資格。 |
   | **準員工註冊期間** | 允許準員工註冊的時段。</br></br>**注意**：本項設定覆寫您在計劃資格規則中設定的任何準員工註冊期間。 |
   | **預設支付頻率** | 新增新背景工作角色時預計使用的預設支付頻率。 |
   | **已啟用的生活事件** | 啟用生活事件。 |
   | **隱藏舊版福利表單** | 允許您隱藏舊版福利表單。 |
   | **福利驗證** | 總結自助服務福利期間預計使用的驗證文字。 |
   | **自動選取被指定對象** | 指明是否根據家屬和受益人的計劃選項資格自動選取。 |

3. 選取 **儲存**。

## <a name="configure-employee-self-service-parameters"></a>配置員工自助服務參數

1. 請在 **設定** 下方的 **福利管理** 工作區選取 **人力資源參數**。

2. 請在 **福利管理** 索引標籤中指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **福利驗證** | 總結自助服務福利期間預計使用的驗證文字。 |
   | **自動選取被指定對象** | 指明是否根據家屬和受益人的計劃選項資格自動選取。 |

3. 選取 **儲存**。




[!INCLUDE[footer-include](../includes/footer-banner.md)]
