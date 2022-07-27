---
title: 產品設定模型概觀
description: 本文定義與產品設定模型相關的術語和概念。 產品設定模型讓您可以建構一般產品結構，該結構可用於為單一產品設定多個產品變型。
author: t-benebo
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage, PCModalWaitDialog, PCTemplateConfigurationManager, PCConfigurationUIGrouping
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "4031"
- intro-internal
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fddad1fffd61ef0cf78977721bdf2da51aa4c682
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449724"
---
# <a name="product-configuration-models-overview"></a>產品設定模型概觀

[!include [banner](../includes/banner.md)]

本文定義與產品設定模型相關的術語和概念。 產品設定模型讓您可以建構一般產品結構，該結構可用於為單一產品設定多個產品變型。

系統會建立產品設定模型以表示一般產品結構。 設定產品設定模型後，您可以設定具有唯一物料清單 (BOM) 和唯一路線的獨特產品變型。 產品設定模型使用聲明性限制式和命令式計算來處理不同產品變型之間的關係和限制。 您可以在銷售訂單、銷售報價單、採購訂單和生產訂單上設定項目。 下表描述以資料表條件約束為基礎的術語和概念。
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>元件</td>
<td>元件是產品設定模型的主要建構元素。 元件以樹狀結構顯示在<strong>條件式產品設定模型詳細資料</strong>頁面上。 元件可以包含以下元素：
<ul>
<li>屬性</li>
<li>限制</li>
<li>計算</li>
<li>子元件</li>
<li>使用者需求</li>
<li>BOM 行</li>
<li>路線作業</li>
</ul></td>
</tr>
<tr class="even">
<td>屬性</td>
<td>屬性描述產品設定模型的所有特性。 您可以使用屬性來指定當設定不同產品時可以選擇的特性。 屬性用於限制式和條件。 建立屬性並將其新增至產品設定模型時，會參考相關的屬性類型。 可以為屬性設定預設值。 設定產品設定模型時，會在設定使用者介面 (UI) 中使用預設值。 您可以指定屬性是必要、唯讀或隱藏的。
<ul>
<li><strong>必要</strong> – 設定產品時必須為屬性設定值。</li>
<li><strong>唯讀</strong> – 屬性值會在設定工作階段期間顯示，但無法變更。</li>
<li><strong>隱藏</strong> – 屬性值包含在限制式和條件中，但在設定工作階段期間不會顯示。</li>
</ul>
您還可以為屬性指定條件。 如果滿足該條件，則必須為必填屬性輸入值。 條件是一種運算式，必須符合該運算式，屬性、BOM 行和路線作業才能包含在產品設定模型中。 條件中參考的任何屬性都會成為必要的。 建議您在<strong>屬性</strong>索引標籤中選取屬性成為必要屬性。這可以更容易識別必要屬性。 屬性值是重複使用設定的重要部分。 系統會使用屬性值來判定符合使用者在設定工作階段期間所做選擇的設定是否存在。</td>
</tr>
<tr class="odd">
<td>屬性類型</td>
<td>屬性類型為產品設定模型中使用的屬性指定一組資料類型。 使用以下屬性類型：
<ul>
<li><strong>整數</strong>：有或沒有範圍</li>
<li><strong>十進位</strong></li>
<li><strong>文字</strong>：有或沒有固定清單</li>
<li><strong>布林值</strong></li>
</ul>
如果屬性類型是<strong>布林值</strong>、具有範圍的<strong>整數</strong>，或具有固定清單的<strong>文字</strong>，則當設定產品設定模型時，該組值可供使用。 <strong>注意：</strong>產品設定求解工具僅識別以下屬性類型：<strong>布林值</strong>、具有固定清單的<strong>文字</strong>，以及具有範圍的<strong>整數</strong>。 因此，只有這些屬性類型可以用於運算式限制式和條件。</td>
</tr>
<tr class="even">
<td>限制</td>
<td>限制式會描述產品模型設定的限制。 限制式用於保證當設定產品時，只會選取有效的值。 限制式可以是運算式限制式或資料表限制式：
<ul>
<li>運算式限制式只能用於它們所繫結的元件。 元件的運算式限制式可以參考元件其子元件的屬性。 產品設定求解工具用於求解限制式，當您撰寫限制式必須使用求解工具語法。 如需詳細資訊，請參閱有關運算式限制式與資料表限制式的主題連結。</li>
<li>必須先定義資料表限制式，才能將限制式套用到產品設定模型中的元件。 資料表限制式可以是使用者定義的，也可以是系統定義的。 使用者定義的資料表限制式是一種矩陣，可用於描述一組由屬性類型定義的屬性值組合。 例如，如果生產揚聲器，則使用者定義的資料表限制式矩陣會有資料欄代表揚聲器飾面和格柵。</li>
</ul>
<strong>範例</strong> 揚聲器有四種飾面可供選擇：黑色、橡木、玫瑰木和白色。 揚聲器可以有以下三種前格柵中的一個：黑色、金屬或白色。 黑色飾面適用於所有格柵，但其他飾面僅限於特定格柵。 下表顯示出現在<strong>編輯資料表限制式</strong>頁面上<strong>允許的組合</strong>索引標籤上的資訊範例。
<table>
<thead>
<tr class="header">
<th>外殼飾面</th>
<th>前格柵</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>黑色</td>
<td>黑色</td>
</tr>
<tr class="even">
<td>黑色</td>
<td>金屬</td>
</tr>
<tr class="odd">
<td>黑色</td>
<td>白色</td>
</tr>
<tr class="even">
<td>橡木</td>
<td>黑色</td>
</tr>
<tr class="odd">
<td>紅木</td>
<td>白色</td>
</tr>
<tr class="even">
<td>白色</td>
<td>黑色</td>
</tr>
<tr class="odd">
<td>白色</td>
<td>白色</td>
</tr>
</tbody>
</table>
系統定義的資料表限制式可表示屬性類型和Supply Chain Management資料表中欄位之間的對應。 系統定義的資料表限制式會將屬性類型動態連結至欄位。 該連結可讓產品設定模型中的屬性反映Supply Chain Management資料表中欄位的資料。</td>
</tr>
<tr class="odd">
<td>計算</td>
<td>計算是對限制式的補充。 您可以使用計算對<strong>十進位</strong>和<strong>整數</strong>類型的屬性執行算術作業，或執行涉及具固定清單和<strong>布林值</strong>類型的<strong>文字</strong>屬性的邏輯作業。 計算有一個目標屬性，此屬性將保留計算運算式的結果。 計算運算式是使用運算式編輯器建構的。</td>
</tr>
<tr class="even">
<td>子元件</td>
<td>子元件會反映產品設定模型的樹狀結構。 您可以使用子元件來建構產品設定模型的結構。 子元件參照現有元件。 因此，子元件鼓勵在多個產品設定模型中重複使用元件。 在子元件的 <strong>BOM 行詳細資料</strong>頁面上，您可以為子元件選擇不同的值。 或者，您可以選擇當設定產品設定模型時要選擇其值的屬性。 若要包含產品作為元件或子元件，當您建立產品時，必須在<strong>建立產品</strong>頁面上指定下列資訊：
<ul>
<li>在<strong>產品類型</strong>欄位中，選擇<strong>品項</strong>。</li>
<li>在<strong>產品子類型</strong>欄位中，選擇<strong>基準產品</strong>。</li>
<li>在<strong>設定技術</strong>欄位中，選擇<strong>限制式設定</strong>.</li>
</ul>
您可以在<strong>已發行產品詳細資料</strong>頁面的<strong>一般</strong>頁面上，檢視是否可使用已發行的產品作為元件或子元件。 如果在<strong>設定技術</strong>欄位中選擇<strong>限制式設定</strong>，則可使用產品作為元件或子元件。 您可以隱藏子元件，使其在設定工作階段期間不會對使用者顯示。 此外也會隱藏與子元件相關的屬性、子元件和使用者需求。</td>
</tr>
<tr class="odd">
<td>使用者需求</td>
<td>使用者需求表示使用者需求與特定元件和屬性之間的抽象。 您無法將使用者需求對應至品項。 例如，客戶正在購買家庭影院系統。 銷售代表可能會詢問客戶打算安裝此系統的房間大小，以決定需要多少瓦特。 在此範例中，房間大小可以是幫助決定特定元件其適當屬性值的使用者需求。 您可以隱藏使用者需求，使其在設定工作階段期間不會對使用者顯示。 此外也會隱藏與使用者需求相關的屬性、子元件和使用者需求。 您可以編寫一個條件來控制是否會隱藏使用者需求。 您必須使用最佳化建模語言 (OML) 語法撰寫條件。</td>
</tr>
<tr class="even">
<td>BOM 行</td>
<td>BOM 行代表產品設定模型中元件的各個材料。 在 <strong>BOM 行詳細資料</strong>頁面上，所有的品項皆可供選擇。 當設定產品設定模型時，可對 BOM 行新增一個條件，讓為不同產品變型選擇的 BOM 行可視使用者的選擇而改變。 條件是一種運算式，必須符合該運算式，屬性、BOM 行和路線作業才能包含在產品設定模型中。 在 <strong>BOM 行詳細資料</strong>頁面上，您可以選擇不同的值。 或者，您可以對應至當設定產品設定模型時選取其值的屬性。</td>
</tr>
<tr class="odd">
<td>路線作業</td>
<td>在<strong>路線作業詳細資料</strong>頁面上，您可以選擇不同的值。 或者，您可以對應至當設定產品設定模型時選取其值的屬性。 條件的寫法類似於運算式限制式。 條件是一種運算式，必須符合該運算式，屬性、BOM 行和路線作業才能包含在產品設定模型中。</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]