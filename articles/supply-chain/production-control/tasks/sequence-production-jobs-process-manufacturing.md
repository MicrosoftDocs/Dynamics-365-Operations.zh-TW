---
title: 排序流程製造的生產作業
description: 此程序以油漆產品為例，說明如何根據顏色和包裝尺寸的優先順序循序計劃訂單。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage, PMFSeqReqRoute, PMFSeqReqRouteChanges, PMFSeqReqSchedDetailsFactBox, PMFSequenceGroup, PMFSequenceItemTable, PMFSequenceTable, PmfSeqWrkCtrCapRes
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e54cfa60fa9efd511aef8c074484b9b1a738e8cb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448551"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>排序流程製造的生產作業

[!include [banner](../../includes/banner.md)]

此程序以油漆產品為例，說明如何根據顏色和包裝尺寸的優先順序循序計劃訂單。 建立此程序的示範資料公司為 USPI。 此程序適用於生產規劃員。


## <a name="run-master-planning-for-uspi"></a>執行 USPI 的主計劃
1. 移至主計劃 > 主計劃 > 執行 > 主計劃。
2. 在主計劃欄位中，按一下下拉式按鈕開啟查詢。
3. 在列表中，按一下所選行中的連結。
    * 選擇 [主計劃]。  
4. 點選 [確定]。
    * 這將啟動主計劃，包括序列流程。 此流程可能需要幾分鐘。  

## <a name="view-planned-orders-for-the-paint-products"></a>查看油漆產品的計劃訂單
1. 移至主計劃 > 主計劃 > 計劃訂單。
2. 展開 [品項] 詳細資料 FactBox。
3. 展開 [排程] 詳細資料 FactBox。
4. 在 [計劃] 欄位中，按一下下拉式按鈕開啟查詢。
5. 在清單中，尋找並選擇所需紀錄。
    * 選擇 [主計劃]。  
6. 在列表中，按一下所選行中的連結。
7. 使用 [快速篩選] 來篩選具有「P300」值的 [品項編號] 欄位。
    * 解除鎖定以向右捲動查看訂單日期和交貨日期。 請注意，這些品項的訂單日期為「今天」，並且計劃訂單的交貨日期不按照顏色和包裝尺寸的優先順序排序，如產品名稱所示。 您可以將滑鼠懸停在品項編號上以查看產品名稱和優先順序。  

## <a name="sequence-planned-orders-for-paint"></a>排序油漆的計劃訂單
1. 關閉頁面。
2. 移至主計劃 > 主計劃 > 循序計劃訂單。
3. 展開 [品項] 詳細資料 FactBox。
4. 展開 [排程] 詳細資料 FactBox。
    * 請注意：在這裡您可以看到計劃訂單的開始日期/時間在 28 天的貯體內根據顏色和包裝尺寸進行排序。 這些期間由 [行銷活動] 欄位中的數字定義。 循序計劃訂單訂單類似於典型的計劃訂單表單，生產規劃員可以在此確定計劃訂單。  
5. 標記所有資料列。
6. 點選 [接受]。
    * 這將使用所選的 [延期] 或 [提前] 順序動作更新計劃訂單。  

## <a name="verify-the-sequence-of-the-planned-orders"></a>驗證循序計劃訂單
1. 關閉頁面。
2. 移至主計劃 > 主計劃 > 計劃訂單。
3. 展開 [品項] 詳細資料 FactBox。
4. 展開 [排程] 詳細資料 FactBox。
5. 在 [計劃] 欄位中，按一下下拉式按鈕開啟查詢。
6. 在清單中，尋找並選擇所需紀錄。
    * 選擇 [主計劃]。  
7. 在列表中，按一下所選行中的連結。
8. 使用 [快速篩選] 來篩選具有「P300」值的 [品項編號] 欄位。
    * 請注意，訂單現在根據顏色和尺寸的優先順序排序，計劃訂單從最早的訂單日期和交貨日期開始。 驗證 [計劃詳細資料] FactBbox 中的訂單日期資料行或開始日期。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]