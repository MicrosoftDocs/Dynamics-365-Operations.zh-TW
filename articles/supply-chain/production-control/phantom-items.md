---
title: 虛擬品項
description: 本主題詳細描述虛擬行類型在 Dynamics 365 Supply Chain Management 中如何用於物料清單 (BOM) 和公式的行項。
author: johanhoffmann
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 8e1b241c826e89909590ae16c8458bc49df995bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448557"
---
# <a name="phantom-items"></a>虛擬品項

[!include [banner](../includes/banner.md)]

本主題詳細描述虛擬行類型如何用於物料清單 (BOM) 和公式的行項。

在下圖中，(a) 是產品 H 及零件 F 和 G 的 BOM，(b) 是產品 H 和零件 F 的路線表。

![兩個層級中的 BOM 結構範例。](media/product-H-part-F.png)

此圖顯示了兩個級別的 BOM 結構示例。 成品 H 代表機器組件的產品。 機器組件由兩部分組成，一個具有兩種材料 (A 和 B) 的電氣單元 (F)，另一個是也具有兩種材料 (C 和 D) 的一組包裝材料 (G)。 在機器的一般組裝過程中使用了另一種材料 (E)。

![產品 H 的工程 BOM。](media/product-H-part-B.png)

上圖表示產品 H 的工程 BOM。此結構很好地概述整個機器組件的零件和元件。 然而，儘管產品設計人員可能更願意看到以這種方式表示的 BOM，但這種結構可能無法正確表示機器在車間的建構方式。

例如，上圖中的工程 BOM 表示將電氣單元 F 組裝成單獨工單上的單獨零件。 然而在車間，判斷將電氣單元組裝為整個機器組件的一部分，而不是作為單獨的工單，可能更佳。

此工程 BOM 也表示零件 G 是單獨的零件。 但是在這種結構中，零件 G 不是代表實體部分，而是代表包裝材料的集合。

因此，儘管工程 BOM 為產品設計和維護該設計提供巨大的價值，但它可能不是支援產品製程的最合乎邏輯方式。 相較之下，製造 BOM 代表建構產品的最佳方式。

下圖顯示如何將前述的工程 BOM 轉換為製造 BOM。 在此圖中，(a) 是產品 H 的 BOM，b 是產品 H 的路線表。

在這個結構中，您可以看到沒有零件 F 和 G 的概念，且這些零件所包含的材料已提升到下一個 BOM 層級。

與具有兩個操作表的工程 BOM 不同，製造 BOM 只有一個操作表。 與零件 G 連結的包裝操作也得到提升，現在是產品 H 操作表的一部分。電氣單元的組裝是第一個操作。 這個順序很合理，因為這個單元用於下一個操作，亦即機器組裝。 最後一個操作是包裝操作，會消耗兩種包裝材料 (C 和 D)。

工程 BOM 和製造 BOM 之間的轉換是通過虛擬 BOM 行類型啟用的。 正如同「虛擬」一詞所示，在兩種 BOM 類型之間轉換的過程中，零件 F 和 G 已經消失。 在此範例中，虛擬行類型會套用到工程 BOM 中零件 F 和 G 的 BOM 行。 建立生產或批次訂單時，工程 BOM 會複製到生產或批次訂單。 然後在估算訂單時，會發生從工程 BOM 轉換到製造 BOM，如上圖所示。 從第二個圖的操作表中，輸入該操作所需的包裝材料 C 和 D。

## <a name="multilevel-phantom-bom-structures"></a>多層虛擬 BOM 結構

虛擬行類型可用於多層級 BOM 結構，如下圖所示。 在此圖中，(a) 是產品 G 的 BOM，(b) 是產品 G 的零件 E 和 F。

![多層級 BOM 結構中使用的虛擬行類型。](media/product-G-route-sheet-G.png)

如果設定零件 E 和 F 的 BOM 行，讓行類型為「虛擬」，則下圖顯示產生的製造 BOM 和路線表。 在此圖中，(a) 是產品 G 的 BOM，(b) 是產品 G 的路線表。

![產品 G。](media/product-G.png)

## <a name="phantom-and-route-network"></a>虛擬與途程網路

虛擬 BOM 也可用於具有途程網路的 BOM。 在途程網路中，一或多項操作並行執行。 下圖顯示在多層級 BOM 中使用的途程網路範例。 在此圖中，(a) 是產品 G 和零件 F 的 BOM，(b) 是產品 G 和零件 F 的路線表，其中具有途程網路。

![在多層級 BOM 中使用的途程網路範例。](media/product-G-part-F.png)

在下圖中，(a) 是產品 G 和零件 F 的 BOM，(b) 是產品 G 和零件 F 的路線表。

![產品 G 和零件 F 的 BOM，以及產品 G 和零件 F 的路由表。](media/product-G-part-F-with-route-sheet.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]