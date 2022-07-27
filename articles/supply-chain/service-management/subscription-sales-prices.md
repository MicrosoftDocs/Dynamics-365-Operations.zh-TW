---
title: 預訂銷售價格
description: 建立預訂時，銷售價格源自在 [銷售價格 (預訂)] 表單中建立的銷售價格設定。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd63fc290263babafabd6e29441f008d0cf10e13
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448260"
---
# <a name="subscription-sales-prices"></a>預訂銷售價格

[!include [banner](../includes/banner.md)]

建立預訂時，銷售價格源自在 **銷售價格 (預訂)** 表單中建立的銷售價格設定。

在 **銷售價格 (預訂)** 表單中，您可以為特定預訂建立銷售價格，也可以建立更廣泛使用的銷售價格。 對於要套用於預訂的銷售價格，預訂的期間代碼和貨幣必須與銷售價格的期間代碼和貨幣相同。

如果預訂和銷售價格的期間代碼和貨幣相同，則根據下表列出的優先順序選擇預訂銷售價格。 資料表中的空白儲存格表示空白欄位，X 表示值等於從其產生交易的預訂中的值。

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>優先順序</p></th>
<th><p><strong>類別</strong></p></th>
<th><p><strong>專案識別碼</strong></p></th>
<th><p><strong>預訂</strong></p></th>
<th><p><strong>銷售幣別</strong></p></th>
<th><p><strong>期間代碼</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

建立預訂費時，選擇最詳細的銷售價格 (如上表所示) 作為預訂銷售價格。

## <a name="update-and-index-subscription-sales-prices"></a>更新預訂銷售價格並編製索引

您可以透過更新基本價格或指數來更新預訂銷售價格。 您可以按百分比更新或更新為新值。

## <a name="subscription-fee-sales-prices"></a>預訂費用銷售價格

建立預訂費用時，銷售價格基於預訂的銷售價格設定。 您可以使用預訂價格設定中的基本價格或建立索引銷售價格。

## <a name="example"></a>範例

要為新專案 9030 設定 EUR 500 的預訂銷售價格。 在 **銷售價格 (預訂)** 表單中建立預訂銷售價格行，如下表所示。

<table>
<colgroup>
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
<th><p>生效日期</p></th>
<th><p>類別</p></th>
<th><p>專案</p></th>
<th><p>預訂</p></th>
<th><p>期間代碼</p></th>
<th><p>銷售幣別</p></th>
<th><p>銷售價格</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>月</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


請注意，**類別** 和 **預訂** 欄位為空白。

然後建立以下預訂。

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>服務預訂</p></th>
<th><p>專案</p></th>
<th><p>預訂群組</p></th>
<th><p>類別</p></th>
<th><p>貨幣</p></th>
<th><p>期間代碼</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat1</p></td>
<td><p>EUR</p></td>
<td><p>每月</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>每月</p></td>
</tr>
</tbody>
</table>


現在已為預訂群組 Sub1 中的兩個預訂都建立了預訂費用：

1.  點選 **服務管理** \> **設定** \> **服務預訂** \> **預訂群組**。

2.  在 **預訂群組** 表單中，點選 **功能** \> **建立預訂費用**。

3.  在 **建立訂閱費用** 表單中，輸入相應的資訊。 有關詳細資訊，請參閱[建立預訂費用交易](create-subscription-fee-transactions.md)。

為兩種預訂建立了銷售價格為 EUR 500 的預訂費用，如下表所示。

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
<th><p>專案日期</p></th>
<th><p>服務預訂</p></th>
<th><p>專案</p></th>
<th><p>類別</p></th>
<th><p>開始日期</p></th>
<th><p>結束日期</p></th>
<th><p>銷售幣別</p></th>
<th><p>銷售價格</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2006</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


稍後，您決定要為專案 9030 的類別 SubCat1 指定銷售價格。 因此，您為專案 9030 和費用類別 SubCat1 的組合建立一個銷售價格為 EUR 550 的新銷售價格行。 專案 9030 現在有兩個預訂銷售價格行，如下表所示。

<table>
<colgroup>
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
<th><p>生效日期</p></th>
<th><p>類別</p></th>
<th><p>專案</p></th>
<th><p>預訂</p></th>
<th><p>期間代碼</p></th>
<th><p>貨幣</p></th>
<th><p>銷售價格</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2007</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>月</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2007</p></td>
<td><p>SubCat1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>月</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>

重複上述過程為預訂群組 Sub1 中的兩個預訂建立預訂費用。 下表顯示了為附加到預訂群組的每個預訂建立的交易。

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
<th><p>專案日期</p></th>
<th><p>預訂</p></th>
<th><p>專案</p></th>
<th><p>類別</p></th>
<th><p>開始日期</p></th>
<th><p>結束日期</p></th>
<th><p>銷售幣別</p></th>
<th><p>銷售價格</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-07-2007</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>28-07-2008</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>

在預訂 00020\_135 的第一個交易中，EUR 550 的銷售價格來自為特定專案和類別的組合設定的預訂銷售價格。 在預訂 00021\_135 的第二筆交易中，EUR 500 的銷售價格用作專案預訂銷售價格，因為沒有為專案 9030 和類別 SubCat2 的組合設定價格。

## <a name="see-also"></a>另請參閱

[更新預訂銷售價格並編製索引](update-and-index-subscription-sales-prices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
