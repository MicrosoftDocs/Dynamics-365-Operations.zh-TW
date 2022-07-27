---
title: 執行看板程序工作
description: 此程序著重於執行看板程序工作。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ac6f0f6139fe17532f6fbd996b314e0b14f3d90
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447924"
---
# <a name="execute-kanban-process-jobs"></a>執行看板程序工作

[!include [banner](../../includes/banner.md)]

此程序著重於執行看板程序工作。 第一個工作按預期數量完成，沒有錯誤。 第二個工作已完成，但發生錯誤。 建立此程序的示範資料公司為 USMF。 此程序適用於機器操作員。


## <a name="select-a-kanban-job"></a>選擇看板工作
1. 前往生產控制 > 看板 > 流程作業看板。
2. 在工作單元欄位中，按一下下拉式按鈕開啟查詢。
3. 按一下資源群組 1250 所在的列。 這會篩選工作清單，僅顯示工作單元 1250 的工作。
    * 標記狀態為「已規劃工作」的列。  

## <a name="complete-a-job-with-expected-quantity"></a>按預期數量完成工作
1. 展開或摺疊「詳細資料」區段。
    * 此區段顯示有關卡片編號、品項編號、訂購數量和活動名稱的重要資訊。  
2. 展開或摺疊「生產說明」區段。
    * 此區段顯示活動的生產說明。 可以透過文字、圖片、繪圖和其他文件提供說明。  
3. 按一下啟動。
    * 選擇未完成的工作。 使用「工作」狀態欄位中的狀態圖示可查看工作狀態。      
4. 按一下完成。
    * 工作即可按預期品質完成。  

## <a name="complete-a-job-with-errors"></a>工作已完成，但發生錯誤
1. 按一下啟動。
    * 工作完成後，系統會自動選取清單中的下一個工作。 因此您不必在按一下啟動前選取工作。  
2. 在「動作窗格」上按一下 [製造]。
3. 按一下完成 (詳細資料)。
4. 在清單中，標記所選資料列。
5. 在「錯誤數量」欄位中，輸入一個數字。
6. 在「良品數量」欄位中，輸入一個數字。
7. 按一下確定。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]