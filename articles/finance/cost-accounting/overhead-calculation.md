---
title: 管銷費用計算
description: 本主題說明計算和分配管銷費用成本的典型流程。
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 60bce611ae1f6ed5d63860793cd5d1da3c421a9e
ms.sourcegitcommit: e3290eb58ae569a59d6ae2e6922e7d8be8f1980f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2021
ms.locfileid: "8450990"
---
# <a name="overhead-calculation"></a>管銷費用計算

[!include [banner](../includes/banner.md)]

本主題說明計算和分配管銷費用成本的典型流程。

## <a name="term-definition"></a>術語定義

管銷成本是為了執行業務所招致的成本，但不能直接歸因於任何特定的商務活動、產品或服務。 管銷成本提供營利活動產生所需的關鍵支援。 間接費用成本的若干範例如下：

-   租金
-   電
-   行政薪資

## <a name="overhead-calculation-overview"></a>管銷計算概觀
管銷成本計算以正確順序執行成本會計政策。 如果成本會計政策已經更改或偵測到特定錯誤，您可以在同一個會計期間數次執行管銷費用計算。 每次執行的管銷費用計算都會儲存，並收到唯一的版本識別碼，讓您可以比較不同版本的計算。 管銷費用計算的成本分錄產生收到會計日期。 此會計日期符合計算中使用會計期間的結束日期。 唯一的版本識別碼包含下列元素：

-   版本類型
-   日期和時間
-   成本會計分類帳
-   會計年度
-   會計期間

管銷計算執行時獨立於版本以外。 因此，您可以在實際版本之前計算預算版本。 管銷計算包括四道步驟，如下圖所示。 每道步驟都會建立含有日記帳分錄的日記帳標題。 此日記帳標題保存每道計算步驟的輸入資料。 政策和規則套用到每條日記帳明細，而成本分錄產生為輸出。 因此，您始終擁有完整的可追溯性。 

[![管銷費用計算。](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>計算和分配電力管銷成本
Financial 會計中，一些成本 (例如電費) 被登記為一次性付訖。 因此，成本會計不提供詳細的管理見解。 成本會計中，為了跨所有組織單位和等級提供正確的管理見解，成本必須流經組織單位。 此類流程必須以精確的消費記錄或公平評估為基礎。 總帳中的電費成本可以過帳，如下表所示。

<table>
<thead>
<tr>
<th>會計日期</th>
<th colspan="2">成本中心</th>
<th colspan="2">主科目</th>
<th>以會計貨幣計的金額</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017 年一月 3 日</td>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>步驟 1：處理成本行為計算

當來源資料從成本分錄匯入時，它們預設會收到 Cost 會計中的 **未歸類** 成本行為分類。 憑藉套用成本行為政策規則，您可以將成本分錄重新歸類為 **固定成本** 或 **變動成本**。

#### <a name="define-the-cost-behavior-rule"></a>定義成本行為規則

某些情況下的部分成本是固定費用，而剩餘成本則以消費角度為主。 電費帳單往往符合這項定義。 等您支付特定的固定費用後，您需要支付每千瓦小時 (Kwh) 的耗用量。 例如，如果固定成本費用 1,000.00，則成本行為規則定義如下：

-   固定金額 1,000.00
    -   0 &lt;= 1,000.00 = 固定
    -   1000,01 &lt; N = 變動

##### <a name="journal"></a>日記帳

<table>
<thead>
<tr>
<th>日記帳</th>
<th>日記帳類型</th>
<th colspan="3">會計行事曆期間</th>
<th>版本</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>成本行為計算日記帳</td>
<td>會計</td>
<td>2017</td>
<td>期間 1</td>
<td>間接費用計算 /01-02-2017 11:51:00 PM / 分類帳 /2017 / 期間 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>日記帳分錄 (成本物件餘額日記帳分錄)

<table>
<thead>
<tr>
<th>會計日期</th>
<th colspan="2">成本物件</th>
<th colspan="2">成本元素</th>
<th>成本行為</th>
<th>金額</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017 年一月 3 日</td>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>未歸類</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>成本分錄

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th colspan="2">成本元素</th>
<th>成本行為</th>
<th>金額</th>
<th>會計日期</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>未歸類</td>
<td>10,000.00</td>
<td>2017 年一月 3 日</td>
</tr>
<tr>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>未歸類</td>
<td>-10,000.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>1,000.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>9,000.00</td>
<td>2017 年一月 31 日</td>
</tr>
</tbody>
</table>

更多資訊，請參閱[建立與指派成本行為政策給成本控制單元](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)。
### <a name="step-2-process-the-cost-distribution-calculation"></a>步驟 2：處理成本分配計算

成本分配用來藉由套用相關分配基數，將成本從一個成本物件重新分配到一個或多個其他成本物件。 成本分配和成本配置的差異點在於成本分配始終發生在原始成本的主成本元素等級。

#### <a name="define-the-cost-distribution-rule"></a>定義成本分配規則

Financial 會計中，電費成本往往被登記為一次性付訖。 Cost 會計中，這類方法不夠詳細。 變動成本應在公平基礎上分配給個別成本物件。 最合乎邏輯的配置依據是用電量 (Kwh)。 已建立名為 Electricity 的統計維度成員，並已記錄用電量。 所有統計維度成員預設下都可當作配置基數。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>Kwh</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>1,000</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>6,000</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>0</td>
</tr>
</tbody>
</table>

下表顯示用電量當作變動成本的分配基數時的結果。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>量幅</th>
<th>配置係數</th>
<th>金額</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>1,000</td>
<td>(1,000 ÷ 7,000) × 9,000.00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>6,000</td>
<td>(6,000 ÷ 7,000) × 9,000.00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>0</td>
<td>(0 ÷ 7,000) × 9,000.00</td>
<td>0.00</td>
</tr>
</tbody>
</table>

固定成本應平均分配給已經用電的個別成本物件。 您可以借助公式配置基礎的電力統計維度成員達到這項結果：(電力&gt;0.00) 下表顯示當電量套用為變動成本配置基礎時的結果。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>公式</th>
<th>量幅</th>
<th>配置係數</th>
<th>金額</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>(1,000 &gt; 0.00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1,000.00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>(6,000 &gt; 0.00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1,000.00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>(0 &gt; 0.00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1,000.00</td>
<td>0.00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>日記帳

<table>
<thead>
<tr>
<th>日記帳</th>
<th>日記帳類型</th>
<th colspan="3">會計行事曆期間</th>
<th>版本</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>成本分配計算日記帳</td>
<td>會計</td>
<td>2017</td>
<td>期間 1</td>
<td>間接費用計算 /01-02-2017 11:51:00 PM / 分類帳 /2017 / 期間 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>日記帳分錄 (成本物件餘額日記帳分錄)

<table>
<thead>
<tr>
<th>會計日期</th>
<th colspan="2">成本物件</th>
<th colspan="2">成本元素</th>
<th>成本行為</th>
<th>金額</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017 年一月 31 日</td>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>1,000.00</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>9,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>成本分錄

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th colspan="2">成本元素</th>
<th>成本行為</th>
<th>金額</th>
<th>會計日期</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>-1,000.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>500.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>500.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC099</td>
<td>預設成本中心</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>-9,000.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>1,285.71</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>7,714.29</td>
<td>2017 年一月 31 日</td>
</tr>
</tbody>
</table>

更多資訊，請參閱[建立與指派成本分配政策給成本控制單元](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)。 

### <a name="step-3-process-the-overhead-rate-calculation"></a>步驟 3：處理管銷費率計算

管銷費率用來對一個或多個特定成本物件收費。 收費依據以預定成本費率和指派配置基礎的量幅為主。 

#### <a name="define-the-overhead-rate"></a>定義管銷費率

成本物件 CC001 HR 負責提撥給一組內部專案。 名為 HR 專案的統計維度成員已建立來衡量消耗的量幅。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>時數</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>專案 1 </td>
<td>3</td>
</tr>
<tr>
<td>Proj 2</td>
<td>專案 2 </td>
<td>1</td>
</tr>
</tbody>
</table>

成本專案提撥的預定成本率已經定義。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>成本元素</th>
<th>成本行為</th>
<th>單位</th>
<th>費率</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>變動成本</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

下表顯示 HR 專案套用為配置基礎時的結果。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>量幅</th>
<th>成本元素</th>
<th>配置係數</th>
<th>金額</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>專案 1 </td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10.00</td>
<td>30.00</td>
</tr>
<tr>
<td>Proj 2</td>
<td>專案 2 </td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10.00</td>
<td>10.00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>日記帳

<table>
<thead>
<tr>
<th>日記帳</th>
<th>日記帳類型</th>
<th colspan="3">會計行事曆期間</th>
<th>版本</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>費用率計算日記帳</td>
<td>會計</td>
<td>2017</td>
<td>期間 1</td>
<td>間接費用計算 /01-02-2017 11:51:00 PM / 分類帳 /2017 / 期間 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>日記帳分錄 (管銷費率計算的日記帳分錄)

<table>
<thead>
<tr>
<th>會計日期</th>
<th colspan="2">成本物件</th>
<th>量幅</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017 年一月 31 日</td>
<td>Proj 1</td>
<td>內部 Proj 1</td>
<td>3.00</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>Proj 2</td>
<td>內部 Proj 2</td>
<td>1.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>成本分錄

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th colspan="2">成本元素</th>
<th>成本行為</th>
<th>金額</th>
<th>會計日期</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>HR</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>-30.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Proj 1</td>
<td>內部 Proj 1</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>30.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>-10.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Proj 2</td>
<td>內部 Proj 2</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>10.00</td>
<td>2017 年一月 31 日</td>
</tr>
</tbody>
</table>

更多資訊，請參閱[執行管銷費用計算](cost-rollup.md#perform-overhead-calculation)。

### <a name="step-4-process-the-cost-allocation-calculation"></a>步驟 4：處理成本配置計算

配置用來藉由套用配置基礎將成本物件的餘額配置給其他成本物件。 財務支援互惠分攤方法。 在互惠分攤方法中，輔助成本標的交換的相互服務得到充分確認。 系統自動確定執行配置的正確順序。 成本標的的餘額由單個分攤基礎分配。 支援跨成本物件維度及其各自成員的配置。 分攤順序由成本控制單元控制。 

[![倒數法。](./media/reciprocal-method.png)](./media/reciprocal-method.png)

#### <a name="define-the-cost-allocation"></a>定義成本配置

以下是簡單範例，解釋您如何追蹤成本流向。 成本物件 CC001 HR 提撥給幾個成本物件。 名為 HR 服務的統計維度成員已建立來衡量消耗的量幅。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>HR 服務</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>10</td>
</tr>
</tbody>
</table>

成本物件 CC002 Finance 提撥給幾個成本物件。 名為 Finance 服務的統計維度成員已建立來衡量消耗的量幅。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>Finance services</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>組件</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>35</td>
</tr>
</tbody>
</table>

成本物件 CC003 Assembly 提撥給幾個成本物件。 名為 Assembly 服務的統計維度成員已建立來衡量消耗的量幅。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>Assembly 服務 (小時)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>60</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>20</td>
</tr>
</tbody>
</table>

成本物件 CC004 Packaging 提撥給幾個成本物件。 名為 Packaging 服務的統計維度成員已建立來衡量消耗的量幅。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>Packaging 服務 (小時)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>80</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>15</td>
</tr>
</tbody>
</table>

> [!NOTE]
> 產品消耗的生產時數等統計量值可從來源資料衍生。 更多資訊，請參閱[統計量值提供者範本](statistical-measure-provider-template.md#statistical-measure-provider-template)。 下表顯示 HR 服務套用為總成本 (固定成本和變動成本) 配置基礎時的結果。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>量幅</th>
<th>配置係數</th>
<th>金額</th>
<th>成本行為</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>35</td>
<td>(35 ÷ 100) × 500.00</td>
<td>175.00</td>
<td>固定成本</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>55</td>
<td>(55 ÷ 100) × 500.00</td>
<td>275.00</td>
<td>固定成本</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>10</td>
<td>(10 ÷ 100) × 500.00</td>
<td>50.00</td>
<td>固定成本</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>35</td>
<td>(35 ÷ 100) × 1,245.71</td>
<td>436.00</td>
<td>變動成本</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>55</td>
<td>(55 ÷ 100) × 1,245.71</td>
<td>685.14</td>
<td>變動成本</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>10</td>
<td>(10 ÷ 100) × 1,245.71</td>
<td>124.57</td>
<td>變動成本</td>
</tr>
</tbody>
</table>

下表顯示 Finance 服務套用為總成本 (固定成本和變動成本) 配置基礎時的結果。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>量幅</th>
<th>配置係數</th>
<th>金額</th>
<th>成本行為</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>組件</td>
<td>65</td>
<td>(65 ÷ 100) × (500.00 + 175.00)</td>
<td>438.75</td>
<td>固定成本</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>35</td>
<td>(35 ÷ 100) × (500.00 + 175.00)</td>
<td>236.25</td>
<td>固定成本</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>65</td>
<td>(65 ÷ 100) × (7,714.29 + 436.00)</td>
<td>5,297.69</td>
<td>變動成本</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>35</td>
<td>(35 ÷ 100) × (7,714.29 + 436.00)</td>
<td>2,852.60</td>
<td>變動成本</td>
</tr>
</tbody>
</table>

下表顯示 Assembly 服務套用為總成本 (固定成本和變動成本) 配置基礎時的結果。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>量幅</th>
<th>配置係數</th>
<th>金額</th>
<th>成本行為</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>60</td>
<td>(60 ÷ 80) × (275.00 + 438.75)</td>
<td>535.31</td>
<td>固定成本</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>20</td>
<td>(20 ÷ 80) × (275.00 + 438.75)</td>
<td>178.44</td>
<td>固定成本</td>
</tr>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>60</td>
<td>(60 ÷ 80) × (5,297.69 + 685.14)</td>
<td>4,487.12</td>
<td>變動成本</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>20</td>
<td>(20 ÷ 80) × (5,297.69 + 685.14)</td>
<td>1,495.71</td>
<td>變動成本</td>
</tr>
</tbody>
</table>

下表顯示 Packaging 服務套用為總成本 (固定成本和變動成本) 配置基礎時的結果。

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th>量幅</th>
<th>配置係數</th>
<th>金額</th>
<th>成本行為</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>80</td>
<td>(80 ÷ 95) × (50.00 + 236.25)</td>
<td>241.05</td>
<td>固定成本</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>15</td>
<td>(15 ÷ 95) × (50.00 + 236.25)</td>
<td>45.20</td>
<td>固定成本</td>
</tr>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>80</td>
<td>(80 ÷ 95) × (2,852.60 + 124.57)</td>
<td>2,507.09</td>
<td>變動成本</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>15</td>
<td>(15 ÷ 95) × (2,852.60 + 124.57)</td>
<td>470.08</td>
<td>變動成本</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>日記帳分錄 (成本物件餘額日記帳分錄)

<table>
<thead>
<tr>
<th>日記帳</th>
<th>日記帳類型</th>
<th colspan="3">會計行事曆期間</th>
<th>版本</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>成本分配日記帳</td>
<td>會計</td>
<td>2017</td>
<td>期間 1</td>
<td>間接費用計算 /01-02-2017 11:51:00 PM / 分類帳 /2017 / 期間 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>日記帳明細

<table>
<thead>
<tr>
<th>會計日期</th>
<th colspan="2">成本物件</th>
<th colspan="2">成本元素</th>
<th>成本行為</th>
<th>金額</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017 年一月 31 日</td>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>500.00</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>1,245.71</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>675.00</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>8,150.29</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>713.75</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>5,982.83</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>CC003</td>
<td>裝箱</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>286.25</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>CC003</td>
<td>裝箱</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>2,977.17</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>Prod 1</td>
<td>產品 1</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>776.36</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>Prod 1</td>
<td>產品 1</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>6,994.21</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>Prod 2</td>
<td>產品 1</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>223.64</td>
</tr>
<tr>
<td>2017 年一月 31 日</td>
<td>Prod 2</td>
<td>產品 1</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>成本分錄

<table>
<thead>
<tr>
<th colspan="2">成本物件</th>
<th colspan="2">成本元素</th>
<th>成本行為</th>
<th>金額</th>
<th>會計日期</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>-500.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>175.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>275.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>50,00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>-1,245.71</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>436.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>685.14</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>124.57</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>-675.00</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>438.75</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>236.25</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>-8,150.29</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>5,297.69</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC004</td>
<td>裝箱</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>2,852.60</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>-713.75</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>535.31</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>178.44</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>-5,982.83</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>4,487.12</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>1,495.71</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>-286.25</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>241.05</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>10001</td>
<td>電</td>
<td>固定成本</td>
<td>45.20</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>CC003</td>
<td>組件</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>-2,977.17</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Prod 1</td>
<td>產品 1</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>2,507.09</td>
<td>2017 年一月 31 日</td>
</tr>
<tr>
<td>Prod 2</td>
<td>產品 2</td>
<td>10001</td>
<td>電</td>
<td>變動成本</td>
<td>470.08</td>
<td>2017 年一月 31 日</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>結論
Financial 會計中，10,000.00 電力成本過帳到虛擬成本中心識別碼。 因此，成本會計師將知道必須配置此成本。 Cost 會計中，成本根據適用策略和規則會跨組織單位和等級流動。 每項成本一直與提供最佳成本配置評定的配置基礎有關。

成本元素 | 成本物件<br>CC099 | 成本物件<br>CC001 | 成本物件<br>CC002 | 成本物件<br>CC003 | 成本物件<br>CC004 | 成本物件<br>Proj 1 | 成本物件<br>Proj 2 | 成本物件<br>Prod 1 | 成本物件<br>Prod 2 | 總計
---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:
10001 電 | 0.00 | 0.00 | 0.00 | 0.00 |  | 30.00 | 10.00 | 7,770.57 | 2,189.43 | 10,000.00 |
未歸類 | 0.00 |  |  |  |  |  |  |  |  |  |
固定成本 | 0.00 | 0.00 | 0.00 | 0.00 | 0.00 |  |  | 776.36 | 223.64 | 1,000.00 |
變動成本 | 000 | 0.00 | 0.00 | 0.00 | 0.00 | 30.00 | 10.00 | 6,994.21 | 1,965.79 | 9,000.00 |

> [!NOTE]
> 本主題顯示主要成本元素 10001 電力如何流經成本物件。 因此，此管銷成本配置給組織中的最低等級。 換言之，最低等級成本物件承擔成本。 如果您需要成本物件之間的成本以視覺式流動為主，您可以使用成本彙總政策規則視覺化成本的流動情況。 更多資訊，請參閱[成本彙總政策和管銷費用計算](cost-rollup.md)。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
