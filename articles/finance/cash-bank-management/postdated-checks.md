---
title: 遠期支票
description: 本文提供有關 Microsoft Dynamics 365 Finance 中的遠期支票支援資訊 . 遠期支票是針對未來日期收付款而開立的支票。 因此，支票須等到指定日期才會兌現。
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f5c4d641a3d3ccc326ee56ce7bd05c891b3fa8a
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451035"
---
# <a name="postdated-checks"></a>遠期支票

[!include [banner](../includes/banner.md)]

本文提供有關遠期支票支援資訊。 遠期支票是針對未來日期收付款而開立的支票。 因此，支票須等到指定日期才會兌現。

Dynamics 365 Finance 支援應收帳款和應付帳款中遠期支票的完整管理週期，如下表所示。
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>方案</th>
<th>詳細資料​​</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>設定遠期支票</td>
<td>您必須設定新付款方式，並指定已發立支票、收到支票和預扣所得稅的付款例行公事。</td>
</tr>
<tr class="even">
<td>登記並過帳廠商的遠期支票</td>
<td>登記您開立給廠商遠期支票的細節。 付款過帳時會認列廠商負債，但銀行帳戶尚未貸記。 結算帳戶反而用於此用途。 </td>
</tr>
<tr class="odd">
<td>登記並過帳客戶的遠期支票</td>
<td>登記您從客戶收到的遠期支票細節。 付款過帳時會貸記客戶應收帳款，但銀行帳戶尚未借記。 結算帳戶反而用於此用途。</td>
</tr>
<tr class="even">
<td>登記並過帳客戶或廠商更換的遠期支票</td>
<td>
如果您遺失或損壞給廠商或從客戶收到的原始支票，您可以開立更換遠期支票。 當您登記支票細節時，請提供原始支票的參考憑據，並指出新支票為原始支票的更換物。 您也可以過帳更換支票。</td>
</tr>
<tr class="odd">
<td>將客戶遠期支票移轉給廠商</td>
<td>當您收到客戶的遠期支票時，您可以將該支票移轉給廠商，作為付款。</td>
</tr>
<tr class="even">
<td>結算客戶或廠商的遠期支票</td>
<td>當支票最終到期時，結算過帳到客戶或廠商過渡帳戶的遠期支票。 支票結算時，銀行最終會對之前使用的清算帳戶借記或貸記。</td>
</tr>
<tr class="odd">
<td>取消廠商的遠期支票</td>
<td>符合下列情況者可以取消已經過帳的遠期支票：-支票被銀行退回。
- 支票適用不正確的發票。
- 現金付款是按支票兌付。
  </td>
  </tr>
  <tr class="even">
  <td>停止支付遠期支票</td>
  <td>您可以因資金不足、與廠商更改協議條款、廠商供應的貨物出現瑕疵或貨物退回廠商等原因停止支付已開給廠商的遠期支票。 您只能停止支付尚未結清的支票。</td>
  </tr>
  </tbody>
  </table>



有關詳細資訊，請參閱下列主題：

[設定遠期支票](tasks/set-up-postdated-checks.md)

[登記並過帳客戶的遠期支票](tasks/register-post-postdated-check-customer.md)

[結算客戶的遠期支票](tasks/settle-postdated-check-customer.md)

[登記並過帳廠商的遠期支票](tasks/register-post-postdated-check-vendor.md) 

[結算廠商的遠期支票](tasks/settle-postdated-check-vendor.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
