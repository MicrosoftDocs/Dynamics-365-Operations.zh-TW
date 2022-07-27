---
title: 維度式產品設定概觀
description: 以維度式產品設定代表了一種簡單的解決方案，用於從單一基準產品及其物料清單建立許多產品變型。
author: t-benebo
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19821"
- intro-internal
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8811d4a43dba05e63b270893600a622527834901
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449676"
---
# <a name="dimension-based-product-configuration-overview"></a>維度式產品設定概觀

[!include [banner](../includes/banner.md)]

以維度式產品設定代表了一種簡單的解決方案，用於從單一基準產品及其物料清單建立許多產品變型。

維度式產品設定是三種內建的產品設定技術之一。 另外兩種技術是預定義的變型和條件式設定。 這三種技術都以基準產品為起點，並允許使用者為一個基準產品建立多個產品變型。

## <a name="key-concepts"></a>關鍵概念
維度式產品設定是根據以下關鍵概念：

-   基準產品
-   產品維度設定
-   設定群組
-   物料清單 (BOM)
-   設定路徑
-   設定規則

### <a name="product-masters"></a>基準產品

基準產品是任何產品設定過程的起點。 對於維度式產品設定，您需要具有這種特定設定技術的基準產品和包含設定產品維度的產品維度群組。

### <a name="configuration-product-dimension"></a>產品維度設定

產品維度設定是用於識別具有維度基礎設定技術的基準產品之產品變型。 設定維度值由使用者輸入，且應有助於識別各別的產品變型。

### <a name="configuration-groups"></a>設定群組

設定群組在中央存放庫中進行定義，可用於所有維度式產品設定模型。 設定群組與各個 BOM 明細相關聯，並將一組互斥的明細組合在一起。 這意表示只能為單一產品變型選擇群組中的一個明細。

### <a name="bill-of-materials-bom"></a>物料清單 (BOM)

BOM 代表維度式產品設定的建構區塊。 它必須包括可用於任何產品變型的所有不同產品。 BOM 中的每一個明細都可以參考一個設定群組。 如果一個明細未參考設定群組，它將包含在所有產品變型中。

### <a name="configuration-route"></a>設定路徑

設定路徑決定了設定群組的順序，因為它們將在產品設定過程中向使用者顯示。

### <a name="configuration-rules"></a>設定規則

設定規則代表一種機制，用於確保包含在 BOM 中的一個設定群組中的產品強制包含或排除同一 BOM 中不同設定群組中的產品。

## <a name="product-modeling-process"></a>產品建模流程
為維度式基準產品建構產品模型的自然順序從定義相關設定群組開始。 確保將在 BOM 中使用的所有產品都已發佈給為其建構產品模型的公司，這一點很重要。 有了這些建構區塊，使用者就可以建立 BOM 並將設定群組指派給所有相關的 BOM 明細。 當 BOM 完成後，便可以進行設定路徑定義，以便按正確的順序對設定群組進行排序。 [![維度式產品建模過程。](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) 如果某些來自不同設定群組的產品必須或不能一起使用，您可以建立將這些產品強制建立關係的設定規則。 在透過 BOM 版本將 BOM 與維度式基準產品聯繫在一起並且都已核准和啟用後，您便可以建立產品設定並為每個設定輸入名稱。 設定可以在產生任何交易之前進行定義，也可以在需要特定設定時進行。

### <a name="suggested-use"></a>建議使用

維度式設定技術最適用於可變性有限的產品，標準產品維度尺寸、顏色、樣式和設定的組合不適合用於識別特定產品變型。 例如具有車架高度、車輪尺寸、剎車類型和不同齒輪的自行車。

### <a name="next-step"></a>下一步 

以下八項工作指南按照您應完成的順序列出。 

1.  [建立維度式基準產品](tasks/create-dimension-based-product-master.md)
2.  [釋出維度式基準產品](tasks/release-dimension-based-product-master.md)
3.  [完成已發布基準產品的基本設定](tasks/complete-basic-setup-released-product-master.md)
4.  [定義設定群組](tasks/define-configuration-groups.md)
5.  [為維度式基準產品建立物料清單](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [定義設定路徑](tasks/define-configuration-route.md)
7.  [建立設定規則](tasks/create-configuration-rules.md)
8.  [建立維度式設定](tasks/create-dimension-based-configurations.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]