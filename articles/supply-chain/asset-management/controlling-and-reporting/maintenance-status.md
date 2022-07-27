---
title: 維護狀態
description: 本主題說明如何在資產管理中計算維護狀態。
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 138e2e72fbf761d209d288c2bd778c08519b9c69b0715f4466d4838255a2a31e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447009"
---
# <a name="maintenance-status"></a>維護狀態

[!include [banner](../../includes/banner.md)]

 

在資產管理中，您可以為特定期間的新的、使用中，和已完成的維護要求、工單和維護停機時間活動進行概觀計算。 您還可以查看同一時期完成的條件評定數量。 使用此計算以取得傳入和已完成維護要求與工單的工作量概覽。

## <a name="make-a-maintenance-status-calculation"></a>進行維護狀態計算

1. 按一下 **資產管理** > **查詢** > **維護狀態**。

2. 在 **計算狀態** 對話方塊中，選擇要在 **開始日期** 和 **結束日期** 欄位中進行計算的時間範圍。

3. 您可使用 **等級** 欄位，指定維護明細有關機能位置的詳細程度。 

  例如，如果在欄位中插入數字「1」，並且您有一個多等級機能位置結構，則一個機能位置的所有維護明細，將顯示在最高等級，因此一個明細上的狀態可能從位於較低等級的機能位置累加。 
  
  如果將數字「0」插入 **等級** 欄位，您會看到一個詳細的結果，其中顯示了與它們相關的所有機能位置層級上的所有維護明細。

4. 按一下 **確定** 以開始計算。

5. 按一下 **分組依據** 按鈕以顯示需要的計算詳細程度。 選定的 **分組依據** 按鈕將反白顯示。 按一下按鈕以啟用或停用。

6. 在您每一次透過啟用或停用 **分組依據** 按鈕，或透過新期間的計算進行變更後，不要忘記按一下 **更新** 按鈕。

7. 如果要建立新的維護狀態計算，請按一下 **狀態**。

>[!NOTE]
>顯示在 **維護狀態** 中的結果僅包括具有實際開始日期和時間的維護要求和工單。 結束日期和時間可能為空白。

## <a name="example-1"></a>範例 1

在以下的螢幕擷取畫面中，**年** 和 **月** 按鈕已啟用。 在這些 **分組依據** 選項已選取後，您將取得每月和與維護要求和工單相關的工作負載和輸送量的總體概觀。 

![每月工作負載範例。](media/13-controlling-and-reporting.png)

## <a name="example-2"></a>範例 2

在下面的螢幕擷取畫面中，已新增有關機能位置的資訊。 現在已經可以做到跨機能位置比較工作負載和輸送量，這些位置可能代表地理位置、工廠或工作區域。 

![機能位置的每月工作負載範例。](media/14-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]