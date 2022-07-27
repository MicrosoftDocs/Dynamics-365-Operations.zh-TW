---
title: 公司間總排程
description: 本主題將介紹公司間總排程
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
ms.openlocfilehash: e28051097905503e291e0c15a50e9363b39b2daa
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447744"
---
# <a name="intercompany-master-scheduling"></a>公司間總排程

[!include [banner](../../includes/banner.md)]

公司間總排程用於計算需求及產生跨多個內部公司的計劃公司間訂單。 在您指定的反覆運算次數上執行公司間總排程。 若要使用 Microsoft Dynamics 365 Supply Chain Management 執行公司間總排程，您必須在其中每個公司中設定總排程。 這需要數次反覆運算，其中 Microsoft Dynamics 365 Supply Chain Management 會自動建立公司間訂購單；這會反過來會導致自動建立公司間銷售訂單，接著再度導致新的需求。

您需要在各個公司間企業的 **主計劃** 參數中設定公司間總計畫和公司間排程訂單。

為了在整個公司間鏈中傳播需求，您必須設定參數來自動確認計劃訂購單；也就是說，訂單時間或數量不能改變。 設定涵蓋群組中的 **確認時界**，或總計畫中的 **確認時界**。 如果不設定 **確認時界**，就不會自動建立公司間訂購單。 只有第一次執行總排程會產生計劃訂單。 然而，由於未建立公司間訂購單，因此不會建立公司間銷售訂單，也不會進一步建立公司間訂購單，依此類推。

當您啟動公司間總排程時，Microsoft Dynamics 365 Supply Chain Management 會對其中每間公司執行一個總排程；然後執行第二次總排程，依此類推，直到達到指定的反覆運算次數。 系統最多可以進行 30 次反覆運算，但您選擇的反覆運算次數越多，排程時間就越長。

因為公司內的總排程由公司間排程序列控制，亦即程式在每個公司間企業之間安排總排程的優先順序，所以您可以從任何公司間企業啟動公司間總排程。 此外，因為公司間排程序列決定了公司內執行總排程的順序，所以從何處啟動公司間總排程都沒關係。 在每次反覆運算中，目前的公司會最後執行。

> [!NOTE]
> 最佳做法是允許從一間 Microsoft Dynamics 365 Supply Chain Management 公司啟動公司間總排程。

在 **公司間總排程** 頁面中，您可以啟動一系列總排程，做法是首次執行總排程時，使用您為所有公司間企業的首次反覆運算所選擇的需求計算更新原則。 後續反覆運算會使用您為下一次反覆運算選擇的次要原則，此原則將一直套用到系統達到您指定的反覆運算次數為止。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
