---
title: 使用客戶付款預測
description: 本主題介紹了使用 Finance Insights 試用版所需的先決條件和廣泛步驟。
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: ed70e133b93c783542d4669b679fc5b6d2d20240
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "8451359"
---
# <a name="use-customer-payment-predictions"></a>使用客戶付款預測

[!include [banner](../includes/banner.md)]

本主題說明如何使用客戶付款預測。 在使用此功能之前，請確保您已完成它的安裝步驟。 如需相關資訊，請參閱[啟用客戶付款預測](enable-cust-paymnt-prediction.md)。

您可以在 **管理客戶信用和收款** 工作區和兩個新的清單頁面：**交易付款預測** 和 **客戶付款預測** 中檢視客戶付款預測。

### <a name="manage-customer-credit-and-collections-workspace"></a>管理客戶信用和收款工作區

**管理客戶信用和收款** 工作區包括兩個新圖塊：**交易付款預測** 和 **客戶付款預測**。

### <a name="transaction-payment-predictions-list-page"></a>交易付款預測清單頁面

在 **交易付款預測** 清單頁面上，您可以在 **準時**、**延遲** 和 **嚴重延遲** 貯體中檢視未完成交易的付款可能性。 對於格線中的每一筆交易，**準時可能性** 欄顯示了發票將在到期日或之前付款的可能性。 如果準時付款的可能性低於 50%，則在 **準時可能性** 欄的百分比旁會出現一個紅色圓圈來指示延遲付款的風險。

[![根據交易頁面的付款預測](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

頁面右側的 **相關資訊** 窗格顯示了有關預測的更多詳情：

- 對於在格線中選取的交易，**付款預測** FastTab 顯示了 **準時**、**延遲** 和 **嚴重延遲** 貯體中的付款預測詳情。 **主要因素** 區段顯示了影響預測的主要因素。 主要因素是所選交易的屬性和/或該筆交易的客戶。
- **Customer Insights** FastTab 顯示了所選交易之客戶目前的發票、付款和收款統計資料。
- **客戶歷程記錄** FastTab 顯示了 **準時**、**延遲** 和 **嚴重延遲** 貯體中的客戶付款歷程記錄。

在 **主要因素** 區段，以及 **Customer Insights** 和 **客戶歷程記錄** 中的資料 FastTabs，有助於說明付款預測。 它可以幫助增加您對預測效果的信心。

[![相關資訊窗格中付款預測的圖形指標。](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="customer-payment-predictions-list-page"></a>客戶付款預測清單頁面

**客戶付款預測** 清單頁面顯示了總未結餘額，以及在 **準時**、**延遲** 和 **嚴重延遲** 貯體中預計將付款的金額。

[![每位客戶付款預測頁面。](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

每個貯體的付款金額計算為交易餘額的加權平均數之和。 此金額是根據每個貯體中的款可能性計算的。

例如，客戶有三個未結交易，在每個貯體中具有以下付款可能性。

| 交易 | 金額 | 準時付款可能性 | 延遲付款可能性 | 嚴重延遲付款可能性 |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | 10%                  | 50%               | 40%                    |
| T2          | 1,000  | 50%                  | 30%               | 20%                    |
| T3          | 10,000 | 1%                   | 4%                | 95%                    |

在這種情況下，請按以下方式為每個貯體預測付款。

| 貯體   | 交易 T1      | 交易 T2         | 交易 T3            | 總計 |
|-----------|---------------------|------------------------|---------------------------|-------|
| 準時   | 100 × 10 ÷ 100 = 10 | 1,000 × 50 ÷ 100 = 500 | 10,000 × 1 ÷ 100 = 100    | 610   |
| 延遲      | 100 × 50 ÷ 100 = 50 | 1,000 × 30 ÷ 100 = 300 | 10,000 × 4 ÷ 100 = 400    | 750   |
| 嚴重延遲 | 100 × 40 ÷ 100 = 40 | 1,000 × 20 ÷ 100 = 200 | 10,000 × 95 ÷ 100 = 9,500 | 9,740 |

頁面右側的 **相關資訊** 區段顯示了有關預測的更多詳情：

- 對於在格線中選取的交易，**付款預測** FastTab 顯示了 **準時**、**延遲** 和 **嚴重延遲** 貯體中的付款預測詳情。
- **Customer Insights** FastTab 顯示了所選交易之客戶目前的發票、付款和收款統計資料。
- **客戶歷程記錄** FastTab 顯示了 **準時**、**延遲** 和 **嚴重延遲** 貯體中的客戶付款歷程記錄。

在 **Customer Insights** 和 **客戶歷程記錄** 中的資料 FastTabs 有助於說明付款預測。 它可以幫助增加您對預測效果的信心。

## <a name="improving-the-accuracy-of-payment-predictions"></a>提高付款預測的準確性

您可以前往 **信用和收款\>設定\>Finance Insights\>Finance Insights 參數** 來檢視付款預測的準確性。 在 **客戶付款見解** 索引標籤，**預測模型** 區段以百分比顯示了預測模型的準確性。

[![付款預測的準確性。](./media/finance-insights-parameters-accuracy-2nd.png)](./media/finance-insights-parameters-accuracy-2nd.png)

如果您對準確性不滿意，請選取 **提高模型準確度** 連結來打開 AI Builder 拓展經驗。 在 AI Builder 拓展經驗中，您可以選取或取消選擇欄位，直到您選取了您認為對準確預測付款可能性最重要的欄位。 完成後，您可以輕鬆地重新訓練預測模型並發佈您的更改。 新訓練的預測模型將自動被挑選出來在 Dynamics 365 Finance 進行預測。

[![AI Builder拓展經驗。](./media/ai-builder.png)](./media/ai-builder.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
