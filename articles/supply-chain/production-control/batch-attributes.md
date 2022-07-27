---
title: 批次屬性
description: 本主題說明批次屬性。 批次屬性是庫存批次中的原物料和成品的特徵。 本主題還詳細說明如何指派批次屬性，以及如何在保留批次時搜尋它們。
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup, WHSBatchAttribReserve
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ceb971e7468245297f2359317533b123a3a4f83a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447804"
---
# <a name="batch-attributes"></a>批次屬性

[!include [banner](../includes/banner.md)]

本主題說明批次屬性。 批次屬性是庫存批次中的原物料和成品的特徵。 本主題還詳細說明如何指派批次屬性，以及如何在保留批次時搜尋它們。

批次屬性是庫存批次中的原物料和成品的特徵。 受到環境條件、用於生產批次的原材料的品質或成品的結果等因素影響，批次屬性可能會有所不同。 用到的批次屬性的數量和類型可能因產業而有巨大差異。 下面是兩個範例，展示如何使用批次屬性：

-   在起司產業中，生產起司的原材料之一的牛奶，擁有脂肪含量和重量百分比等屬性。 由牛奶製成的起司可以具有其他屬性，例如含水量和發酵時間。
-   在鋼鐵工業中，生產出的鐵可能會有鎂含量、銀含量和鋅含量等屬性。

為了更好地管理屬性的數量和類型，您可以使用批次屬性群組。 以這種方式，您不必單獨新增每個屬性。

## <a name="assign-batch-attributes"></a>指派批次屬性
您可以將批次屬性指派給庫存批次中的單個產品，也可以指派給與特定客戶關聯的產品。 若要在客戶層面指派批次屬性，您必須先在產品層面指派。 在追蹤維度群組中，產品的批次維度必須設定為 **啟用中**。 若要將批次屬性指派給給單個產品，請使用產品專屬頁面。 如果屬性專屬一個客戶的產品，請使用客戶專屬頁面。 當您對產品新增屬性時，您也要定義其他參數。 這裡有些範例：

-   **整數** 或 **分數** 類型的屬性，其最小和最大範圍。
-   **整數** 或 **分數** 類型的屬性，其容錯動作。 如果屬性值超出最小和最大範圍限制，則動作可以是警告訊息或錯誤訊息。
-   屬性的目標值。 該值是屬性的最佳值，適用於所有屬性類型。

在產品資訊管理的 **發佈產品** 頁面選定的產品，您可以讀取其頁面。 將批次屬性指派給產品後，到 **庫存批次屬性** 頁面，您可以新增特定值給屬性。

## <a name="reserve-batches"></a>保留批次
當您為銷售訂單執行批次保留以履行客戶訂單時，或者為生產訂單揀貨和保留批次時，您可以搜尋批次屬性。 對於想要的批次屬性，搜尋有助於找到其產品具有該屬性的庫存批次。 在您找到一個或多個批次後，您可以將產品保留到原始庫存交易記錄明細。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]