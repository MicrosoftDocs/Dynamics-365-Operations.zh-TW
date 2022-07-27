---
title: 工單介紹
description: 本主題提供資產管理中的工單概覽。
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderLineNote, EntAssetWorkOrderTable, EntAssetWorkOrderActive, EntAssetWorkOrderHoursInfoPart, EntAssetWorkOrderLineListPage, EntAssetWorkOrderAddObjectBOMItem, EntAssetWorkOrderTablePoolAdd, EntAssetWorkOrderPurchReqListPagePreviewPane, EntAssetWorkOrderPoolReferenceAdd, EntAssetWorkOrderWorkspace, EntAssetWorkOrderTableAdjust, EntAssetWorkOrderGantt, EntAssetWorkOrderNotes, EntAssetWorkOrderActivePart, EntAssetWorkOrderTableInfoPart, EntAssetWorkOrderLineListPagePreviewPane, EntAssetWorkOrderTool, EntAssetMobileWorkOrderLineDetails, EntAssetMobileWorkOrderLineList, EntAssetMobileWorkOrderDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3891ea08a484950d8fef57d6229117e90ed93a92ab800f9de3ad82db3aff956d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447051"
---
# <a name="introduction-to-work-orders"></a>工單介紹

[!include [banner](../../includes/banner.md)]



工單用於管理維護工作，提供維護所需的資訊，並於上方登記消耗。 每個工單可以包含一個或多個工單工作，並且可以與一個或多個資產建立連線。 每個工單工作，定義資產上排定的維護作業。

可以通過以下方式建立工單：

- 針對行事曆為基礎的維護計畫，且開啟「自動建立」設定時，可以使用自動[排程維護計畫](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md)。

- 針對維護回和，且開啟「自動建立」設定時，可以使用自動[安排維護回合](../preventive-and-reactive-maintenance/maintenance-rounds.md)。

- 針對預防性維護工作或維護要求，請從[維護排程](../preventive-and-reactive-maintenance/maintenance-schedule.md)。

- 手動

- 從 **所有維護要求**、**主動維護要求** 或是 **我的功能位置維護要求** 頁面。

>[!NOTE]
>相同專案 ID 相關的同一資產工單工作。

## <a name="all-work-orders"></a>所有工單

選擇 **資產管理** > **一般** > **工單** > **所有工單**，以開啟 **所有工單** 清單頁面。 此頁面顯示所有工單，及每個工單相關的一些資訊。

下圖顯示 **所有工單** 清單頁面的範例。

![圖 1。](media/01-work-orders.png)

若僅檢視使用中的工單，請選擇 **資產管理** > **一般** > **工單** > **使用中的工單**。 

若要以背景工作角色的身分，檢視包含資產的工單工作，該資產安裝於功能位置上，請選擇 **資產管理** > **一般** > **工單** > **我的功能位置工單維護工作**。 (背景工作角色與功能位置之間的關係，可以於 **工作者** 頁面設定。 如需詳細資訊，請參閱[維護的背景工作角色及背景工作角色群組](../setup-for-objects/workers-and-worker-groups.md)。)

以下是您使用 **所有工單** 頁面的一些方法：

- 在格線檢視中，在 **工單** 欄選取一個連結，顯示所選記錄的詳細資訊。 然後您可以選擇 **編輯** 開啟記錄進行編輯。

- 在詳細資訊檢視中，您可以檢視工單的詳細資訊。  

- 在詳細資訊檢視中，選擇 **行** 索引標籤，以檢視工單工作的詳細資訊，或選擇 **標題** 索引標籤，以檢視工單的詳細資訊。  

- 展開頁面右側的 **相關資訊** 窗格，以檢閱與所選工單相關的其他資訊。

下圖顯示 **所有工單** 檢視詳細資訊的範例。

![圖 2。](media/02-work-orders.png)


動作窗格上的按鈕排列於索引標籤上。 下列資料表簡短說明與資產管理相關的按鈕：



| 按鈕名稱                     | 描述                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 編輯                            | 編輯選取的工單。                                                                                                                                                                                                                                           |
| 新產品                             | 建立新工單。                                                                                                                                                                                                                                                  |
| 刪除                          | 刪除選取的工單。                                                                                                                                                                                                                                         |
| 工單集區                 | 將選取的工單新增至工單集區，或是從工單集區移除工單。                                                                                                                                                                                           |
| 調整                          | 所選工單的調整資訊，包含預期開始和結束時間、服務等級、負責的維護背景工作角色，或是負責的維護背景工作角色群組。                                                                                                                                     |
| 相關聯的工單              | 從已選取的工單工作建立新的相關聯工單。 如果您要登記主要和次要工單，這是很實用的功能。                                                                                                                              |
| 複製工單                 | 根據現有的工單建立新的工單。                                                                                                                                                                                                               |
| 事件歷程記錄                   | 檢視工單的登記記錄。                                                                                                                                                                                                                |
| 工單維護作業附註                           | 建立工單的說明，或是插入附註或備註。 首先，選擇 **新增時間戳記**，將您的使用者名稱和時間戳記新增至附註。 附註會顯示在 **工單** 頁面的 **明細詳細資料** FastTab 上的 **說明** 索引標籤。         |
| 工具                           | 建立工單上所需的工具清單。 工具可從 **組織管理**  >  **資源**  >  **資源** 中設定。                                                                                                      |
| 維護檢查清單           | 檢視已經與工單建立聯繫的資產檢查清單。                                                                                                                                                                                                              |
| 資產錯誤                     | 檢視或登記資產的錯誤資訊。 此資訊用於錯誤管理。                                                                                                                                                                                      |
| 維護停機時間            | 指定工單的維護停機時間。                                                                                                                                                                                                                               |
| 條件評定            | 工單的登記條件評定測量。                                                                                                                                                                                                             |
| 資產計數器                 | 建立或檢視資產的計數登記時間。                                                                                                                                                                                                                     |
| 預測                        | 檢視或建立工單的預測。                                                                                                                                                                                                                               |
| 日記帳                        | 檢視或建立工單日記帳。 日記帳行可以從預測複製。                                                                                                                                                                                         |
| 專案交易            | 檢視為資產建立的工單相關的已過帳交易。                                                                                                                                                                                             |
| 更新工單狀態           | 更新工單的生命週期狀態。                                                                                                                                                                                                                                                |
| 生命週期狀態記錄檔                      | 檢視所選工單生命週期狀態的記錄檔。                                                                                                                                                                                                                   |
| 資產文件                | 檢視附加到與工單相關的資產文件清單。 文件可以在 **資產管理** > **設定** > **資產文件** 中設定。                                                                                                 |
| 排程                        | 排程所選的工單。                                                                                                                                                                                                                                      |
| 分派            | 將所選的工單排程給一名背景工作角色。                                                                                                                                                                                                                        |
| 刪除排程                 | 刪除所選工單的排程。                                                                                                                                                                                                                          |
| 已排程工單維護作業             | 開啟 **排定的工單維護作業** 清單頁面。                                                                                                                                                                                                                             |
| 工單採購申請 | 開啟 **工單採購申請** 清單頁面。                                                                                                                                                                                                                 |
| 工單採購             | 開啟 **工單採購** 清單頁面。                                                                                                                                                                                                                             |
| 成本控制                    | 比較工單上的預算成本和實際成本。                                                                                                                                                                                                                |
| 時數控制                    | 比較工單上的預估時數和實際時數。                                                                                                                                                                                                                |
| 工單報表               | 列印工單報表。                                                                                                                                                                                                                                                |
| 工單消耗          | 列印消耗報表。                                                                                                                                                                                                                                               |


動作窗格中 **工單** 索引標籤上的 **專案** 群組按鈕，與 **專案管理和會計** 模組中的預測、日記帳和發票功能相關。

>[!NOTE]
>執行總排程時，若要包括工單上建立的預測，請使用 **資產管理參數** 頁面中所選的預測模型。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]