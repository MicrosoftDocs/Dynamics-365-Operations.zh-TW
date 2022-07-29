---
title: 收入確認概覽 (包含影片)
description: 本主題提供有關收入確認功能的資料。 本功能提供一個靈活的框架，讓您能夠定義公司特定的準則，以確認多元素訂單的收入價格和收入排程。
author: kweekley
ms.date: 03/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: aae46fa90d306355608200f96ae5cf10793c8464
ms.sourcegitcommit: 0925b9ee0cb0df93047681a243aacc2abd404dea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "8451851"
---
# <a name="revenue-recognition-overview"></a>收入確認概覽

[!include [banner](../includes/banner.md)]

在銷售多種元素的產業中，例如產品、服務、訂閱等，公司必須能夠拆解多元素訂單，以便根據一套公司特定和產業特定的準則來確認收入。

不支援在 Commerce 管道 (電子商務、POS、呼叫中心) 中使用收入確認，包括搭售方案功能。 包含收入確認的項目不應加入在 Commerce 管道中建立的訂單或交易中。

一般來說，收入確認流程可用於執行以下任務：

* 分配收入，以協助確保根據多元素訂單上的組件價值確認合理的收入價格。
* 按照代表合約時間範圍以及該段時間內收入確認百分比的收入排程來遞延收入。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

[如何在 Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) 使用收入確認影片 (如上所示) 包含在 YouTube 上提供的[財務和營運播放清單](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)中。

收入確認功能提供一個靈活的框架，讓您能夠定義特定的公司準則，以確認收入價格和收入排程。

已發佈產品用於支援銷售訂單文件的收入確認。 已發佈產品包含確定收入價格和收入排程所需的設定。 銷售訂單可能源自時間和材料專案。

公司可在不使用收入價格功能的情況下使用收入排程功能。 因此，銷售訂單明細上的價格將作為收入或遞延收入。 如果銷售訂單明細中有收入排程，則將遞延銷售訂單明細的價格。 如果銷售訂單明細上不存在收入排程，則銷售訂單明細上的價格將在開票時過帳到收入科目。

在確認銷售訂單或過帳發票時計算收入價格。 若要在發票過帳之前預覽收入價格，則必須確認銷售訂單。

確認銷售訂單後，如果任何銷售訂單明細具有收入排程，則也會建立預期收入排程。 銷售訂單開立發票後，將刪除預期收入排程，並以實際收入確認排程取代預期收入排程。

每個銷售訂單明細均保存收入確認排程詳細資料。 因此，在完成合約義務後，收入確認經理可以查看詳細資料並將銷售訂單明細發佈到收入。 每個期間結束時，收入確認經理可以建立收入日記帳來發佈任何在其指定的日期當日或之前截止的排程明細。 此收入日記帳不會立即過帳。 因此，收入確認經理可驗證從遞延收入向實際收入發佈的金額是否正確。

如果因合約更改，而導致在現有銷售訂單或新的銷售訂單中加入新的銷售訂單明細，則可以執行重新分配流程以更正銷售訂單中所有明細的收入價格。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
