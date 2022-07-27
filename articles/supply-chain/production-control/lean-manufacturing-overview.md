---
title: 精益製造概述
description: 本文提供 Dynamics 365 Supply Chain Management 精益製造功能概述與說明。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow, Kanban, KanbanQuantityOverview, KanbanAssignCard, KanbanCirculatingCards, KanbanRules, WHSKanbanWaveTableManagePickingListPool
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19371"
- intro-internal
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e0c8b5ec4d4a391773e32a61a321c28868678baa
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449769"
---
# <a name="lean-manufacturing-overview"></a>精益製造概述

[!include [banner](../includes/banner.md)]

本文提供 Dynamics 365 Supply Chain Management 精益製造功能概述與說明。

精益製造提供可將精益作業模型化的工具。 這些工具可支援並促進以下概念和商務活動：
-   將製造和物流程序模型化為生產流程，建立精益製造基礎。
-   使用看板發出需求信號，實施精益拉式系統。
-   監控及維護看板作業。

精益製造架構由生產流程、活動和看板規則組成。 這些結構與 Supply Chain Management 程序完全整合。 您可以在混合模式的製造環境中使用精益製造，結合各種供應、生產和採購策略。 這些策略包括生產訂單、加工業的批次訂單、採購訂單和轉移訂單。

| **重要注意事項**                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 您可以使用 Supply Chain Management 來支援以看板實施的精益製造程序。 然而，能否成功落實精益原則取決於您使用的內部業務程序，以及實際的生產條件和環境。 |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a>將製造和物流程序模型化為生產流程
若要建立精益製造基礎，需將製造和物流程序模型化為生產流程。 這項活動包括以下工作：
1.  確定要實施精益補貨策略的程序，然後將這些程序模型化為生產流程。 然後，您可以分析及簡化程序。 落實精益作業的目標之一是透過改善材料和資訊流程來減少浪費。
2.  將生產流程定義為說明材料流程的一系列活動。 轉移活動代表一或多種產品移動至其他位置的程序。 程序活動代表套用於產品的增值作業。
3.  建立生產流程版本，定義產距時間要求。 這些要求用於計算生產流程中每個活動的週期時間。 您可以建立多個生產流程版本，然後使用這些版本改進程序。

## <a name="using-kanbans-to-signal-demand-requirements"></a>使用看板發出需求信號
拉式系統僅在需要貨物時才生產貨物。 這種做法可縮短交期及減少多餘的庫存。 您可以根據生產流程，使用看板來規劃、追蹤及處理相關需求。 若要建立看板架構，請建立看板規則，定義看板建立時間以及如何滿足要求。 您可以建立兩種類型的看板規則。 製造規則建立看板處理作業，撤銷看板規則建立轉移看板轉移作業。 您可以設定以下補貨策略：
-   **固定數量** 看板規則與固定數量的承辦單位相關，代表活動看板數量固定不變。 每當一個看板中的所有產品都消耗完畢，且承辦單位已手動清空時，就會建立一個相同類型的新看板。 建立固定數量看板規則時，您可以計算最適當的看板數量和使用的產品數量。 計算時請將預測、未結算訂單的實際需求、補貨品項交期和歷史需求納入考量。
-   **排程** 看板規則補充由總體規劃計算的需求。 總體規劃會產生已規劃看板，這些看板可固定在看板中。
-   **事件** 看板規則補充來自銷售訂單明細、生產 BOM 明細、看板明細或最低庫存設定的需求。 事件看板產生時會與來源需求建立關聯。

建立看板時，會根據看板規則中定義的看板流程活動，產生一或多個看板作業。

## <a name="monitoring-and-maintaining-kanban-jobs"></a>監控及維護看板作業
您可透過精益製造，掌握看板規則管理的製造和物流活動目前狀態。 因此，您可以計劃並排定以下工作的優先順序：

-   取得目前看板作業排程的概覽。
-   規劃並重新為看板作業排程。
-   追蹤及登錄看板作業狀態。

以下清單列出專門的看板：
-   看板作業調度 – 提供看板作業的概述。 看板顯示一個或多個工作單元的看板作業及其狀態。 系統會根據生產流程模型定義的規劃週期 (天或週) 列出作業。 看板還會顯示每個規劃期間的容量消耗，以便您監控已排程的負載。 您可以變更看板作業狀態、將看板作業重新安排到不同的規劃期間，以及執行其他任務。
-   轉移作業看板：此看板提供目前轉移作業的概覽。 您可以更新並登錄揀料單、開始及完成轉移作業，以及執行其他任務。
-   程序作業看板：此看板旨在支援正常的生產流程，並概述一或多個工作單元的目前情況。 可以從這個看板挑選、製造看板，或排定看板優先順序。 該看板也設計為可透過掃描條碼來產生看板報告。

## <a name="kanban-jobs-and-integration-with-supply-chain-management-processes"></a>看板作業與 Supply Chain Management 程序整合
看板作業與目前的 Supply Chain Management 庫存交易程序完全整合。
-   您可以執行揀料活動來補貨，藉此滿足看板作業要求。
-   使用看板時，您可以列印看板卡、循環看板卡和揀料單來做為輔助。 這些文件用於表示、追蹤及登錄倉庫和工廠的看板作業。
-   您可以掃描條碼來登錄庫存中的揀料和轉移活動。

此外，精益製造支援承包活動參考的服務採購和發票開立程序。
-   您可以將採購合約明細和服務指派給承包活動。
-   您可以建立定期訂購單和收據建議，支援服務的採購和開立發票。







[!INCLUDE[footer-include](../../includes/footer-banner.md)]