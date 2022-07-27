---
title: 資產和工單
description: 本主題介紹資產管理中的資產和工單。
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
ms.openlocfilehash: a2872dc84ec11ae7fad9fd5b225b9207f13280db334cc0d010a3d6749a591ee2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446676"
---
# <a name="assets-and-work-orders"></a>資產和工單

[!include [banner](../../includes/banner.md)]

 

本主題介紹資產管理中的資產和工單。 資產和工單是資產管理的核心部分。 *資產* 是需要持續維護和保養的機器或機器零件。 資產可以按階層結構建立，並且可以與功能位置相關聯。 維護作業可在資產結構中的所有層級處規劃。

對每個資產設有各種資料，例如產品資訊、資產規格以及所需的維護計劃。 下圖顯示資產資料的概觀，以及資產與作業類型的關聯。 紅色文字用於可顯示繼承和相依性的範例。

![顯示與作業類型相關資產資料的圖表。](media/05-overview-image.png)

每個工單都有工單類型，例如預防性維護、矯正性維護或檢查。 工單包含一或多個工單作業。 每個工單作業都定義必須在資產上執行的作業和相關的作業類型。 相關作業類型的範例包括 10,000 公里、50,000 公里、1 年大修和安全檢查。 一個工單可以與多個資產相關。

下圖說明工單中關鍵資料的概觀。

![顯示工單中關鍵資料的圖表。](media/06-overview-image.png)

一個工單可以與另一個工單相關，且作業類型可以包含會建立工單的後續作業。 一般而言，工單之間沒有相依性。 因此，它們可以變更其工單生命週期狀態，並且可以彼此獨立地排程。

可以透過與矯正性、預防性或反應性維護相關的各種方式建立工單。 您也可以手動建立工單。 下圖顯示自動或手動建立工單的程序概觀。

![顯示自動或手動建立工單的圖表。](media/07-overview-image.png)

當您要在工單上排程和執行維護作業時，必須完成幾個步驟。 下圖說明工單中程序的概觀。

![顯示處理工單概觀的圖表。](media/08-overview-image.png)

> [!NOTE]
> 一般而言，當您在 Dynamics 365 Supply Chain Management 和 **資產管理** 模組中工作時，您可選擇 **新增** 建立新記錄、選擇 **編輯** 更新現有記錄，及選擇 **儲存** 儲存新的或已編輯的資料。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]