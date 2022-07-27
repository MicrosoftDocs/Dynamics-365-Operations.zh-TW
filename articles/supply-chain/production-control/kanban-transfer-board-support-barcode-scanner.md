---
title: 條碼掃描器的看板轉移板支援
description: 看板轉移板支援介面控件條碼掃描器的掃描器輸入，以選擇、開始、完成和清空看板作業。
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b18aad4dcdbf8c2d18960ae306556c3ea679d622
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447948"
---
# <a name="kanban-transfer-board-support-for-bar-code-scanners"></a>條碼掃描器的看板轉移板支援

[!include [banner](../includes/banner.md)]

看板轉移板支援介面控件條碼掃描器的掃描器輸入，以選擇、開始、完成和清空看板作業。

## <a name="registration-modes"></a>登記模式

在 **掃描器登記** FastTab 您可以選擇註冊模式，以便在您掃描看板卡號或在看板卡號欄位手動輸入數字時控制動作。

| 設定登記模式 | 描述                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| 開始                 | 將看板轉移作業登記為正在進行。                                                 |
| 完成              | 將看板轉移工作登記為已完成。                                                   |
| 空白                 | 將看板卡參考的物料承辦單位登記為空白。              |
| 選取                | 登記看板卡號，並在看板清單中自動選取參考的作業。 |

 
## <a name="registration-mode-select"></a>登記模式選擇

您使用條碼閱讀器選擇作業時，看板的顯示模式會發生變化。 在此模式中會套用以下條件：

-   僅顯示掃描的看板作業。
-   所選作業的詳細資料顯示在 **詳細資料** FastTab。
-   **訊息** FastTab 僅顯示所選作業的訊息。
-   您可以使用動作窗格上提供的功能來變更作業的狀態。 在此期間，看板轉移板繼續僅顯示一個作業。
-   您可以按一下動作窗格的 **重新整理** (Shift+F5) 以手動更新作業清單資訊。 重新值整理資訊後，作業篩選器的完整結果將再次顯示。

## <a name="job-status-and-possible-actions"></a>作業狀態和可能的動作
所選作業的狀態和事件看板的任何需求追蹤作業狀態，決定了您是否可以進一步處理該作業。 下表顯示了有關這些狀態和任務的資訊：
-   可用於作業或作業所參考承辦單位的狀態。
-   您可以為作業執行的每項任務。

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>工作類型</th>
<th>作業狀態或承辦單位狀態</th>
<th>更新揀料單</th>
<th>開始</th>
<th>更新登記</th>
<th>完成</th>
<th>空白</th>
<th>建立事件看板</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>轉移</td>
<td><ul>
<li>未計劃</li>
<li>沒有需求追蹤作業，或需求追蹤作業已完成</li>
</ul></td>
<td>是</td>
<td>是</td>
<td>是</td>
<td>是</td>
<td>否</td>
<td>是</td>
</tr>
<tr class="even">
<td>轉移</td>
<td><ul>
<li>未計劃</li>
<li>需求追蹤作業未完成</li>
</ul></td>
<td>是</td>
<td>否</td>
<td>是</td>
<td>否</td>
<td>否</td>
<td>否</td>
</tr>
<tr class="odd">
<td>轉移</td>
<td>進行中</td>
<td>是</td>
<td>否</td>
<td>是</td>
<td>是</td>
<td>否</td>
<td>否</td>
</tr>
<tr class="even">
<td>轉移</td>
<td>已完成</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>是</td>
<td>否</td>
</tr>
<tr class="odd">
<td>轉移或處理</td>
<td>空白</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
</tr>
<tr class="even">
<td>轉移或處理</td>
<td>未找到看板卡</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
</tr>
<tr class="odd">
<td>轉移或處理</td>
<td>找到了看板卡，但未將其指派給看板</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
</tr>
<tr class="even">
<td>流程</td>
<td><ul>
<li>未計劃</li>
<li>已備妥</li>
<li>進行中</li>
</ul></td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
</tr>
<tr class="odd">
<td>流程</td>
<td>已完成</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
<td>否</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]