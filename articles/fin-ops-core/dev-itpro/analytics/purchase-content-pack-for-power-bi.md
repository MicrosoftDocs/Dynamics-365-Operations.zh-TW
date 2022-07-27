---
title: 採購支出分析 Power BI 內容
description: 本主題介紹採購支出分析 Power BI 內容中包含的內容。
author: FrankDahl
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a40d4f39a7119def9ed0393d4ced2be1f7e801a5c1c3f984b002e5224299915a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460374"
---
# <a name="purchase-spend-analysis-power-bi-content"></a>採購支出分析 Power BI 內容

[!include [banner](../includes/banner.md)]

本主題介紹 **採購支出分析** Microsoft Power BI 內容中包含的內容。 它解釋了如何存取 Power BI 報表，並提供有關用於構建內容的資料模型和實體的資訊。

## <a name="overview"></a>概觀

**採購支出分析** Power BI 內容旨在幫助採購經理和負責預算的經理追蹤採購支出。 經理可以透過以下方式分析採購支出：

- 年初至今的採購 (按廠商組和單個廠商、採購類別和單個產品以及廠商位置)
- 逐年採購變化 (按廠商組和採購類別)

該內容使用採購交易資料，並提供公司範圍內採購資料的匯總檢視表以及廠商和產品的採購支出明細。 報表強調了購買支出在一段時間內的變化。 因此，這些報表可用於提醒經理有關各個廠商和產品的積極和消極支出趨勢。 此外，圖表顯示了不同採購類別和廠商組的採購支出。 因此，類別和區域經理可以使用圖表來幫助識別消費行為的變化。

## <a name="accessing-the-power-bi-content"></a>存取 Power BI 內容
**採購支出分析** Power BI 內容顯示在 **購買和支出分析** 頁 (**採購和溯源**\>**查詢和報表**\>**採購績效分析**\>**購買和支出分析**)。

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 內容中包含的計量
**採購支出分析** Power BI 內容包括由一組指標組成的報表。 這些指標可視覺化為圖表、圖格和資料表。 

以下部分提供了視覺效果的概述。

### <a name="purchase-by-vendor-report-page"></a>按廠商報表頁面購買
**圖表**
- 採購量排名前 10 位的廠商 (堆疊橫條圖)
- 按廠商組/國家/地區/名稱的總採購量 (圓形圖)
- 按廠商組/國家/地區/名稱購買 (直條圖)
- 按廠商組/國家/地區/名稱的平均購買量 (直條圖)

**圖格**
- 總採購
- YOY 採購成長
- 廠商總數
- 有效廠商總數

**範例**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>按產品報表頁面購買

**圖表**
- 按採購類別/產品名稱採購 (直條圖)
- 按採購類別/產品名稱的總採購量 (圓形圖)
- 採購量排名前 10 位的產品 (堆疊橫條圖)

**圖格**
- 產品總數</li>
- 有效產品總數佔產品總數的百分比
- 佔採購量 80%的產品數量

**範例**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>按定期報表頁面購買
該頁面顯示了今年和去年的採購情況，以及採購類別的成長情況。

**圖表** 
- 按月/日購買 (直條圖)
- 累計採購 YOY 差異 (統計圖)
- 總購買量 YOY 成長 (直條圖)
- 採購聲明 (矩陣)

**圖格**
- YOY 採購成長
- YOY 採購成長 %

**範例**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>按廠商位置報表頁面購買

**圖表**
- 按城市購買
- 購買 YOY 成長 %
- 按國家/地區購買

**範例**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>按時間報表頁面的購買支出分析

**圖表** 
- 按月/日購買當年 (折線圖)
- 購買目前和去年 (折線圖和直條圖)

**範例**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>按廠商報表頁面的購買支出分析

**圖表** 
- 前 10 名廠商採購量佔採購量 % (漏斗圖)
- 支出 YOY 成長的前 10 名廠商
- 支出 YOY 減少的前 10 名廠商

**範例** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>資料模型和實體
以下資料用於填入 **購買支出分析** Power BI 內容中的報表頁面。 此資料表示為在實體存放區中暫存的聚合量值。 實體存放區是針對分析最佳化的 Microsoft SQL Server 資料庫。 如需相關資訊，請參閱[Power BI 與實體存放區的整合](power-bi-integration-entity-store.md)。

此內容中的彙總測量是 Microsoft Dynamics AX 2012 和 Microsoft Dynamics AX 2012 R3 的採購多維資料集中可用的彙總測量的子集。 若要在實體儲存中暫存多維資料集的彙總測量，您必須使它們可部署。 如需相關資訊，請參閱[Power BI 與實體儲存整合](power-bi-integration-entity-store.md)中的實體儲存中暫存彙總測量的過程。 以下關鍵彙總測量可直接從發票行實體獲得，並用作內容的基礎。

| 實體        | 關鍵彙總量值 | 資料來源                                 | 欄位              | 描述                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| 發票明細 | 購買                   | VendInvoiceTrans                            | SUM(LineAmountMST) | 記帳貨幣的金額。 |

下表顯示了根據發票行實體計算的內容中的關鍵測量。

| 量值               | 計算                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| 購買當年 | 採購當年 = SUM('發票行'\[購買\])                                            |
| 採購去年    | 去年購買 = CALCULATE(SUM('發票行'\[購買\])，SAMEPERIODLASTYEAR(日期\[日期\])) |
| YOY 採購成長   | YOY 購買成長 =\[購買當年\]–\[去年購買\]                            |

內容中的以下關鍵維度用作篩選器以對彙總測量進行配量，以便您可以獲得更多細微性並獲得更深入的分析見解。

| 實體                 | 屬性範例                                |
|------------------------|-------------------------------------------------------|
| 廠商                | 廠商組、廠商國家或地區、廠商名稱 |
| 產品               | 產品編號、產品名稱、項目組名稱        |
| 採購類別 | 採購類別、採購類別名稱      |
| 法律實體         | 法律實體名稱                                     |
| 日期                  | 日期，年份偏移                                    |

在預設情況下，內容顯示目前日曆年的資料。 但是，您可以在報表篩選器區塊更改日期篩選器。 您還可以更改公司篩選器。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]