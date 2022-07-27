---
title: 週期盤點
description: 本文說明將週期盤點與倉庫管理中可用的倉庫解決方案結合使用的方法。 本文不適用於庫存管理中可用的倉庫解決方案。
author: Mirzaab
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adaed1d5a4f1ac62df35bcc1497610ce0f44043c
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449541"
---
# <a name="cycle-counting"></a>週期盤點

[!include [banner](../includes/banner.md)]

本文說明將週期盤點與倉庫管理中可用的倉庫解決方案結合使用的方法。 本文不適用於庫存管理中可用的倉庫解決方案。

週期盤點是一個倉庫處理程序，您可以用來稽核現有庫存項目。 週期盤點處理程序可以分為三個步驟：

1.  **建立週期盤點工作** – 根據項目的閥值參數，或是週期盤點計畫，可以建立自動化週期盤點工作。 或者，您可以使用 **按項目的週期盤點工作** 頁面，或是 **按位置的週期盤點工作** 頁面上的項目或倉庫參數，建立手動週期盤點工作。
2.  **處理週期盤點** – 創建週期盤點工作後，您通過計算倉庫位置中的項目，然後使用行動裝置將結果輸入到 Dynamics 365 Supply Chain Management。 或者，您可以計算倉庫位置的項目，但是不建立週期盤點工作。 此過程也稱為 *抽樣週期盤點*。
3.  **解決計算後數值的差異** – 週期盤點後，任何計算後的值有差異的項目，會在 **所有工作** 頁面上處於 **待審核** 工作狀態。 您可以在 **週期盤點工作待審核** 頁面上，解決差異項目。

以下圖示說明週期盤點的處理程序。 ![週期盤點的處理流程。](./media/performcyclecountinginawarehouselocation.jpg)

## <a name="cycle-counting-prerequisites"></a>週期盤點先決條件
以下資料表顯示週期盤點使用之前必須具備的先決條件。
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>先決條件</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>項目</td>
<td>品項必須啟用 Warehouse Management 流程。</td>
</tr>
<tr class="even">
<td>倉庫</td>
<td>倉庫必須啟用 Warehouse Management 程序。 若要為倉庫管理處理程序啟用倉庫，在<strong>倉庫</strong>頁面，選擇倉庫，然後選擇<strong>使用倉庫管理處理程序</strong>選項。 若要允許工人在週期盤點期間移動托盤，在<strong>倉庫管理</strong> FastTab，選擇<strong>週期盤點期間允許移動托盤</strong>選項。</td>
</tr>
<tr class="odd">
<td>工作集區</td>
<td>可選：建立工作集區，以根據工作類型 (在本範例中為週期盤點工作) 分隔倉庫工作。</td>
</tr>
<tr class="even">
<td>位置</td>
<td>啟用位置的週期盤點。 若要啟用倉庫位置的週期盤點，在<strong>位置資料</strong>頁面，選擇<strong>允許週期盤點</strong>選項。</td>
</tr>
<tr class="odd">
<td>倉庫管理參數</td>
<td>設定週期盤點參數。 在<strong>倉庫管理參數</strong>頁面，指定週期盤點的預設調整類型代碼、工作類別識別碼和工作優先順序。</td>
</tr>
<tr class="even">
<td>行動裝置</td>
<td><ul>
<li>在<strong>行動裝置功能表項目</strong>頁面上，建立具有以下方式之一的功能表項目：
<ul>
<li>使用者指導的週期盤點</li>
<li>系統指導的週期盤點</li>
<li>週期盤點群組</li>
<li>抽樣週期盤點</li>
</ul>
</li>
<li>為行動裝置設定功能表。</li>
<li>建立工作使用者帳戶，並將行動裝置功能表指派至工作使用者識別碼。</li>
</ul></td>
</tr>
<tr class="odd">
<td>相關設定工作</td>
<td>為倉庫位置設定週期盤點計劃。</td>
</tr>
</tbody>
</table>

## <a name="automatically-create-cycle-counting-work"></a>自動建立週期盤點工作
安排定期建立週期盤點工作有兩種方法：設定週期盤點閥值，或設定週期盤點計劃。

-   週期盤點閥值表示庫存數量或百分比限制。 到達閥值限制時，會自動建立週期盤點工作。
-   週期盤點計劃會透過批次作業，建立立即性或定期性週期盤點工作。 建立週期盤點工作時，盤點工作明細會包括要計算的位置資訊。 與此位置關聯的現有庫存不會遭到封鎖，因此可用於保留和出庫處理程序，即使有尚未完成的盤點工作也是如此。

### <a name="create-cycle-counting-work-based-on-threshold-parameters-for-items"></a>根據項目的閥值參數，建立週期盤點工作

當項目數量低於某個位置的特定閥值時，可以建立週期盤點工作。 例如，一個位置有 60 個項目，其週期盤點閥值為 40。 在銷售訂單事務處理期間，從該庫位挑選 25 件物品並將其放入暫存庫位。 因為新的項目計數 35 小於閾值數量，所以會自動為該庫位創建週期盤點工作。

### <a name="schedule-cycle-counting-work"></a>安排週期盤點工作

您可以安排週期盤點計劃，以立即或定期建立週期盤點工作。 透過設定週期盤點計劃，您可以控制建立週期盤點工作的工作集區、不同位置內項目週期盤點次數的最大值，和再次計算倉庫位置的天數。 例如，一個項目在倉庫中有三個可用位置，並且最大週期盤點數設定為 **2**。 在這種情況下，當您執行週期盤點計劃時，將為存在項目的兩個位置建立兩個週期盤點。 另一個範例，您將週期盤點之間的天數設定為 **5**。 在這種情況下，每五天會建立一次週期盤點工作。 但是，如果在第 3 天處理週期盤點工作，則下一個週期盤點工作將在處理最後一個週期盤點 5 天後的第 8 天創建。

## <a name="create-cycle-counting-work-manually"></a>手動建立週期盤點工作
若要手動建立週期盤點工作，您可以使用 **按項目的週期盤點工作** 或是 **按位置的週期盤點工作** 頁面。 您可以指定要建立的最大週期盤點數量。 例如，如果倉庫經理指定的值為 **5**，即使項目存在於 10 個位置，也只會建立五個位置的週期盤點工作。 您還可以選擇一個工作集區識別碼，來指派建立的週期盤點工作識別碼。 當工作集區識別碼處理週期盤點時，週期盤點工作識別碼會被指派到工作集區，作為群組進行處理。

## <a name="perform-a-cycle-count-by-using-a-mobile-device"></a>使用行動裝置執行週期盤點
在行動裝置上使用 Supply Chain Management 處理週期盤點工作有多種方法：

-   **使用者引導** – 工作人員可以指定一個週期盤點工作識別碼，其狀態為 **打開**。
-   **系統引導** – Supply Chain Management 將週期盤點工作識別碼指派給工作人員。
-   **週期盤點群組** – 工作人員可以對特定位置、區域或工作集區，對特定的週期盤點工作識別碼進行分組。
-   **抽樣週期盤點**：工作人員可以隨時盤點倉庫位置中的項目，無須建立週期盤點工作。 若要執行位置的抽樣週期盤點，工作人員輸入位置識別碼。

以下範例顯示，如何使用行動裝置執行抽樣週期盤點。 工作人員在裝置上看到的說明會有所不同，具體取決於抽樣週期盤點功能表的設定。

1.  在行動裝置上，選擇功能表以處理現場週期盤點工作。
2.  登記要執行抽樣週期盤點的位置。
3.  登記並確認項目編號，和盤點的項目數量。 **請注意：** 週期盤點工作的狀態為會在 **所有工作** 頁面上更新為 **待審核** 或 **關閉**，取決於 **工作人員** 頁面上設定的參數。
4.  選用：對位置中的剩餘項目，重複步驟 3，並確認沒有其他項目可用於盤點。

## <a name="resolve-cycle-counting-differences"></a>解決週期盤點差異
週期盤點差異發生在以下情況下，如果 **是週期盤點主管對於工作使用者識別碼** 選項設定為 **否**：

-   盤點值不在指定的偏差範圍內，就是 **工作使用者** 頁面上指定的 **最大百分比限制** 或 **最大數量限制** 上的欄位。 例如，一個位置的現有庫存數量為 50，工作使用者的偏差限制為 10。 如果工作使用者輸入的值不在 40 和 60 之間，則會出現差異。
-   盤點值與現有庫存數量不同，不設定偏差限制。

您可以調整盤點值的差異，然後在 **週期盤點待審核** 頁面上接受盤點值。 您可以在 **按位置的庫存** 頁面上，驗證修改後的盤點項目數量。 如果無法批准差異，則拒絕盤點值。

## <a name="additional-resources"></a>其他資源
[為倉庫工作設定行動裝置](configure-mobile-devices-warehouse.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]