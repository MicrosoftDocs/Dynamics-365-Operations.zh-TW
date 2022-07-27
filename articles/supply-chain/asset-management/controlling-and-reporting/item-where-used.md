---
title: 品項使用位置
description: 本主題說明如何在資產管理中取得品項使用位置的概覽。
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2308fc4fabe541b8affeba5860a3154f81e8903e4853fd36d777f15a503d9dd8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447033"
---
# <a name="item-where-used"></a>品項使用位置

[!include [banner](../../includes/banner.md)]

 

您可以對特定品項進行計算，以大致瞭解該品項在資產管理中的使用位置。 結果顯示品項在其生命週期中的使用脈絡。 **品項使用位置** 頁面可以從主資產管理功能表開啟，也可以從以下頁面存取：

- [資產 BOM](../objects/object-BOM.md)

- [資產類型預設的備用零件](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [維護作業類型類別和維護作業類型、維護作業類型變體、維護作業工種和維護檢查清單](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [維護預測](../work-orders/maintenance-forecasts.md)

- [採購](../work-orders/procurement.md)

- [工單採購](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>進行品項使用位置的計算

1. 按一下 **資產管理** > **查詢** > **品項使用位置**，或選擇前述頁面之一的 **品項使用位置** 按鈕。

2. 在 **品項使用位置** 對話方塊中，在 **品項編號** 欄位選擇您要進行計算的品項。

3. 您可使用 **等級** 欄位，指定品項行有關功能位置的詳細程度。 

    例如，如果您在欄位中插入數字「1」，且您有一個多等級功能位置結構，則功能位置的所有品項行都將顯示在頂層。 因此，行上的關係/數量可以從位於較低等級的功能位置累加起來。 
    
    如果將數字「0」插入 **等級** 欄位，您將看到一個詳細的結果，其中顯示了與它們相關的所有功能位置層級上的所有品項行。

4. 在 **包含** 區段於您要納入計算的切換按鈕選擇「是」。

5. 按一下 **確定** 以開始計算。

6. 在 **品項使用位置** 索引標籤選擇 **分組方式** 按鈕以顯示需要的計算詳細程度。 選定的 **分組依據** 按鈕將反白顯示。 按一下按鈕以啟用或停用。

7. 如果要顯示與品項相關的維度，請按一下 **顯示維度**，然後選擇要顯示的維度。

## <a name="example"></a>範例

在下面的螢幕擷取畫面中，您可以看到品項編號「1000」的品項使用位置計算範例。

![品項使用位置計算範例。](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]