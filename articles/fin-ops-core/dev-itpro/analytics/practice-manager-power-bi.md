---
title: 實務經理 Power BI 內容
description: 本主題介紹實務經理 Power BI 內容中包含的內容。
author: kfend
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjManagementWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.assetid: ''
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4acef3c595f25fa0be16945a9f41611832cfcea9
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2021
ms.locfileid: "8460377"
---
# <a name="practice-manager-power-bi-content"></a>實務經理 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **實務經理** Microsoft Power BI 內容中包含的內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="overview"></a>概觀

**實務經理** Power BI 內容是為實務經理和專案經理建立的。 它提供了與組織正在進行的專案相關的關鍵指標。 儀表板概述了專案和相關客戶。 報表級別篩選器可用於報表特定法律實體。 此 Power BI 內容從專案會計彙總測量中擷取資料。

**實務經理** Power BI 內容包含五個報表頁面：一個概述頁面和四個頁面，這些頁面提供有關項目成本、收入、掙值管理和按各個維度細分的小時指標的詳情。

內容中的所有金額均以系統貨幣顯示。 您可以在 **系統參數** 頁面設定系統貨幣。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容

**實務經理** Power BI 內容顯示在 **專案管理** 工作區中。

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的報表

下表提供了有關在 **實務經理** Power BI 內容中的每個報表頁面上找到的指標的詳情。

| 報表頁       | 指標 |
|-------------------|---------|
| 專案概觀 | <ul><li>已建立專案</li><li>估計的專案</li><li>處理中的專案</li><li>客戶的實際收入</li><li>專案的預算毛利</li><li>掙值管理概述</li></ul> |
| 成本              | <ul><li>按月計算的實際成本與預算成本</li><li>按年計算的實際成本與預算成本</li><li>按目錄計算的實際與預算成本</li><li>按交易類型劃分的實際成本</li></ul> |
| 收入           | <ul><li>按月的實際收入</li><li>郵遞區號的實際收入</li><li>按目錄計算的實際與預算收入</li><li>客戶產業的實際收入</li></ul> |
| EVM               | 按專案劃分的成本和進度績效指標 |
| 時數             | <ul><li>實際可計費使用小時數與實際可計費負擔小時數與預算小時數</li><li>按專案劃分的實際應計費使用小時與實際應計費負擔小時</li><li>按資源劃分的實際應計費使用小時與實際應計費負擔小時</li><li>按專案的實際計費工時比率</li><li>按資源的實際計費工時比率</li></ul> |

所有這些報表上的圖表和圖格都可以篩選並固定到儀表板上。 如需如何在 Power BI 中篩選和釘選的相關資訊，請參閱[建立和設定儀表板](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/)。 您還可以使用匯出基礎資料函數匯出視覺效果中匯總的基礎資料。

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體

以下資料用於填入 **實務經理** Power BI 內容中的報表頁面。 此資料表示為在實體存放區中暫存的聚合量值。 實體存放區是針對分析最佳化的 Microsoft SQL Server 資料庫。 如需相關資訊，請參閱[Power BI 與實體存放區的整合](power-bi-integration-entity-store.md)。

以下部分描述了每個實體中使用的彙總度量。

### <a name="entity-projectaccountingcube_actualhourutilization"></a>實體：ProjectAccountingCube\_ActualHourUtilization
**來源資料：** ProjEmplTrans

| 關鍵彙總量值      | 欄位                              | 描述 |
|--------------------------------|------------------------------------|-------------|
| 實際計費使用時數 | Sum(ActualUtilizationBillableRate) | 實際可計費的使用小時總數。 |
| 實際計費不計費時數   | Sum(ActualBurdenBillableRate)      | 實際負擔率的總和。 |

### <a name="entity-projectaccountingcube_actuals"></a>實體：ProjectAccountingCube\_Actuals
**來源資料：** ProjTransPosting

| 關鍵彙總量值 | 欄位              | 描述 |
|---------------------------|--------------------|-------------|
| 實際收入            | Sum(ActualRevenue) | 所有交易記錄的總收入。 |
| 實際成本               | Sum(ActualCost)    | 所有交易類型的過帳成本總和。 |

### <a name="entity-projectaccountingcube_customer"></a>實體：ProjectAccountingCube\_Customer
**資料來源：** CustTable

| 關鍵彙總量值 | 欄位                                             | 描述 |
|---------------------------|---------------------------------------------------|-------------|
| 專案數        | COUNTA(ProjectAccountingCube\_Projects\[PROJECTS\]) | 可用專案的計數。 |

### <a name="entity-projectaccountingcube_forecasts"></a>實體：ProjectAccountingCube\_Forecasts
**來源資料：** ProjTransBudget

| 關鍵彙總量值 | 欄位                  | 描述 |
|---------------------------|------------------------|-------------|
| 預算成本               | Sum(BudgetCost)        | 所有交易類型的預測成本總和。 |
| 預算收入            | Sum(BudgetRevenue)     | 預測的應計/開票收入總額。 |
| 預算毛利       | Sum(BudgetGrossMargin) | 總預測收入之和與總預測成本之和之間的差額。 |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>實體：ProjectAccountingCube\_ProjectPlanCostsView
**資料來源：** 專案

| 關鍵彙總量值 | 欄位                    | 描述 |
|---------------------------|--------------------------|-------------|
| 計劃的成本              | Sum(SumOfTotalCostPrice) | 具有計劃工作的所有專案交易處理類型的估算總成本價。 |

### <a name="entity-projectaccountingcube_projects"></a>實體：ProjectAccountingCube\_Projects
**資料來源：** 專案

| 關鍵彙總量值    | 欄位 | 描述 |
|------------------------------|-------|-------------|
| 成本績效指數       | ProjectAccountingCube\_Projects\[掙值\] ÷ ProjectAccountingCube\_Projects\[已完成工作的總實際成本\] | 總掙值除以總實際成本的計算。 |
| 進度績效指數   | ProjectAccountingCube\_Projects\[掙值\] ÷ ProjectAccountingCube\_Projects\[已完成工作的總計劃成本\] | 總掙值除以總計劃成本的計算。 |
| 已完成工作的百分比 | 已完成工作的百分比 = ProjectAccountingCube\_Projects\[已完成工作的總實際成本\]÷ (ProjectAccountingCube\_Projects\[已完成工作的總實際成本\]+ ProjectAccountingCube\_Projects\[專案總計劃成本\] – ProjectAccountingCube\_Projects\[已完成工作的總計劃成本\]) | 已完成工作的總百分比，基於已完成工作的總實際成本和專案的計劃成本。 |
| 實際計費工時比率  | ProjectAccountingCube\_Projects\[專案總實際可計費使用小時數\] ÷ (ProjectAccountingCube\_Projects\[專案總實際可計費使用小時數\] + ProjectAccountingCube\_Projects\[專案總實際計費負擔小時數\]) | 實際計費總小時數，基於已用小時數和負擔小時數。 |
| 掙值                 | ProjectAccountingCube\_Projects\[專案總計劃成本\] × ProjectAccountingCube\_Projects\[已完成工作的百分比\] | 總計劃成本乘以已完成工作的百分比。 |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>實體：ProjectAccountingCube\_TotalEstimatedCosts 
**資料來源：** ProjTable

| 關鍵彙總量值       | 欄位               | 描述 |
|---------------------------------|---------------------|-------------|
| 已完成活動計劃成本 | Sum(TotalCostPrice) | 具有已完成工作的所有專案交易處理類型的估算總成本價。 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
