---
title: 計算材料耗用
description: 本文提供有關與材料耗用計算相關之各種選項的資訊。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e62d49b5fa2b26c34106e5bbf3dfbc27145e5c4e9acf798b8faef273d8957e51
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447273"
---
# <a name="calculate-material-consumption"></a>計算材料耗用

[!include [banner](../includes/banner.md)]

本文提供有關與材料耗用計算相關之各種選項的資訊。 

以下與材料耗用計算相關的選項可在 **物料清單** 頁面、**細項詳細資料** FastTab 上的 **設定** 和 **逐步耗用** 索引標籤找到。

## <a name="variable-and-constant-consumption"></a>變數和常數耗用
在 **耗用是否可變** 欄位中，您可以選擇應將耗用計算為常數數量還是變數數量。 如果生產需要固定數量或體積，無論生產的數量為何，請選擇 **常數**。 如果成品中所需的材料數量與生產的成品數量成正比，請選擇 **變數**，這是預設設定。

## <a name="calculating-consumption-from-a-formula"></a>從公式計算耗用
在 **公式** 欄位，您可以設定計算材料耗用的各種公式。 如果使用預設值 **標準**，耗用量不是根據公式計算的。 以下公式配合 **高度**、**寬度**、**深度**、**密度** 和 **常數** 欄位運作：

-   高度 \* 常數
-   高度 \* 寬度 \* 常數
-   高度 \* 寬度 \* 深度 \* 常數
-   (高度 \* 寬度 \* 深度 / 密度) \* 常數

## <a name="rounding-up-and-multiples"></a>向上進位和倍數
**向上進位** 和 **倍數** 欄位可讓您向上進位材料耗用值。 例如，您可以根據為生產挑選原材料的處理單位來向上進位該值。 下列選項可在 **向上進位** 欄位使用：**數量**、**度量** 和 **耗用**。

### <a name="quantity"></a>數量

如果您選擇 **數量** 作為向上進位機制，數量必須是指定數量的倍數。 例如，如果需要整數，請在 **倍數** 欄位裡面選擇 **1**。 數字會向上進位到可以被 1 整除的數量。

### <a name="measurement"></a>度量

通常您會選擇 **度量** 作為原材料為特定尺寸時的向上進位機制。 例如，成品需要一根 2 公尺長的金屬管，金屬管以 4.5 公尺的長度存放。 此時 **度量** 向上進位機制可用於計算生產特定數量的成品，需要多少金屬管。 在此例中，**公式** 欄位設為 **高度 \* 常數**。 **高度** 欄位設為 **2**，代表成品所需的金屬管長。 **倍數** 欄位設為 **4.5**，代表金屬管長 4.5 公尺。 計算方式如下：

1.  10 件成品所需的倍數：10 ÷ 2 = 5 件
2.  總耗用量：4.5 × 5= 22.5 公尺的金屬管

假設每耗用 5 根金屬管，就會報廢 0.5 公尺的管子。

### <a name="consumption"></a>耗用

原材料必須為產品的特定處理單位的整批提取時，通常選擇 **耗用** 作為向上進位機制。 例如，生產一件成品使用 2 夸脫塗料，然後塗料每罐 25 夸脫。 此時 **耗用** 向上進位機制可用於將耗用量向上進位為 25 夸脫罐的整數。 如果必須生產 180 件成品，以下是對所需塗料量的計算：

1.  所需塗料，不含廢料：180 × 2 = 360 夸脫
2.  罐數：360 ÷ 25 = 14.4，向上進位為 15
3.  所需塗料，含廢料：15 × 25 = 375 夸脫

## <a name="step-consumption"></a>逐步耗用
逐步耗用於計算數量間隔中的常數耗用。 如果您在 **設定** 索引標籤的 **公式** 欄位選擇 **逐步耗用**，可以在 **逐步耗用** 索引標籤加入有關逐步的資訊。可以按生產數量的間隔設定固定耗用數量。 例如，逐步耗用設定如下表所示。

| From series | 數量 |
|-------------|----------|
| 0.00        | 10.0000  |
| 100.00      | 20.0000  |
| 200.00      | 40.0000  |

物料清單 (BOM) 數量為 1，生產數量為 110。 耗用的公式為 From series (Quantity) = 耗用量。 因為生產數量是 110，所以屬於「From 100 series」。 因此數量為 20。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]