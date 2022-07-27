---
title: 用提取看板補貨
description: 本主題說明如何使用提取看板對製造活動進行物料補貨。
author: johanhoffmann
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanFlow, KanbanRules, WHSKanbanWaveTable, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b90e4699c440d0dd753cd16ff17cf958507e7872138a7f2c2c84f645f713d3db
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446910"
---
# <a name="replenishment-with-withdrawal-kanbans"></a>用提取看板補貨

[!include [banner](../includes/banner.md)]

本主題說明如何使用提取看板對製造活動進行物料補貨。

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>使用提取看板的物料補貨工作流程

提取看板可用於在倉庫和消耗物料的生產地點之間移動單個品項的看板。 提取看板支援提取型物料補貨解決方案，其中需要提取訊號來觸發供應特定需求。 

以下情境顯示了一個提取型的補貨系統，其中提取訊號觸發建立看板以補充物料給生產流程。 

[![提取訊號觸發建立看板以補充物料給生產流程。](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  提取看板
2.  看板「來源」位置和倉庫作業放置位置
3.  看板「目的地」位置和生產輸入位置
4.  製造流程
5.  看板揀貨的倉庫工作
6.  原料倉庫位置
7.  材料倉庫
8.  製造倉庫

在這種情況下，製造流程 (4) 從製造倉庫 (8) 中的生產輸入位置 (3) 消耗材料。 物料 (看板) 的承辦單位消耗時，會登記為空白。 為物料來源建立補貨訊號，並建立新看板 (1)。 在這種情況下，品項來源由材料倉庫 (7) 中的位置組成。 看板的物料揀選並放置到同一倉庫中的位置 (2)。 物料揀選後，即可從位置 2 轉移到製造倉庫 (8) 中的生產輸入位置 (3)。

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>為提取看板設定看板揀貨的倉庫工作

要為提取看板啟用原料揀選，請為提取看板設定波次範本、工作範本和位置指令用於 **看板揀貨** 工單類型。 這種工單類型不僅支援提取看板的揀貨流程， 也支援製造看板的揀貨流程。 但是，您可以透過分離波次範本、工作範本和位置指令，來為每種類型的看板設定單獨的揀貨流程。 要分離波次範本、工作範本和位置指令，請在這些實體的查詢中，於活動類型設定標準 (**過程** 或 **轉移**)。

## <a name="configure-the-withdrawal-kanban"></a>設定提取看板

用於提取看板的轉移活動設定為精益生產流程中啟動活動計劃的一部分。 作為轉移活動設定的一部分，您指定轉移的「來源」和「目的地」位置。 設定轉移活動後，您可以將其指派給 **提取** 類型的看法規則。 看板規則設定提取看板的策略和設定。 看板的數量定義了看板在轉移過程中承載的承辦單位的單位數量。 選擇固定補貨策略時使用固定看板數量。 此數量定義了需要多少看板才能防止庫存或建立庫存在需求來源處用完。 固定數量可以根據實際需求、歷史需求和服務等級來計算。 以下兩個情境說明如何使用提取看板管理物料補貨。

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>情境 1：使用固定提取看板補貨生產輸入位置

製造流程從製造倉庫中的生產輸入位置消耗購買的原料。 從供應商處收到原料後，將其儲存在物料倉庫中的位置。 因為在一段時間內對物料的需求是穩定的，所以設定以固定數量的看板流程供應生產。 在生產輸入位置消耗看板時，會註冊一個空白訊號，並將相同類型的新看板新增到流程中。 

空白訊號可以設定為在看板完成時自動出現。 或者，可以將空白訊號設定為手動互動，從看板轉移板或從手持裝置上的功能表提供。 看板轉移板是管理看板生命週期中所有活動的工作區。 

建立看板時，會將原料的波次線新增到物料倉庫的看板波次中。 在看板轉移板的揀料單部分，可以監控從波次建立到工作建立的物料和相關倉庫流程狀態，直到物料在「轉移自」位置現場並準備轉移到生產輸入位置。 看板可以透過看板轉移板或手持裝置上的功能表完成。 

在此情境中，物料倉庫中的揀料工作是作為一項活動處理。 物料倉庫和生產倉庫之間的轉移活動是作為單獨的活動處理。 例如，如果兩個倉庫之間的實際距離很大，這種方法可能很有用。 在這種情況下，看板轉移活動可以代表卡車裝載。 

如果倉庫位置和生產輸入位置之間的距離很小，則將轉移活動包含在揀貨流程中可能會更有效。 然後，物料揀選後可以直接將其放入生產輸入位置。 為支援此流程，您要設定轉移活動，以便在處理提取看板的揀貨工作時自動完成。

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>情境 2：在處理看板揀貨工作時自動完成轉移活動

在以下情境中，提取看板的轉移活動設定為在同一倉庫的兩個位置之間轉移。 提取看板的轉移活動設定為自動完成。 

[![在處理看板揀貨工作時自動完成轉移活動。](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  原料及生產共用倉庫
2.  原料倉庫位置
3.  看板「來源」位置和倉庫作業放置位置
4.  提取看板
5.  產品輸入位置
6.  製造流程

在生產輸入位置消耗看板後，會將看板回報為空白，並將新看板新增到流程中。 建立看板時，會在看板波次中新增波次行。 處理看板波次時，會建立看板揀貨的倉庫工作。 倉庫工作人員處理看板揀貨的工作，並受工作指示在倉庫位置為看板揀選物料。 這個倉庫工作人員確認揀貨後，看板自動完成，倉庫工作人員將接受引導把材料放到生產輸入位置。



[!INCLUDE[footer-include](../../includes/footer-banner.md)]