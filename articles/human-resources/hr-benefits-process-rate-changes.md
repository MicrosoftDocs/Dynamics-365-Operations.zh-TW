---
title: 處理費率變更
description: 本主題說明如何在 Microsoft Dynamics 365 Human Resources 的處理福利費率變更方式。
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e0dfbdde8ee950a0341fffb1e268fff05434953
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452628"
---
# <a name="process-rate-changes"></a>處理費率變更


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明當新的或既有的福利計劃資格規則設定有任何變更時，在 Microsoft Dynamics 365 Human Resources 處理福利費率變更的方式。 如果已建立新的資格規則並將其指派給計劃，則會提示系統重新執行背景工作角色資格，以根據新資格選項檢查背景工作角色現在是否有資格加入此項計劃。 

1. 請在 **處理** 下方的 **福利管理** 工作區選取 **費率變更更新處理**。

2. 請在 **執行福利費率更新流程** 對話方塊中指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **註冊期間** | 處理費率變更所屬的註冊期間。 |

3. 如果您希望背景執行此流程，請選取 **背景執行** 並進行任務如下：

   1. 輸入流程資訊。

   2. 若要設定重覆性工作，請選取 **重覆性**，輸入重覆性資訊並選取 **確定**。

   3. 若要設定工作警報，請選取 **警報** 和要接收的警報，然後選取 **確定**。

   4. 選取 **確定**。 本段流程將使用您設定的參數執行。

4. 選取 **確定**。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
