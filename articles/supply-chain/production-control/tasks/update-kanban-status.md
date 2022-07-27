---
title: 更新看板狀態
description: 當看板被錯誤清空或收到的看板需要清空時，需要更新看板狀態。
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3fd19febe38d5d0a201d5a50bc57ddb541e12051
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448713"
---
# <a name="update-kanban-status"></a>更新看板狀態

[!include [banner](../../includes/banner.md)]

當看板被錯誤清空或收到的看板需要清空時，需要更新看板狀態。 建立此程序的示範資料公司為 USMF。 此程序適用於工廠主管。


## <a name="find-the-kanban"></a>尋找看板。
1. 移至生產控制 > 看板 > 看板。
2. 打開處理單元狀態欄篩選。
3. 點選 [清除]。
    * 這將重設篩選。  
4. 使用快速篩選器尋找記錄。 例如，在卡片編號欄位使用「000149」的值進行篩選。

## <a name="change-emptied-status-to-received-status"></a>將已清空狀態變更為已接收狀態
1. 點選 [還原空的處理單元]。
2. 點選 [確定]。
    * 請注意，處理單元狀態為「已接收」。  

## <a name="change-received-status-to-emptied-status"></a>將已接收狀態變更為已清空狀態
1. 點選 [空看板]。
2. 在清單中，標記所選資料列。
    * 請注意，處理單元狀態為「已清空」。  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]