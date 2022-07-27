---
title: 銷售和獲利表現 Power BI 內容
description: 本主題介紹銷售和獲利表現 Power BI 內容中包含的內容。
author: ShylaThompson
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesProfitabilityPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9ec9ef5f4abf898100c670b1ca1cc845d6ebeeea36f21cdda3a9b7d3f1027d4e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460277"
---
# <a name="sales-and-profitability-performance-power-bi-content"></a>銷售和獲利表現 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **銷售和獲利表現** Microsoft Power BI 內容中包含的內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="overview"></a>概觀

**銷售和獲利表現** Power BI 建立內容以便銷售經理可以監控收入、毛利潤和利潤率等關鍵銷售指標。 它使用銷售交易資料，並提供公司範圍內銷售資料的匯總檢視表以及客戶和產品的銷售業績明細。

報表強調了收入和利潤增長在一段時間內的變化。 因此，這些報表可用於提醒經理個人客戶和產品的正面和負面趨勢。 此外，圖表還比較了不同產品類別和客戶群的收入和獲利能力。 因此，類別和區域經理可以識別落後者和領導者。 最後，一份綜合報表繪製了單個客戶的收入與利潤率的關係。 因此，客戶經理有一個資料支援的基礎，他們可以使用它來調整他們的銷售和行銷工作，以適應每個客戶的個人資料。

**銷售和獲利表現** 內容讓銷售經理透過以下方式分析銷售業績：

- 年初至今的收入 (按客戶組和個人客戶、銷售類別以及個人產品和地區)
- 收入變化，逐年 (按客戶地區和銷售類別)

可以透過以下方式分析獲利能力：

- 毛利潤和獲利率 (按客戶群體和產品銷售類別)
- 毛利變化，逐年
- 客戶獲利能力 (按收入與毛利)

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容
**銷售和獲利表現** Power BI 內容顯示在 **銷售和獲利表現** 頁 (**銷售和行銷**\>**查詢和報表**\>**銷售業績分析**\>**銷售和獲利表現**)。

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的計量
**銷售和獲利表現** Power BI 內容包括由一組指標組成的報表。 這些指標可視覺化為圖表、圖格和資料表。 下表概述了內容中的視覺效果。

| 報表頁            | 圖表                                     | 圖格                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| 客戶的收入    | 依收入排列的前 10 大客戶                | 總收入                                           |
|                        | 按客戶組劃分的總收入            | 收入 YOY 增長                                      |
|                        | 按客戶群劃分的平均客戶收入 | 毛利                                            |
|                        | 按客戶群劃分的收入和毛利潤   |                                                         |
| 產品收入     | 按銷售類別劃分的收入和毛利潤   | 產品總數 \#                                    |
|                        | 依收入排列的前 10 大產品                 | 有效產品總數和占總數的百分比 |
|                        | 按銷售類別劃分的總收入            | 佔收入 80%的產品數量           |
| 收入 (依期間)\*    | 按月的收入                           | 收入 YOY 增長                                      |
|                        | 追踪收入差異，YOY             | 收入 YOY 增長 %                                    |
|                        | 客戶區域的總銷售差異    |                                                         |
| 收入 (依位置顯示)    | 各城市的銷售收入                      |                                                         |
|                        | 收入 YOY 增長 %                       |                                                         |
|                        | 各區域的銷售收入                    |                                                         |
| 客戶獲利能力 | 毛利與收入，按客戶   | 毛利潤、毛利率、收入 YOY 增長          |
| 獲利能力分析 | 月收入和毛利潤          |                                                         |
|                        | 毛利前 15 名的客戶           |                                                         |
|                        | 按月計算的毛利潤，YOY                 |                                                         |

\*今年和去年的收入，以及按銷售類別劃分的增長。

## <a name="understanding-the-data-model-and-entities"></a>了解資料模型和實體
以下資料用於填入報表中的 **銷售和獲利績效** Power BI 內容。 此資料表示為在實體存放區中暫存的聚合量值。 實體存放區是針對分析最佳化的 Microsoft SQL Server 資料庫。 如需相關資訊，請參閱[Power BI 與實體存放區的整合](power-bi-integration-entity-store.md)。

此內容中的彙總測量是 Microsoft Dynamics AX 2012 和 Microsoft Dynamics AX 2012 R3 銷售立方體中可用的彙總測量的子集。 若要在實體儲存中暫存多維資料集的彙總測量，您必須使它們可部署。 如需相關資訊，請參閱[Power BI 與 Dynamics 中的實體儲存整合](/archive/blogs/dynamicsaxbi/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update)部落格文章中的在實體儲存中暫存彙總測量的過程。

發票行實體的以下關鍵彙總測量用作內容的基礎。

| 實體        | 關鍵彙總量值                   | Dynamics 365 的資料來源 | 欄位                                        | 描述                                       |
|---------------|----------------------------------------------|------------------------------|----------------------------------------------|---------------------------------------------------|
| 發票明細 | 收入                                      | CustInvoiceTrans             | SUM(LineAmountMST)                           | 記帳貨幣的金額。            |
|               | 銷貨成本                           | InventTrans                  | SUM(CostAmountPosted + CostAmountAdjustment) | 成本金額和調整的總和。    |
|               | 佣金明細金額 - 記帳貨幣 | CustInvoiceTrans             | SUM(CommissAmountMST)                        | 依記帳貨幣計價的佣金金額。 |

下表顯示了發票行實體的關鍵彙總測量，這些測量用於在內容的資料集中建立多個計算測量。

| 量值           | 計算                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| 毛利      | SUM(Revenue – COGS – Commission – Sales tax (included in customer invoice line amount))          |
| 毛利      | SUM(Gross profit / (Revenue - Sales tax (included in customer invoice line amount)))             |
| 去年收入 | 去年收入 = CALCULATE(SUM('發票行'\[收入\]), SAMEPERIODLASTYEAR(日期\[日期\]) |

銷售立方體中的以下關鍵維度用作篩選器來對彙總測量進行配量，以便您可以獲得更大的細微性並獲得更深入的分析見解。

| 實體           | 屬性範例                               |
|------------------|------------------------------------------------------|
| 客戶        | 客戶群、客戶地區、地址、行業 |
| 產品         | 產品編號、產品名稱、項目組名稱       |
| 銷售類別 | 銷售類別名稱                                 |
| 法律實體   | 法律實體名稱                                   |
| 日期            | 日期                                                |

在預設情況下，內容顯示目前日曆年的資料。 但是，您可以在報表篩選器區塊更改日期篩選器。 您還可以更改公司篩選器。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]