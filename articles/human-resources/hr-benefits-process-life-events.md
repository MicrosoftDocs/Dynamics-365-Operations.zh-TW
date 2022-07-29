---
title: 處理生活事件
description: 在 Microsoft Dynamics 365 Human Resources 的員工生命週期期間，每位員工都有可能遭遇各種生活事件的變化。
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9155795edf657d6589539e58d4c1536f7e9d64c3
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452568"
---
# <a name="process-life-events"></a>處理生活事件


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

在 Microsoft Dynamics 365 Human Resources 的員工生命週期期間，每位員工都有可能遭遇各種生活事件的變化。 例如，婚姻、就業變化或家屬/受益人變化。 若要使用生活事件，您必須在 **福利參數** 頁啟用生活事件、設定生活事件類型，並為計劃類型設定生活事件選項。

在您可以處理生活事件之前，您必須在錄用時間範圍內至少執行一次開放註冊。 在美國，典型開放註冊是每年一次。 美國境外則在錄用時開放註冊。 背景工作角色不必選取福利計劃才能處理生活事件，但他們必須已納入開放註冊處理範圍。 

當您的背景工作角色某個未來日期當天發生生活事件，請使用生活事件處理。 本事件將處理所有尚未處理的生活事件 (比方未來生活事件，或已新增不特定於任何一個背景工作角色的生活事件 - 一個範例是新福利)。 即時生活事件已隱藏。

例如，如果今天是二月 1 日，而背景工作角色 Joe Smith 排定二月 14 日變更法人實體，如果您執行二月 15 日的生活事件處理，系統會處理直到二月 15 日的所有事件。 

1. 請在 **處理** 下方的 **福利管理** 工作區選取 **生命事件處理**。

2. 請在 **執行生活事件流程** 對話方塊中指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **註冊期間** | 處理生活事件所屬的註冊期間。 |
   | **法人實體** | 處理生活事件所屬的法人實體。 |
   | **生活事件日期** | 系統處理在此日期之前發生的註冊期間所有事件。 |
   | **工作人員** | 處理生活事件所屬的背景工作角色。 如果您將本欄位留空白，將處理所有背景工作角色的生活事件。 |

3. 如果您希望背景執行此流程，請選取 **背景執行** 並進行任務如下：

   1. 輸入流程資訊。

   2. 若要設定重覆性工作，請選取 **重覆性**，輸入重覆性資訊並選取 **確定**。

   3. 若要設定工作警報，請選取 **警報** 和要接收的警報，然後選取 **確定**。

   4. 選取 **確定**。 本段流程將使用您設定的參數執行。

4. 選取 **確定**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
