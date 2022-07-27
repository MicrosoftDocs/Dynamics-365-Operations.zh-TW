---
title: 採購申請總覽
description: 本主題說明採購申請工作流程以及採購申請可以具有的不同狀態。
author: Henrikan
ms.date: 11/02/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqConsolidation, PurchReqCreate, PurchReqCreatePurchDetails, PurchReqCreatePurchListPage, PurchReqTable, PurchReqTableListPage, PurchReqConsolidationPartByVendor, PurchReqConsolidationLineDetail, PurchReqConsolidationCreate, PurchReqConsolidationBulkEdit, PurchReqConsolidationAddLine
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2174"
- intro-internal
ms.assetid: 77d07119-4d9f-4c0e-acbe-d319203571ab
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acd0deebe79e29bd1beb32ea21cd179f5bf12c43
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449673"
---
# <a name="purchase-requisition-overview"></a>採購申請總覽

[!include [banner](../includes/banner.md)]

本主題說明採購申請工作流程以及採購申請可以具有的不同狀態。

根據您的組織設定，您可以為組織使用的產品建立採購申請。 採購申請是一種內部文件，可授予採購部門購買物品或服務的權限。  

採購申請獲得核准後，可用於產生訂購單。 訂購單是採購部門提交給供應商的外部文件。

## <a name="creating-purchase-requisitions"></a>建立採購申請
您可以在 **我的採購申請** 頁面建立採購申請，然後選擇所需的項目和服務。 您可以從您組織已建立的採購目錄中選擇項目，也能透過選取採購類別並輸入產品詳細資料，來要求目錄中找不到的項目。  

在您提交採購申請以供審核之前，必須設定工作流程。 您將使用工作流程推動採購申請的審核流程，從初始狀態 **草稿** 到最終狀態 **已核准**。

### <a name="purchase-requisition-statuses"></a>採購申請狀態

當您建立採購申請時，系統會為其指派一個狀態。 狀態也指派給您新贈至採購申請的每個明細行。 當您將採購申請提交到工作流程進行審查時，採購申請的狀態和每個明細的狀態會隨著明細在工作流過程中的移動而更新。  

您可以設定採購申請工作流程，以將採購申請作為單一文件進行審核流程。 或者，可以將採購申請上的明細單獨傳送給適當的審核者。 如果單獨審查採購申請明細，則每個採購申請明細的狀態可以隨著明細在審查流程中的移動而更新。 當所有明細都完成審核流程，且採購申請沒有剩餘審核步驟時，整個採購申請的狀態都會更新。

### <a name="purchase-requisition-workflow"></a>採購申請工作流程

下圖顯示在採購申請和採購申請明細進行工作流程時，系統為兩者指派的狀態。  

[![採購申請標題和明細狀態。](./media/purchasereq_headerline_statuses.jpg)](./media/purchasereq_headerline_statuses.jpg)

### <a name="purchase-requisition-header-and-line-status-relationships"></a>採購申請標題和明細狀態關係

採購申請的整體狀態是由採購申請明細的狀態決定。 因此，必須先完成所有採購申請明細的審核流程，才能完成整個採購申請的審核流程。 下表說明在採購申請和採購申請明細進行工作流程時，系統為兩者指派的狀態。

<table>
<thead>
<tr class="header">
<th>採購申請狀態</th>
<th>採購申請明細狀態</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>草稿</td>
<td>草稿</td>
<td>已建立採購申請和採購申請明細，但兩者尚未提交審核&#39;。 狀態為<strong>草稿</strong>的採購申請和採購申請明細可以修改。 如果採購申請或採購申請明細遭到撤回，但尚未已重新提交審核&#39;，採購申請或採購申請明細的狀態也會為<strong>草案</strong>。 <strong>注意：</strong>您可以在文件層級提交或撤回採購申請。 但是，您無法提交或撤回單一採購申請明細&#39;。</td>
</tr>
<tr class="even">
<td>審查中</td>
<td><ul>
<li>審查中</li>
<li>已拒絕</li>
</ul></td>
<td>如果工作流程已設為將採購申請明細傳送給各個審閱者，則每個明細的狀態可以是<strong>審查中</strong>或<strong>已拒絕</strong>。 當所有採購申請明細都完成審核流程，且採購申請沒有剩餘審核步驟時，採購申請的狀態就會更新。
<ul>
<li><strong>審查中</strong>– 已將採購申請明細提交審核。 完成採購申請明細的工作流程後，該明細的狀態保持為<strong>審查中</strong>，直到所有剩餘的採購申請明細都已審核完畢。</li>
<li><strong>已拒絕</strong> – 採購申請明細已遭到拒絕。 遭到拒絕的採購申請明細可以修改並重新提交。</li>
</ul>
如果您重新提交已遭拒絕的採購申請行，系統將針對採購申請中仍在審核的所有明細重新開始審核流程。 </br><strong>注意：</strong>您可以撤回已提交的採購申請。 當您撤回採購申請時，所有其他採購申請明細也會遭到撤回。 已撤回的採購申請明細可以刪除。</td>
</tr>
<tr class="odd">
<td>已拒絕</td>
<td>已拒絕</td>
<td>採購申請和所有採購申請明細已遭到拒絕。 已遭到拒絕的採購申請和採購申請明細可以重新提交。</td>
</tr>
<tr class="even">
<td>已核准</td>
<td><ul>
<li>已核准</li>
<li>已取消</li>
<li>已結案</li>
</ul></td>
<td>所有採購申請明細已完成審核流程，且採購申請沒有剩餘審核步驟。
<ul>
<li><strong>已核准</strong>– 採購申請明細的審核流程已完成，並且明細已獲核准。</li>
<li><strong>已取消</strong>– 採購申請行已核准，但因為沒有需求已遭到取消&#39;。 只有已核准的採購申請明細可以取消。</li>
<li><strong>已關閉</strong>– 採購申請明細已獲核准，且已產生文件，實際取決於申請目的。
<ul>
<li>如果申請目的是消耗，則已為採購申請明細產生訂購單。</li>
<li>如果申請目的是補貨，則已產生一或多份履行文件。</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>已取消</td>
<td>已取消</td>
<td>採購申請和所有採購申請明細已取消。</br> <strong>注意：</strong>如果您不再需要採購申請明細上的項目，而採購申請明細已經獲核准，您必須取消該採購申請明細。 只有已核准的採購申請明細可以取消。 如果任何採購申請明細正在審核中，採購申請的狀態將為<strong>審查中</strong>。 在這種情況下，您可以撤回採購申請並刪除相關的採購申請明細。</td>
</tr>
<tr class="even">
<td>已結案</td>
<td><ul>
<li>已結案</li>
<li>已取消</li>
</ul></td>
<td>如果採購申請已關閉，則已產生一或多份履行文件。
<ul>
<li><strong>已關閉</strong>– 採購申請明細已獲核准，且已產生文件，實際取決於申請目的。
<ul>
<li>如果申請目的是消耗，則已為採購申請明細產生訂購單。</li>
<li>如果申請目的是補貨，則已產生一或多份履行文件。</li>
</ul></li>
<li><strong>已取消</strong>– 採購申請行已核准，但因為沒有需求已遭到取消&#39;。 只有已核准的採購申請明細可以取消。</li>
</ul>
<strong>注意：</strong>如果您不再需要已關閉的採購申請明細上的項目，您必須取消為採購申請明細產生的履行文件上的明細。</td>
</tr>
</tbody>
</table>

## <a name="distributing-costs-to-multiple-financial-accounts"></a>將成本分配到多個財務帳戶
您可以將採購申請中包含的產品成本分配到多個財務帳戶。 如果您的組織使用成本中心和部門等維度，您可以將產品成本分配到財務帳戶的維度。

## <a name="requisition-purposes"></a>申請目的
申請目的使滿足申請需求的過程更加靈活。 建立申請時，您可以為其指派兩個用途之一：消耗或補貨。 根據申請目的和組織設定，可以透過訂購單、轉移訂單、生產訂單或看板來滿足申請需求。  

在採購原則中，您可以控制在為您的組織建立申請時可用的申請目的。

### <a name="requisitions-that-have-a-purpose-of-consumption"></a>有消耗目的申請

具有消耗目的的申請表示對將由您的組織內部使用的項目或服務的需求。 此類申請建立的需求一律由訂購單滿足。 如果將 Supply Chain Management 設定為自動產生採購訂單，則在採購申請獲得核准後建立採購訂單。

### <a name="requisitions-that-have-a-purpose-of-replenishment"></a>有捕貨目的申請

具有補貨目的的請購單表示補充庫存的需求。 例如，您建立一個補貨申請，以讓商品可以在特定時間在特定零售地點銷售。 此類申請建立的需求可以透過採購訂單、轉移訂單、生產訂單或看板來滿足。  

當申請目的是補貨時，需求表示為數量而不是金額。 因此，保留會計、預算控制、已設定的固定資產決定規則、傳案會計和任何相關規則均不適用。 只有入庫並發佈到指定法律實體的產品才能滿足補貨申請需求。 若要定義在申請目的是補貨時可用的產品，請使用 **補貨類別存取原則規則** 頁面。  

若要使用具有補貨目的的採購申請，您必須設定總排程以包括申請需求。 然後，根據為您的組織中的項目設定並使用總排程進行計劃的供應原則，自動確定由此類申請建立的需求的履行方法。

## <a name="purchase-requisitions-and-requests-for-quotation"></a>採購申請和詢價要求
在某些情況下，您必須啟動詢價 (RFQ) 流程來識別採購申請中要求的產品供應商和價格。 審核採購申請時可以產生詢價。 當您接受出價時，有關供應商、價格等的資訊將轉移到申請單。  

您可以透過選取 **採購申請詳情** 頁面上的 **保留中** 核取方塊來保留採購申請。 只有在您透過清除核取方塊來移除保留後，才能繼續處理採購申請。  

> [!NOTE]
> 在電子採購中，採購申請的 RFQ 可能允許供應商新增備用明細。 在這種情況下，您的採購申請將反映已核准的替代品。

## <a name="demand-consolidation"></a>需求合併
透過合併來自多個採購申請的採購申請明細，您可以提高與供應商的談判能力，從而實現更好的定價、更低的運輸和處理成本，並減少間接成本。  

只有在下列陳述為真時，採購申請明細才有資格進行需求合併：

-   採購申請已獲核准。
-   採購申請滿足人工處理和需求合併的採購策略規則標準。

符合人工處理標準的已核准採購申請明細列在 **發布已核准的採購申請** 頁面。 如果採購申請明細也滿足需求合併的條件，則可以將該明細新增到合併商機。  

合併商機是一組分組在一起的採購申請明細，以便採購專業人員可以與供應商協商最佳交易。 您為合併商機選擇的採購申請明細顯示在 **採購申請合併** 頁面。 如果需要更改，您可以修改此頁面上的明細。 您也可以向合併商機新增明細或刪除現有明細。  

將申請明細新增到合併商機，並進行所需的任何更改後，您可以為合併的採購申請明細建立採購訂單。  

> [!NOTE]
> 您對採購申請明細所做的更改 **採購申請合併** 頁面會反映在您建立的採購訂單上。 但是，該明細在採購申請中保持不變，因此保留了其歷史記錄。  

要為不符合需求合併或未選擇合併商機的採購申請明細建立訂購單，您必須手動處理這些明細。

### <a name="consolidating-purchase-requisition-lines"></a>合併採購申請明細

當採購申請在工作流程中獲得核准時、如果為您的組織已設定預算控制、已記錄預算預留和預支款時，需求合併程序就會開始。 下圖顯示需求合併的程序流程。  

[![需求合併的程序流程。](./media/demand-consolidation.gif)](./media/demand-consolidation.gif)  

若要合併已核准的採購申請明細，請執行以下步驟：

1.  審查已為手動處理保留且符合需求合併條件的已核准申請明細。
2.  選擇要新增到合併商機的明細。
3.  建立新的合併商機，或將申請明細新增到現有的合併商機。
4.  對申請明細進行任何必要的更改，並刪除您不再希望包含在合併商機中的申請明細項目。
5.  為合併申請明細或合併商機中的採購申請明細建立採購訂單。


## <a name="additional-resources"></a>其他資源

[建立消費申請](tasks/create-requisition-consumption.md)

[採購申請工作流程](purchase-requisitions-workflow.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]