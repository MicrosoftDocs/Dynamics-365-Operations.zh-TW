---
title: 規劃多個站點的貨運路線
description: 本文介紹您在 Dynamics 365 Supply Chain Management 中用於規劃貨運路線的各種元素。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate, TMSRouteSchedule, TMSRouteRateDetail
audience: Application User
ms.reviewer: kamaybac
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eff1efd7530c410b392646e39325b58cbd8bcf78
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448392"
---
# <a name="plan-freight-transportation-routes-with-multiple-stops"></a>規劃多個站點的貨運路線

[!include [banner](../includes/banner.md)]

本文介紹您在 Dynamics 365 Supply Chain Management 中用於規劃貨運路線的各種元素。

您可以將路線計劃和路線指南用於具有多個站點的複雜運輸路線。 如果定期使用相同的路線，您可以設定預定路線。

## <a name="route-plans"></a>路線計劃
路線計劃包含路段，這些路段提供有關在路線上造訪的站點以及每個路段的承運業者資訊。 您必須將路線上的站點定義為樞紐。 樞紐可以是廠商、倉庫、客戶，甚至只是您要更換承運業者的重新裝載地點。 對於每個路段，您可以定義各種費用的「即期費率」。 這裡有些範例：

-   運往指定路段的費用
-   提貨費用
-   卸貨費用

每個路線計劃都必須與路線指南相關聯。

## <a name="route-guides"></a>路線指南
路線指南定義將裝載與特定路線計劃比對的條件。 例如，您可以指定起點樞紐和目的地樞紐、集裝箱體積或重量的限制，以及承運業者、服務或群組。 路線指南可在 **費率路線工作台** 頁面上取得，在此可以手動或自動將裝載與路線比對。 如果路線指南是針對預定路線的，它也可以在 **裝載建構工作台** 頁面上取得。

## <a name="scheduled-routes"></a>預定路線
預定路線是預先定義的路線計劃，其中包含發貨日期的時間表。 預定路線和非預定路線的不同之處在於將裝載指派給路線的方式。 如果您使用 [費率路線工作台] 指派非預定路線，則僅驗證裝載和路線指南。 如果您指派預定路線，則還會考慮訂單和樞紐的日期和地址，以及路線計劃上的日期。 您不必使用 [費率路線工作台] 頁面手動將裝載指派給預定路線。 相反的，您可以使用裝載建構工作台以根據所指定預定路線其銷售訂單中的客戶地址與交貨日期建議要建構的裝載。 對於預定路線，路線計劃將具有固定的起點和目的地樞紐。 通常所有路段的承運業者和服務都是相同的，但也可以不同。 目的地樞紐是使用在路線上所造訪客戶的郵遞區號建立的。 可為一個路線計劃定義多個路線時間表。 路線計劃都必須與路線指南相關聯。 但是對於預定路線，該計劃只能與一個路線指南相關聯。 路線時間表僅用於在 **路線時間表** 頁面上建立實際路線。 當您在裝載建構工作台上建議裝載時，可以使用預設裝載範本。

## <a name="load-building-workbench"></a>裝載建構工作台
裝載建構工作台使用銷售訂單中的客戶地址和交貨日期，以及可用的預定路線，來建議裝載。 依預設，會在工作台上輸入來自路線的值。 但是，您可以選擇早於路線上 [開始] 日期的 [開始] 日期。 當建議裝載時，請檢查所有未結銷售訂單的交貨地址和交貨日期。 如果收貨地址的郵遞區號符合路線計劃中樞紐的郵遞區號，且如果交貨日期在於條件中選擇的範圍內，則建議使用銷售訂單進行裝載。 此外也會考慮裝載範本的容量。 一次只會建議一個裝載。 如果您有未納入的銷售訂單，您可能必須使用不同的裝載範本 (例如，更大卡車或集裝箱的裝載範本) 或規劃額外的交貨。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]