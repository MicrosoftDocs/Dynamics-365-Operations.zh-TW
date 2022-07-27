---
title: 使用計劃最佳化進行庫存標記
description: 本主題提供關於您使用計算最佳化，對確定的訂單進行庫存標記時可用的選項資訊。
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: dc94ca8b15d626d8ff64f50718d7d2e3e0326144465f3d27787805220842849f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446613"
---
# <a name="inventory-marking-with-planning-optimization"></a>使用計劃最佳化進行庫存標記

[!include [banner](../../includes/banner.md)]

本主題提供關於您使用計算最佳化，對確定的訂單進行庫存標記時可用的選項資訊。

*標記* 用於連接供應與需求。 類似於 *需求追蹤*，表示總體規劃預期滿足需求的方式。 從規劃的角度來看，主要不同在於標記比需求追蹤時間更久。

引入標記是為了支持先進先出 (FIFO) 和後進先出 (LIFO) 的特殊成本計算方案。 但是，現在也適用於一些非成本核算的方案。 供應與需求之間的標記是可選且幾乎是永久性的。 使用者可以手動移除標記，也可以展開銷售訂單行，選取 **移除標記** 選項，來移除標記。

需求追蹤是由總體規劃滿足期間控制，連結需求與所需供應。 每次執行規劃時可以更新需求追蹤，以最佳化的方式滿足需求所需的供應。 當總體規劃更新需求追蹤的資訊時，會採用任何現有標記。

需求追蹤會包括相關標記、現有保留、現有訂單保留，根據以下順序：

1. 標記需求與供應
1. 現有保留
1. 現有訂單保留

當您確定計劃訂單時，**確認** 對話方塊會提供一個 **更新標記**，您可以用於確認期間建立的訂單設定的標記選項欄位。 選擇下列其中一個值：

- **不** – 不應用庫存標記。
- **標準** – 根據需求追蹤更新庫存標記。 需求訂單 (需求) 被標記為履行訂單 (供應)。 如果履行訂單上仍有一些剩餘數量，則不會進行標記，參考資訊會維持空白。 例如，如果 100 ea 的銷售訂單與 150 ea 的訂購單建立需求追蹤，則參考資訊將僅分配給該銷售訂單。
- **擴展** – 需求訂單 (需求) 和履行訂單 (供應) 都進行標記，無論履行訂單上剩餘的數量如何。 例如，如果 100 ea 的銷售訂單與 150 ea 的訂購單建立需求追蹤，則參考資訊將分配給銷售訂單和訂購單。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]