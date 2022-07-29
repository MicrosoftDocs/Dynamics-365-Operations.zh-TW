---
title: 會計分配和普通發票的日記帳分錄
description: 會計分配用於定義如何對帳金額，例如如何在普通發票上對帳收入、稅金或費用。 將普通發票記入日記帳時，必須對帳的每一筆金額都將具有一個或多個會計分配。
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da1d1b41c4da1fafcf20246022c4020b60152917f5df85f8e003e23aaef9433c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450297"
---
# <a name="accounting-distributions-and-subledger-entries-for-free-text-invoices"></a>會計分配和普通發票的子分類帳分錄

[!include [banner](../includes/banner.md)]

會計分配用於定義如何對帳金額，例如如何在普通發票上對帳收入、稅金或費用。 將普通發票記入日記帳時，必須對帳的每一筆金額都將具有一個或多個會計分配。

## <a name="accounting-distributions"></a>會計分配

您可以使用普通發票頁面中的以下按鈕，查看和變更普通發票上每個金額的會計分配。

-   **分配金額** – 查看和變更個別行以及任何下層行的會計分配，例如稅金或費用。 您還可以直接從銷售稅交易頁面或費用交易頁面查看和變更下層行的會計分配。
    -   變更普通發票標題金額，例如費用或貨幣進位金額。
    -   變更普通發票明細金額。
-   **查看分配** – 查看文件上所有行的會計分配。 您不能從此檢視表變更會計分配。
    -   查看標題和行金額。

## <a name="distributing-amounts"></a>分配金額
當您輸入普通發票時，每筆金額將按以下方式分配。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>金額類型</th>
<th>顯示主科目的位置</th>
<th>確定要顯示預設財務維度的優先順序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>普通發票明細</td>
<td>普通發票明細上的分類帳科目。</td>
<td><ol>
<li>如果主科目是分配科目，則使用分配科目定義中的預設值。</li>
<li>如果主科目不是分配科目，則使用普通發票明細上的財務維度預設範本。</li>
<li>在普通發票明細上使用預設財務維度值。</li>
<li>使用會計科目表頁面中分類帳科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="even">
<td>固定資產編號和價值模型組合的普通發票明細
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>附註</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>普通發票明細上的主科目將是固定資產處置科目。</td>
</tr>
</tbody>
</table>
</div></td>
<td>普通發票明細上的分類帳科目。</td>
<td><ol>
<li>在普通發票明細上使用預設財務維度值。</li>
<li>使用會計科目表頁面中分類帳科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="odd">
<td>普通發票折扣金額</td>
<td>現金折扣頁面中的客戶折扣主科目欄位。</td>
<td><ol>
<li>如果主科目是分配科目，則使用分配科目定義中的預設值。</li>
<li>如果主科目不是分配科目，則使用普通發票明細上的財務維度預設範本。</li>
<li>在普通發票明細上使用預設財務維度值。</li>
<li>使用會計科目表頁面中分類帳科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="even">
<td>普通發票銷售稅金額</td>
<td>分類帳過帳群組頁面的應納銷售稅欄位。</td>
<td><ol>
<li>使用在普通發票明細金額或費用明細金額的分配中定義的財務維度。</li>
<li>在普通發票明細上使用預設財務維度值。</li>
<li>使用會計科目表頁面中分類帳科目的預設財務維度值。</li>
</ol></td>
</tr>
<tr class="odd">
<td>普通發票費用明細金額</td>
<td>費用代碼頁中的貸方科目欄位。</td>
<td><ol>
<li>如果主科目是分配科目，則使用分配科目定義中的預設值。</li>
<li>如果主科目不是分配科目，則使用普通發票明細上的財務維度預設範本。</li>
<li>在普通發票明細上使用預設財務維度值。</li>
<li>使用會計科目表頁面中分類帳科目的預設財務維度值。</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>分配稅款
只有在計算完稅款後，才能建立稅款的會計分配。 若要計算銷售稅，您必須在普通發票表單中完成以下工作之一：
-   檢視銷售稅。
-   檢視發票總額。
-   檢視現金流。
-   檢視整個普通發票的會計分配。
-   檢視子分類帳日記帳。

## <a name="subledger-journals-for-free-text-invoices"></a>普通發票的子分類帳日記帳
在過帳普通發票之前，您可以查看發票的完整會計分錄，其中包括借方和貸方，以驗證發票是否過帳到正確的科目。 這種完整會計分錄的檢視表稱為子分類帳日記帳。 如果子分類帳日記帳分錄不正確，在預覽後，記帳普通發票前，您無法變更子分類日記帳分錄。 反之，您必須變更會計分配或過帳日記帳。 會計分配用於定義會計分錄、借方或貸方的一側。 沖銷子分類帳日記帳科目分錄是從過帳設定檔建立的，例如從客戶帳戶或稅金。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]