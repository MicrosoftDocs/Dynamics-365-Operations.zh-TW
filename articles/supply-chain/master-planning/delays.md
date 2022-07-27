---
title: 延誤
description: 本主題提供有關主計劃中延遲日期的資訊。 如果主計劃計算的最早履行日期晚於請求日期，則延遲日期是交易收到的實際到期日期。
author: ChristianRytt
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e89830feea12b4f5703e0eda622729887dd9bf46
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448650"
---
# <a name="delays"></a>延誤

[!include [banner](../includes/banner.md)]

本主題提供有關主計劃中延遲日期的資訊。 如果主計劃計算的最早履行日期晚於請求日期，則延遲日期是交易收到的實際到期日期。

主計劃可以根據提前期、材料可用性、產能可用性和各種計劃參數計算交易的最早履行日期。 

如果主計劃計算的訂單日期早於目前日期，則無法按時履行訂單。 因此，訂單被延遲。 在這種情況下，主計劃會從目前日期向前計劃訂單並包括提前期。 這些提前期從任何較低等級的元件項目開始。 然後訂單會收到一個延遲的日期。 延遲日期是依據目前資料的實際到期日期。 總體規劃還計算延遲天數。 

在某些情況下，您可能會選擇不計算延遲，例如當使用者知道他們可以選擇其他交貨方式來加快交貨時間時。 

您可以設定如何計算險種群組的延遲。 然後，您可以稍後將險種群組附加到項目。 

在 **總體規劃參數** 頁面上，您可以設定延遲計算的開始時間。 如果在此時間之後完成訂單，則會在訂單的延遲日期中增加一天的延遲。 

> [!NOTE]
> 在早期版本中，計算的延遲被稱為 *期貨消息*，延遲的日期被稱為 *期貨日期*，延遲交易被稱為 *未來設定的交易*。

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>具有多個 BOM 等級的生產設定延遲有限
當您在具有多個 BOM 等級的生產設定中處理延遲時，請務必注意，只有在物料正上方 (在 BOM 結構中) 導致延遲的物料才會作為主計劃的一部分進行延遲更新運行。 BOM 結構中的其他項目將不會套用延遲，直到第一次主計劃運行，當頂層的計劃訂單被批准或確定時。 

為了解決這個已知限制，可以在下一次主計劃運行之前批准 (或確定) 位於 BOM 結構頂部的具有延遲的生產訂單。 這樣，延遲批准的計劃生產訂單的延遲將被保留，所有基礎元件都將相應更新。
由於 BOM 結構中的其他延遲，動作訊息還可以用於識別可移至以後日期的計劃訂單。

## <a name="desired-date"></a>希望日期

在 **計劃訂單** 頁面，在 **延誤** 索引標籤是計劃訂單的 **希望日期**。 計劃訂單的所需日期是延遲的基準日期，這是一個計算日期，等於 **申請日期** (由 **淨需求** 計算)。 如果計劃訂單是 BOM 列、生產列或看板列，則所需日期會依據 **要求日期**，且希望日期不會顯示在 **計劃訂單** 頁面。

## <a name="additional-resources"></a>其他資源

[險種設定](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]