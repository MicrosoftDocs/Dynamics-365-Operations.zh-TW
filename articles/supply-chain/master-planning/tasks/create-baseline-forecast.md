---
title: 指南：建立基準預測
description: 生產計劃者可以透過使用時間序列預測模型或複製歷史需求來建立基準預測。
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 843e0b3827851e1251a2c77269859bb7903f69ec
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449097"
---
# <a name="guide-create-a-baseline-forecast"></a>指南：建立基準預測

[!include [banner](../../includes/banner.md)]

生產計劃者可以透過使用時間序列預測模型或複製歷史需求來建立基準預測。 此程序顯示如何複製歷史需求，以使用一個項目分配索引鍵為所有產品建立基準預測。

## <a name="set-up-an-item-allocation-key"></a>設定項目分配索引鍵

1. 前往 **主計劃 > 設定 > 公司間規劃群組**。
2. 使用快速篩選器尋找記錄。 例如，以 *10* 這個值來篩選 *名稱* 欄位。
    * 需求預測是可以跨越法人實體執行的。 因此您需要在一個公司間規劃群組中設定要產生預測的所有公司。  
3. 在清單中，尋找並選擇所需紀錄。
4. 選擇 **項目分配索引鍵**。
    * 選擇所有您要建立預測的項目分配索引鍵。  
5. 在清單中，標記所選資料列。
    * 選擇 D_Aloc 項目分配索引鍵。  
6. 選擇 **>**。
7. 關閉頁面。
8. 關閉頁面。

## <a name="set-up-the-demand-forecasting-parameters"></a>設定需求預測參數

1. 前往 **主計劃 > 設定 > 需求預測 > 需求預測參數**。
2. 展開 **預測演算法參數** 區段。
3. 在 **預測產生策略** 欄位中，選擇 **複製歷史需求**。
4. 選擇 **儲存**。

## <a name="create-a-baseline-forecast"></a>建立基準預測

1. 前往 **主計劃 > 預測 > 需求預測 > 產生統計基準線預測**。
2. 請在 **開始日期** 欄位中輸入日期。
    * 如果您有從 2015 年 1 月 1 日開始的銷售訂單，請輸入此日期。 如果您不這麼做，請輸入銷售訂單的最早日期。  
3. 請在 **截止日期** 欄位中輸入日期。
    * 輸入銷售訂單的最後日期，例如 *2015-03-31*。  
4. 請在 **開始日期** 欄位中輸入日期。
    * 輸入 *2015-04-01*。 此日期將自動計算為下一個預測時段的開始日期。  
5. 展開 **要包括的記錄** 區段。
6. 選擇 **篩選**。
7. 在清單中，標記所選資料列。
    * 標記 **欄位** = *公司間規劃群組* 的資料列。  
8. 在 **條件** 欄位中，輸入一個值。
    * 輸入您在第一個任務中使用的公司間規劃群組 (例如 *10*)。  
9. 在清單中，尋找並選擇所需紀錄。
    * 選擇 **欄位** = *項目分配索引鍵* 的資料列。  
10. 在 **條件** 欄位中，輸入一個值。
11. 選擇 **確定**。
12. 展開 **進階參數** 區段。
13. 在 **預測時段** 欄位中，選擇 *月*。
14. 在 **預測範圍** 欄位中，輸入 *3*。
15. 在 **凍結時間範圍** 欄位中，輸入 *1*。
16. 選擇 **確定**。

## <a name="visualize-the-demand-forecast"></a>視覺化需求預測

1. 前往 **主計劃 > 預測 > 需求預測 > 調整需求預測**。
2. 在彙總檢視資料表中，選擇第 1 列第 2 欄中的儲存格。 這是您建立預測的第二個月。
3. 將 **QtyCell** 設為 *400*。
    * 在儲存格中，輸入與預測數字不同的數字，例如 400。  
4. 您已對預測進行了手動調整。 請在下一步中注意圖形指示。
5. 選擇 **預測行詳細資訊**。
    * 在此頁面中，您可以查看正確性值、歷史需求和預測。 您也可以變更預測。  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]