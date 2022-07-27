---
title: 產品設定模型中的運算式限制式和資料表限制式
description: 本主題將說明如何使用運算式限制式和資料表限制式。 限制式可控制您在設定銷售訂單、銷售報價單、訂購單或生產訂單產品時可選取的屬性值。 您可以使用運算式限制式或資料表限制式，視您偏好的限制式建立方式而定。
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8775a9225313c0f5a132dbccbe583470fe23beab
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448338"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>產品設定模型中的運算式限制式和資料表限制式

[!include [banner](../includes/banner.md)]

本主題將說明如何使用運算式限制式和資料表限制式。 限制式可控制您在設定銷售訂單、銷售報價單、訂購單或生產訂單產品時可選取的屬性值。 您可以使用運算式限制式或資料表限制式，視您偏好的限制式建立方式而定。 

限制式用於控制您在設定銷售訂單、銷售報價單、訂購單或生產訂單產品時可選取的屬性值。 您可以使用運算式限制式或資料表限制式，視您偏好的限制式建立方式而定。

## <a name="what-are-expression-constraints"></a>什麼是運算式限制式？
運算式限制式是使用算數、布林值運算子和函數的運算式。 運算式限制式只能用於產品設定模型中的特定元件， 無法重複使用或與其他元件共用。 不過元件的運算式限制式可以參照其子元件的屬性。

## <a name="what-are-table-constraints"></a>什麼是資料表限制式？
資料表限制式會列出設定產品時允許用於屬性的值組合。 資料表限制式定義可以通用。 為產品設定模型中的元件建立資料表限制式時，可選取資料表限制式定義。 若要建立允許的組合，請將特定類型的屬性新增至元件中。 每個屬性類型都有一個特定值。

### <a name="example-of-a-table-constraint"></a>資料表限制式範例

此範例說明如何將喇叭設定限制為特定的箱體飾面和正面。 第一個資料表顯示通常可用於設定的箱體飾面和正面。 這些值定義為 **箱體飾面** 和 **前格柵** 屬性類型。

| 屬性類型 | 值                      |
|----------------|-----------------------------|
| 箱體飾面 | 黑色、橡木、紅木、白色 |
| 前格柵    | 黑色，金屬，白色         |

下表顯示由 **顏色和飾面** 資料表限制式定義的組合。 使用此資料表限制式即可設定具有橡木飾面和黑色格柵、紅木飾面和白色格柵等的喇叭。

| 飾面         | 格柵                       |
|----------------|-----------------------------|
| 橡木            | 黑色                       |
| 紅木       | 白色                       |
| 白色          | 黑色                       |
| 白色          | 白色                       |
| 黑色          | 黑色                       |
| 黑色          | 金屬                       | 

您可以建立由系統定義和使用者定義的資料表限制式。 若需更多相關資訊，請參閱[系統定義和使用者定義的資料表限制式](system-defined-user-defined-table-constraints.md)。

## <a name="what-syntax-should-be-used-to-write-constraints"></a>應該使用什麼語法來編寫限制式？
您必須使用最佳化模組化語言 (OML) 語法編寫限制式。 系統會採用 Microsoft Solver Foundation 限制式求解器對限制式求解。

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>我應該使用資料表限制式還是運算式限制式？
您可以使用運算式限制式或資料表限制式，視您偏好的限制式建立方式而定。 資料表限制式會建立為矩陣，運算式限制式則是建立為獨立陳述式。 無論使用哪種限制式都能設定產品。 以下範例會顯示這兩種方法的不同之處。  

使用以下限制式設定來設定產品時，可採用以下組合：

-   產品顏色為黑色，尺寸為 30 或 50
-   產品顏色為紅色，尺寸為 20

### <a name="table-constraint-setup"></a>資料表限制式設定

| 色彩 | 大小 |
|-------|------|
| 黑色 | 30   |
| 黑色 | 50   |
| 紅色   | 20   |

### <a name="expression-constraint-setup"></a>運算式限制式設定

(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>編寫運算式限制式時應該使用運算子還是中置標記法？
您可以透過可用的前置運算子或中置標記法來編寫運算式限制式。 若為 **Min**、**Max** 和 **Abs** 運算子，則無法使用中置標記法。 這些運算子在大多數程式設計語言中屬於標準運算子。

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>編寫運算式限制式時能使用哪些運算子和中置標記法？
下表列出為產品設定模型中的元件編寫運算式限制式時可使用的運算子和中置標記法。 第一個資料表中的範例顯示如何使用中置標記法或運算子編寫運算式。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>運算子</th>
<th>描述</th>
<th>語法</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implies</td>
<td>如果第一個條件為 false、第二個條件為 true 或兩者皆成立，則為 true。</td>
<td>Implies[a, b], infix: a -: b</td>
<td><ul>
<li><strong>運算子：</strong>Implies[x != 0, y &gt;= 0]</li>
<li><strong>中置標記法：</strong>x != 0 -: y &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>和</td>
<td>只有當所有條件都為 true 時，才為 true。 如果條件數為 0 (零)，則產生 <strong>True</strong>。</td>
<td>And[args], infix: a &amp; b &amp; ... &amp; z</td>
<td><ul>
<li><strong>運算子：</strong>And[x == 2, y &lt;= 2]</li>
<li><strong>中置標記法：</strong>x == 2 &amp; y &lt;= 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>或</td>
<td>如果任何條件為 true，則為 true。 如果條件數為 0 (零)，則產生 <strong>False</strong>。</td>
<td>Or[args], infix: a | b | ... | z</td>
<td><ul>
<li><strong>運算子：</strong>Or[x == 2, y &lt;= 2]</li>
<li><strong>中置標記法：</strong>x == 2 | y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Plus</td>
<td>這會將運算式條件加總。 如果條件數為 0 (零)，則產生 <strong>0</strong>。</td>
<td>Plus[args], infix: a + b + ... + z</td>
<td><ul>
<li><strong>運算子：</strong>Plus[x, y, 2] == z</li>
<li><strong>中置標記法：</strong>x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Minus</td>
<td>這會否定運算式引數。 運算式必須只有一個條件。</td>
<td>Minus[expr], infix: -expr</td>
<td><ul>
<li><strong>運算子：</strong>Minus[x] == y</li>
<li><strong>中置標記法：</strong>-x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>Abs</td>
<td>這取運算式條件的絕對值。 運算式必須只有一個條件。</td>
<td>Abs[expr]</td>
<td><strong>運算子：</strong>Abs[x]</td>
</tr>
<tr class="odd">
<td>Times</td>
<td>這是運算式條件的乘積。 如果條件數為 0 (零)，則產生 <strong>1</strong>。</td>
<td>Times[args], infix: a * b * ... * z</td>
<td><ul>
<li><strong>運算子：</strong>Times[x, y, 2] == z</li>
<li><strong>中置標記法：</strong>x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Power</td>
<td>這會以指數呈現運算式條件。 該運算子會從右到左套用乘冪。 (換言之，此為右向關聯。) 因此，<strong>Power[a, b, c]</strong> 等於 <strong>Power[a, Power[b, c]]</strong>。 只有當指數為正常數時才能使用 <strong>Power</strong>。</td>
<td>Power[args], infix: a ^ b ^ ... ^ z</td>
<td><ul>
<li><strong>運算子：</strong>Power[x, 2] == y</li>
<li><strong>中置標記法：</strong>x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>Max</td>
<td>這會產生最大條件。 如果條件數為 0 (零)，則產生 <strong>Infinity</strong>。</td>
<td>Max[args]</td>
<td><strong>運算子：</strong>Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Min</td>
<td>這會產生最小條件。 如果條件數為 0 (零)，則產生 <strong>Infinity</strong>。</td>
<td>Min[args]</td>
<td><strong>運算子：</strong>Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>Not</td>
<td>這會產生運算式條件的反向邏輯。 運算式必須只有一個條件。</td>
<td>Not[expr], infix: !expr</td>
<td><ul>
<li><strong>運算子：</strong>Not[x] &amp; Not[y == 3]</li>
<li><strong>中置標記法：</strong>!x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

下表中的範例顯示如何編寫中置標記法。


|  中置標記法   |                                          描述                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     x + y + z     |                                           加法                                            |
|    x \* y \* z    |                                        乘法                                         |
|       x - y       | 二進位減法的翻譯與二進位加法相同，其中第二項遭否定。 |
|     x ^ y ^ z     |                          具有右向關聯的指數                          |
|        !x         |                                          布林值 Not 函數                                          |
|      x -: y       |                                      布林值 implication 函數                                      |
|         x         |                                               y                                               |
|     x & y & z     |                                          布林值 And 函數                                          |
|    x == y == z    |                                           等式                                            |
|    x != y != z    |                                           相異                                            |
|  x &lt; y &lt; z  |                                           Less than                                           |
|  x &gt; y &gt; z  |                                         Greater than                                          |
| x &lt;= y &lt;= z |                                     小於或等於                                     |
| x &gt;= y &gt;= z |                                   大於或等於                                    |
|        (x)        |                           括號覆寫預設優先順序。                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>為什麼我的運算式限制式未正確驗證？
您不能將保留關鍵字做為產品設定模型的屬性、元件或子元件求解器名稱。 以下是無法使用的保留關鍵字清單：

-   Ceiling
-   Element
-   Equal
-   Floor
-   If
-   Less
-   Greater
-   Implies
-   記錄
-   Max
-   Min
-   Minus
-   Plus
-   Power
-   Times
-   Slot
-   Model
-   決定
-   Goal


## <a name="additional-resources"></a>其他資源

[建立運算式限制式](tasks/add-expression-constraint-product-configuration-model.md)

[對產品設定模型新增計算](tasks/add-calculation-product-configuration-model.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]