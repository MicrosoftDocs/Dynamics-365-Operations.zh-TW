---
title: 服務訂單品項要求
description: 本主題介紹服務訂單品項要求。
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae211cb24e3ed0e9e54643448ee378a20658ad89
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448599"
---
# <a name="service-order-item-requirements"></a>服務訂單品項要求

[!include [banner](../includes/banner.md)]

您可以創建服務訂單，來追蹤和管理提供給客戶的服務。 如果您需要為服務訂單預留特定項目，您可以為其創建庫存項目需求。 項目需求可以從庫存中立即消耗，也可以為項目啟動生產訂單。

通過使用項目需求而不是項目交易，您可以在項目實際使用之前計劃交貨，創建採購訂單，將項目包括在貿易合約框架中，並將項目要求包括在生產計劃中。

服務訂單的項目需求通過專案處理。 若要在服務訂單上建立項目要求，必須將服務訂單附加至專案。

為服務訂單建立品項要求後，就可以從個人服務訂單中的 **專案** 或透過 **銷售訂單** 表單查看該品項要求。

## <a name="view-an-item-requirement-from-a-service-order"></a>從服務訂單查看品項要求

1. 前往 **服務管理** \> **一般** \> **服務訂單** \> **服務訂單**。
1. 選擇 **分派**，然後選擇 **品項要求** 以打開 **品項要求** 表單。
1. 選擇 **專案** 索引標籤，然後檢查 **服務訂單** 欄位以查看品項要求的服務訂單。

## <a name="delete-service-orders-with-item-requirements"></a>刪除具有品項要求的服務訂單

如果針對某個服務訂單建立品項要求，則無法刪除該服務訂單。 您必須先刪除品項要求，然後才能刪除服務訂單。

1. 前往 **服務管理** \> **一般** \> **服務訂單** \> **服務訂單**。
1. 選擇 **分派**，然後選擇 **品項要求** 以打開 **品項要求** 表單。 此表單列出了在服務訂單上建立的品項要求。
1. 選擇要刪除的品項要求，然後選擇 **刪除**。

-或-

1. 移至 **專案管理和會計** \> **一般** \> **專案** \> **所有專案**。
1. 打開具有建立了品項要求之服務訂單的專案。
1. 在 **專案** 表單中，於右窗格選擇 **品項要求**。 **品項要求** 表單列出了與所選品項關聯的品項要求。
1. 選擇要刪除的品項要求，然後選擇 **刪除**。

## <a name="see-also"></a>另請參閱

[品項要求 (表單)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]