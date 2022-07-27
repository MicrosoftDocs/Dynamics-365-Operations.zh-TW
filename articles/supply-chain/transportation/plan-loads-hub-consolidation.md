---
title: 使用樞紐合併概觀規劃裝載
description: 本文介紹當您從不同倉庫將裝載交付給同一個客戶時，或者當您從同一個倉庫中收到多個廠商的裝載時，可在樞紐中合併貨件的功能。
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "92273"
- intro-internal
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd47a5745719873cc491d93b9a98a7fde609fe38
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449754"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>使用樞紐合併概觀規劃裝載

[!include [banner](../includes/banner.md)]

本文介紹當您從不同倉庫將裝載交付給同一個客戶時，或者當您從同一個倉庫中收到多個廠商的裝載時，可在樞紐中合併貨件的功能。

當您從不同倉庫將裝載交付給同一個客戶時，或者當您將多個廠商的裝載時交付到同一個倉庫時，在樞紐中合併貨件會很有用。

## <a name="building-loads"></a>建構裝載
您必須先在 **運輸管理參數** 頁面上啟用 **在運輸途中規劃** 選項，才能使用樞紐合併。 您還必須建立會進行合併的樞紐。 下圖顯示樞紐合併的範例。 在這種情況下，來自不同倉庫的銷售訂單將發往同一個客戶。 基本裝載是透過使用 **裝載規劃工作台** 頁面以一般方式根據銷售訂單建立的。 若要先將兩件裝載於樞紐中合併，再交付給客戶，請在 **裝載規劃工作台** 頁面中的 **運輸工具** 欄位中選擇 **樞紐合併**。 當您為每個裝載選擇正確的樞紐時，裝載會將該樞紐作為「卸貨」目的地。 您在 **裝載規劃工作台** 頁面的 **供應與需求** 區段中也有兩個「運輸工具要求行」。 之後，您可以將這兩行新增到新裝載中。 這個新裝載將具有兩個銷售訂單行，而且還會將樞紐作為「取貨」地址，將客戶 A 作為「卸貨」目的地。 然後就可以像任何其他裝載一般，將這三個裝載設定費率與路線。 您可以為每個裝載選擇系統建議的任何承運業者。 [![樞紐合併。](./media/hubconsol.jpg)](./media/hubconsol.jpg) 您還可以使用相同的方法來合併多個轉移訂單的裝載。 在這種情況下，上圖中的客戶 A 是一個倉庫。 或者，您可以合併多個採購訂單的裝載，其中裝載是從不同的廠商交付到同一個倉庫。 您可以擁有多個合併樞紐，並且可以在多個樞紐中合併來自不同倉庫的更多裝載。 在建構基本裝載並使用樞紐合併選項後，您可以使用合併的運輸工具要求行來建構新裝載。 然後，您對裝載設定費率與路線。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]