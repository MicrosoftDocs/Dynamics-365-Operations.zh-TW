---
title: 品質關聯
description: 本主題介紹如何在 Microsoft Dynamics 365 Supply Chain Management 中使用品質關聯自動產生與您的銷售、採購和生產流程相關的品質檢驗訂單。
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28984730e5660414eec1ba087eb5de1eba4cbbb8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448470"
---
# <a name="quality-associations"></a>品質關聯

[!include [banner](../includes/banner.md)]

本主題介紹如何在 Microsoft Dynamics 365 Supply Chain Management 中使用品質關聯自動產生與您的銷售、採購和生產流程相關的品質檢驗訂單。

品質關聯定義產生的品質檢驗訂單的所有以下資訊：

- 交易事件
- 必須對品項執行的一組測試
- 可接受的品質等級 (AQL)
- 取樣計劃

您必須為需要自動產生品質檢驗訂單的業務流程中的每個變體定義品質關聯。 例如，可以在訂購單、檢疫訂單、銷售訂單和生產訂單的業務流程中產生品質檢驗訂單。

## <a name="working-with-quality-associations"></a>與品質關聯合作

使用品質關聯的業務流程可以與各種來源文件相關，例如訂購單、銷售訂單或生產訂單。

每個品質關聯記錄定義適用於所產生的品質檢驗訂單的測試集、AQL 和取樣計劃。 您必須為業務流程中的每個變體定義品質關聯記錄。 例如，您可以設定在更新訂購單產品收據時產生品質檢驗訂單的品質關聯。 根據執行計劃的設定，觸發流程本身可以在有未結品質檢驗訂單時遭到封鎖。 或者，可以封鎖後續流程，例如訂購單開票。

> [!NOTE]
> 當有未結品質檢驗訂單時，系統會自動阻止庫存數量發出。 根據 **品項取樣** 頁面的 **完全封鎖** 欄位設定，數量是品質檢驗訂單上的數量或來源文件明細上的數量。 有關詳細資訊，請參閱[品質管理項目取樣](quality-item-sampling.md)。

對於給定的業務流程，品質關聯記錄識別為其產生品質訂單的事件和條件。 條件可以特定於站點或法律實體。 僅有當事件有現有庫存時，才能產生涉及破壞性測試的品質檢驗訂單。

要與品質關聯一同運作，請移至 **庫存管理 \> 設定 \> 品質控制 \> 品質關聯**。 以下示例說明如何為每個業務流程中的變體定義品質關聯記錄。 對於每個示例，下表總結了品質關聯記錄定義的事件和條件。

<table>
<thead>
<tr>
<th>參考類型</th>
<th>事件類型</th>
<th>執行</th>
<th>事件封鎖</th>
<th>文件參考</th>
</tr>
</thead>
<tbody>
<tr>
<td>庫存</td>
<td>不適用</td>
<td>不適用</td>
<td>無</td>
<td>全部</td>
</tr>
<tr>
<td rowspan="7">銷售</td>
<td rowspan="4">揀貨流程已安排</td>
<td rowspan="4">之前</td>
<td>無</td>
<td rowspan="22">僅限特定識別碼、群組或全部</td>
</tr>
<tr>
<td>揀貨流程</td>
</tr>
<tr>
<td>裝箱單</td>
</tr>
<tr>
<td>發票</td>
</tr>
<tr>
<td rowspan="3">裝箱單</td>
<td rowspan="3">之前</td>
<td>無</td>
</tr>
<tr>
<td>裝箱單</td>
</tr>
<tr>
<td>發票</td>
</tr>
<tr>
<td rowspan="15">購買</td>
<td rowspan="7">收據清單</td>
<td rowspan="4">之前</td>
<td>無</td>
</tr>
<tr>
<td>收據清單</td>
</tr>
<tr>
<td>產品收貨</td>
</tr>
<tr>
<td>發票</td>
</tr>
<tr>
<td rowspan="3">之後</td>
<td>無</td>
</tr>
<tr>
<td>產品收貨</td>
</tr>
<tr>
<td>發票</td>
</tr>
<tr>
<td rowspan="3">註冊</td>
<td rowspan="3">不適用</td>
<td>無</td>
</tr>
<tr>
<td>產品收貨</td>
</tr>
<tr>
<td>發票</td>
</tr>
<tr>
<td rowspan="5">產品收貨</td>
<td rowspan="3">之前</td>
<td>無</td>
</tr>
<tr>
<td>產品收貨</td>
</tr>
<tr>
<td>發票</td>
</tr>
<tr>
<td rowspan="2">之後</td>
<td>無</td>
</tr>
<tr>
<td>發票</td>
</tr>
<tr>
<td rowspan="8">生產</td>
<td rowspan="3">註冊</td>
<td rowspan="3">不適用</td>
<td>無</td>
<td rowspan="12">全部</td>
</tr>
<tr>
<td>報告為完成</td>
</tr>
<tr>
<td>結束</td>
</tr>
<tr>
<td rowspan="5">報告為完成</td>
<td rowspan="3">之前</td>
<td>無</td>
</tr>
<tr>
<td>報告為完成</td>
</tr>
<tr>
<td>結束</td>
</tr>
<tr>
<td rowspan="2">之後</td>
<td>無</td>
</tr>
<tr>
<td>結束</td>
</tr>
<tr>
<td rowspan="4">隔離</td>
<td rowspan="3">報告為完成</td>
<td rowspan="2">之前</td>
<td>報告為完成</td>
</tr>
<tr>
<td>結束</td>
</tr>
<tr>
<td>之後</td>
<td>結束</td>
</tr>
<tr>
<td>結束</td>
<td>之前</td>
<td>結束</td>
</tr>
<tr>
<td rowspan="3">途程作業</td>
<td rowspan="3">報告為完成</td>
<td rowspan="2">之前</td>
<td>無</td>
<td rowspan="3">特定識別碼、群組或全部，以及特定資源、群組或全部</td>
</tr>
<tr>
<td>報告為完成</td>
</tr>
<tr>
<td>之後</td>
<td>無</td>
</tr>
<tr>
<td rowspan="3">副產品生產</td>
<td>註冊</td>
<td>不適用</td>
<td rowspan="3">無</td>
<td rowspan="3">全部</td>
</tr>
<tr>
<td rowspan="2">報告為完成</td>
<td>之前</td>
</tr>
<tr>
<td>之後</td>
</tr>
</tbody>
</table>

> [!NOTE]
> *倉庫流程的品質管理* 功能增加了生產品質檢驗訂單處理的功能，其中 **事件類型** 欄位設定為 *報告為完成*，**執行** 欄位設為 *之後*，並且對於購買 **事件類型** 欄位設為 *登記*。 若需更多資訊，請參閱[倉庫流程的品質管理](quality-management-for-warehouses-processes.md)。

下表提供了有關如何為特定類型的流程產生品質檢驗訂單的更多資訊。

<div class="tableSection">
<table>
<thead>
<tr>
<th>程序類型</th>
<th>什麼時候可以自動產生品質檢驗訂單</th>
<th>如果需要破壞性測試，何時可以產生品質檢驗訂單</th>
<th>條件資訊</th>
<th>手動產生資訊</th>
</tr>
</thead>
<tbody>
<tr>
<td>訂購單</td>
<td>在過帳收到材料的收據清單或產品收據之前或之後</td>
<td>在收到材料的產品收據過帳後，因為材料必須可用於破壞性測試</td>
<td>品質檢驗訂單的要求可以反映特定的站點、品項或廠商，或這些條件的組合。</td>
<td>參考訂購單的手動產生的品質檢驗訂單可以使用品質關聯記錄中的資訊，例如測試取樣計劃。</td>
</tr>
<tr>
<td>檢疫訂單</td>
<td>在檢疫訂單報告為完成或結束之前或之後</td>
<td>無法產生要求破壞性測試的品質檢驗訂單。 假設檢疫訂單功能處理已銷毀材料的處置。</td>
<td>品質檢驗訂單的要求可以反映特定的站點、品項或廠商，或這些條件的組合。</td>
<td>參考檢疫訂單的手動產生的品質檢驗訂單可以使用品質關聯記錄中的資訊，例如測試取樣計劃。</td>
</tr>
<tr>
<td>銷售訂單</td>
<td>在計劃的揀貨流程或正在裝運的品項的裝箱單更新之前</td>
<td>在任何一個步驟</td>
<td>品質檢驗訂單的要求可以反映特定的站點、品項、廠商或客戶，或這些條件的組合。</td>
<td>參考銷售訂單的手動產生的品質檢驗訂單可以使用品質關聯記錄中的資訊，例如測試取樣計劃。</td>
</tr>
<tr>
<td>生產訂單</td>
<td>在報告生產訂單的完成數量之前或之後</td>
<td>在報告生產訂單的完成數量之後</td>
<td>品質檢驗訂單的要求可以反映特定的站點或品項，或這些條件的組合。</td>
<td>參考生產訂單的手動產生的品質檢驗訂單可以使用品質關聯記錄中的資訊，例如測試取樣計劃。</td>
</tr>
<tr>
<td>具有途程作業的生產訂單</td>
<td>作業報告完成之前或之後</td>
<td>上一個作業的報表製作完成後</td>
<td>品質檢驗訂單的要求可以反映特定的站點、品項或營運資源，或這些條件的組合。</td>
<td>參考途程作業的手動產生的品質檢驗訂單可以使用品質關聯記錄中的資訊，例如測試取樣計劃。</td>
</tr>
<tr>
<td>庫存</td>
<td>無法為庫存日記帳中的交易或轉移訂單交易自動產生品質檢驗訂單。</td>
<td></td>
<td></td>
<td>必須為物料的庫存數量手動建立品質檢驗訂單。 需要實物庫存。</td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a>自動產生品質檢驗訂單的範例

### <a name="purchasing"></a>採購

在採購時，如果您在 **品質關聯** 頁面上，將 **事件類型** 欄位設定為 *產品收據*，將 **執行** 欄位設為 *之後*，您會得到以下結果：

- 如果 **每更新數量** 選項設定為 *是*，根據收到的數量和物料取樣中的設定，針對訂購單為每個收貨產生質品質檢驗訂單。 每次收到訂購單的數量時，都會根據新收到的數量產生新的品質檢驗訂單。
- 如果 **每更新數量** 選項設定為 *否*，根據收到的數量和物料取樣中的設定，針對訂購單為第一個收貨產生質品質檢驗訂單。 此外，根據追蹤維度，根據剩餘數量建立一或多個品質檢驗訂單。 不會為訂購單的後續收貨產生品質檢驗訂單。

### <a name="production"></a>生產

在生產時，如果您在 **品質關聯** 頁面上，將 **事件類型** 欄位設定為 *報告為完成*，將 **執行** 欄位設為 *之後*，您會得到以下結果：

- 如果 **每更新數量** 選項設定為 *是*，根據品項取樣中的每個完成數量和設定產生質品質檢驗訂單。 每次收到訂購單的數量報告為已完成時，都會根據新完成的數量產生新的品質檢驗訂單。 這種產生邏輯與購買是一致的。
- 如果 **每更新數量** 選項設定為 *否*，第一次數量報告為完成時，系統會根據完成數量產生品質檢驗訂單。 此外，根據品項取樣的追蹤維度，根據剩餘數量建立一或多個品質檢驗訂單。 不會為後續完成的數量產生品質檢驗訂單。

<table>
<thead>
<tr>
<th>品質規格</th>
<th>每更新數量</th>
<th>每追蹤維度</th>
<th>結果</th>
</tr>
</thead>
<tbody>
<tr>
<td>百分比：10%</td>
<td>是</td>
<td>
<p>批次編號：否</p>
<p>序號：否</p>
</td>
<td>
<p>訂購數量：100</p>
<ol>
<li>報告為完成 (30 個)
<ul>
<li>3 的品質檢驗訂單 1 (30 的 10%)</li>
</ul>
</li>
<li>報告為完成 (70 個)
<ul>
<li>品質檢驗訂單 2 比 7 (剩餘訂單數量的 10%，在本例中為 70)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>固定數量：1</td>
<td>否</td>
<td>
<p>批次編號：否</p>
<p>序號：否</p>
</td>
<td>訂購數量：100
<ol>
<li>報告為完成 (30 個)
<ul>
<li>品質檢驗訂單 1 比 1 (針對第一個報告為完成的數量，其具有固定值 1)</li>
<li>品質檢驗訂單 2 比 1 (剩餘數量，其具有固定值 1)</li>
</ul>
</li>
<li>報告為完成 (10 個)
<ul>
<li>沒有建立任何品質檢驗訂單。</li>
</ul>
</li>
<li>報告為完成 (60 個)
<ul>
<li>沒有建立任何品質檢驗訂單。</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>固定數量：1</td>
<td>是</td>
<td>
<p>批次編號：是</p>
<p>序號：是</p>
</td>
<td>
<p>訂購數量：10</p>
<ol>
<li>報告為完成：批號 b1，序號 s1 為 3: 1；批號 b2，序號 s2 為 3: 1；批號 b3，序號 s3 為 3: 1
<ul>
<li>批號 b1、序號 s1 的品質檢驗訂單 1 比 1</li>
<li>批號 b2、序號 s2 的品質檢驗訂單 2 比 1</li>
<li>批號 b3、序號 s3 的品質檢驗訂單 3 比 1</li>
</ul>
</li>
<li>報告為完成 2：1 為批號 b4，序號 s4；和 1 用於批號 b5，序號 s5
<ul>
<li>批號 b4、序號 s4 的品質檢驗訂單 4 比 1</li>
<li>批號 b5、序號 s5 的品質檢驗訂單 5 比 1</li>
</ul>
</li>
</ol>
<p><strong>注意：</strong>批次可以重複使用。</p>
</td>
</tr>
<tr>
<td>固定數量：2</td>
<td>否</td>
<td>
<p>批次編號：是</p>
<p>序號：是</p>
</td>
<td>
<p>訂購數量：10</p>
<ol>
<li>報告為完成：批號 b1，序號 s1 為 4: 1；批號 b2，序號 s2 為 4: 1；批號 b3，序號 s3 為 4: 1；批號 b4，序號 s4 為 4:1
<ul>
<li>批號 b1、序號 s1 的品質檢驗訂單 1 比 1</li>
<li>批號 b2、序號 s2 的品質檢驗訂單 2 比 1</li>
<li>批號 b3、序號 s3 的品質檢驗訂單 3 比 1</li>
<li>批號 b4、序號 s4 的品質檢驗訂單 4 比 1</li>
</ul>
<ul>
<li>品質檢驗訂單 5 比 2，不參考批號和序號</li>
</ul>
</li>
<li>報告為完成 6: 1 批號 b5，序號 s5 報告完成；1 為批號 b6，序號 s6；1 為批號 b7，序號 s7；1 為批號 b8，序號 s8；1 為批號 b9，序號 s9；和 1 用於批號 b10，序號 s10
<ul>
<li>沒有建立任何品質檢驗訂單。</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>其他資源

- [品質管理流程](quality-management-processes.md)
- [啟用品質和不符合項管理](enable-quality-management.md)
- [倉庫流程的品質管理](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
