---
title: 批次平衡
description: 本主題介紹批次平衡程序。
author: johanhoffmann
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMTable, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: a9e69b4d9213e57e5a920c7adda934ba845d17410c17d9c8a6356d717870ac23
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447315"
---
# <a name="batch-balancing"></a>批次平衡

[!include [banner](../includes/banner.md)]

本主題介紹如何支援批次平衡程序。

如需更多資訊，請觀看[批次平衡影片](https://www.youtube.com/watch?v=4SNLWsU9KyI&feature=youtu.be)。

在批次平衡程序中，生產批次中使用的成分總量是根據選定產品批次中的有效成分密度計算的。

## <a name="products-that-have-an-active-ingredient"></a>含有有效成分的產品

產品可以通過其有效成分的密度來定義。 使用具有最小值、最大值和目標量的產品專屬批次屬性來模型化產品的有效成分。

批次屬性的目標量表示產品中有效成分的預估百分比。 最小值和最大值表示與目標量偏差的可接受範圍。 例如，它們可以用作產品收貨時批次的可接受容許量。

一種產品只能有一種有效成分。 要指定產品的有效成分，您必須首先定義產品專屬的批次屬性。 然後，您將該屬性關聯爲產品的基本屬性。

在產品級別，您還必須指定應如何記錄一批產品的有效成分量：作為採購收貨程序的一部分或作為品質檢驗訂單程序的一部分。

要將基本屬性與產品相關聯，需要進行以下設定：

- 產品必須是批次控制的。 若要使產品受批次控制，您必須將追蹤維度群組指派給給具有啟用中「批次」維度的產品。

- 指示成分量的屬性必須定義為產品的產品專屬批次屬性。

若要查找和編輯批次的有效成分的實際值：
1. 前往 **庫存管理\>查詢和報告\>追蹤維度\>批次**。
1. 從網格中選取一個批號。
1. 在動作窗格上，開啟 **查看** 索引標籤，接著選取 **庫存批次屬性**。

## <a name="ingredient-types-and-how-they-interact-in-the-batch-balancing-process"></a>成分類型及其在批次平衡程序中的交互作用

建立的配方明細可以具有以下成分類型之一：

- 無
- 使用中
- 補償
- 填料

本節的其餘部分將提供範例，展示每種成分類型的運作方式。 這些範例基於以下配方，其中總批次大小為 100 公升。

| 成分類型 | 品項編號 | 配方明細數量 | 單位 |
|---|---|---|---|
| 無 | A | 20 | 公升 |
| 使用中 | B | 30 | 公升 |
| 補償 | C | 10 | 公升 |
| 填料 | D | 40 | 公升 |

下表概述了每個範例的結果。

| 品項編號 | 成分類型 | 預估數量 | 平衡數量 | 有效數量 | 單位 | 基值 |
|---|---|---|---|---|---|---|
| A | 無 | 20 | 20 | | 公升 | |
| B | 使用中 | 30 | 25.71 | 9.00 | 公升 | 30.00 |
| C | 補償 | 10 | 14.72 | | 公升 | |
| D | 填料 | 40 | 39.57 | | 公升 | |

### <a name="active-ingredients"></a>有效成分

具有基本屬性的產品被新增到配方明細時，會被稱為配方的 *有效成分*。 批次訂單的配方包含有效成分，則可用於批次平衡程序。 對於配方中的每種成分，批次平衡程序會估算生產產品需要的量。 數量的預估是基於選取批次中有效成分的密度。

#### <a name="active-ingredient-example"></a>有效成分範例

成分 B 具有基本屬性 X 和 30 的目標量，包含在每 100 公升產品需要 30 公升成分 B 的配方中。 建立批次大小為 100 公升的批次訂單。 批次訂單開始，在批次平衡程序中，使用者選擇了效力等級為 35 的成分 B 批次。 由於 35 的效力等級高於 30 的目標量，因此成分 B 的平衡量使用效力值與批次目標量的比率乘以估計數量，因而減少。 平衡數量的計算如下所示：

(30 ÷ 35) × 30 公升 = 25.71 公升

### <a name="none-ingredients"></a>無成分

當您套用批次平衡程序，且 **成分類型** 是 *沒有*，批次訂單中配方明細的預估數量和平衡數量是一樣的。

#### <a name="none-ingredient-example"></a>沒有成分範例

成分 A 被指派 *沒有* 類型，並新增到產品配方中。 每 100 公升成品配方需要 10 公升成分 A。 當批次訂單需要 200 公升時，成分 A 的預估數量和平衡數量均計算為 20 公升。

### <a name="compensating-ingredients"></a>補償成分

補償成分可以抵消或補充產品中有效成分的作用。 因此，消耗的補償成分的數量取決於產品的效力：

- **反作用**–如果有效成分的量超過預期，您必須加入較少的補償成分。

- **補充作用**–如果有效成分的量少於預期，您必須加入較多的補償成分。

有效成分和補充成分之間的關係在 **補償原則** 頁面設定。

按照以下步驟設定成分之間的關係。

1. 選取 **產品資訊管理 \> 計費和物料和配方 \> 配方**。
1. 打開配方明細，然後選取 **成分** 打開 **補償原則** 頁面。
1. 選擇代表補償原則的明細，然後選擇要補償的有效成分。

在補償原則中，您還可以輸入一個正或負補償因子來指定補償的量，以及該原則應該是抵銷的還是補充的。 正因素表示補充效應，負因素表示抵銷效應。

#### <a name="compensating-ingredient-example"></a>補償成分範例

成分 B 是一種有效成分，具有基本屬性 X 和目標量 30。 在一個配方中，每 100 公升成品需要 30 公升成分 B。 成分 C 是一種補償成分，同一配方中包含 10 的數量。 為補償原則設定了 1.10 的補償係數。 因此，補償成分減少的平衡數量是有效成分的平衡量與預估需要量之差乘以 1.10。

在範例中 *有效* 成分類型，需要的有效成分的平衡量計算為 25.71，預估需要量計算為 30。 在這種情況下，補償成分的平衡量計算如下：

1. 確定估計量和平衡量之間的差異：  
    25.71 – 30 = –4.29

1. 結果乘以補償因子：  
    4.29 × 1.10 = –4.72

1. 預估的補償量減少 –4.72 以確定平衡補償量：  
    10 – (–4.72) = 14.72

因為 1.10 是一個正補償因子，所以這個補償原則具有補充作用。 在這種情況下，有效成分比預期的更有效。 因此，需要更多的補償成分。

### <a name="filler-ingredients"></a>填料成分

*填料成分* 是一種中性成分，被用於達到成品需要的輸出量。 填充量的調整方式是根據有效成分和補償成分與標準量相比的變化來計算的。

#### <a name="filler-ingredient-example"></a>填料成分範例

您已完成產品配製，其中包含 100 公升配方大小的成分 A、B、C 和 D。 您已經計算了所有成分類型的平衡量，除了 *填料* 在一明細上使用的成分類型。
填充成分的平衡量計算為批次大小 100 公升與成分 A、B 和 C 的和的差值：

100 – (20 + 25.71 + 14.72) = 39.57

## <a name="the-batch-balancing-process"></a>批次平衡程序

批次平衡程序是在 **批次平衡** 頁面執行。
選取 **成本管理\>批次訂單**，然後在 **程序** 索引標籤，選取 **批次平衡**。 在批次訂單中可用的批次平衡狀態為 **開始**。

一般來說，如果配方至少有一個配方明細的 **成分類型** 是 *有效*，則批次平衡可用於批次訂單。 (有關此規則的例外情況，請參閱本主題後面的“不適用於批次平衡的批次訂單”區段。)

批量平衡程序可以分為兩個次程序：

1. 平衡批次成分
1. 確認並發佈配方

### <a name="balance-batch-ingredients"></a>平衡批次成分

在平衡批次成分次程序中，生產批次中使用的成分總量是根據選定具有效成分的批次來計算的。 作為規則，只有完整涵蓋所有成分的計算才能完成。 在批次訂單設定為生產批次時，您不能僅平衡這部分的批次。

> [!NOTE]
> 您不能保存計算，然後再完成批次平衡程序。 如果你關閉 **批次平衡** 頁面，您必須重複計算過程才能完成該程序。

### <a name="confirm-and-release-the-formula"></a>確認並發佈配方

計算出成分數量後，您可以確認並發布配方。 發布程序會有所不同，取決於在倉庫管理程序是否啟用了產品：

- 如果倉庫管理程序啟用了產品，則會根據 倉庫管理程序的原則將配方明細發布到倉庫。 配方明細發佈的量與平衡量相符，並且為有效成分選定的特定批次發佈。

    > [!NOTE]
    > 配方明細只能在批次平衡程序中發佈到倉庫。 儘管還有其他選項可以將生產物料下達到倉庫，但這些選項不能用於配方明細。

- 如果沒有在倉庫管理程序啟用的產品，則在您確認並發佈配方時會為該產品建立生產揀料單。

在單一配方中，您可以組合在倉庫管理程序啟用的產品和未在倉庫管理程序啟用的產品。 當兩種類型的產品包含在一個配方中時，倉庫管理程序啟用的產品將發佈到倉庫。 沒有在倉庫管理程序啟用的產品，則在確認並發佈配方時會為該產品建立生產揀料單。

### <a name="batch-orders-that-arent-applicable-for-batch-balancing"></a>不適用於批次平衡的批次訂單

如果配方具有至少一個其 **成分類型** 是 *有效* 的配方明細，則批次訂單適用於批次平衡的規則，此規則有兩個例外。

1. 如果配方包含的有效成分為倉庫管理程序啟用的產品，但批次編號在保留階層結構中的下方位置，則批次訂單不適用於批次平衡。
1. 如果配方測量單位與有效成分庫存的測量單位不同，則批次訂單不適用於批次平衡。

不適用於批次平衡的批次訂單走完批次訂單的常規程序週期。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]