---
title: 使用看板工作轉移物料
description: 此程序會著重於執行取款看板工作以轉移物料。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11771bbedc9fe4bdfaaa074c449cd329ce1a1d8f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448068"
---
# <a name="transfer-materials-with-kanban-jobs"></a>使用看板工作轉移物料

[!include [banner](../../includes/banner.md)]

此程序會著重於執行取款看板工作以轉移物料。 建立此程序的示範資料公司為 USMF。 此程序適用於倉庫工作人員。


## <a name="display-transfer-jobs"></a>顯示轉移工作
1. 前往生產控制 > 看板 > 轉移工作的看板。
2. 展開或摺疊篩選器區段。
    * 在篩選器部分，您可以透過篩選生產流程、活動名稱、從倉庫和位置以及到倉庫和位置來指定要查看的工作。  
3. 在倉庫發貨欄位，輸入 '11。
4. 在運送位置欄位，輸入 '12'。

## <a name="start-a-transfer-job"></a>開始轉移工作
1. 在列表中，取消所選資料列 (如有)。
2. 在清單中選擇第4列。
    * 選擇狀態為未規劃的第一個工作。 確保這是唯一選擇的工作。  
3. 按一下啟動。
    * 請注意，此圖示表示工作已啟動。  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>選擇第二個轉移工作並更改數量
1. 在清單中，尋找並選擇所需紀錄。
    * 您可以選擇多個工作，但現在請選擇第 5 資料列。  
2. 在清單中，尋找並選擇所需紀錄。
    * 確保上一步中的工作是唯一選擇的工作。 取消選擇所有其他工作。  
3. 記下工作數量欄位中的值以供稍後參考
4. 將工作品質設為 '30'。
    * 注意警告！ 不允許轉移 30。 根據看板規則的設置，只能轉移原始數量。  
5. 使用先前在工作品質欄位中記下的值
    * 將工作數量設定為之前的值。  

## <a name="start-the-second-transfer-job"></a>開始第二次轉移工作
1. 按一下啟動。
    * 這將啟動資料列 5 中的工作轉移。  

## <a name="complete-both-transfer-jobs"></a>完成兩個轉移工作
1. 在清單中選擇第4列。
    * 現在在資料列 4 和資料列 5 選擇了兩個轉移工作。  
2. 按一下「完成」。
    * 這將完成兩個工作的轉移。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]