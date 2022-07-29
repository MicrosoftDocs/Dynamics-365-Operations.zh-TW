---
title: 廠商過帳設定檔
description: 廠商過帳設定檔控制將廠商交易到總帳的過帳。
author: abruer
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f8ebb67bddf6fa9aae8ba6c6ed290c94bb2e0a047ca6157aa1325f4cf21f148f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450837"
---
# <a name="vendor-posting-profiles"></a>廠商過帳設定檔

[!include [banner](../includes/banner.md)]

廠商過帳設定檔控制將廠商交易到總帳的過帳。

## <a name="vendor-posting-profiles"></a>廠商過帳設定檔

廠商過帳設定檔使您能夠將總帳科目和文件設定指派給所有廠商、一組廠商或單個廠商。 當您建立訂購單、廠商發票和現金付款時，將會使用這些設定。 對於某些交易，您可以選取某個過帳設定檔，它們不同於並優先於本頁面上為交易設定的過帳設定檔。 預設過帳設定檔在 **應付帳款參數** 頁面的 **分類帳和銷售稅** FastTab 上定義。 預設過帳設定檔之後會自動納入在新文件的標題中，其中您可以在需要時將其更改為不同的過帳設定檔。

您還可以將過帳定義與 **交易過帳定義** 頁面上的交易過帳類型連結。 過帳定義控制從廠商交易到總帳的過帳，而不是過帳設定檔。

## <a name="creating-a-posting-profile"></a>建立過帳設定檔
### <a name="setup"></a>**設定**

指定在使用所選過帳設定檔過帳交易時使用的分類帳科目。 選取科目代碼，並盡可能為所選過帳設定檔選取科目或群組。 在過帳流程中，透過在以下優先順序中搜尋最具體的科目代碼、科目或群組和號碼組合來定位每個交易最合適的過帳設定檔。

| **科目代碼** 欄位值 | **科目/群組號碼** 欄位值        | 搜尋優先順序 |
|------------------------------|---------------------------------------------|-----------------|
| **表格**                    | 特定廠商科目                     | 1               |
| **群組**                    | 指派給廠商的廠商群組 | 2               |
| **全部**                      | 空白                                       | 3               |

如果您希望所有廠商交易有相同的過帳設定檔，請在 **科目代碼** 欄位中僅設定一個含 **全部內容** 的過帳設定檔。 指定以下值以設定您的過帳設定檔。

<table>
<thead>
<tr class="header">
<th>欄位</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>過帳設定檔</strong></td>
<td>輸入過帳設定檔的代碼。 例如，您可以建立兩個過帳設定檔來獲取一個用於本國貨幣廠商餘額的科目和另一個用於外幣廠商餘額的科目。 您可以調用一個本國科目和另一個外國科目。</td>
</tr>
<tr class="even">
<td><strong>描述</strong></td>
<td>輸入過帳設定檔的描述。</td>
</tr>
<tr class="odd">
<td><strong>客戶代碼</strong></td>
<td>指定過帳設定檔是否適用於特定供應商、廠商群組或所有廠商：
<ul>
<li><strong>資料表</strong> – 過帳設定檔適用於單個廠商。 選取<strong>科目/群組號碼</strong>欄位中的廠商科目。</li>
<li><strong>組成群組</strong> – 過帳設定檔適用於廠商群組。 選取<strong>科目/群組號碼</strong>欄位中的廠商群組。</li>
<li><strong>全部</strong> – 過帳設定檔適用於所有供應商。 將<strong>科目/群組號碼</strong>欄位留白。</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>科目/群組號碼</strong></td>
<td>如果<strong>資料表</strong>已在<strong>科目代碼</strong>欄位中選取，則選取與過帳設定檔有關的廠商帳號。 如果已選取<strong>群組</strong>，則選取一個廠商群組。 如果已選取<strong>全部</strong>，請將此欄位留白。</td>
</tr>
<tr class="odd">
<td><strong>彙總科目</strong></td>
<td>選取將用作與過帳設定檔相關廠商的匯總科目的分類帳科目。 系統會標記此主科目的<strong>不允許手動輸入</strong>參數。 如果您隨後從過帳設定檔中移除此科目，請驗證<strong>主科目</strong>頁面上的<strong>不允許手動輸入</strong>設定。 
<p><strong>注意事項：</strong>如果<strong>使用過帳定義</strong>選項已在<strong>總帳參數</strong>頁面上選取，則使用廠商發票的交易過帳定義而不是匯總科目。</p>
</td>
</tr>
<tr class="even">
<td><strong>結算科目</strong></td>
<td>選取用於現金流量預測的流動性分類帳科目。 此欄位僅在現金流量預測啟用時可用。</td>
</tr>
<tr class="odd">
<td><strong>銷售稅預付款</strong></td>
<td>選取預先收到的銷售稅付款科目。
<p><strong>注意事項</strong>：在付款標記為預付款時使用的過帳設定檔已在<strong>過帳</strong>設定檔中選取，包括在<strong>應付帳款參數</strong>頁面上<strong>分類帳和銷售稅</strong>區域的<strong>預付款日記帳憑證</strong>中欄位。</p>
</td>
</tr>
<tr class="even">
<td><strong>到貨</strong></td>
<td>選取已過帳有關未核准廠商發票資訊的分類帳科目。 將該資訊輸入到發票登記日記帳中。 例如，當發票登記收到廠商發票時，使用者會輸入其非常基本的資訊。 當過帳發票登記時，交易會過帳到在此處輸入的科目和<strong>沖銷科目</strong>欄位。 當核准發票後，借方從到貨科目轉移到廠商匯總科目。</td>
</tr>
<tr class="odd">
<td><strong>沖銷科目名稱</strong></td>
<td>選取用於沖銷未核准廠商發票的分類帳科目，這些廠商發票會使用發票登記來更新。 沖銷科目充當過帳到到貨科目之交易的沖銷科目。 因此，該科目包含尚未核准的廠商採購。</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**資料表限制**

對於具有選定過帳的交易，指定是否自動結算交易、計算利息和發出收帳委託書。 您還可以選取在關閉具有所選過帳設定檔的交易時使用的科目。

指定以下的值來設定您的過帳設定檔

| 欄位          | 描述                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **結算** | 選取此選項以啟用具有此過帳設定檔的交易自動結算。 如果清除此選項，您必須使用 **結算未結交易** 頁面來手動結算交易。 |
| **取消**     | 如果您想要能夠取消有此過帳設定檔的交易，請選取此選項。                                                                                                               |
| **關閉**      | 在關閉具有此過帳設定檔的交易時，更改至選定的過帳設定檔。 某筆交易在全額結清後視為已結算。                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]