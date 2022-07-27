---
title: 計算品項預測
description: 本主題說明如何在資產管理中計算品項預測。
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5773149760ecb2a26f4916036fe36c9cc04f654039dee4eab9bfac86eb02e1fd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446628"
---
# <a name="calculate-item-forecast"></a>計算品項預測

[!include [banner](../../includes/banner.md)]

 

您可以進行的產能負載計算，如上一區段所述，您也可以進行品項預測計算，如下所述：

- 維護排程明細  
- 尚未排程的工單  
- 已排程的工單

如果您想要了解在特定期間的預期品項耗用 (完成工作訂單需要的備件以及其他品項) 的摘要，這很有用。 可以對所有資產或選定資產進行品項預測的計算。 您還可以計算維護停機時間活動 (**所有維護停機時間活動** 或 **現行維護停機活動**)，或計算工作訂單池 (**所有工單池** 或 **現行工單池**)。

1. 按一下 **資產管理** > **查詢** > **品項預測**，或 **資產管理** > **一般** > **工單池** > **所有工單池** / **現行工單池**> 在清單中選取工單池 >**品項預測** 按鈕，或者是 **資產管理** > **一般** > **維護停機時間活動** > **所有維護停機時間活動** / **現行維護停機活動**> 在清單中選取維護停機時間活動 >**品項預測** 按鈕。

2. 在 **計算品項預測** 對話方塊中，於 **開始日期/時間** 和 **結束日期/時間** 欄位，選取一個計算週期。

3. 如果您想在預測計算中包括維護排程明細，在 **包含維護計劃** 切換按鈕上選取「是」。

4. 如果您想在預測計算中包括工單作業，在 **包含工單** 切換按鈕上選取「是」。

5. 您可使用 **程度** 欄位，指定品項預測明細相關功能位置的詳細程度。 

      例如，如果在欄位中插入數字「1」，並且您有一個多級功能位置結構，則一個功能位置的所有維護排程明細和工單將顯示在上級，因此一個明細上的時數可能從位於較低層級的功能位置累加。 
  
      如果將數字「0」插入 **程度** 欄位，您將看到一個詳細的結果，其中顯示了與它們相關的所有功能位置層級上的所有維護排程明細和工單。

6. 按一下 **確定** 以開始計算。

7. 在 **按…分組** 群組，按一下相關按鈕以顯示需要的計算詳細程度。 在下面的螢幕擷取畫面中，選定的 **按…分組** 按鈕以藍色醒目提示。 按一下按鈕以啟用或停用。

8. 如果您想查看與品項相關的產品、儲存或追蹤維度，請按一下 **顯示尺寸** 按鈕。 選取相關核取方塊，然後按一下 **確定**。

![圖 1。](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]