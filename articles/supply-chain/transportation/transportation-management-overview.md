---
title: 運輸管理概覽
description: 本主題概述了 Supply Chain Management 中的運輸管理功能。
author: Henrikan
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench, TMSLoadBuildTemplateApply, WHSLoadTemplate, TMSTransportationStatus, TMSLoadSeal, TMSLoadBuildProposal, TMSLoadBuildWorkbench, TMSLoadBuildStrategy, TMSLoadBuildStrategyAttributeValue
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "30251"
- intro-internal
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68082a736fd45c6701324a1492087c1b16bf0566
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449739"
---
# <a name="transportation-management-overview"></a>運輸管理概覽

[!include [banner](../includes/banner.md)]

本主題概述了 Supply Chain Management 中的運輸管理功能。

運輸管理讓您可以使用公司的運輸，還可以讓您為入站和出站訂單確定供應商和路由解決方案。 例如，您可以確定貨運的最快路線或最便宜的運費。 下方資料表中描述了使用運輸管理的主要場景。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>狀況</th>
<th>運輸管理如何提供協助</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>使用外部物流供應商進行運輸活動。</td>
<td>將運輸管理用於入庫和/或出庫運輸。</td>
</tr>
<tr class="even">
<td>公司&#39;自己的車隊可用於送貨/取貨，交貨費用會轉嫁給客戶。</td>
<td>對於出庫流程，您可以使用運輸管理來確定運輸費用並將其傳遞給客戶。 但是，承運人發票對帳流程並非&#39;必要。</td>
</tr>
<tr class="odd">
<td>公司&#39;自己的車隊可用於送貨/取貨，但送貨費&#39;傳遞給客戶，因為產品價格包括運輸。</td>
<td>許多運輸管理功能並非&#39;必要。 但是，您可以使用運輸管理來確定運輸費率並相應地調整銷售價格。</td>
</tr>
<tr class="even">
<td>物流服務由同一公司的另一個法律實體提供。</td>
<td><ul>
<li>您可以將其他法律實體視為任何其他運輸承運人，進行運輸管理。 您不能&#39;自動化法律實體之間的經濟交易。 因此，您必須手動處理這些交易 (例如，透過建立訂購單)。</li>
<li>在提供物流服務的法律實體中，運輸管理可用於確認運輸費率。</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-supply-chain-management"></a>在 Supply Chain Management 中規劃運輸
在運輸管理中，運輸計劃可以基於訂單或基於這些訂單建立的運送。 運送總會存在某個時間點，但不是運輸規劃所必需的。 轉移訂單是出庫方案的一部分，可以與銷售訂單一起規劃。 

![載入圖紙。](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>入庫運輸
當您從廠商處訂購物品且必須將物品運送到您的倉庫時，您可能需要自己安排物品的運輸。 您可以使用 Supply Chain Management 來計劃入庫貨物的運輸和接收。 下圖顯示的是入庫負載計劃運輸的商務程序流程。 

![入庫貨物運輸的商務程序流程。](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>出庫運輸
您可以計劃和處理出站負載，將特定項目從公司倉庫運送給客戶。 您可以使用 Supply Chain Management 來計劃出庫負載的運輸和運送。 下圖顯示的是運送出庫負載計劃和處理的商務程序流程。 

![計劃和處理出站負載。](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>負載建構
Supply Chain Management 提供了一種負載建構策略，稱為體積型負載建構策略。 此策略允許您使用負載範本中高度和重量的指定最大值，或者您可以輸入新值來覆蓋設定。 要使用此策略，請在 **負載構建工作台** 頁面的 **設定** FastTab **負載建構策略** 欄位中。 此外，您可以通過在應用程式物件樹 (AOT) 中建立新類別，來新增自己的負載建構策略。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]