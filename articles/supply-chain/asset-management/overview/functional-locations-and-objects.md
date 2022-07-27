---
title: 機能位置與資產
description: 本主題介紹資產管理中的機能位置與資產。 資產管理是 Dynamics 365 Supply Chain Management 中用於管理資產和維護作業的進階模組。
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e0bf90d99a8bd093817f9e804e8075e779428f1fadb3128c5a455ca839dece55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446976"
---
# <a name="functional-locations-and-assets"></a>機能位置與資產

[!include [banner](../../includes/banner.md)]

 

本主題介紹資產管理中的機能位置與資產。 資產管理是 Dynamics 365 Supply Chain Management 中用於管理資產和維護作業的進階模組。

## <a name="overview"></a>概觀

資產管理與其他財務和營運應用程式的多個模組無縫整合。 下圖顯示與其他模組的介面。

![圖表顯示資產管理與其他模組的介面方式。](media/01-overview-image.png)

資產管理可讓您有效地管理和執行您公司中多種類型設備的所有管理和維護任務。 此設備包括機器、生產設備和車輛。 資產管理也支援眾多產業的解決方案。

下圖顯示了資產管理涵蓋的主要功能概觀。

![顯示資產管理中主要功能的圖表。](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>機能位置與資產

機能位置會用於管理位置上的資產。 這種管理包括在機能位置上的資產成本追蹤。 機能位置結構是階層式的，而這些位置可以有子位置。 機能位置的結構是靜態的。 換句話說，位置是不能改變的。 資產可以安裝在機能位置，且可以根據需要稍後安裝在其他機能位置。

資產成本會一律跟隨資產的位置。 換言之，如果您在新機能位置安裝資產，則該資產會自動使用與新機能位置相關的財務維度。 因此，資產成本會一律與目前安裝資產的機能位置相關。 當您的公司對機能位置進行專案控制和報告時，這種財務維度的自動處理可有助於確保完全的成本追蹤。

您建構機能位置階層的方式，取決於貴公司對維護內部設備或服務客戶設備的需求。 下圖顯示依據地理位置的機能位置範例。

![依據地理位置顯示機能位置的圖表。](media/03-overview-image.png)

下圖顯示依據客戶的機能位置範例。

![依據客戶顯示機能位置的圖表。](media/04-overview-image.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]