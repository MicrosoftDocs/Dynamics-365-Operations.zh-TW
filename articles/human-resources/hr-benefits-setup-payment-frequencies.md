---
title: 設定付款頻率
description: Microsoft Dynamics 365 Human Resources 使用支付頻率計算年度福利薪資，判定員工在每個支付期間所支付的福利保費金額，以及支付給提供者的頻率。
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
ms.openlocfilehash: ee21f24b2da8501888ac3c0a8b9a35c24785aa4f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452559"
---
# <a name="set-up-payment-frequencies"></a>設定付款頻率


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources 使用支付頻率計算年度福利薪資，判定員工在每個支付期間所支付的福利保費金額，以及支付給提供者的頻率。

福利支付頻率使用轉換因子在每月、每半月、每兩週、每週和每日支付頻率之間轉換福利支付週期。 這允許公司定義福利計劃內支付頻率之間的相互依存關係。

轉換因子欄位從支付頻率到標準支付週期辨別轉換因子，並且允許系統在支付頻率之間計算。 轉換因子金額也判定員工應在每次支付頻率支付的福利保費金額。

1. 請在 **設定** 下方的 **福利管理** 工作區選取 **付款頻率**。

2. 選取 **新增**。

3. 請指定下列欄位值：

   | 欄位 | 描述 |
   | --- | --- |
   | **付款頻率** | 唯一的付款頻率名稱。 |
   | **描述** | 付款頻率說明。 |
   | **期間** | 最福利提供者和員工付款頻率最適配的適當期間。 期間清單由標準付款期間組成。 |
   | **支付期數** | 代表福利提供者或僱主支付各筆的支付期數。 本金額將用來計算員工的年度福利薪資金額。 |
   | **年轉換因子** | 支付頻率的年轉換因子。 例如，月支付頻率的年轉換因子為： </br></br>(12 個月付款/1 年) = 12 |
   | **半年轉換因子** | 付款頻率的半年轉換因子。 例如，月支付頻率的半年轉換因子為： </br></br>(12 個月付款/每年 2 次) = 6 |
   | **季轉換因子** | 付款頻率的季轉換因子。 例如，月支付頻率的季轉換因子為： </br></br>(12 個月付款/ 4 季) = 3 |
   | **月轉換因子** | 付款頻率的月轉換因子。 例如，月支付頻率的月轉換因子為： </br></br>(12 個月付款/ 12 個月) = 1 |
   | **半個月轉換因子** | 付款頻率的半個月轉換因子。 例如，月支付頻率的半個月轉換因子為： </br></br>(12 個月付款/ 24 (2 x 每個月)) = 0.5 | 
   | **雙週轉換因子** | 支付頻率的年轉換因子。 例如，月支付頻率的年轉換因子為： </br></br>(12 個月付款/ 26 週) = 0.461538 |
   | **週轉換因子** | 支付頻率的年轉換因子。 例如，月支付頻率的年轉換因子為： </br></br>(12 個月付款/ 52 週) = 0.230769 |
   | **日轉換因子** | 支付頻率的年轉換因子。 例如，月支付頻率的年轉換因子為： </br></br>(12 個月付款/ 365 日) = 0.032877 |
   | **小時轉換因子** | 支付頻率的年轉換因子。 例如，月支付頻率的年轉換因子為： </br></br>(12 個月付款/ 2080 小時) = 0.005769

4. 選取 **儲存**。 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
