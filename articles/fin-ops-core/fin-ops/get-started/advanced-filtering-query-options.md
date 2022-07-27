---
title: 進階篩選和查找句法
description: 本主題介紹進階篩選/排序對話方塊的篩選和查找選項，以及篩選窗格或格線資料欄標題篩選條件中的比對運算子。
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0fefac5a7a2b299ba606a854824ee456c572487
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460157"
---
# <a name="advanced-filtering-and-query-syntax"></a>進階篩選和查找句法

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題介紹了當您使用進階篩選/排序對話方塊時可用的篩選和查找選項，或篩選窗格或格線資料欄標題篩選中的 **比對** 運算子。

## <a name="advanced-query-syntax"></a>進階查找句法

<table>
<thead>
<tr>
<th>句法</th>
<th>字元描述</th>
<th>描述</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr>
<td><em>值</em></td>
<td>等於輸入的值</td>
<td>輸入要尋找的值。</td>
<td><strong>Smith</strong> 發現 &quot;Smith&quot;。</td>
</tr>
<tr>
<td>!<em>值</em> (驚嘆號)</td>
<td>不等於輸入的值</td>
<td>輸入驚嘆號，然後輸入要排除的值。</td>
<td><strong>!Smith</strong> 發現所有值，除了 &quot;Smith&quot;。</td>
</tr>
<tr>
<td><em>起始值</em>..<em>結束值</em> (雙句點)</td>
<td>在由雙句點分隔的兩個值之間</td>
<td>輸入起始值，然後輸入兩個句點，然後輸入結束值。</td>
<td><strong>1..10</strong> 尋找從 1 到 10 的所有值。 但是，在字串欄位中，<strong>A..C</strong> 尋找所有開頭為 &quot;A&quot; 和 &quot;B&quot; 的值，以及值完全等於 &quot;C&quot; 的值。 例如，此查找不會找到 &quot;Ca&quot;。 若要尋找所有從 &quot;A<em>&quot; 到 &quot;C</em>&quot; 值，請輸入 <strong>A..D</strong>。</td>
</tr>
<tr>
<td>..<em>值</em> (雙句點)</td>
<td>小於或等於輸入的值</td>
<td>輸入兩個句點，然後輸入值。</td>
<td><strong>..1000</strong> 尋找小於或等於 1000 的任何數字，例如 &quot;100&quot;、&quot;999.95&quot; 和 &quot;1,000&quot;。</td>
</tr>
<tr>
<td><em>值</em>.. (雙句點)</td>
<td>大於或等於輸入的值</td>
<td>輸入值，然後輸入兩個句點。</td>
<td><strong>1000..</strong> 尋找大於或等於 1000 的任何數字，例如 &quot;1,000&quot;、&quot;1,000.01&quot; 和 &quot;1,000,000&quot;。</td>
</tr>
<tr>
<td>&gt;<em>值</em> (大於符號)</td>
<td>大於輸入的值</td>
<td>輸入大於符號 (<strong>&gt;</strong>) 然後是值。</td>
<td><strong>&gt;1000</strong> 尋找任何大於 1000 的數字，例如 &quot;1000.01&quot;、&quot;20,000&quot; 和 &quot;1,000,000&quot;。</td>
</tr>
<tr>
<td>&lt;<em>值</em> (小於符號)</td>
<td>小於輸入的值</td>
<td>輸入小於符號 (<strong>&lt;</strong>) 然後是值。</td>
<td><strong>&lt;1000</strong> 尋找任何小於 1000 的數字，例如 &quot;999.99&quot;、&quot;1&quot; 和 &quot;-200&quot;。</td>
</tr>
<tr>
<td><em>值</em>* (星號)</td>
<td>從輸入的值開始</td>
<td>輸入起始值，然後輸入星號 (<strong>*</strong>)。</td>
<td><strong>S*</strong> 尋找任何以 &quot;S&quot; 開頭的任何字串，如 &quot;Stockholm (斯德哥爾摩) &quot;、&quot;Sydney (雪梨) &quot;和 &quot;San Francisco (舊金山) &quot;。</td>
</tr>
<tr>
<td>*<em>值</em> (星號)</td>
<td>以輸入的值結束</td>
<td>輸入星號，然後輸入結束值。</td>
<td><strong>*east</strong> 尋找以 &quot;east&quot; 結束的任何字串，如 &quot;Northeast (東北) &quot;和 &quot;Southeast (東南) &quot;。</td>
</tr>
<tr>
<td>*<em>值</em>* (星號)</td>
<td>包含輸入的值</td>
<td>輸入一個星號，然後鍵入一個值，然後輸入另一個星號。</td>
<td><strong>*th*</strong> 尋找包含 &quot;th&quot; 的任何字串，如 &quot;Northeast (東北) &quot;和 &quot;Southeast (東南) &quot;。</td>
</tr>
<tr>
<td>? (問號)</td>
<td>有一個或多個未知字元</td>
<td>在值中未知字元的位置輸入問號。</td>
<td><strong>Sm?th</strong> 尋找 &quot;Smith&quot; 和 &quot;Smyth&quot;。</td>
</tr>
<tr>
<td><em>值</em>，<em>值</em> (逗號)</td>
<td>比對以逗號分隔的值</td>
<td>輸入所有標準，並使用逗號分隔它們。</td>
<td><strong>A、D、F、G</strong> 準確尋找 &quot;A&quot;、&quot;D&quot;、&quot;F&quot; 和 &quot;G&quot;。 <strong>10、20、30、100</strong> 準確尋找 &quot;10、20、30、100&quot;。</td>
</tr>
<tr>
<td>"" (兩個雙引號)</td>
<td>比對一個空白值</td>
<td>輸入兩個連續的雙引號以過濾該欄位中的空白值。</td>
<td>兩個連續的雙引號 (<strong>""</strong>) 尋找現行這資料欄沒有值的資料列。</td>
</tr>
<tr>
<td> (<span class="code">財務和營運查找</span>) (括號之間的財務和營運查找)</td>
<td>比對定義的查找</td>
<td>使用財務和營運查找語言在括號之間輸入查找作為 SQL 陳述式。</td>
  <td><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong><br><br> 
       作為來自根資料來源欄位以及來自不同資料來源欄位的篩選條件句法範例 (適用於所有客戶頁面)</td>
</tr>
<tr>
<td>T</td>
<td>今天的日期</td>
<td>輸入 <strong>T</strong>。</td>
<td><strong>T</strong> 符合今天的日期。</td>
</tr>
<tr>
<td>(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> 括號之間的方法)</td>
<td>比對由 <strong>SysQueryRangeUtil</strong> 方法之參數指定的值或值範圍</td>
<td>輸入指定值或值範圍並且有參數的 <strong>SysQueryRangeUtil</strong> 方法。</td>
<td>
<ol>
<li>點選<strong>應收帳款</strong>&gt;<strong>發票</strong>&gt;<strong>打開客戶發票</strong>。</li>
<li>按 Ctrl+Shift+F3 打開<strong>查找</strong>頁面。</li>
<li>在<strong>範圍</strong>索引標籤，點選<strong>新增</strong>。</li>
<li>在<strong>資料表</strong>欄位中，選取<strong>打開客戶交易</strong>。</li>
<li>在<strong>欄位</strong>欄位中，選取<strong>到期日</strong>。</li>
<li>在<strong>標準</strong>欄位，輸入<strong>(yearRange(-2,0))</strong>。</li>
<li>按一下<strong>確定</strong>。 清單頁面已更新並列出與您輸入標準相符的發票。 在此範例中，列出了前兩年到期的發票。</li>
</ol>
如需有關<strong>SysQueryRangeUtil</strong>資料方法的其他詳情，請參閱下一節中的資料表以及幾個範例。</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>使用 SysQueryRangeUtil 方法的進階日期查找

<table>
<thead>
<tr>
<th>方法</th>
<th>描述</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr>
<td>天 (_relativeDays=0)</td>
<td>尋找相對於工作階段日期的日期。 正值表示未來日期，負值表示過去日期。</td>
<td>
<ul>
<li><strong>明天</strong> - 輸入 <strong>(Day(1))</strong>。</li>
<li><strong>今天</strong> - 輸入 <strong>(Day(0))</strong>。</li>
<li><strong>昨天</strong> - 輸入 <strong>(Day(-1))</strong>。</li>
</ul>
</td>
</tr>
<tr>
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>尋找相對於工作階段日期的日期範圍。 正值表示未來日期，負值表示過去日期。</td>
<td>
<ul>
<li><strong>過去 30 天</strong> - 輸入 <strong>(DayRange(-30,0))</strong>。</li>
<li><strong>前 30 天和後 30 天</strong> - 輸入 <strong>(DayRange(-30,30))</strong>。</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>尋找指定相對日期之後的所有日期。</td>
<td>
<ul>
<li><strong>從現在起超過 30 天</strong> - 輸入 <strong>(GreaterThanDate(30))</strong>。</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanUtcNow ()</td>
<td>尋找現行時間之後的所有日期/時間輸入指令。</td>
<td>
<ul>
<li><strong>所有未來的日期/時間</strong> - 輸入 <strong>(GreaterThanUtcNow())</strong>。</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>尋找指定相對日期之前的所有日期。</td>
<td>
<ul>
<li><strong>從現在起不到 7 天</strong> - 輸入 <strong>(LessThanDate(7))</strong>。</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanUtcNow ()</td>
<td>尋找現行時間之前的所有日期/時間輸入指令。</td>
<td>
<ul>
<li><strong>所有過去的日期/時間</strong> - 輸入 <strong>(LessThanUtcNow())</strong>。</li>
</ul>
</td>
</tr>
<tr>
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>根據相對於現行月份的月份尋找日期範圍。</td>
<td>
<ul>
<li><strong>前兩個月</strong> - 輸入 <strong>(MonthRange(-2,0))</strong>。</li>
<li><strong>未來三個月</strong> - 輸入 <strong>(MonthRange(0,3))</strong>。</li>
</ul>
</td>
</tr>
<tr>
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>根據相對於現行年份的年份尋找日期範圍。</td>
<td>
<ul>
<li><strong>明年</strong> - 輸入 <strong>(YearRange(0, 1))</strong>。</li>
<li><strong>前一年</strong> - 輸入 <strong>(YearRange(-1,0))</strong>。</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]