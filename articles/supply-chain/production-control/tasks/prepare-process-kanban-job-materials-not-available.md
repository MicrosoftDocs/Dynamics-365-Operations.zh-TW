---
title: 當材料不可用於工作單元時，準備流程看板作業
description: 當某些材料無法用於工作單元時，此程序側重於準備流程看板作業，因此有必要從倉庫中挑選材料。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f75cdbc6ce6f7e427bf266c90428d73c065eac3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448932"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>當材料不可用於工作單元時，準備流程看板作業

[!include [banner](../../includes/banner.md)]

當某些材料無法用於工作單元時，此程序側重於準備流程看板作業，因此有必要從倉庫中挑選材料。 “材料可用時準備流程看板作業”程序是建立此程序的先決條件。 此程序適用於機器操作員。 建立此程序的示範資料公司為 USMF。

1. 前往生產控制 > 看板 > 流程作業看板。
2. 在工作單元欄位中，按一下下拉式按鈕開啟查詢。
3. 在列表中，按一下所選行中的連結。
    * 選擇工作單元 1250。  
4. 在清單中，尋找並選擇所需紀錄。
    * 選擇看板 000356。  
5. 在清單中，尋找並選擇所需紀錄。
    * 在清單中，取消選取第4列。 或如果您尚未完成“當材料可用時準備流程看板作業”工作，請選擇第 4 列。  
6. 切換揀料單部分的擴充。
    * 供應狀態中的無項目圖示表示工作單元缺少48件項目 P0002。  

## <a name="transfer-materials-to-work-cell"></a>將材料轉移到工作單元
1. 切換轉移作業部分的擴充。
2. 使用 [快速篩選器] 篩選具有「P0002」值的品項編號欄位。
3. 在清單中，尋找並選擇所需紀錄。
4. 按一下 [開始]。
    * 轉移正在進行中。  
5. 按一下 [完成]。
    * 品項 P0002 現在在看板作業的揀料單中可用。 這意味著我們可以用所有需要的材料準備看板。  
6. 按一下 [準備]。
    * 請注意，作業狀態中的圖示表示該作業現已準備就緒。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]