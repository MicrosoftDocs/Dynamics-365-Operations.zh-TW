---
title: 排程看板作業
description: 此程序著重於為特定工作單元安排流程看板作業。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cab3af0802ae6fa942460cfdd9c0819e1d31d4b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449175"
---
# <a name="schedule-kanban-jobs"></a>排程看板作業

[!include [banner](../../includes/banner.md)]

此程序著重於為特定工作單元安排流程看板作業。 [材料不可用時準備流程看板作業] 程序是建立此程序的先決條件。 建立此程序的示範資料公司為 USMF。 此作業適用於使用看板的工廠主管和生產規劃員。


## <a name="select-kanban-jobs-for-a-work-cell"></a>為工作單元選擇看板作業
1. 移至生產控制 > 看板 > 看板作業排程。
2. 展開 [期間產能 FactBox]
    * 展開 [看板 FactBox]。  
3. 在工作單元欄位中，按一下下拉式按鈕開啟查詢。
4. 在清單中，標記所選資料列。
    * 選擇工作單元 1250。 這將篩選檢視表以僅顯示 1250 工作單元的作業。  
5. 在列表中，按一下所選行中的連結。
6. 按一下 [選取]。

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a>在第一個可用期間排程看板作業
1. 在清單中，標記所選資料列。
    * 選擇具有 [未規劃狀態] 清單的第一行。 [作業狀態] 欄位中的點圖示表示未規劃。  
2. 按一下 [排程]。
    * 這將在第一個可用期間排程看板作業。  
    * 請注意，該看板作業已移至清單末尾，因為它已新增到從今天開始的期間。  
    * 如果從今天開始的期間已滿，則作業將移至第一個可用期間。  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a>為特定日期安排兩個看板作業
1. 在清單中，選擇第 1 列。
    * 請查看 [作業狀態] 欄位中顯示 [未規劃狀態] 的第一行。  
2. 在清單中，選擇第 2 列。
    * 請查看 [作業狀態] 欄位中顯示 [未規劃狀態] 的第二行。 現在您已選擇前兩個作業。  
3. 點選 [從日期排程] 以打開下拉式對話方塊。
4. 核取或取消核取 [複寫產能不足反應方塊]。
    * 此選項可讓您覆寫預設產能不足反應。  
5. 在 [產能不足反應] 欄位中，選擇 [新增到要求的期間]。
    * 此選項確保將作業新增到要求的期間，無論工作單元是否可能超載。  
6. 按一下 [排程]。
    * 請注意，這兩個作業都新增到所需的期間。  
    * 在 [期間產能] 區段可查看每個期間的負載。 [使用量] 欄位顯示此期間的預定使用量。 如果該期間預定的使用量高於此期間的可用產能，則會選擇超載使用量。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]