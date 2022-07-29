---
title: 會計分配和廠商發票的日記帳分錄
description: 會計分配用於定義如何對帳金額，例如如何在廠商發票上對帳費用、稅金或費用。 將廠商發票記入日記帳時，必須對帳的每一筆金額都將具有一個或多個會計分配。
author: sunfzam
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f10ddf113f59da4800a97a48300ab1310bfb42dd
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451644"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>會計分配和廠商發票的日記帳分錄

[!include [banner](../includes/banner.md)]

會計分配用於定義如何對帳金額，例如如何在廠商發票上對帳費用、稅金或費用。 將廠商發票記入日記帳時，必須對帳的每一筆金額都將具有一個或多個會計分配。 

## <a name="accounting-distributions"></a>會計分配 

您可以使用廠商發票頁面中的以下按鈕，查看和修改廠商發票上每個金額的會計分配。
-   **分配金額** – 查看和修改個別行以及任何下層行的會計分配，例如稅金或費用。 您還可以直接從 **銷售稅交易** 頁面或 **費用交易** 頁面查看和修改下層行的會計分配。
    -   修改廠商發票標題金額，例如費用或貨幣進位金額。
    -   修改廠商發票明細金額
-   **查看分配** – 查看單據上所有行的會計分配。 您不能從此檢視表修改會計分配。
    -   查看標題和行金額。

如果廠商發票參考訂購單，您可以拆分和修改包含無庫存品項行的會計分配。 如果廠商發票明細不參考訂購單行，您可以刪除會計分配。 但不能拆分或刪除費用、稅金和行折扣的行。 您可以修改分類帳科目，但不能變更金額或百分比。
> [!NOTE]                                                                                                                                 
> 如果上層行包含無庫存的品項且會計分配被拆分，則將自動拆分下層行以與上層行的財務維度相符。 不能進一步拆分或刪除下層行的會計分配，但根據下層行的設定，您可能可以修改下層行會計分配的分類帳。

## <a name="distributing-amounts"></a>分配金額
當您輸入廠商發票時，每筆金額將按以下方式分配。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>廠商發票明細類型</th>
<th>確定主科目顯示位置的優先順序</th>
<th>確定要顯示預設財務維度的優先順序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>庫存產品</td>
<td><ol>
<li>訂購單行的會計分配。</li>
<li>當在<strong>過帳</strong>頁面選擇產品採購支出時的<strong>主科目</strong>欄位。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>在廠商發票上使用預設財務維度值。</li>
</ol></td>
</tr>
<tr class="even">
<td>無庫存的採購類別或產品</td>
<td><ol>
<li>如果廠商發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>當在<strong>過帳</strong>頁面選擇支出中採購支出時的<strong>主科目</strong>欄位。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>如果主科目是分配科目，則使用分配科目定義中的預設值。</li>
<li>在廠商發票上使用預設財務維度值。</li>
<li>使用廠商發票明細的財務維度值。</li>
<li>使用<strong>會計科目表</strong>頁面中主科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="odd">
<td>固定資產</td>
<td><ol>
<li>如果廠商發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>如果在<strong>廠商發票</strong>頁面的<strong>交易類型</strong>欄位中選擇<strong>購置</strong>，則在<strong>固定資產過帳設定檔</strong>頁面中選擇<strong>購置</strong>時使用<strong>主科目</strong>欄位。</li>
<li>如果在<strong>交易類型</strong>欄位中選擇<strong>購置調整</strong>，則在<strong>固定資產過帳設定檔</strong>頁面中選擇<strong>購置調整</strong>時使用<strong>主科目</strong>欄位。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，則使用訂購單行的會計分配。</li>
<li>使用廠商發票明細的財務維度值。</li>
<li>使用<strong>會計科目表</strong>頁面中主科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="even">
<td>在廠商發票明細上定義的專案</td>
<td><ol>
<li>如果發票明細參考訂購單行，則使用訂購單行的會計分配。</li>
<li>如果在<strong>專案群組</strong>頁面的<strong>過帳成本 - 品項</strong>欄位中選擇了<strong>餘額</strong>，則在<strong>分類帳過帳設定</strong>頁面中選擇<strong>成本</strong>時使用<strong>主科目</strong>欄位。</li>
<li>如果在<strong>專案群組</strong>頁面的<strong>過帳成本 - 品項</strong>欄位中選擇了<strong>損益</strong>，則在<strong>分類帳過帳設定</strong>頁面中選擇<strong>成本 - 品項</strong>時使用<strong>主科目</strong>欄位。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
</ol></td>
</tr>
<tr class="odd">
<td>明細折扣</td>
<td><ol>
<li>如果發票明細參考訂購單行，則使用訂購單行的會計分配。</li>
<li>在過<strong>帳頁</strong>頁面中選擇<strong>折扣</strong>時使用<strong>主科目</strong>欄位。</li>
<li>如果未在過帳設定檔上定義折扣主科目，則使用訂購單行上總價的會計分配。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的科目分配。</li>
<li>將會計分配中的財務維度用於廠商發票明細上的總價。</li>
<li>使用廠商發票明細的財務維度值。</li>
<li>使用<strong>會計科目表</strong>頁面中主科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="even">
<td>在訂購單行的<strong>價格和折扣</strong>索引標籤上輸入的採購費用</td>
<td><ol>
<li>如果發票明細參考訂購單行，則使用訂購單行的會計分配。</li>
<li>訂購單行總價的會計分配。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>將會計分配中的財務維度用於廠商發票明細上的總價。</li>
</ol></td>
</tr>
<tr class="odd">
<td>明細費用</td>
<td><ol>
<li>如果發票明細參考訂購單行，則使用訂購單行的會計分配。</li>
<li>如果在<strong>費用代碼</strong>頁面的<strong>借方類型</strong>欄位中選擇了<strong>分類帳科目</strong>，則使用<strong>費用代碼</strong>頁面的<strong>借方科目</strong>欄位。</li>
<li>如果在<strong>費用代碼</strong>頁面的<strong>借方類型</strong>欄位中選擇<strong>品項</strong>，則使用採購訂單行的總價的會計分配。</li>
<li>如果在<strong>費用代碼</strong>頁面的<strong>借方類型</strong>欄位中選擇了<strong>客戶/廠商</strong>，則使用<strong>費用代碼</strong>頁面的<strong>貸方科目</strong>欄位。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>將會計分配中的財務維度用於廠商發票明細上的總價。</li>
<li>使用廠商發票明細的財務維度值。</li>
<li>使用<strong>會計科目表</strong>頁面中主科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="even">
<td>滿足以下條件的稅金：
<ul>
<li>在<strong>總帳參數</strong>頁面選擇<strong>套用美國稅收規則</strong>選項。</li>
</ul></td>
<td><ol>
<li>如果發票明細參考訂購單行，則使用訂購單行的會計分配。</li>
<li>總價或費用的會計分配。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>將會計分配中的財務維度用於廠商發票明細上的總價。</li>
<li>使用廠商發票明細的財務維度值。</li>
</ol></td>
</tr>
<tr class="odd">
<td>滿足以下條件的稅金：
<ul>
<li>在<strong>總帳參數</strong>頁面清除<strong>套用美國稅收規則</strong>選項。</li>
<li>在<strong>銷售稅群組</strong>頁面清除銷售稅群組的<strong>使用稅</strong>欄位。</li>
</ul></td>
<td><ol>
<li>如果稅額可以回收，則使用<strong>分類帳過帳群組</strong>頁面的<strong>應收銷售稅</strong>欄位。</li>
<li>如果稅額無法回收，則使用該費用的總價或會計分配。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>用於廠商發票明細的費用使用來自總價或會計分配的財務維度。</li>
<li>使用廠商發票明細的財務維度值。</li>
<li>使用<strong>會計科目表</strong>頁面中主科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="even">
<td>滿足以下條件的稅金：
<ul>
<li>在<strong>總帳參數頁面</strong>清除「套用美國稅收規則」選項。</li>
<li>在<strong>銷售稅群組</strong>頁面選擇銷售稅群組的<strong>使用稅</strong>欄位。</li>
</ul></td>
<td><ol>
<li>如果稅額可以回收，則使用<strong>分類帳過帳群組</strong>頁面的<strong>應收銷售稅</strong>欄位。</li>
<li>如果稅額無法回收，則使用<strong>分類帳過帳群組</strong>頁面的<strong>使用稅費用</strong>欄位。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>用於廠商發票明細的費用使用來自總價或會計分配的財務維度。</li>
<li>使用廠商發票明細的財務維度值。</li>
<li>使用<strong>會計科目表</strong>頁面中主科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="odd">
<td>標題費用</td>
<td><ol>
<li>如果在<strong>費用代碼</strong>頁面的<strong>借方類型</strong>欄位中選擇了<strong>分類帳</strong>科目，則使用<strong>費用代碼</strong>頁面的<strong>借方科目</strong>欄位。</li>
<li>如果在<strong>費用代碼</strong>頁面的<strong>借方類型</strong>欄位中選擇了<strong>客戶/廠商</strong>，則使用<strong>費用代碼</strong>頁面的<strong>貸方科目</strong>欄位。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>如果主科目是分配科目，則使用分配科目定義中的預設值。</li>
<li>使用廠商發票標題的財務維度預設範本值。</li>
<li>使用廠商發票明細的財務維度值。</li>
<li>使用<strong>會計科目表</strong>頁面中主科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="even">
<td>標題折扣</td>
<td><ol>
<li><strong>自動交易科目</strong>頁面中<strong>廠商發票折扣過帳類型</strong>的<strong>主科目</strong>欄位。</li>
</ol></td>
<td><ol>
<li>如果發票明細參考訂購單行，請使用訂購單行的會計分配。</li>
<li>將會計分配中的財務維度用於廠商發票明細上的總價。</li>
<li>使用廠商發票明細的財務維度值。</li>
<li>使用<strong>會計科目表</strong>頁面中主科目的預設財務維度值。</li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="distributing-taxes"></a>分配稅

只有在計算完稅款後，才能建立稅款的會計分配。 若要計算銷售稅，您必須在 **廠商發票** 頁面中完成以下工作之一：
-   檢視發票總額。
-   檢視銷售稅。
-   檢視子分類帳日記帳。
-   檢視完整廠商發票的會計分配。
-   擱置廠商發票。
-   過帳廠商發票。

## <a name="subledger-journals-for-vendor-invoices"></a>廠商發票的子分類帳日記帳
在過帳廠商發票之前，您可以查看發票的完整會計分錄，其中包括借方和貸方，以驗證發票是否過帳到正確的科目。 這種完整會計分錄的檢視表稱為子分類帳日記帳。 

如果子分類帳日記帳分錄不正確，在預覽後，記帳廠商發票前，您無法修改子分類日記帳分錄。 反之，您必須修改會計分配或過帳日記帳。 會計分配用於定義會計分錄、借方或貸方的一側。 沖銷子分類帳日記帳科目分錄是使用過帳設定檔建立的，例如從廠商帳戶或稅金。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
