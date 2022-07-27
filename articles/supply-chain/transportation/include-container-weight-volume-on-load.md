---
title: 包括貨櫃重量和裝載體積
description: 本主題介紹如何設定並套用功能，以納入貨櫃重量和裝載體積。
author: Henrikan
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52b42bd0b97564a493a50331d1424ca8084b389b29518f012f443d9cf722efe7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447138"
---
# <a name="include-container-weight-and-volume-on-load"></a>包括貨櫃重量和裝載體積

[!include [banner](../includes/banner.md)]

將貨櫃重量和體積納入負載上的功能，清楚地表示了正在裝載的貨櫃和品項的總重量與體積。

裝載包含了單一裝運或多個裝運，且這些裝運包含屬於單一銷售訂單或多個銷售訂單的不同項目。 項目會存放在貨櫃內，貨櫃會裝載在負載上。 貨櫃外的項目也可以是負載的一部分。 根據這些條件，系統會透過考慮貨櫃與項目的重量和體積，來計算負載的重量和體積。

如果計算值不精確，您可以透過輸入裝載重量和體積的實際值來進行調整。 重量和體積的值會用於運輸管理過程。 例如，這些值會在費率路線工作台中使用，以協助定義負載費率和路線，並也用於運輸招標和駕駛員簽入。

## <a name="where-it-applies"></a>適用處

將貨櫃重量和體積包含在負載上的功能也適用於運輸管理流程，例如費率路線工作台、運輸招標和駕駛員登記。

## <a name="how-it-is-set-up"></a>設定方式為何

應考慮裝載的貨櫃數量，是依據貨櫃的重量和體積以及使用貨櫃的百分比來計算的。

-   若要設定貨櫃的重量和體積，請按一下 **倉庫管理** \> **設定** \> **貨櫃** \> **貨櫃類型**。

-   如要設定容器利用率百分比，請按一下 **倉庫管理** \> **設定** \> **貨櫃** \> **貨櫃群組**，然後在 **容器利用率百分比** 欄位輸入一個值。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]