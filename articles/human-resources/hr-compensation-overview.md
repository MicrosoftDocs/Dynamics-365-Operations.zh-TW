---
title: 薪酬計算支付計劃
description: 本主題說明如何使用薪酬管理來管理和處理薪酬計劃。
author: twheeloc
ms.date: 08/25/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 7571f220780ca383f57338bb69505cc68a741877
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452280"
---
# <a name="compensation-plans"></a>薪酬計算支付計劃


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

薪酬和福利經理可以使用 **薪酬管理** 維護和處理組織員工的固定和變動薪酬計劃。

### <a name="introduction"></a>簡介

薪酬管理用來控制基本工資和獎勵的發放。 員工的固定基本工資和績效增加透過固定薪酬計劃控制。 激勵獎金的支付，例如紅利、績效獎勵、股票選擇權和贈款，也包括一次性獎勵，皆透過變動薪酬計劃控制。 

員工可以註冊兩種類型的一項或多項計劃。 員工必須符合下列要求才能具備薪酬計劃註冊資格：
-   員工必須接受有效的職位指派。
-   員工必須符合薪酬計劃資格規則定義的標準。

## <a name="compensation-setup"></a>薪資設定
下表列出薪酬流程的組成部分，它們可以和設定貴公司的薪酬計劃保持一致。

<table>
<thead>
<tr class="header">
<th>組成部份</th>
<th>更多資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>固定薪酬動作</td>
<td>固定薪酬行動達成兩個目的如下：
<ul>
<li>動作可以指明員工薪酬變動時必須記錄的資訊類型。 例如，您可以要求記錄更改的原因，例如升職或降職。</li>
<li>動作可以確保處理固定薪酬計劃時會套用計算。  例如，Equity 類型的動作將比較員工支薪與員工等級的最低參考點&#39;並確保員工至少獲得最低工資。</li>
</ul></td>
</tr>
<tr class="even">
<td>等級</td>
<td>等級與工作及任何工作參考相關職位有所關聯。 您可以針對三種類型的薪酬計劃建立離散等級：分級、波段和級距。</td>
</tr>
<tr class="odd">
<td>範圍利用率矩陣</td>
<td>範圍利用率矩陣幫助您轉移員工到他們工作的控制點。 您也可以使用範圍利用率控制公司的支付費率權益，無關單名員工&#39;的績效或公司的整體績效。 例如，範圍內低支薪員工比高支薪員工獲得更高的加薪佔比。 透過這種方式，您可以系統性地抵消權益差額。 範圍利用率計算如下： (固定支付費率 - 範圍最小值)÷ (範圍最大值 - 範圍最小值)。</td>
</tr>
<tr class="even">
<td>參考點設定</td>
<td>參考點設定包括一套代表矩陣範圍的參考點。 每個範圍都會與支付費率產生關聯。 例如，分級計劃往往會有最小值、中點和最大值的參考點。</td>
</tr>
<tr class="odd">
<td>薪酬矩陣</td>
<td>薪酬矩陣是用於建立薪酬結構的一套參考點和等級。</td>
</tr>
<tr class="even">
<td>薪酬結構</td>
<td>薪酬結構是薪酬矩陣，支付費用與每個等級的參考點相關聯。</td>
</tr>
<tr class="odd">
<td>資格規則</td>
<td>資格規則用來辨別特定薪酬計劃涵蓋的特定工作、工作職能、工作類型、部門、工會或薪酬區域的員工。 您必須針對變動薪酬計劃和固定薪酬計劃建立資格規則，才能幫員工註冊該計劃。 待薪酬計劃指明資格規則後，您可以定義應適用計劃涵蓋的工作等級。</td>
</tr>
<tr class="even">
<td>支付頻率</td>
<td>支付頻率用來定義指明薪酬的時段。  例如，支付頻率幫助您了解薪酬金額是否指明為年薪和時薪支付費率。 支付頻率也用來設定轉換因子，將薪酬金額從月、週、雙週和小時的支付頻率轉換為年度支付頻率。</td>
</tr>
<tr class="odd">
<td>薪酬區域</td>
<td>薪酬區域用來根據工作場所的位置指明員工薪酬。</td>
</tr>
<tr class="even">
<td>控制點</td>
<td>控制點定義您認為所有員工按薪酬等級推估的理想支付費率。 分級計劃結構方面，典型的控制點是範圍的中點。 波段結構很少使用控制點。 您可以在 **固定薪酬計劃** 頁面指明固定薪酬計劃的控制點。</td>
</tr>
<tr class="odd">
<td>工作職能</td>
<td>工作職能用來對特定工作的薪酬計劃分類和篩選。</td>
</tr>
<tr class="even">
<td>工作類型</td>
<td>工作類型用來對特定工作的薪酬計劃分類和篩選。</td>
</tr>
<tr class="odd">
<td>變動薪酬計畫類型</td>
<td>變動薪酬類型，例如股票獎勵或現金獎勵分紅，皆在變動薪酬計劃中設定。</td>
</tr>
<tr class="even">
<td>薪酬格線</td>
<td>薪酬格線包含薪酬結構。  一項或多項薪酬計劃可以使用薪酬格線。</td>
</tr>
<tr class="odd">
<td>績效計劃</td>
<td>績效計劃用來將績效與分配矩陣產生關聯，方便您在按績效支付的策略中使用此計劃。</td>
</tr>
<tr class="even">
<td>績效評等</td>
<td>績效評等用在績效計劃，判定功績獎勵或績效獎勵的金額。</td>
</tr>
</tbody>
</table>

## <a name="process-events"></a>流程事件
流程事件會針對註冊一項或多項固定或變動薪酬計劃的所有員工計算特定時期的薪酬資訊。 您可以重覆執行流程事件測試或更新計算的薪酬結果。

## <a name="compensation-events"></a>薪酬事件

每次執行流程事件將會連帶建立薪酬事件。  薪酬事件包含每位納入流程事件的員工，他們的薪酬流程結果。  計算正確時，您可以載入薪酬事件更新受到流程事件影響的員工的薪酬記錄。

## <a name="recommendations"></a>建議
待您執行流程事件後，您可以根據流程事件的計算指南建議調整員工的功績加薪或獎勵金額。 為了向員工提供建議，您必須在設定薪酬計劃或設定流程事件時啟用建議。





[!INCLUDE[footer-include](../includes/footer-banner.md)]
