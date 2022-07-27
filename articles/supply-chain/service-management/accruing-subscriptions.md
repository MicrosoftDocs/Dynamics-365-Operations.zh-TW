---
title: 計入訂閱
description: 使用服務訂閱，您可以在為費用交易開票日之後的期間手動計入收入。
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d17737c415f6204359dae3ea4b2a0cb4ebb5d65
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449313"
---
# <a name="accruing-subscriptions"></a>計入訂閱 

[!include [banner](../includes/banner.md)]


使用服務訂閱，您可以在為費用交易開票日之後的期間手動計入收入。

應計期間的建立是為了訂閱費用設定的發票期間，應計期間為訂閱的期間代碼所建立的。

您可以計入和沖銷應計收入。

## <a name="reverse-accruals-of-credit-amounts"></a>貸方金額的沖銷應計

如果您貸記已開票的訂閱金額，您可以使用兩種方法來沖銷應計金額：

  - 在為交易建立貸項通知單建議之前，您可以單獨沖銷每個應計收入交易。 這是手動方法。 (手動的)

  - 您可以在貸項通知單的過帳日期或應計項目的原始過帳日期沖銷應計金額。

更多詳細資料，請參閱[訂閱參數 (表單)](/dynamicsax-2012//subscription-parameters-form)。

## <a name="setup-requirements"></a>設定要求

要計入收入，請確保滿足以下資料要求：

## <a name="account-setup"></a>科目設定

**WIP - 訂閱** 和 **應計收入 - 訂閱** 科目必須設定在 **專案** 模組中。

當您過帳應計收入時，**WIP - 訂閱** 科目借記了應計總額，並且 **應計收入 - 訂閱** 科目貸記了應計總額。

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>設定應計訂閱收入的科目

1.  按一下 **專案管理和會計**\>**設定**\>**過帳**\>**分類帳過帳設定**。

2.  按一下 **收入科目** 索引標籤，然後選取 **WIP - 訂閱** 或 **應計收入 - 訂閱** 設定科目。

## <a name="subscription-group-setup"></a>訂閱群組設定

若要能夠計入訂閱收入，必須選取 **計入收入** 核取方塊。 這可以在 **訂閱群組** 表單上找到，位於附加到訂閱的群組中。 點選 **服務管理** \> **設定** \> **服務預訂** \> **預訂群組**。

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>在訂閱群組上啟用應計收入

點選 **服務管理** \> **設定** \> **服務預訂** \> **預訂群組**。

## <a name="periods"></a>期間

您必須設定開票期間代碼。 除非您希望在與開票相同的時間間隔內計入收入，否則您還必須設定一個應計期間。

下表概述了可以為每個開票期間設定哪些應計期間：

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>發票期</p></th>
<th><p>應計期</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>年</strong></p></td>
<td><ul>
<li><p><strong>年</strong></p></li>
<li><p><strong>季</strong></p></li>
<li><p><strong>月</strong></p></li>
<li><p><strong>天</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>季</strong></p></td>
<td><ul>
<li><p><strong>季</strong></p></li>
<li><p><strong>月</strong></p></li>
<li><p><strong>天</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>月</strong></p></td>
<td><ul>
<li><p><strong>月</strong></p></li>
<li><p><strong>天</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>週</strong></p></td>
<td><ul>
<li><p><strong>天</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>天</strong></p></td>
<td><ul>
<li><p><strong>天</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

設定發票週期是整個訂閱群組設定的強制性部分。 您可以決定是否也為訂閱群組設定應計期限。 如果您為訂閱群組設定了一個應計期間，該期間在 **期間代碼** 欄位中建議。 當您計入訂閱收入時，此欄位於 **計入訂閱收入** 表格。 但是，應計期間是有關訂閱群組的可選資訊。


> [!NOTE]
> <P>使用以下路徑打開<STRONG>計入訂閱收入</STRONG>表單。 按一下<STRONG>服務管理</STRONG>&gt;<STRONG>定期</STRONG>&gt;<STRONG>服務訂閱</STRONG>&gt;<STRONG>計入訂閱收入</STRONG>。</P>


## <a name="transactions"></a>交易

您可以控制在過帳應計收入時建立的分類帳交易的數量。 在訂閱時，定義分類帳交易是應該建立成總計還是依每明細。

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>指定應計交易顯示的過帳詳細資料層級

1.  按一下 **專案管理和會計** \> **設定** \> **專案管理和會計參數**。

2.  在 **金融** 索引標籤，在 **發票** 欄位，選擇 **全部** 或 **明細**。


## <a name="see-also"></a>另請參閱

[計入訂閱收入](accrue-subscription-revenue.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]