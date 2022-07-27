---
title: 建立多家公司的公司間訂購單和銷售訂單
description: 本主題將說明如何建立多家公司的公司間訂購單或銷售訂單
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
ms.openlocfilehash: 5d756a82abb7e7b19080128353d863f29837fc5b
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447729"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>建立多家公司的公司間訂購單和銷售訂單

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management 並非只能處理一家生產公司和多家銷售公司的交易， 凡是屬於公司間交易範圍的公司可以同時身為貿易公司和生產公司。

如果多家公司可以交付相同品項，您就能自由選取向誰購買；即使一張銷售訂單變成多張訂購單，系統也會予以更新。

與自動建立公司間訂購單的方式相同，您可以在貴公司內建立一張原始銷售訂單，然後讓多個公司間廠商公司建立多張公司間訂購單來完成訂單。 Microsoft Dynamics 365 Supply Chain Management 會自動在廠商公司中建立公司間銷售訂單。

若要做到這一點，必須將所有公司設為貿易關係。 您必須在 Microsoft Dynamics 365 Supply Chain Management 中，將廠商公司設為相關品項的主要公司間廠商。 在銷售訂單的 **標題檢視** 中，您必須在 **公司間設定** FastTab 上選擇 **自動建立公司間訂單** 欄位和 **直接交貨** 欄位。 這是預設設定。

然後請按照以往的方式建立銷售明細。 當您留下記錄時，系統會顯示一則訊息，告知您已建立公司間訂購單和公司間銷售訂單。 該訊息包含新訂單的連結。 若要檢視在廠商公司中建立的公司間銷售訂單，請開啟原始銷售訂單，然後在 **一般** 索引標籤的 **相關資訊** 群組中，選擇 **參考項目**。

開啟廠商的公司間訂購單時，Microsoft Dynamics 365 Supply Chain Management 會自動填入原始銷售訂單編號和每個廠商的公司間銷售訂單編號。

同樣地，開啟廠商的公司間銷售訂單時，Microsoft Dynamics 365 Supply Chain Management 會自動填入原始銷售訂單編號和每個廠商的公司間訂購單編號。

> [!NOTE]
> 如果其中一家公司間廠商公司有提供訂單品項，但其他公司沒有，則 Microsoft Dynamics 365 Supply Chain Management 將針對提供該品項的廠商公司建立公司間訂單，而不會針對其他公司建立訂單。 發生這種情況時，系統會顯示一則通知訊息。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
