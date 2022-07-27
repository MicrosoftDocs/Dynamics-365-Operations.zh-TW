---
title: 生產效能 Power BI 內容
description: 本主題介紹生產效能 Power BI 內容中包含的內容。
author: AndersGirke
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProductionPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 940e49b43ec1dba0917c67ad6ef4562351d175bcb1c0be7f98d00e73371e5346
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460375"
---
# <a name="production-performance-power-bi-content"></a>生產效能 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **生產效能** Microsoft Power BI 內容中包含的內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="overview"></a>概觀

**生產效能** Power BI 內容適用於組織中負責生產控制的生產經理或個人。

包含的報表讓您可以使用 Power BI 監控製造營運在即時執行、品質和成本方面的效能。 這些報表使用來自生產訂單和批次訂單的交易資料，並提供公司範圍內生產指標的匯總檢視表以及按產品和資源劃分的指標細分。

Power BI 內容突出了組織按時、完整地完成生產的能力。 未來的效能是根據生產計劃預測的。 綜合報表提供對由生產引起的產品缺陷以及資源和營運缺陷率的詳細洞察。

此 Power BI 內容還可以讓您分析生產差異。 生產差異計算為估計成本與實際成本之間的差額。 當生產訂單或批次訂單達到 **結束** 狀態時計算生產差異。

**生產效能** Power BI 內容包括源自生產訂單和批次訂單的資料。 這些報表不包括與看板生產相關的資料。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容
**生產效能** Power BI 內容顯示在 **生產效能** 頁 (**生產控制**\>**查詢和報表**\>**生產效能分析**\>**生產效能**)。 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的計量

**生產效能** Power BI 內容包括一組報表頁面。 每一頁由一組可視覺化為圖表、圖格和表格的指標組成。

下表提供了包含的視覺效果概述。

| 報表頁                                | 圖表 | 圖格 |
|--------------------------------------------|--------|-------|
| 生產效能                     | <ul><li>按日期劃分的生產數量</li><li>按產品和項目組劃分的生產數量</li><li>按日期劃分的計劃生產數量</li><li>按準時 &amp; 全量劃分的排名倒數 10 的產品</li></ul> | <ul><li>總訂單</li><li>準時 &amp; 全 ％</li><li>未完成 %</li><li>提前 %</li><li>延後 %</li></ul> |
| 按產品劃分的缺陷                         | <ul><li>按日期劃分的缺陷率 (ppm)</li><li>按產品和項目組劃分的缺陷率 (ppm)</li><li>按日期生產的數量</li><li>按有效率排名前 10 位的產品</li></ul> | <ul><li>缺陷率 (ppm)</li><li>有缺陷的數量</li><li>總數量</li></ul> |
| 按產品劃分的缺陷趨勢                   | 按生產數量劃分的缺陷率 (ppm) | 缺陷率 (ppm) |
| 按資源劃分的缺陷                        | <ul><li>按日期劃分的缺陷率 (ppm)</li><li>按資源和站點劃分的缺陷率 (ppm)</li><li>按日期劃分的作業 (ppm)</li><li>按缺陷率排名 10 大資源</li></ul> | 有缺陷的數量 |
| 按資源劃分的缺陷趨勢                  | 按處理數量劃分的缺陷率 (ppm) | |
| 作業訂單成本核算的生產差異 | <ul><li>按日期和成本群組類型排列的生產差異</li><li>按站點和成本群組類型排列的生產差異</li><li>生產差異不利的 10 大產品</li><li>按資源分類的 10 大不利生產差異</li></ul> | <ul><li>已實現的成本</li><li>生產差異</li><li>生產差異 %</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體

以下資料用於 **生產效能** Power BI 內容中的報表頁面。 此資料表示為在實體存放區中暫存的聚合量值。 實體存放區是針對分析最佳化的 Microsoft SQL Server 資料庫。 若要進一步了解有關實體存放區，請參閱[與實體存放區整合的 Power BI](power-bi-integration-entity-store.md)。

下表顯示了用作 Power BI 內容基礎的關鍵彙總量值。

| 實體                   | 關鍵彙總量值  | 財務和營運應用程式的資料來源 | 欄位              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

下表顯示了如何使用關鍵彙總量值在內容的資料集中建立多個計算量值。

| 量值                  | 如何計算量值 |
|--------------------------|-------------------------------|
| 生產差異，%   | SUM('生產差異'\[生產差異\]) / SUM('生產差異'\[估計成本\]) |
| 所有已計劃的訂單       | COUNTROWS('計劃生產訂單') |
| 提前                    | COUNTROWS(FILTER('計劃生產訂單', '計劃生產訂單'\[預定結束日期\]\<'計劃生產訂單'\[要求日期\])) |
| 延遲                     | COUNTROWS(FILTER('計劃生產訂單', '計劃生產訂單'\[預定結束日期\]\>'計劃生產訂單'\[要求日期\])) |
| 準時                  | COUNTROWS(FILTER('計劃生產訂單', '計劃生產訂單'\[預定結束日期\] = '計劃生產訂單'\[要求日期\])) |
| 準時 %                | IF ( '計劃生產訂單'\[準時\]\<\>0, '計劃生產訂單'\[準時\], IF ('計劃生產訂單'\[所有計劃訂單\]\<\>0, 0, BLANK()) ) / '計劃生產訂單'\[所有計劃訂單\] |
| 已完成                | COUNTROWS(FILTER('生產訂單', '生產訂單'\[被 RAF\]= TRUE)) |
| 缺陷率 (ppm)     | IF('生產訂單'\[總數量\]= 0, BLANK(), (SUM('生產訂單'\[有缺陷的數量\])/ '產品訂單'\[總數量\])\* 1000000) |
| 延後生產率  | '產品訂單'\[延後\#\]/ '產品訂單'\[已完成\] |
| 提前 & 全量          | COUNTROWS(FILTER('生產訂單', '生產訂單'\[是全量\]= TRUE && '生產訂單'\[已提前\] = TRUE)) |
| 提前\#                 | COUNTROWS(FILTER('生產訂單', '生產訂單'\[已提前\]= TRUE)) |
| 提前 %                  | IFERROR( IF('生產訂單'\[提前\#\]\<\>0, '生產訂單'\[提前\#\]，IF('生產訂單'\[總訂單\]= 0, BLANK(), 0)) / '生產訂單'\[總訂單\], BLANK()) |
| 未完成               | COUNTROWS(FILTER('生產訂單', '生產訂單'\[是全量\]= FALSE && '生產訂單'\[被 RAF\] = TRUE)) |
| 未完成 %             | IFERROR( IF('生產訂單'\[未完成\] \<\> 0, '生產訂單'\[未完成\]，IF('生產訂單'\[總訂單\] = 0, BLANK(), 0)) / '生產訂單'\[總訂單\], BLANK()) |
| 已延後               | '生產訂單'\[被 RAF\] = TRUE && '生產訂單'\[已延後的訂單\] = 1 |
| 已提前                 | '生產訂單'\[被 RAF\] = TRUE && '生產訂單'\[已延後的天數\] \< 0 |
| 是全量               | '生產訂單'\[良品數量\]\>= '生產訂單'\[預定數量\] |
| 被 RAF                | '產品訂單'\[生產狀態值\]= 5\|\| '產品訂單'\[生產狀態值\]= 7 |
| 延後 & 全量           | COUNTROWS(FILTER('生產訂單', '生產訂單'\[是全量\]= TRUE && '生產訂單'\[已延後\] = TRUE)) |
| 延後\#                  | COUNTROWS(FILTER('生產訂單', '生產訂單'\[已延後\]= TRUE)) |
| 延後 %                   | IFERROR( IF('生產訂單'\[延後\#\]\<\>0, '生產訂單'\[延後\#\]，IF('生產訂單'\[總訂單\]= 0, BLANK(), 0)) / '生產訂單'\[總訂單\], BLANK()) |
| 準時 & 全量        | COUNTROWS(FILTER('生產訂單', '生產訂單'\[全量\]= TRUE && '生產訂單'\[已延後\]= FALSE && '生產訂單'\[已提前\]=錯誤)) |
| 準時 & 全量 %      | IFERROR( IF('生產訂單'\[準時 & 全量\] \<\> 0, '生產訂單'\[準時 & 全量\]，IF('生產訂單'\[已完成\] = 0, BLANK(), 0)) / '生產訂單'\[已完成\], BLANK()) |
| 總訂單             | COUNTROWS('生產訂單') |
| 總數量           | SUM('生產訂單'\[良品數量\]) + SUM('生產訂單'\[有缺陷的數量\]) |
| 缺陷率 (ppm)        | IF( '路由交易'\[已處理數量\] = 0, BLANK(), (SUM('路由交易'\[有缺陷的數量\]) / '路由交易'\[已處理數量\]) \* 1000000) |
| 混合缺陷率 (ppm) | IF( '路由交易'\[總混合數量\] = 0, BLANK(), (SUM('路由交易'\[有缺陷的數量\]) / '路由交易'\[總混合數量\]) \* 1000000) |
| 已處理數量       | SUM('路由交易'\[良品數量\]) + SUM('路由交易'\[有缺陷的數量\]) |
| 總混合數量     | SUM('生產訂單'\[良品數量\]) + SUM('路由交易'\[有缺陷的數量\]) |

下表顯示了用作篩選器以對彙總量值進行配量的關鍵維度，以便您可以獲得更大的細微性並獲得更深入的深入解析。

| 實體                    | 屬性範例                                        |
|---------------------------|---------------------------------------------------------------|
| 報表為完成日期 | 完成 (RAF) 日期、月份和年份偏移                 |
| 結束的日期                | 結束的月份偏移和月份                                  |
| 要求日期          | 要求日期月份偏移量和要求日期            |
| 路由交易日期    | 路由交易月份偏移和日期                       |
| 網站                     | 站點識別碼、站點名稱、州和城市                          |
| 實體                  | 識別碼和名稱                                                   |
| 資源                 | 資源識別碼、資源名稱、資源類型和資源群組 |
| 產品                  | 產品編號、產品名稱、項目識別碼和項目群組         |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]