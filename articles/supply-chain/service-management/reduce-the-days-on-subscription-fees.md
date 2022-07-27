---
title: 減少訂用費天數
description: 若要減少現有訂用費的天數，可以建立一個新的交易，在其中刪除不應繼續作為訂用費間隔的部分期間。
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
ms.openlocfilehash: df1a27576b93c4ace4a5f17271595d259e96a51a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448602"
---
# <a name="reduce-the-days-on-subscription-fees"></a>減少訂用費天數 

[!include [banner](../includes/banner.md)]


若要減少現有訂用費的天數，可以建立一個新的交易，在其中刪除不應繼續作為訂用費間隔的部分期間。

## <a name="reduce-the-days-on-a-subscription-fee"></a>減少訂用費天數

1.  按一下 **服務管理** \> **通用** \> **服務訂閱** \> **所有服務訂閱**。 選擇服務訂用，並在動作窗格中按一下 **訂用費**

2.  在 **訂用類型** 欄位中，選擇 **減少天數**。

3.  使用 **開始日期** 和 **結束日期** 欄位來定義要從訂用費期間刪除的訂用費的日期間隔，然後按一下 **確定**。

若要查看已建立的交易，則在 **訂用** 表單中，按一下 **費用交易**。

## <a name="example"></a>範例

如果某一訂用交易記錄期間是從 1 月 1 日到 1 月 31 日，並且您想要將該期間減少 10 天，則建立一個減少期間為 1 月1 日到 1 月10 日的新交易。 (減少期間也可以是 1 月 5 日至 1 月 15 日，或其他任何為期十天的期間)。

此外，如果該減少期間的 **開始日期** 是 1 月 21 日 (31 減 10)，則可以將 **結束日期** 設定為 1 月 31 日之後的任何日期，10 天仍將從費用交易期間中刪除。

## <a name="see-also"></a>另請參閱

[減少天數範例](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]