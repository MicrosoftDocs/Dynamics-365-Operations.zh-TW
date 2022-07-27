---
title: Dynamics 365 Supply Chain Management 客戶入口網站概述 (包含影片)
description: 本主題介紹客戶入口網站，並說明使用對象及其運作方式。
author: Henrikan
ms.date: 06/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 50bdbe6c5f5d23f49bdf8040f2c7811a28da3f32
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449829"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>Dynamics 365 Supply Chain Management 客戶入口網站概述

[!include [banner](../includes/banner.md)]


## <a name="what-is-the-customer-portal"></a>什麼是客戶入口網站？

現代供應鏈系統仰賴整合， 因此需要將庫存、客戶需求和銷售部門整合起來，而不是各自為政。 客戶入口網站幫助執行 Microsoft Dynamics 365 Supply Chain Management 的組織加強這類整合，更有效地讓他們的客戶瞭解情況。

客戶入口網站是一個 [Power Apps 入口網站](/powerapps/maker/portals/overview)範本，協助公司建立面向外部的企業對企業 (B2B) 網站，因應銷售訂單處理相關情境。 範本使用[雙重寫入](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)、Supply Chain Management 和 Power Apps 入口網站，使外部企業客戶能夠由公司的 Dynamics 365 環境檢視和建立資料。

客戶入口網站範本具有 Power Apps 入口網站功能的所有自訂功能。 範本可輕鬆修改以代表公司品牌、新增更多功能並改變使用者體驗。 範本提供的所有功能均立即可用，並可根據需要進行修改。

> [!IMPORTANT]
> 就其本身而言，範本預計不會提供完整功能。 範本只是為希望建立面向外部網站的客戶提供支援，以便企業客戶可以使用來自 Supply Chain Management 的資料。

> [!NOTE]
> 客戶入口網站文件的目標對象包括為 Supply Chain Management 設備安裝客戶入口網站的管理員、自訂人員和系統整合商。 其中使用 _客戶_ 及 _使用者_ 等詞彙描述執行 Supply Chain Management 組織的客戶，以及使用最終入口網站的人員。

## <a name="video"></a>影片

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

[Dynamics 365 Supply Chain Management 客戶入口網站範本概述](https://youtu.be/nPrqoLuHfV8)影片 (如上所示) 包含在[財務和營運播放清單](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)之中，可在 YouTube 觀看。

## <a name="who-should-use-it"></a>誰應該使用？

客戶入口網站專為執行 Supply Chain Management 並具有以下特色的公司設計：

- 希望建立一個面向外部的網站，將訂單處理資訊 (例如訂單狀態或帳戶資訊) 直接從 Supply Chain Management 系統傳達給企業客戶。
- 正從 Dynamics AX 2012 轉移到 Supply Chain Management，而且以前使用過 [AX 2012 客戶自助服務入口網站](/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal)。

以下類型組織 **不適合** 實作客戶入口網站：

- 想要為非企業客戶建立網站的公司。 這些公司應該考慮建立 [Dynamics 365 Commerce 電子商務網站](../../commerce/create-ecommerce-site.md)。
- 已經使用現有 Power Apps 入口網站用於類似用途的公司。 這些公司不會從客戶入口網站中獲得任何額外的好處。 客戶入口網站是以範本提供，為希望連結雙重寫入、Supply Chain Management 和 Power Apps 入口網站的客戶提供指南及入門起點。 如果您已經建立了一個用於此用途的網站，您使用客戶入口網站範本重新佈建該網站可能不會獲得太多價值。

## <a name="how-does-it-work"></a>其運作方式為何？

客戶入口網站是以 Power Apps 入口網站範本提供。 該網站仰賴 Power Apps 入口網站和雙重寫入。

[Power Apps 入口網站](/powerapps/maker/portals/overview)是一項功能，允許使用者建立面向外部的網站，讓組織外部的人可以登入該網站。 製作入口網站幾乎不需要編碼作業。 客戶入口網站是眾多 [Dynamics 365 入口網站範本](/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365)之一，可從 Microsoft 獲得。

[雙重寫入](/powerapps/maker/portals/overview)是一種立即可用的基礎結構產品，可在客戶互動應用程式與財務和營運應用程式之間提供近即時互動。 雙重寫入提供財務和營運應用程式與 Microsoft Dataverse 之間的雙向整合。 因此其中提供了跨應用程式的整合式使用者體驗。 客戶入口網站仰賴與雙重寫入同步的資料表。 在 Supply Chain Management 中的資料可以顯示在客戶入口網站之前，必須為所有適當的資料表啟用雙重寫入。

![客戶入口網站相依性。](media/customer-portal-elements.png "客戶入口網站相依性")

客戶入口網站可作為入門起點，協助組織使用 Power Apps 入口網站建構面向外部的網站，於其中使用來自 Supply Chain Management 設備的資料。 此外也能協助組織連結雙重寫入、Supply Chain Management 和 Power Apps 入口網站。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]