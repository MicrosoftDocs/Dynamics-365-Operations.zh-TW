---
title: 處理註冊資格
description: 本主題說明如何執行註冊資格流程。
author: twheeloc
ms.date: 08/23/2021
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
ms.openlocfilehash: e8997cf24bf24097e46a05acffef8b3839056c57
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452376"
---
# <a name="process-enrollment-eligibility"></a>處理註冊資格


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明如何執行註冊資格流程。

1. 請在 **處理** 下方的 **福利管理** 工作區選取 **註冊資格處理**。

2. 請在 **執行福利註冊資格流程** 對話方塊中指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **註冊期間** | 處理註冊資格所屬的註冊期間。 |
   | **法人實體** | 處理註冊資格所屬的法人實體。 |
   | **工作人員** | 處理註冊資格所屬的背景工作角色。 如果您將本欄位留空白，將處理所有背景工作角色的註冊資格。 |
   | **福利計劃** | 處理註冊資格所屬的福利計劃。

3. 如果您希望背景執行此流程，請選取 **背景執行** 並進行任務如下：

   1. 輸入流程資訊。

   2. 若要設定重覆性工作，請選取 **重覆性**，輸入重覆性資訊並選取 **確定**。

   3. 若要設定工作警報，請選取 **警報** 和要接收的警報，然後選取 **確定**。

   4. 選取 **確定**。 本段流程將使用您設定的參數執行。

4. 選取 **確定**。

## <a name="view-process-results"></a>檢視處理結果

本主題說明如何檢視資格處理結果。

1.  請在 **處理** 下方的 **福利管理** 工作區選取 **處理結果**。

2.  請 **處理結果** 頁面指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **流程識別碼** | 背景工作角色、法人實體和流程執行組合的唯一識別碼。 |
   | **流程類型** | 這可辨別執行的流程。 例如：註冊。 |
   | **時間戳記** | 資格流程的執行時間。 |
   | **法人實體** | 註冊流程期間指定的法人實體。 |
   | **工作人員** | 被處理的背景工作角色。 |
   | **計劃 | 企圖註冊的福利計劃。 |
   | **資格規則** | 已經處理的資格規則。 如果在執行資格之前遭遇錯誤，這將會空白。 例如：如果尚未為背景工作角色定義薪酬，則資格流程將不會執行，並且此欄位將會留下空白。 |
   | **結果狀態** | 這將是具備資格或不具備資格。 如果背景工作角色不符合資格規則標準、背景工作角色缺少必要資訊如支付頻率或固定薪酬，或者福利計劃缺少資訊，阻止背景工作角色註冊，則結果狀態將為不具備資格。 |
   | **結果訊息** | 指出背景工作角色沒有資格享有福利計劃的原因或是否通過資格規則審查。 |



[!INCLUDE[footer-include](../includes/footer-banner.md)]
