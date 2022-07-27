---
title: 成本和日期控制
description: 本主題說明資產管理中的成本和日期控制。
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetBICostControlWorkspace, EntAssetWorkOrderDateControl, EntAssetWorkOrderForecastCostInfoPart, EntAssetMaintenanceCostTrans, EntAssetWorkOrderDateControlCalcDialog, EntAssetCostControl, EntAssetCostObjectCalendar, EntAssetWorkOrderCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 826e0aab8c717bb951d80aff61b2d72dad802189706f720c48e72c8a1c393ead
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446802"
---
# <a name="cost-and-date-control"></a>成本和日期控制

[!include [banner](../../includes/banner.md)]

在資產管理中，您可以計算成本，獲得實際成本摘要並且與資產、機能位置和工單的預算成本進行比較。 實際成本是以已過帳的交易記錄為基礎。

如果要將已排定的開始日期和結束日期與工單的實際開始日期和結束日期比較，也可以進行日期計算。

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>資產、機能位置和工單的成本控制

對資產、功能位置和工單的計算幾乎相同。 唯一的區別是對於資產和機能位置，您還可以在計算中包括子資產和子位置。 日期為記錄登記時的交易日期。

1. 按一下 **資產管理** > **查詢** > **資產** > **資產成本控制** 或 **機能位置成本控制**，或 **資產管理** > **查詢** > **工單** > **工單成本控制**。

2. 在 **資產成本控制** / **機能位置成本控制** / **工單成本控制** 對話方塊中，選擇要計算的時間範圍。

3. 如果需要，選擇要包含在計算中的財務維度集。

4. 如果您不想顯示成本為零的結果，在 **跳過零** 切換按鈕上選取「是」。

5. 您可使用 **程度** 欄位，指定成本控制明細相關功能位置的詳細程度。 

    例如，如果在欄位中插入數字「1」，並且您有一個多級功能位置階層，則一個功能位置的所有成本控制明細將顯示在上級，因此一個明細上的時數可能從位於較低層級的功能位置累加。

    如果將數字「0」插入 **層級** 欄位，您將看到一個詳細的結果，其中顯示了與它們相關的所有功能位置層級上的所有成本控制明細。

6. 如果您想在計算中包括該欄，在 **顯示未結承諾成本** 切換按鈕上選擇「是」。

7. 若要將與子資產關聯的成本顯示為單獨行，請在 **包括子資產** 切換按鈕上選擇 [是]。

8. 如果要限制搜尋，可以 **要包括的記錄** 快速索引標籤上選取特定資產/功能位置/工單。

9. 按一下 **確定** 以開始計算。

    下圖顯示了一個範例的 **資產成本控制** 對話方塊。

    ![資產成本控制對話方塊。](media/01-controlling-and-reporting.png)

10. 在 **資產成本控制** 頁面，按一下 **按…分組** 按鈕以顯示需要的計算詳細程度。 選定的 **分組依據** 按鈕將反白顯示。 按一下按鈕以啟用或停用。

## <a name="example-of-calculation-results-in-asset-cost-control"></a>資產成本控制中的計算結果範例

以下的螢幕擷取畫面顯示了一個範例的 **資產成本控制** 計算結果。

- **原始預算** 欄位中，顯示來自工單預測的預算成本。 
- **承諾成本** 欄位顯示法律實體已承諾支付的費用總額。 
- **未結承諾成本** 欄位顯示您已訂購或收到但尚未付款的項目、時數和服務的付款承諾。 
- **實際成本** 欄位顯示所有耗用登記過帳後的相關成本。

![資產成本控制中的計算結果範例。](media/02-controlling-and-reporting.png)

進行成本計算的另一種方法是在 **所有資產** 或 **使用中資產** 選擇多個資產。 然後，按一下 **一般** 索引標籤上的 **成本控制** 按鈕。在 **資產成本控制** 對話方塊中，選定的資產會自動插入到 **要包括的記錄** FastTab 上的 **資產** 欄位。 按一下 **確定**，即會顯示所選資產的成本計算。 可以在 **所有功能位置** 或 **有效功能位置** 中對功能位置執行同樣的程序，也可以在 **所有工單** 或 **有效工單** 中對工單執行同樣的程序。

## <a name="work-order-date-control"></a>工單日期控制

使用此頁面，可概覽比較預期的開始日期和結束日期與工單上實際的開始日期和結束日期。

1. 按一下 **資產管理** > **查詢** > **工單** > **工單日期控制**。

2. 按一下 **計算**。

3. 於 **功能位置** 欄位選擇功能位置。

4. 在 **開始日期** 和 **結束日期** 欄位填入想要計算的範圍。 將包括預期開始日期在該範圍內的所有工單。

5. 按一下 **確定**。

6. 按一下 **分組依據** 按鈕以顯示需要的計算詳細程度。 選定的 **分組依據** 按鈕將反白顯示。 按一下按鈕以啟用或停用。

## <a name="example-of-calculation-results-in-work-order-date-control"></a>工單日期控制中的計算結果範例

以下的螢幕擷取畫面顯示了一個範例的 **工單日期控制** 計算結果。

- **平均開始延遲** 欄位顯示工單的預定開始日期與實際開始日期之間的天數差異。 例如，如果實際開始日期比預定開始日期早兩天，則此欄位中將顯示「-2」。  
- **平均結束延遲** 欄位顯示工單的預定結束日期與實際結束日期之間的天數差異。 例如，如果實際結束日期比預定結束日期晚三天，則此欄位中將顯示「3」。  
- **發生次數** 欄位顯示與工單上的預計和實際開始日期以及預計和實際結束日期相關的偏差發生次數。

![工單日期控制中的計算結果範例。](media/03-controlling-and-reporting.png)




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]