---
title: 同步處置代碼
description: 本主題說明如何同步公司間商務的處置代碼
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 04a25324e79a1f9cb30a7da19d648bda995ba7b2
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447726"
---
# <a name="synchronize-intercompany-disposition-codes"></a>同步公司間處置代碼

[!include [banner](../../includes/banner.md)]

為了支援公司間退貨，Microsoft Dynamics 365 Supply Chain Management 使您能夠將外部定義的處置代碼，對應至相應的內部處置代碼。 當公司間鏈結設定時，兩個公司之間對應的處置動作必須相同。 如果不同，則無法成功同步流程。

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>關於三方之間直接退貨的處置代碼

處置代碼會與公司間銷售訂單行到原始銷售訂單行同步。 但是，同步處理只會對原始銷售訂單行產生立即性的效果。 該效果會導致，雜項費用根據處置代碼刪除，而該雜項費用是由 A 公司設定。A 公司是建立退貨單的公司。

在三方直接交貨的鏈結中，所有處置動作都支援公司間的銷售訂單行。 但是，如果將產品退回給客戶，您應確認退過單中的交貨地址，與指定的原始訂單中的客戶交貨地址一致。

> [!NOTE]
> 訂購訂單中不存在處置代碼。 因此，從公司間銷售訂單同步處理處置代碼至原始退貨單，必須從銷售訂單至銷售訂單之間執行。

## <a name="replacing-returned-items"></a>取代退回的項目

如果退回的項目已經遭到取代，並且已經在 B 公司內建立取代訂單，則無法選擇處置代碼，並且不會在 A 公司中建立額外的取代訂單。

## <a name="rules-for-intercompany-direct-deliveries"></a>公司間直接交貨的規則

涉及公司間直接交貨的情況下，原始退回訂單一般適用下列規則：

- 如果原始銷售訂單行的基礎處置動作是貸記和報廢、貸記或退貨給客戶，則會套用貸記處置動作。 但是，退回給客戶動作代碼集，會將現有行，已及公司間銷售訂單行新的同步淨額設定為 0 (零)。 此外，報廢行永遠不會同步。 當公司間銷售訂單新增行時，對於有正數量和報廢處置動作 (例如：貸記和報廢，或取代和報廢) 的銷售訂單，永遠不會進行同步。
- 貸記和取代，或報廢和取代的基本處置動作，不會遭到駁回。 會將其視為貸記和取代，或報廢和取代處置動作。 即使 A 公司沒有建立報廢行，且 B 公司沒有建立取代訂單 (接受退回項目的公司)，也適用此規則。 只有當裝箱單更新時，才會在 A 公司中建立取代訂單。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
