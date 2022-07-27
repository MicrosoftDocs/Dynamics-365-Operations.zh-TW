---
title: 還原看板作業狀態
description: 此程序側重於還原不正確的看板作業狀態。
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
ms.openlocfilehash: 771c3b95be05904c84483473a533c708964fbe62
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448719"
---
# <a name="revert-kanban-job-status"></a>還原看板作業狀態

[!include [banner](../../includes/banner.md)]

此程序側重於還原不正確的看板作業狀態。 這在機器操作員更新錯誤作業或設定錯誤狀態的情況下很實用。 在此程序中，看板作業錯誤地登記為已準備，然後還原其狀態。 建立此程序的示範資料公司為 USMF。 此程序適用於在精益製造公司工作的車間主管或機器操作員。


## <a name="open-process-board-for-the-work-cell"></a>打開該工作單元的程序版
1. 前往流程作業看板。
2. 在工作單元欄位中，輸入或選擇一個值。
    * 選擇工作單元 1260。  

## <a name="prepare-kanban-job"></a>準備看板作業
1. 按一下 [準備]。
    * 如果由於顯示為灰色而無法點選 [準備]，請確保所選看板作業的狀態為「已計劃」，其以空白看板圖示表示。 如果準備失敗，請確保揀料單中的所有材料都可用。  
2. 在清單中，選擇已準備作業。
    * 選擇您已準備的第一個作業。  
    * 請注意，作業狀態為「已準備」，以看板圖示內的三角形表示。  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>還原已準備看板作業的狀態
1. 在清單中，標記所選資料列。
    * 選擇您準備好的第一個作業。  
2. 在「動作窗格」上按一下 [製造]。
3. 按一下 [還原狀態]。
    * 當滿足以下條件時，您可以使用替代看板規則：- 兩個規則的補貨原則相同。  - 兩個規則的生產流程版本相同。  - 兩個規則所提供的產品相同。  - 兩個規則的的任意下游活動必須相同，這些活動決定該看板規則的最後一項活動。  - 必須為這兩個規則設定相同的提供庫存維度。  - 承辦單位的狀態必須為「未指派」。  - 事件看板的設定必須相同。  
    * 確認該新狀態為「已計劃」。  
4. 按一下 [確定]。
5. 在清單中，取消標記所選資料列。
    * 選擇相同的作業。  
    * 請注意，該看板作業的作業狀態已還原為「已計劃」，以空的看板圖示表示。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]