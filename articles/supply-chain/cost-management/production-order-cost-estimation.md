---
title: 生產訂單成本估算
description: 本文提供有關生產成本估算的資訊。 生產成本估算提供按計劃生產訂單數量生產項目的預計材料和產能消耗成本。
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5debf62a3a0fc3ae8828473d7dd593c690e298712e5ed696077db1562796943
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446733"
---
# <a name="production-order-cost-estimation"></a>生產訂單成本估算

[!include [banner](../includes/banner.md)]

本文提供有關生產成本估算的資訊。 生產成本估算提供按計劃生產訂單數量生產項目的預計材料和產能消耗成本。 

建立生產訂單後，您必須估算生產成本。 目的是估算生產過程的項目和途程消耗，因為這些估計會使用作為後續排程和生產過程的基礎。

## <a name="production-cost-estimation"></a>生產成本估算
生產成本的估算以下列資訊為根據：

-   生產訂單上的數量
-   生產物料清單 (BOM) 上的組件
-   生產途程中的傳送作業
-   適用於組件和營運的間接成本
-   截至計算日期的有效活動成本資料

如果生產 BOM 中有虛擬明細項目，則計算會反映虛擬的組件和傳送作業。 您可以使用估算任務重新計算估計成本，讓估計成本反映出更新的資訊。 例如，更新資訊可能是生產訂單上的數量、生產 BOM 上的組件、生產途程中的傳送作業、適用於這些組件和作業的間接成本，或截至重新計算日期的有效成本資料。 估計成本的計算也會根據成本加價法的生產項目的銷售價格。 估計成本的計算可以視需要套用至反映已連結至生產訂單的其他生產訂單的參考訂單。

## <a name="view-the-estimated-costs"></a>查看估計成本
執行估算後，您可以在 **價格計算** 頁面上查看結果。 估算作業會計算下列值：

-   **生產成本** – 生產成本是估算最重要的部分。 可以顯示執行生產訂單的完整成本和生產的總銷售價格。 這個值是估算中所有成本明細的總和。
-   **路線或資源成本** – 路線或資源成本是生產操作的成本。 包含例如設定時間、執行時間和開銷等元素的成本。
-   **材料成本** – 材料成本是指生產項目所需的 BOM 組件的成本和價格。 這些成本之前已經確定並輸入到系統中。

## <a name="other-uses-of-cost-estimation"></a>成本估算的其他用途
成本估算也提供下列資訊：：

-   有意義的報價
-   訂單盈利能力的估算
-   原料使用估算
-   與過去生產相比的成本資訊
-   預算和預測資訊
-   為維持特定成本所需的生產規模估算






[!INCLUDE[footer-include](../../includes/footer-banner.md)]