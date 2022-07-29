---
title: 客戶帳齡報表
description: 客戶帳齡報表顯示應收客戶的餘額，按日期間隔或帳齡期間排序。
author: JodiChristiansen
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33bee60a3807c92cc97f0f5e6d660a67cdd7f297
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451014"
---
# <a name="customer-aging-report"></a>客戶帳齡報表 

**客戶帳齡** 報表顯示應收客戶的餘額，按日期間隔或帳齡期間排序。

產生此報告時，會顯示以下預設參數。 您可使用這些參數篩選報表中顯示的資料。 更多資訊，請參閱[設定收款](set-up-collections.md)。

<table>
<colgroup>
<col>
<col>
</colgroup>
<thead>
<tr class="header">
<th><p>欄位</p></th>
<th><p>描述</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>計費分類</strong></p></td>
<td><p>選擇一個或多個計費分類以包含在報表中。</p>
<div class="alert">

**請注意：** 只有在選取<STRONG>公共部門</STRONG>組態金鑰時，才有此控制項可用。</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>納入無計費分類的交易</strong></p></td>
<td><p>如果選取此核取方塊，則所有未指派計費分類的交易都將顯示在報表中。</p>
<div class="alert">

**請注意：** 只有在選取<STRONG>公共部門</STRONG>組態金鑰時，才有此控制項可用。</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>帳齡截止日期</strong></p></td>
<td><p>輸入目前帳齡時段使用的日期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>餘額截止日期</strong></p></td>
<td><p>輸入查看客戶餘額的日期。 這也稱為交易的截止日期。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始日期</strong></p></td>
<td><p>輸入要包含在報表中的第一個期間間隔或帳齡期間的日期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>條件</strong></p></td>
<td><p>選取報表所依據的日期類型。</p>
<ul>
<li><p><strong>交易日期</strong> - 交易的過帳日期。 例如，這可能是作為到期日計算基礎的發票日期。</p></li>
<li><p><strong>截止日期</strong> – 付款期限中規定的交易到期日。</p></li>
<li><p><strong>文件日期</strong> – 使用者定義的文件日期，其為計算到期日的基礎。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>帳齡期間定義</strong></p></td>
<td><p>選擇帳齡期間定義。 如果選擇帳齡期間定義，則不使用<strong>間隔</strong>欄位。</p>
<p>超過六個帳齡期間的帳齡期間定義不能用於列印報表。</p>
<div class="alert">

**請注意：** 您可以在<STRONG>帳齡期間定義</STRONG>頁面上設定帳齡期間。</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>列印帳齡期間描述</strong></p></td>
<td><p>選擇<strong>是</strong>以在報表的每個帳齡期間欄的頂端包括帳齡期間描述。 選擇<strong>否</strong>以列印不包含欄標題的報表。</p></td>
</tr>
<tr class="even">
<td><p><strong>間隔</strong></p></td>
<td><p>透過輸入每個期間期間的日或月單位數來定義要使用的期間。 例如，要按週查看帳齡資訊，請在此欄位中輸入 7，並在<strong>日/月</strong>欄位選擇<strong>日</strong>。</p>
<div class="alert">

**筆記：** 僅在未選擇帳齡期間定義時，才能使用在此欄位中輸入的資訊。 否則，在帳齡期間定義中定義列印方向。</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>日/月</strong></p></td>
<td><p>選擇單位，<strong>日</strong>或<strong>月</strong>，用於定義<strong>間隔</strong>欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>列印方向</strong></p></td>
<td><p>選擇是否計算餘額並列印過去或未來期間的帳齡報表。 相對於餘額<strong>截止日期</strong>欄位中選擇的日期評估日期。 選擇<strong>逆向</strong>顯示過去期間的資訊。 選擇<strong>正向</strong>顯示過去未來的資訊。</p>
<div class="alert">
  
<STRONG>請注意：</STRONG>僅在未選擇帳齡期間定義時，才能使用在此欄位中輸入的資訊。</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>詳細資料​​</strong></p></td>
<td><p>選擇以列出報表上顯示的餘額中包含的交易。</p></td>
</tr>
<tr class="even">
<td><p><strong>包含金額 (以交易貨幣計)</strong></p></td>
<td><p>選擇以包括以會計貨幣表示的金額以外的以交易貨幣表示的金額。 如果未選取此核取方塊，則報表上的金額僅以會計貨幣顯示。</p></td>
</tr>
<tr class="odd">
<td><p><strong>負餘額</strong></p></td>
<td><p>選擇以包括餘額為負數的客戶帳戶。</p></td>
</tr>
<tr class="even">
<td><p><strong>排除零餘額科目</strong></p></td>
<td><p>選擇以排除餘額為零的客戶帳戶。</p></td>
</tr>
<tr class="odd">
<td><p><strong>付款定位</strong></p></td>
<td><p>選擇以顯示尚未結算的付款。 這些都顯示在報表的第一欄中。</p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]