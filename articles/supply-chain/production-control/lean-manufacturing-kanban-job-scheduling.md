---
title: 精益製造的看板作業排程
description: 本文提供有關看板作業排程的視覺控制項，以及各種看板作業排程方式的資訊。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f70c3cf44ce90b13250836013636920267d2016d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448284"
---
# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>精益製造的看板作業排程

[!include [banner](../includes/banner.md)]

本文提供有關看板作業排程的視覺控制項，以及各種看板作業排程方式的資訊。  

**看板作業排程** 頁面提供精益製造工作單元的視覺排程控制項。 該頁面提供所有看板作業概覽和多種篩選功能。 您可以從該頁面前往有關看板設定和執行的所有其他頁面。

## <a name="automatic-scheduling-of-kanban-jobs"></a>看板作業的自動排程
如果您設定看板規則的 **自動規劃數量** 參數，即可自動觸發排程作業。 將 **自動規劃數量** 設為 **1** 時，每個看板作業就會在建立時立即進行規劃， 進而產生一系列先提取先服務作業。 如果將 **自動規劃數量** 設為大於 1 的值，系統會先將看板作業分組，再進行規劃。 

這個概念可讓看板數量縮至小於實際經濟批量。 例如特定品項 (或品項系列) 的經濟批量為 30， 請使用看板規則，將產品數量和 **自動規劃數量** 的值分別設為 10 和 **3**，而不是建立產品數量為 30 的看板。 雖然必須有三個取消規劃的作業才能使用自動規劃為工作單元看板作業排程，但規劃員和工廠主管可以清楚得知，兩個取消規劃的作業可能正在等候執行。 計劃員或工廠主管隨後可以透過手動規劃或建立額外看板，將這兩項作業投入生產。

## <a name="manual-scheduling"></a>手動排程
Microsoft Dynamics AX 2012 導入了看板排程板來進行手動排程。 手動排程可以與自動排程合併使用。 看板排程板可讓您規劃及取消規劃作業、按順序移動作業，或將作業移至不同期間。 如果作業的看板規則 **自動規劃** 值大於 **0**，您可以手動取消規劃。 不過，出現下一個自動規劃事件 (即建立新看板) 時，系統會重新規劃這些作業。 以下選項可用於手動排程：

-   **排程** 會根據到期日期為選定的作業排程。 (此選項類似於自動規劃。)
-   **從開始日期向前排程** 會嘗試根據到期日期為所選作業排程，但會指定的最早開始日期限制結果。
-   **逆向** 會將期間內所選的已排程作業序列往後移。
-   **正向** 會將期間內所選的已排程作業序列往前移。
-   **上一個期間** 會將所選的已排程作業移至上一個期間的開頭或結尾。
-   **下一個期間** 會將所選的已排程作業移至下一個期間的開頭或結尾。
-   **計劃**&gt;**還原作業狀態** 可讓您將已排程的作業取消排程。

## <a name="lean-scheduling-groups"></a>精益作業計畫群組
每種顏色代表一個精益作業計畫群組。 精益作業計畫群組可以任意定義為通用群組或單一工作單元專屬群組。 您可以將品項和維度任意指派給計畫群組。 例如，在繪圖單元中，計畫群組可以代表產品顏色。 在基於特定工具要求的工作中，品項可能按工具要求分組，而包裝工作單元可能按包裝範本將品項分組。 您可以選擇是否對精益作業群組套用顏色，但建議使用。 這樣有助於清楚掌握計畫狀態。 舉例來說，您可以輕鬆看出哪天生產了哪些顏色，立即瞭解如何最佳化這項工作。

## <a name="work-cell-capacity-and-period-capacity"></a>工作單元產能和期間產能
精益作業工作單元的產能一律為同時產能。 也就是說，一個工作單元中的多個作業可以同時處於活動狀態。 您可以透過輸送量和時數這兩種模式追蹤產能。

### <a name="throughput"></a>輸送量

工作單元產能定義為參考期間 (標準工作日、週或月) 的平均輸送量。 然後系統會根據分配給工作單元的日曆工時，計算每天或每週的實際產能。 作業載入的產能為作業數量，會根據工作單元中的品項輸送量比率調整。

### <a name="hours"></a>時數

每天或每週可用產能由指派給工作單元的日曆定義。 作業載入的產能為活動週期，會根據工作單元中的品項數量 (預設活動數量對照實際作業數量) 和輸送量比率調整。

#### <a name="period-capacity-factbox"></a>期間產能 FactBox

**看板作業排程** 清單頁面中的 FactBox 顯示所選工作單元的可用和預訂期間產能。 視生產流程模型中的所選排程期間而定，期間會顯示天數或週數。

## <a name="additional-resources"></a>其他資源





[!INCLUDE[footer-include](../../includes/footer-banner.md)]