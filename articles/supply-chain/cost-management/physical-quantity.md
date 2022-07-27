---
title: 庫存物件值
description: 本文提供有關如何計算庫存物件值的資訊。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6564df5bd9c768f647138714875c60ddd6df3c85
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448158"
---
# <a name="inventory-object-values"></a>庫存物件值

[!include [banner](../includes/banner.md)]

本文提供有關如何計算庫存物件值的資訊。 

有一個名為 **實體數量** 的新功能，可讓您查看特定庫存物件的值。 

成本物件代表執行庫存會計的實體級別。 如需成本物件的詳細資訊，請參閱[成本物件](cost-object.md)。 

若要查看特定庫存物件的值，請按一下 **成本物件** 頁面上的 **實體數量**。 以下是計算庫存物件值的方式： 

庫存物件.值 = 成本物件.平均單位成本 × 庫存物件.數量 

以下範例顯示如何計算庫存物件與成本物件的值。 在品項 A 上登記了兩個產品收據事件：

-   產品收據 1：數量 = 100 件，金額 = $1,000.00，站點 = 1，倉庫 =11，批號 = B1
-   產品收據 2：數量 = 50 件，金額 = $800.00，站點 = 1，倉庫 =11，批號 = B2

下表顯示成本物件的計算結果。 您可以在 **成本物件** 頁面中檢視結果。

<table>
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>物件類型</th>
<th>品項編號</th>
<th>網站</th>
<th>數量</th>
<th>庫存單位</th>
<th>值</th>
<th>平均單位成本</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>成本物件</td>
<td>A</td>
<td>1</td>
<td>150</td>
<td>件</td>
<td><p>$1800.00</p></td>
<td><p>$12.00</p></td>
</tr>
</tbody>
</table>

下表顯示庫存物件的計算結果。 按一下 **成本物件** 頁面上的 **實體數量** 可以檢視結果。

<table>
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th>物件類型</th>
<th>品項編號</th>
<th>網站</th>
<th>倉庫</th>
<th>批號。</th>
<th>數量</th>
<th>庫存單位</th>
<th>值</th>
<th>平均單位成本</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>庫存物件</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B1</td>
<td>100</td>
<td>件</td>
<td><p>$1200.00</p></td>
<td><p>$12.00</p></td>
</tr>
<tr class="even">
<td>庫存物件</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B2</td>
<td>50</td>
<td>件</td>
<td><p>$600.00</p></td>
<td><p>$12.00</p></td>
</tr>
</tbody>
</table>



## <a name="additional-resources"></a>其他資源

[成本物件](cost-object.md)

[成本項目](cost-entries.md)

[新消息與變更](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]