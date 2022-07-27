---
title: 建立提單
description: 本主題介紹如何在使用倉庫管理流程時建立提單。
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b79408e21e9acda12617cf35464007e58ae1b5fe
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448590"
---
# <a name="create-a-bill-of-lading"></a>建立提單

[!include [banner](../includes/banner.md)]

本主題介紹如何在使用倉庫管理流程時建立提單。  

提單是運送物品之公司與承運商之間的法律文件。 該文件伴隨已出貨的物品，並在物品到達目的地時用作運送收據。 如果您正使用倉庫管理，有兩種方法可以產生提單：

  -   使用 **提單** 頁面手動建立報告。
  -   從 **負載規劃工作台** 產生報告。

如果您要從 **負載規劃工作台** 產生提單，則貨物狀態必須是 **已發貨。** 如果裝載的貨物不止一件，則每批貨物都會建立一份提單。 建立提單後，您可以在 **提單** 頁面進行變更。

## <a name="master-bill-of-lading"></a>主提單
如果一次裝載的貨物不止一件，您可以產生主提單。 這與提單具有相同的配置和資訊，但包含了所有貨物的彙總內容。 如果在 **運輸管理參數** 頁面上將 **在單次裝載多個貨物時建立主提單** 的選項設定為 **是**，則若您從 **負載規劃工作台** 建立提單時，會自動產生主提單，並且有不止一批貨物。 您也可以透過按一下 **相關資訊**&gt;**提單** 來取得提單清單。 如果您是手動建立提單，您可以在 **提單** 頁面建立主提單。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]