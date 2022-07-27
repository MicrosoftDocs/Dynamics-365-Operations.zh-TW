---
title: 預訂工作流程概觀
description: 本主題概述預訂工作流程。
author: kamaybac
ms.date: 05/07/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd1484563e9650b9ddae543e3440eec2a3ed075c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449679"
---
# <a name="subscription-workflow-overview"></a>預訂工作流程概觀 

[!include [banner](../includes/banner.md)]


您是一家提供照明設備維護預訂的照明公司的預訂管理員。 客戶連絡您的公司購買一年的照明設備維護預訂。

## <a name="setting-up-subscriptions"></a>設定預訂

若要設定預訂，您必須先為新服務合約建立預訂群組或確定某預訂群組是否存在。 如果存在預訂群組，您必須將其設定為每年向客戶開立發票，並且計入當年每個月的銷售收入。 更多有關設定預訂方式的資訊，請參閱[設定預訂群組](set-up-subscription-groups.md)。

建立預訂群組後，您可以建立預訂。 有關如何建立服務預訂的更多資訊，請參閱[從預訂群組建立服務預訂](create-service-subscriptions-from-subscription-group.md)。

## <a name="create-and-modify-subscription-transactions"></a>建立和修改訂閱交易

設定預訂後，為第一個開立發票期間 (即一年) 建立預訂費用交易。 這些交易是 **標準** 類型。 因此，您只能建立開始日期和結束日期對應於先前在 **期間類型** 中建立的期間的預訂交易。 有關費用交易的詳細資訊，請參閱[建立預訂費用交易](create-subscription-fee-transactions.md)。

為您的客戶設定預訂後，記住對於您提供的服務的所有標價，雙方已協商了 10% 的折扣。 因此，您必須降低已建立的交易費用的價格。

當天晚些時候，您的客戶連絡人打來電話說，雖然他們仍然想要照明設備的服務合約，但他們計劃在今年下半年引入新的照明設備。 因此，維護時間只需要延續到 2013 年 10 月。 為了減少客戶預訂的月數，您可建立 **減少天數** 類型的新預訂費用交易。 有關如何減少天數的更多資訊，請參閱[減少預訂費用天數](reduce-the-days-on-subscription-fees.md)。

## <a name="invoice-and-accrue-subscription-transactions"></a>開立發票和計入預訂交易

您現在已完成預訂設定，並準備為您的客戶開立發票。 更多有關為預訂開立發票的資訊，請參閱[開立預訂交易發票](invoice-subscription-transactions.md)。

兩天後，您的客戶打電話說預訂應以美元而非歐元開立發票。 因此，您建立了一張折讓單，並且還以正確的貨幣建立了一個新的預訂交易。 有關如何建立貸方預訂交易的更多資訊，請參閱[貸方預訂交易](credit-subscription-transactions.md)。

每個月末，可將來自客戶的預訂的當月收入計入損益科目和 WIP 科目。 有關如何計入預訂收入的更多資訊，請參閱[應計預訂收入](accrue-subscription-revenue.md)。

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]