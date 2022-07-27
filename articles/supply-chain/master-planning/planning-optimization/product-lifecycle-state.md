---
title: 排除具有特定產品生命週期狀態的產品
description: 本主題說明在使用規劃最佳化功能時，如何根據產品的生命週期狀態排除產品。
author: ChristianRytt
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 030bdea7c03dd5eb3347c1d43acd1aeabdf566602872dd8ef5aab6d16b06f503
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446862"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>排除具有特定產品生命週期狀態的產品

[!include [banner](../../includes/banner.md)]

已發佈的產品和已發佈的產品版本包括 **產品生命週期狀態** 欄位。 除其他事項外，此欄位可讓您控制在總規劃期間包括哪些產品。 您可以根據需要新增、移除和編輯生命週期狀態，方法是前往 **產品資訊管理 \> 設置 \> 產品生命週期狀態**。 針對每個產品生命週期狀態，若具有該狀態的產品應包括在總規劃期間，則將 **正在積極進行規劃** 選項設為 *是*。 當選項設為 *否*，則相關的產品和變體將被排除在所有總規劃和物料清單 (BOM) 層級的所有計算之外。

**產品生命週期狀態** 欄位留空的已發佈產品和變體被視為似乎具有產品生命週期狀態，其中 **正在積極進行規劃** 選項設為 *是*。 換句話說，它們將包含在總規劃中。

> [!NOTE]
> 為幫助避免不必要的供應建議，我們強烈建議您將所有過時的已發佈產品和變體與產品生命週期狀態建立關聯，其中 **正在積極進行規劃** 選項設為 *否*。 當您使用不可重複使用的產品設定變體時，這種方法尤其重要，因為它有助於避免浪費。

## <a name="related-resources"></a>相關資源

有關產品生命週期狀態的更多資訊，請參閱 [產品生命週期狀態概觀](../../pim/product-lifecycle.md)。

有關包括使用產品生命週期狀態從總規劃和 BOM 層級計算中排除產品的步驟的詳細資訊，請參閱 [建立產品生命週期狀態以從總規劃中排除產品](../../pim/tasks/exclude-products-master-planning.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]