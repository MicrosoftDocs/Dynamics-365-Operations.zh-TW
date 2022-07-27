---
title: 成本管理 Power BI 內容
description: 本主題介紹成本管理 Power BI 內容中包含的內容。
author: ShylaThompson
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, CostObjectWithLowestAccuracy, CostVarianceChart, CostObjectWithLowestTurn
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9fbdc6addc820aadc1f5469cb059a62724cfe905
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "8460527"
---
# <a name="cost-management-power-bi-content"></a>成本管理 Power BI 內容

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>概觀

**成本管理** Microsoft Power BI 內容面向庫存會計師或組織中負責或對庫存或製作中 (WIP) 狀態感興趣或負責或對分析標準成本差異感興趣的個人。

此 Power BI 內容提供了一種分類格式，可幫助您監控庫存績效並視覺化成本流經庫存的方式。 您可以在偏好彙總級別 (公司、項目、項目組或端點) 獲得管理深入解析，例如周轉率、庫存天數、準確性和「ABC 分類」。 提供的資訊也可以用作財務報表的詳細補充。

Power BI 內容基於 **CostObjectStatementCacheMonthly** 彙總量值，該量值以 **CostObjectStatementCache** 表作為其主要資料來源。 該表由資料集快取架構管理。 在預設情況下，資料表每 24 小時更新一次，但您可以更改更新頻率或在資料集快取的設定中啟用手動更新。 可以在 **成本管理** 工作區或 **成本分析** 工作區中執行手動更新。

每次更新 **CostObjectStatementCache** 表後，必須先更新 **CostObjectStatementCacheMonthly** 彙總量值，然後再更新 Power BI 視覺化中的資料。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容

**成本管理** Power BI 內容顯示在 **成本管理** 和 **成本分析** 工作區中。

**成本管理** 工作區包含以下索引標籤：

- **概述** – 此索引標籤顯示應用程式資料。
- **庫存會計狀態** – 此索引標籤會顯示 Power BI 內容。
- **製造會計狀態** – 此索引標籤會顯示 Power BI 內容。

**成本分析** 工作區包含以下索引標籤：

- **概述** – 此索引標籤顯示應用程式資料。
- **庫存會計分析** – 此索引標籤會顯示 Power BI 內容。
- **製造會計分析** – 此索引標籤會顯示 Power BI 內容。
- **標準成本差異分析** – 此索引標籤會顯示 Power BI 內容。

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的報表頁面

**成本管理** Power BI 內容包括一組由一組指標組成的報表頁面。 這些指標可視覺化為圖表、圖格和資料表。 

下表概述了 **成本管理** Power BI 內容中的視覺化。

### <a name="inventory-accounting-status"></a>庫存會計狀態

| 報表頁                               | 視覺化                                   |
|-------------------------------------------|-------------------------------------------------|
| 庫存概述                        | 期初餘額                               |
|                                           | 淨變化                                      |
|                                           | 淨變化 %                                    |
|                                           | 期末餘額                                  |
|                                           | 庫存正確性                              |
|                                           | 庫存周轉率                        |
|                                           | 現有庫存天數                          |
|                                           | 期間使用中產品                        |
|                                           | 期間使用中成本標的                   |
|                                           | 按項目組計算的餘額                           |
|                                           | 按端點計算的餘額                                 |
|                                           | 按類別計算的報表                           |
|                                           | 按季度計算的淨變化                           |
| 按端點和項目組計算的庫存概述 | 按端點計算的庫存正確性                      |
|                                           | 按端點計算的庫存周轉率                |
|                                           | 按端點計算的庫存期末餘額                |
|                                           | 按項目組計算的庫存正確性                |
|                                           | 按項目組計算的庫存周轉率          |
|                                           | 按端點和項目組計算的庫存期末餘額 |
| 庫存報表                       | 庫存報表                             |
| 按端點計算的庫存報表               | 按端點計算的庫存報表                     |
| 按產品階層計算的庫存報表  | 庫存報表                             |
| 按產品階層計算的庫存報表  | 按端點計算的庫存報表                     |

### <a name="manufacturing-accounting-status"></a>製造會計狀態

| 報表頁                | 視覺化                       |
|----------------------------|-------------------------------------|
| WIP 概述 YTD           | 期初餘額                   |
|                            | 淨變化                          |
|                            | 淨變化 %                        |
|                            | 期末餘額                      |
|                            | WIP 周轉率                  |
|                            | 現有 WIP 天數                    |
|                            | 期間使用中成本標的        |
|                            | 資源群組的淨變化        |
|                            | 按端點計算的餘額                     |
|                            | 按類別計算的報表               |
|                            | 按季度計算的淨變化               |
| WIP 報表              | 期初餘額                   |
|                            | 期末餘額                      |
|                            | 按類別計算的 WIP 報表           |
| 按端點計算的 WIP 報表      | 期初餘額                   |
|                            | 期末餘額                      |
|                            | 按類別和端點計算的 WIP 報表  |
| 按階層計算的 WIP 報表 | 期初餘額                   |
|                            | 期末餘額                      |
|                            | 按類別階層計算的 WIP 報表 |

### <a name="inventory-accounting-analysis"></a>庫存會計分析

| 報表頁        | 視覺化                                                                |
|--------------------|------------------------------------------------------------------------------|
| 庫存詳情  | 按期末餘額計算的前 10 大資源                                           |
|                    | 按淨變化增加計算的前 10 大資源                                      |
|                    | 按淨變化減少計算的前 10 大資源                                      |
|                    | 按庫存周轉率計算的前 10 大資源                                 |
|                    | 按低庫存周轉率且高於閾值之期末餘額計算的資源 |
|                    | 按低正確性計算的前 10 大資源                                             |
| ABC 分類 | 庫存期末餘額                                                     |
|                    | 消耗材料                                                            |
|                    | 已售出 (COGS)                                                                  |
| 庫存趨勢   | 庫存期末餘額                                                     |
|                    | 庫存淨變化                                                         |
|                    | 庫存周轉率                                                     |
|                    | 庫存正確性                                                           |

### <a name="manufacturing-accounting-analysis"></a>製造會計分析

| 報表頁 | 視覺化      |
|-------------|--------------------|
| WIP 趨勢  | WIP 期末餘額 |
|             | WIP 淨變化     |
|             | WIP 周轉率 |

### <a name="std-cost-variance-analysis"></a>標準成本差異分析

| 報表頁                             | 視覺化                                        |
|-----------------------------------------|------------------------------------------------------|
| 採購價格差異 (標準成本) YTD | 採購餘額                                     |
|                                         | 採購價格差異                              |
|                                         | 採購價格差異率                        |
|                                         | 按項目組的差異                               |
|                                         | 按端點計算的差異                                     |
|                                         | 按季度購買價格                            |
|                                         | 按季度和項目組計算的採購價格             |
|                                         | 按不利採購價格率計算的前 10 大資源 |
|                                         | 按利於採購價格率計算的前 10 大資源   |
| 生產差異 (標準成本) YTD     | 製造成本                                    |
|                                         | 生產差異                                  |
|                                         | 生產差異比                            |
|                                         | 按項目組的差異                               |
|                                         | 按端點計算的差異                                     |
|                                         | 按季度計算的生產差異                       |
|                                         | 按季度和差異類型計算的生產差異     |
|                                         | 按不利生產差異計算的前 10 大資源  |
|                                         | 按利於生產差異計算的前 10 大資源    |

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體

來自應用程式的資料用於填入 **成本管理** Power BI 內容中的報表頁面。 此資料表示為在實體儲存中暫存的彙總合量值，實體儲存是針對分析進行了最佳化的 Microsoft SQL Server 資料庫。 如需相關資訊，請參閱[Power BI 與實體存放區的整合](power-bi-integration-entity-store.md)。

以下對象的關鍵彙總量值用作 Power BI 內容的基礎。

| 物件                          | 關鍵彙總量值 | Finance and Operations 的資料來源 | 欄位               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | 金額                     | CostObjectStatementCache               | 金額              |
| CostObjectStatementCacheMonthly | 數量                   | CostObjectStatementCache               | 數量                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

下表顯示了 Power BI 內容中的主要計算量值。

| 量值                            | 計算 |
|------------------------------------|-------------|
| 期初餘額                  | 期初餘額 =\[期末餘額\]-\[淨變化\] |
| 期初餘額數量             | 期初餘額數量 =\[期末餘額數量\]-\[淨變化數量\] |
| 期末餘額                     | 期末餘額 = (CALCULATE(SUM(\[Amount\]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| 期末餘額數量                | 期末餘額數量 = CALCULATE(SUM(\[QTY\]), FILTER(ALL(FiscalCalendar),FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\]))) |
| 淨變化                         | 淨變化 = SUM(\[AMOUNT\]) |
| 淨變化數量                    | 淨變化數量 = SUM(\[QTY\]) |
| 按金額計算的庫存周轉率 | 按金額計算的庫存周轉率 = if(OR(\[庫存平均餘額\]\<= 0, \[Inventory sold or consumed issues\] \>= 0), 0, ABS(\[庫存已售或已消耗問題\])/\[庫存平均餘額\]) |
| 庫存平均餘額          | 庫存平均餘額 = ((\[期末餘額\] + \[期初餘額\]) / 2) |
| 現有庫存天數             | 現有庫存天數 = 365 / CostObjectStatementEntries\[按金額計算的庫存周轉率\] |
| 庫存正確性                 | 按金額計算的庫存正確性 = IF(\[期末餘額\]\<= 0, IF(OR(\[Inventory counted amount\] \<\>0,\[期末餘額\]\<0), 0, 1), MAX(0, (\[期末餘額\]- ABS (\[庫存盤點金額\]))/\[期末餘額\])) |

以下關鍵維度用作過濾器來對彙總測量進行交叉分析，以便您可以獲得更大的細微性並獲得更深入的分析見解。


| 實體                                                  | 屬性範例                          |
|---------------------------------------------------------|-------------------------------------------------|
| 產品                                                | 產品編號、產品名稱、單位、項目組 |
| 類別階層 (指派給角色成本管理) | 類別階層，類別級別              |
| 法律實體                                          | 法律實體名稱                              |
| 會計行事曆                                        | 會計行事曆、年、季度、期間、月   |
| 網站                                                    | ID、名稱、地址、州、國家/地區               |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
