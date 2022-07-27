---
title: 從計畫中刪除看板作業
description: 此程序側重於透過將作業狀態恢復為「未規劃」，以從計劃中刪除規劃的流程看板作業。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 838270189e08065f791c9e58888351025e0a6df8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448635"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>從計畫中刪除看板作業

[!include [banner](../../includes/banner.md)]

此程序側重於透過將作業狀態恢復為「未規劃」，以從計劃中刪除規劃的流程看板作業。 建立此程序的示範資料公司為 USMF。 此程序適用於工廠主管或生產規劃員。


## <a name="find-a-planned-kanban-job"></a>查找規劃的看板作業
1. 移至生產控制 > 看板 > 看板作業排程。
2. 在工作單元欄位中，按一下下拉式按鈕開啟查詢。
3. 在列表中，按一下所選行中的連結。
    * 選擇工作單元 1250。  
4. 按一下 [選取]。
5. 在顯示作業狀態欄位中，選取「已排程」。

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>從計畫中刪除規劃的看板作業
1. 在清單中，尋找並選擇所需紀錄。
    * 選擇具有「已規劃」狀態的作業，例如開始於 2012 年 12 月 19 日的作業。  
2. 在動作窗格上，按一下計畫。
3. 按一下 [還原工作狀態]。
4. 按一下 [確定]。
    * 這會將目前作業狀態從「已規劃」還原為「未規劃」並將其從流程板上刪除。   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]