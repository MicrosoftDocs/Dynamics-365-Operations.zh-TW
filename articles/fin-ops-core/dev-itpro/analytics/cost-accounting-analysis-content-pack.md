---
title: 成本會計分析 Power BI 內容
description: 本主題介紹成本會計分析 Power BI 內容中包含的內容。
author: AndersGirke
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d3b8832e5a5612fd0311811f43454689d5b274c36404b4fb92b710411d45e573
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460528"
---
# <a name="cost-accounting-analysis-power-bi-content"></a>成本會計分析 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **成本會計分析** Microsoft Power BI 內容中包含的內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="overview"></a>概觀

**成本會計分析** Power BI 內容適用於成本控制人員或負責執行組織成本控制的任何人。 它包括關鍵指標，例如按實際成本、預算成本和彈性預算成本計算的成本、規模和成本率。 它使用來自 **成本會計** 模組的交易資料，並以一種報表貨幣提供整個組織的成本彙總視圖。 經理可以按成本標的過濾資料，以對其組織單位進行成本控制，即使組織可以有多個法律實體。

由於 **成本會計分析** 內容突出了實際成本和預算成本之間的差異，因此可以通知管理人員其營運單位的正面和負面趨勢。 管理員可以向下切入到成本要素階層或單個成本要素。 透過這種方式，管理人員可以詳細了解成本差異是如何發生的，然後採取有效的行動。

**成本會計分析** 內容讓成本會計分析成本如何流經整個組織的成本標的。

若要進一步了解成本會計，請參閱[成本會計主頁](../../../finance/cost-accounting/cost-accounting-home-page.md)。

透過在成本會計中定義存取級別安全性並將其與 Power BI 中的行級別安全性相結合，您可以授予所有成本標的所有者存取 **成本會計分析** Power BI 內容的權限。 然後將根據成本會計中控制的存取級別過濾可視化中的所有資料。 若要進一步了解存取級安全性和資料列級安全性，請參閱[為成本會計分析 Power BI 內容設定安全性](setup-security-cost-accounting-content-pack.md)。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容
您可以在 Microsoft Dynamics Lifecycle Services (LCS) 的共用資產庫中找到 **成本會計分析** Power BI 內容。 如需如何下載內容並在您的組織中實作的相關資訊，請參閱[來自 Microsoft 和您的合作夥伴的 LCS 中的 Power BI 內容](/archive/blogs/dynamicsaxbi/power-bi-content-from-microsoft-and-your-partners)。

請務必下載適用於您正在使用的 Microsoft Dynamics 365 版本的 **成本會計分析** 內容。

> [!NOTE]
> KB 4011327 是此 Power BI 內容的先決條件。 登入 LCS 後，您可以在 <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327> 存取 KB。

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的計量
內容包括一組報表頁面。 每一頁由一組可視覺化為圖表、圖格和表格的指標組成。 下表概述了 **成本會計分析** Power BI 內容中的視覺化。

| 報表頁                      | 圖表                                                                                                                         | 圖格                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 按會計期間控制成本    | 按成本元素階層級別的實際成本和預算成本                                                                   | 實際成本與預算成本                    |
|                                  | 按成本元素階層級別的預算差異                                                                               | 實際成本率與預算成本率          |
|                                  | 按成本元素劃分的前 10 大預算差異百分比                                                                          | 實際規模與預算規模          |
| 年初至今的成本控制     | 按曆年期間的實際成本和預算成本                                                                           | 實際成本與預算成本                    |
|                                  | 按日曆年期間的預算差異                                                                                       | 實際成本率與預算成本率          |
|                                  | 按成本元素劃分的前 10 大預算差異百分比                                                                          | 實際規模與預算規模          |
| 按會計年度的成本率         | 按成本行為的實際成本率                                                                                             | 實際成本率與預算成本率          |
|                                  | 成本元素階層級別的實際成本率、預算成本率差異、預算成本率百分比和預算成本率 | 實際規模與預算規模          |
|                                  | 按成本元素階層級別的預算差異                                                                               |                                               |
|                                  | 按成本元素劃分的前 10 大預算差異百分比                                                                          |                                               |
| 按會計期間的彈性預算 | 按成本元素級別劃分的實際成本、預算成本和彈性預算成本                                             | 實際規模與預算規模          |
|                                  | 按成本元素階層級別的預算差異和彈性預算差異                                                  | 實際成本與彈性預算成本           |
|                                  | 按成本行為和成本元素階層級別的實際成本、預算成本和彈性成本                                  | 實際成本率與彈性預算成本率 |
| 按會計期間的成本表  | 按成本元素階層級別和成本標的維度成員名稱的實際成本                                             |                                               |
|                                  | 按成本標的維度成員名稱和成本元素維度成員名稱的實際成本                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體
以下資料用於填入 **成本會計分析** Power BI 內容中的報表頁面。 此資料表示為在實體存放區中暫存的聚合量值。 實體存放區是針對分析最佳化的 Microsoft SQL Server 資料庫。 如需相關資訊，請參閱[Power BI 與實體存放區的整合](power-bi-integration-entity-store.md)。

以下關鍵彙總測量值用作內容的基礎。

| 實體                  | 關鍵彙總量值 | Dynamics 365 的資料來源      | 欄位     | 描述                                        |
|-------------------------|---------------------------|-----------------------------------|-----------|----------------------------------------------------|
| 成本會計分錄 | SUM(Amount)               | CAMDATAAggregatedCostEntry        | 金額    | 成本會計分類帳貨幣中的金額。 |
| 統計分錄     | SUM(Magnitude)            | CAMDATAAggregatedStatisticalEntry | 幅度 |                                                    |

下表顯示了如何使用關鍵彙總量值在內容的資料集中建立多個計算量值。

| 量值                                       | 如何計算量值                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| 實際成本                                   | CALCULATE('Cost accounting entries'\[Measure\], 'Transaction versions'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)            |
| 預算成本                                   | CALCULATE('Cost accounting entries'\[Measure\], 'Transaction versions'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)            |
| 預算成本差異                          | \[預算成本\] - \[實際成本\]                                                                                      |
| 預算差異百分比                    | IF(\[Budget cost\] = 0, blank(), \[Budget variance\] / \[Budget cost\])                                                |
| 實際幅度                              | CALCULATE('Statistical entries'\[FullMagnitude\], 'Transaction versions'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)          |
| 預算幅度                              | CALCULATE(\[FullMagnitude\], 'Transaction versions'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)                               |
| 統計預算差異                   | \[預算幅度\] - \[實際幅度\]                                                                            |
| 統計預算差異百分比        | IF(\[Budget magnitude\] = 0, blank(), \[Statistical budget variance\] / \[Budget magnitude\])                          |
| 實際成本率                              | IF(\[Actual magnitude\] = 0, BLANK(), \[Actual cost\] / \[Actual magnitude\])                                          |
| 預算成本率                              | IF(\[Budget magnitude\] = 0, BLANK(), \[Budget cost\] / \[Budget magnitude\])                                          |
| 預算成本率差異                     | \[預算成本率\] - \[實際成本率\]                                                                            |
| 預算成本率差異百分比          | IF(\[Budget cost\] = 0, blank(), \[Budget cost rate variance\] / \[Budget cost rate\])                                 |
| 固定預算成本                             | CALCULATE(\[Budget cost\], 'Cost accounting entries'\[COSTBEHAVIOR\] = 1)                                              |
| 變動預算成本                          | CALCULATE(\[Budget cost\], 'Cost accounting entries'\[COSTBEHAVIOR\] = 2)                                              |
| 固定彈性預算成本                    | \[固定預算成本\]                                                                                                  |
| 變動彈性預算成本                 | IF(\[預算幅度\] = 0, BLANK(), (\[變數預算成本\] / \[預算幅度\]) \* \[實際幅度\])       |
| 彈性預算成本                          | \[固定變動預算成本\] + \[變數變動預算成本\]                                                     |
| 彈性預算差異                      | \[變動預算成本\] - \[實際成本\]                                                                             |
| 彈性預算差異百分比           | IF(\[Flexible budget cost\] = 0, BLANK(), \[Flexible budget variance\] / \[Flexible budget cost\])                     |
| 彈性預算成本率                     | IF(\[Actual magnitude\] = 0, BLANK(), \[Flexible budget cost\] / \[Actual magnitude\])                                 |
| 彈性預算成本率差異            | \[變動預算成本率\] - \[實際成本率\]                                                                   |
| 彈性預算成本率差異百分比 | IF(\[Flexible budget cost rate\] = 0, BLANK(), \[Flexible budget cost rate variance\] / \[Flexible budget cost rate\]) |

以下關鍵維度用作過濾器來對彙總測量進行交叉分析，以實現更大的細微性並提供更深入的深入解析。

| 實體                             | 屬性範例                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| 成本會計分類帳            | 成本會計分類帳                                                                                               |
| 成本控制裝置                 | 成本控制裝置名稱                                                                                               |
| 成本元素維度            | 成本元素維度名稱，成本元素維度成員名稱，成本元素維度成員描述          |
| 成本標的維度             | 成本標的維度名稱，成本標的維度成員名稱，成本標的維度成員描述              |
| 統計維度             | 統計維度名稱，統計維度成員名稱，統計維度成員描述              |
| 成本物件維度階層  | 成本標的維度階層名稱，成本標的維度階層級別，成本標的維度階層樹狀結構    |
| 成本元素維度階層 | 成本元素維度階層名稱，成本元素維度階層級別，成本元素維度階層樹狀結構 |
| 統計維度階層  | 統計維度階層名稱，統計維度階層級別，統計維度階層樹狀結構    |
| 交易版本               | 版本名稱                                                                                                         |
| 會計行事曆                   | 日曆，日曆描述                                                                                       |
| 會計年度                       | 曆年                                                                                                        |
| 會計期間                     | 曆年期間                                                                                                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]