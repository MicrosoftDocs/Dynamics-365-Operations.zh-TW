---
title: 職位預算疑難排除
description: 本文針對您在配置職位預算時可能遇到的問題提供解答。 它設法解決有關如何建立預算成本元素、薪酬群組和薪酬網格的常見問題。
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492a0798d1934b0fe1adf4f0546013f394beab06948f02f92358bae408e7748f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450249"
---
# <a name="position-budgeting-troubleshooting"></a>職位預算疑難排除

[!include [banner](../includes/banner.md)]

本文針對您在配置職位預算時可能遇到的問題提供解答。 它設法解決有關如何建立預算成本元素、薪酬群組和薪酬網格的常見問題。 

## <a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>為何我在人力資源找不到預測職位頁面？

預測職位已移到 Budgeting (編列預算)。

## <a name="why-cant-i-delete-a-budget-cost-element"></a>為何我不能刪除預算成本元素？
您不能刪除指派給預測職位的預算成本元素。 您必須先從所有預測職位移除，才能刪除預算成本元素。 **訣竅：** 若要尋找已指派預算成本元素的所有職位，請在 **預算成本元素** 頁面上選取成本元素，然後點選 **更新職位**。 使用成本元素的職位列在上半部網格。

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>我如何在不打開各預測職位情況下，從多組預測職位移除成本元素？
您不能刪除成本元素。 不過，如果您將開始日期和結束日期更改為超出預算規劃週期日期，則成本元素將不再指派給該預算規劃週期的預測職位。 若要進行此項更改，請打開預算成本元素，然後在 **成本計算** FastTab 點選 **更改日期**，並更改生效日期或到期日。 接著點選 **確定** 自動更新已指派成本元素的所有預測職位。 **訣竅：** 如果您使用此方法，請注意它從 **所有** 開始和結束日期不再納入適當範圍的預測職位移除預算成本元素。 如果此項效果不是您原本想要的，您必須打開希望刪除預算成本元素的各個預測職位，並且手動進行更改。

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>為何我不能在 Cost 計算 FastTab 上輸入年度預算成本元素金額？
如果 **Calculation 依據** FastTab 上有預算成本元素，您就不能輸入年度金額，因為系統需要佔比計算數值。 若要更改此值，請從 **Calculation 依據** FastTab 移除所有預算成本元素。

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>我為何不能將預算成本類型從收入更改為另一種預算成本類型？
一些預算成本元素使用收入成本元素作為計算依據。 若要更改 **預算成本類型** 欄位，請從所有預算成本元素的 **Calculation 依據** FastTab 移除收入成本元素。

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>我為何不能更改預算成本元素明細的預算成本元素日期？
當預測職位使用預算成本元素時，您無法更改預算成本元素明細上的日期。 此項限制有助於保證預測職位始終在預算成本元素的指南內。 若要更改日期，請在 **成本計算** FastTab 上點選 **更改日期**，然後輸入新日期。 接著點選 **確定** 更新已指派成本元素的職位。

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>我為何不能在薪酬群組頁面上更改預算成本元素的成本？
您只能在 **預算成本元素** 頁上建立和更改預算成本元素。

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>我為何在更改預測職位的成本元素日期時收到錯誤訊息？
預測職位成本元素明細的日期必須在下列範圍內：

-   職位的啟動和退休日期。
-   預算成本元素的啟動和到期日。
-   與預測職位的預算規劃流程有關聯的預算週期開始和結束日期。






[!INCLUDE[footer-include](../../includes/footer-banner.md)]