---
title: 減少天數範例
description: 減少天數範例。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97fb032d02df1dbedaeccec14496cb1d63e8cf70
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448065"
---
# <a name="reduction-days-example"></a>減少天數範例

[!include [banner](../includes/banner.md)]

您已經為客戶的維護預訂建立了預訂交易記錄，如下表中所述。

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>開始日期</p></th>
<th><p>結束日期</p></th>
<th><p>訂用</p></th>
<th><p>訂用類型</p></th>
<th><p>專案</p></th>
<th><p>類別</p></th>
<th><p>銷售幣別</p></th>
<th><p>銷售價格</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2011 年 3 月 1 日</p></td>
<td><p>2011 年 3 月 31 日</p></td>
<td><p>NR-2</p></td>
<td><p><strong>正常</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>200.00</p></td>
</tr>
</tbody>
</table>

客戶報告兩天 (3 月 10 日和 3 月 11 日) 不需要服務。 您同意減少這兩天的訂用。

您如下表中所述，建立類型為 **減少天數** 的新交易記錄。

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>開始日期</p></th>
<th><p>結束日期</p></th>
<th><p>訂用</p></th>
<th><p>訂用類型</p></th>
<th><p>專案</p></th>
<th><p>類別</p></th>
<th><p>銷售幣別</p></th>
<th><p>銷售價格</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2011 年 3 月 10 日</p></td>
<td><p>2011 年 3 月 11 日</p></td>
<td><p>NR-2</p></td>
<td><p><strong>減少天數</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>-12.90</p></td>
</tr>
</tbody>
</table>

為 2011 年 3 月的交易開票時，200 歐元的銷售價格將減少 12.90 歐元。 因此，預訂交易的計費金額為 187.10 歐元，兩筆交易的發票總額為 187.10 歐元。

## <a name="see-also"></a>另請參閱

[減少訂用費天數](reduce-the-days-on-subscription-fees.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]