---
title: 庫存帳齡報告範例和邏輯
description: 本主題提供一些範例，說明如何解釋庫存帳齡報告的結果。
author: AndersGirke
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: 59c1740f6e07be08ad9379d4ccb6aeca29220d557aceb38bf6faef946e16fee7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447027"
---
# <a name="inventory-aging-report-examples-and-logic"></a>庫存帳齡報告範例和邏輯

[!include [banner](../includes/banner.md)]

本主題提供一些範例，說明如何解釋 **庫存帳齡** 報告的結果。 此報告將所選項目或項目群組中，現有的數量和庫存值，分類至多個貯體期間。 本主題還顯示報告的內部邏輯。

本主題中的範例，顯示標準 **庫存帳齡** 報告呈現的結果。 但是，一般情況下，我們建議您使用[庫存帳齡報表儲存體](inventory-aging-report-storage.md)版本，尤其當您必須處理許多庫存和倉庫時。 庫存帳齡報表儲存體，會儲存每次產生的報告，透過互動式頁面和圖表顯示結果，並允許您匯出任何已存檔的報告。

## <a name="sample-data-that-is-used-in-these-examples"></a>範例中使用的資料

本主題中的範例，是根據本章節中描述的樣本庫存交易資料。

### <a name="storage-dimension-setup"></a>儲存維度群組設定

範例系統包含下列儲存維度的設定。

| 姓名      | 使用中 | 實物庫存 | 財務庫存 |
|-----------|--------|--------------------|---------------------|
| 網站      | 是    | 是                | 是                 |
| 倉庫 | 是    | 是                | 否                  |

### <a name="inventory-model"></a>庫存模型

針對範例系統，已發布產品的庫存模型為 *先進先出*，而 **成本價格** 庫存模型的設定為 *包括實物價值*。

### <a name="inventory-transactions"></a>庫存交易

範例系統包含下列已發佈產品的庫存交易，品項編號為 *1000*。

| 參考      | 網站 | 倉庫 | 收貨   | 簽發 | 實體日期 | 財務日期 | 數量 | 成本金額 | 實體成本金額 |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| 訂購單 | 1    | 11        | 已購買 |       | 3 月 15 日      | 3 月 15 日       | 10       | 1,000       | 1,000                |
| 訂購單 | 2    | 21        | 已購買 |       | 3 月 15 日      | 3 月 15 日       | 10       | 2,000       | 2,000                |
| 訂購單 | 1    | 11        | 已收到  |       | 4 月 15 日      |                | 5        |             | 375                  |
| 轉移訂單 | 1    | 11        |           | 已售出  | 5 月 2 日         | 5 月 2 日          | -5       | -458.33     | -458.33              |
| 轉移訂單 | 1    | 12        | 已購買 |       | 5 月 2 日         | 5 月 2 日          | 5        | 458.33      | 458.33               |
| 銷售訂單    | 1    | 12        |           | 已售出  | 5 月 3 日         | 5 月 3 日          | -1       | -91.67      | -91.67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>如何計算每個貯體期間的數量和金額

透過使用先前章節中描述的樣本資料，您可以執行具有下列設定的 **庫存帳齡** 報告：

- **截至日期：** *2020 年 5 月 9 日*
- **地點：** *檢視*
- **倉庫：** *無*
- **品項編號：** *總計*
- **帳齡期間：** 設定此欄位以產生每月貯體。

在此案例中，產生的報告內容類似於下列範例。

<table>
<thead>
<tr>
    <th rowspan="2">品項編號</th>
    <th rowspan="2">網站</th>
    <th rowspan="2">現有數量</th>
    <th rowspan="2">現有價值</th>
    <th rowspan="2">庫存價值數量</th>
    <th rowspan="2">庫存值</th>
    <th rowspan="2">平均單位成本</th>
    <th colspan="2">2020 年 5 月 1 日至 2020 年 5 月 8 日</th>
    <th colspan="2">2020 年 4 月 1 日至 2020 年 4 月 30 日</th>
    <th colspan="2">2020 年 3 月 1 日至 2020 年 3 月 31 日</th>
</tr>
<tr>
    <th>P1：數量</th>
    <th>P1：金額</th>
    <th>P2：數量</th>
    <th>P2：金額</th>
    <th>P3：數量</th>
    <th>P3：金額</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 總計</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

請注意此範例報告中的下列詳細資訊：

- 顯示於報告上的 **庫存價值數量**、**庫存價值**，和 **平均單位成本** 的值，是用於財務庫存維度的值 (在此案例中為 **地點**)。

    例如，針對地點 1，報告顯示下列資訊：

    - **庫存價值數量** 的值為 *14* (= 10 + 5 – 5 + 5 – 1)。
    - **庫存值** 的值為 *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67)。
    - **平均單位成本** 的值為 *91.67*。
    - 每個貯體期間的 **現有價值** 和 **金額** 的值，是使用 **平均單位成本** 值進行計算。

- 報表透過加總每個貯體期間的總接收庫存數量，決定目前的庫存數量。 然後，無論項目使用的庫存模型如何，都會套用先進先出 (FIFO) 原則來扣除總發出數量。

如果您再次執行相同的報告，但這次您同時設定 **地點** 和 **倉庫** 欄位以供 *檢視*，新的報告將類似於下列範例。

<table>
<thead>
<tr>
    <th rowspan="2">品項編號</th>
    <th rowspan="2">網站</th>
    <th rowspan="2">倉庫</th>
    <th rowspan="2">現有數量</th>
    <th rowspan="2">現有價值</th>
    <th rowspan="2">庫存價值數量</th>
    <th rowspan="2">庫存值</th>
    <th rowspan="2">平均單位成本</th>
    <th colspan="2">2020 年 5 月 1 日至 2020 年 5 月 8 日</th>
    <th colspan="2">2020 年 4 月 1 日至 2020 年 4 月 30 日</th>
    <th colspan="2">2020 年 3 月 1 日至 2020 年 3 月 31 日</th>
</tr>
<tr>
    <th>P1：數量</th>
    <th>P1：金額</th>
    <th>P2：數量</th>
    <th>P2：金額</th>
    <th>P3：數量</th>
    <th>P3：金額</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 總計</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

這次，位置 1 分成兩列，一列是 11 號倉庫，另一列是 12 號倉庫。 但是，報告上的 **庫存價值數量**、**庫存價值**，和 **平均單位成本** 的值都相同，因為，**倉庫** 不是財務庫存維度的值。

此外，請注意位置 1 的數量分配不同。 第一次執行的報告中，系統將同一位置中發生的轉移訂單忽略，並從位置 1 扣除 **2020 年 3 月 1 日至 2020 年 3 月 31 日** 貯體期間的銷售發票數量。 但是，新的報告中，系統從倉庫 12 扣除 **2020 年 5 月 1 日至 2020 年 5 月 8 日** 貯體期間的銷售發票。

## <a name="effects-of-inventory-closing"></a>庫存結算的影響

如果您執行 5 月的庫存結算，然後再次執行先前的報表，但您將 **截至日期** 欄位設定到 *2020 年 5 月 31 日*，您會注意到下列結果：

- **庫存值** 和 **平均單位成本** 值會更新。
- 每個貯體期間內 **現有價值** 的值和所有 **金額** 的值都會相應更新。

新的報告將類似於下列範例。

<table>
<thead>
<tr>
    <th rowspan="2">品項編號</th>
    <th rowspan="2">網站</th>
    <th rowspan="2">倉庫</th>
    <th rowspan="2">現有數量</th>
    <th rowspan="2">現有價值</th>
    <th rowspan="2">庫存價值數量</th>
    <th rowspan="2">庫存值</th>
    <th rowspan="2">平均單位成本</th>
    <th colspan="2">2020 年 5 月 1 日至 2020 年 5 月 31 日</th>
    <th colspan="2">2020 年 4 月 1 日至 2020 年 4 月 30 日</th>
    <th colspan="2">2020 年 3 月 1 日至 2020 年 3 月 31 日</th>
</tr>
<tr>
    <th>P1：數量</th>
    <th>P1：金額</th>
    <th>P2：數量</th>
    <th>P2：金額</th>
    <th>P3：數量</th>
    <th>P3：金額</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0.00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 總計</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]