---
title: 為倉庫工作設定行動裝置
description: 本主題介紹在行動裝置上如何設定倉庫工作人員使用的功能表項目。
author: Mirzaab
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFSysDirSort, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29941
ms.assetid: 6dff6313-dc6e-4f06-9c0c-dab24eefe4da
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9e0f27839d9e6330cc8a11874a5cb1786daf8dc
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449538"
---
# <a name="set-up-mobile-devices-for-warehouse-work"></a>為倉庫工作設定行動裝置

[!include [banner](../includes/banner.md)]

本主題介紹在行動裝置上如何設定倉庫工作人員使用的功能表項目。

> [!NOTE]
> 本主題適用在 Warehouse Management 中的功能。 不適用庫存管理中的功能。 到 **行動裝置功能表項目** 頁面設定倉庫行動裝置功能表上顯示的功能表項目。 因為功能表項目可以放在不同的功能表上，所以很容易將功能表結構設定為只對特定使用者開放特定類型的工作。 您可以設定功能表項目，以執行以下任務：

- 處理查詢或執行活動，例如列印標籤、生成牌照號碼、啟動生產訂單或快速查找某個位置上的品項的相關訊息。
- 建立會在另一個流程執行的工作。 例如，接收訂購單品項可以為另一個工作人員建立存放工作。
- 執行由另一個流程建立的工作 (現有工作)，例如在收到訂購單品項時建立的存放工作。

若要為活動或查詢建立功能表品項，請將 **模式** 欄位設定為 **間接**。 然後 **活動代碼** 選項的清單變為可用，您便可以選擇功能表項目提供的查詢或活動的類型。 若要建立可生成倉庫工作的功能表品項，請將 **模式** 欄位設定為 **工作**。 然後 **工作建立流程** 選項的清單變為可用。 若要建立可處理現有倉庫工作的功能表項目，請將 **模式** 欄位設定為 **工作**，然後設定 **使用現有工作** 選項為 **是**。 

> [!NOTE]
> 其他欄位或許可用於功能表項目，這取決於您為功能表項目選擇的模式以及該功能表項目是否用於執行現有工作。 有關其他欄位選擇的更多資訊，請參閱本主題後面的「其他功能表項目選項」部分。

## <a name="configure-menu-items-for-activities-and-inquiries"></a>設定活動和查詢的功能表項目

如果 **模式** 功能表項目的欄位設定為 **間接**，您可以建立一個功能表項目來執行不會建立工作的一般活動或查詢。 範例包括重新列印牌照標籤和查詢某個位置的品項。 下表列出了可用的選項。

| 選項 | 描述 |
|---|---|
| 無 | 此預設值不啟用活動或查詢。 |
| 關於 | 查看系統的相關資訊，例如版本號碼、倉庫識別碼和登入中的工作人員。 |
| 變更倉庫 | 變更工作人員登入的倉庫。 |
| 位置查詢 | 對一個位置查看其所有品項和數量。 |
| 牌照查詢 | 查看牌照上的品項數量和牌照位置。 |
| 啟動生產訂單 | 啟動生產訂單。 |
| 生產報廢 | 為每個物料清單 (BOM) 明細輸入在生產期間產生的報廢數量。 |
| 生產最後一個棧板 | 指示生產訂單的最後一個棧板品項已生產，並且必須將生產訂單的狀態更新為 **報告為完成**。 生產過程中未消耗的原物料的狀態從 **已揀選** 改回為 **訂單上**，並且品項可以返回庫存。 |
| 品項查詢 | 掃描品項可確定它在倉庫中的位置。 查詢回傳掃描品項的所有位置和數量。 |
| 重印標籤 | 重印牌照標籤。 |
| 牌照組建 | 在同一位置合併多個牌照以建立上層牌照。 如果您要同時移動多個牌照，此選項很有用。 移動上層牌照後，您必須先執行牌照拆分，然後才能從每個牌照中揀選品項。 <p></p>**提示：** 若要移動上層牌照，您必須使用設定能建立移動工作的行動裝置。 |
| 牌照拆分 | 拆分牌照組建，以便您可以從組建中的牌照揀選品項。 |
| 駕駛員簽入 | 如果您使用的是運輸管理，請掃描出庫負載識別碼、預約識別碼或裝運識別碼來登記司機到達。 對於此選項，必須將負載指派給預約，並且負載的狀態必須是 **已裝載**。 |
| 駕駛員簽出 | 登記司機完成預約。 |
| 排清數列快取 | 從編號序列快取中刪除數列編號。 此活動通常由系統管理員執行，以解決使用行動裝置時的快取問題。 |
| 變更批次處置 | 允許工作人員對品項和批次指定批次處置代碼。 此選擇更新對批次指定的處置代碼。 |
| 顯示打開的工作清單 | 向特定用戶顯示可用工作清單。 然後，使用者可以選擇要執行的工作並將被導向到該工作。 此清單設計給螢幕尺寸為 7 英寸以上平板裝置。 當您選擇此選項目時，**編輯查詢** 和 **欄位清單** 功能表項目變為可用。 **編輯查詢** 頁面可讓設定清單中顯示工作的準則。 **欄位清單** 頁面可讓您選取工作清單中顯示的欄位。 例如，您可以減少出現的欄位數量，以便使用者可以更快地選取最合適的工作項目。 在 **一般** FastTab，在 **每頁記錄** 欄位，您還可以選擇每頁顯示多少工作記錄。 如果 **允許用戶按交易類型篩選工作** 選項選定，工作列表將包括一個 **篩選工作** 控制項，使用者可以用來按交易類型篩選。 在工作清單中，使用者只會看到他們有權存取的工作。 對於使用者應能存取的特定工作類類型，可支援其存取的一個或多個使用者導向的功能表選項，請確保使用者具備權限。 當使用者嘗試執行清單中的工作時，會驗證權限。|
| 從牌照建立轉移單 | 允許倉庫工作人員直接透過 Warehouse Management 行動應用程式建立及處理轉移單。 倉庫工作人員首先選取目的地倉庫，然後可以使用該應用程式掃描一個或多個牌照。 當倉庫工作人員選取 **完成訂單**，批次作業將依據為這些牌照登記的現有庫存建立必要的轉移單和訂單明細。 如需更多相關資訊，請參閱[從倉庫應用程式建立轉移單](create-transfer-order-from-warehouse-app.md)

## <a name="configure-menu-items-to-create-work-for-another-worker-or-process"></a>設定為其他工作人員或流程建立工作的功能表項目

您可以設定一個功能表項目，在行動裝置上執行初始動作後，該功能表項目會為其他工作人員建立工作。 例如，若一名工作人員使用行動裝置接收品項，會為另一名工作人員建立存放工作。 若要設定可建立工作的功能表項目，請在 **行動裝置功能表項目** 頁面，在 **模式** 欄位，選取 **工作**。 在下表中，**工作建立流程** 欄位中的選項按工單類型排列。

<table>
<tbody>
<tr>
<th>工單類型</th>
<th>選項</th>
<th>描述</th>
</tr>
<tr>
<td rowspan="8">訂購單</td>
<td>訂購單明細接收</td>
<td>使用訂購單編號和訂購單明細編號登記品項數量的接收，並為另一個工作人員建立存放工作。</td>
</tr>
<tr>
<td>訂購單明細接收及存放</td>
<td>使用訂購單編號和採訂購單明細編號登記品項數量的接收，並存放品項。 同一個工作人員執行這兩個動作。</td>
</tr>
<tr>
<td>訂購單品項接收</td>
<td>登記訂購單編號和品項編號以登記品項數量的收貨，並為另一個工作人員建立存放工作。</td>
</tr>
<tr>
<td>訂購單品項接收及存放</td>
<td>登記訂購單編號來為訂購單登記品項數量的收貨，並存放品項。 同一個工作人員執行這兩個動作。</td>
</tr>
<tr>
<td>牌照接收</td>
<td>使用牌照識別碼接收一個入庫提前出貨通知 (ASN)。</td>
</tr>
<tr>
<td>牌照接受及存放</td>
<td>使用牌照識別碼接收並存放一個入庫提前出貨通知 (ASN)。</td>
</tr>
<tr>
<td>負載品項接收</td>
<td>使用負載識別碼登記負載數量的接收，並為其他工人建立存放工作。 以品項編號和產品維度比對收據與訂購訂單明細。</td>
</tr>
<tr>
<td>負載品項接收及存放</td>
<td>使用負載品項登記負載收貨，並將物品存放。 以品項編號和產品維度比對收據與訂購訂單明細。 同一個工作人員執行這兩個動作。</td>
</tr>
<tr>
<td rowspan="2">退貨單</td>
<td>退貨單接收</td>
<td>登記 RMA 識別碼以登記品項數量的接收，並為其他工人建立存放工作。</td>
</tr>
<tr>
<td>退貨單接收及存放</td>
<td>登記 RMA 號碼以登記品項數量的接收，並存放品項。 同一個工作人員執行這兩個動作。</td>
</tr>
<tr>
<td rowspan="6">轉移訂單</td>
<td>轉移訂單品項接收</td>
<td>登記品項數量的接收，並為其他工作人員建立存放工作。

<strong>注意：</strong>僅在品項從未啟用 Warehouse Management 流程的倉庫發貨時才使用此選項。</td>
</tr>
<tr>
<td>轉移訂單品項接收及存放</td>
<td>登記品項數量的接收，並存放品項。 同一個工作人員執行這兩個動作。

<strong>注意：</strong>僅在品項從未啟用 Warehouse Management 流程的倉庫發貨時才使用此選項。</td>
</tr>
<tr>
<td>轉移訂單明細接收</td>
<td>登記品項數量的接收，並為其他工作人員建立存放工作。</td>
</tr>
<tr>
<td>轉移單明細接收及存放</td>
<td>登記品項數量的接收，並存放品項。 同一個工作人員執行這兩個動作。</td>
</tr>
<tr>
<td>牌照接收</td>
<td>使用牌照識別碼接收一個入庫提前出貨通知 (ASN)。</td>
</tr>
<tr>
<td>牌照接受及存放</td>
<td>使用牌照識別碼接收並存放一個入庫提前出貨通知 (ASN)。</td>
</tr>
<tr>
<td rowspan="4">生產</td>
<td>報告為完成</td>
<td>登記已完成生產的成品數量，並為其他工作人員建立存放工作。 數量可以是計劃生產的部分或全部數量。</td>
</tr>
<tr>
<td>報告完成並存放</td>
<td>登記已完成生產的成品數量，並存放品項。 數量可以是計劃生產的部分或全部數量。 同一個工作人員執行這兩個動作。</td>
</tr>
<tr>
<td>看板</td>
<td>指示看板已完成，並為另一個工作人員建立存放工作。</td>
</tr>
<tr>
<td>看板存放</td>
<td>指示看板完成，存放品項。 同一個工作人員執行這兩個動作。</td>
</tr>
<tr>
<td rowspan="5">庫存</td>
<td>移動</td>
<td>登記品項已從一個位置移動到另一個位置。 工作人員指定品項移動的出發位置和移動的抵達位置。</td>
</tr>
<tr>
<td>隔離</td>
<td>變更牌照或位置的現有庫存狀態，令損壞或丟失的庫存品項不可使用。</td>
</tr>
<tr>
<td>以範本移動</td>
<td>以半自動的方式將物品從一個位置移動到另一個位置。 工作人員選取移動品項的起始位置，系統使用位置指令來確定將品項移動到哪裡。</td>
</tr>
<tr>
<td>倉庫轉移</td>
<td>登記品項已轉移到另一個倉庫。 此選項要求允許工作人員被可以兩個倉庫中執行工作。

<strong>注意：</strong>此功能表項目需要一個預設的庫存轉移日記帳，其中<strong>憑單製作</strong>欄位設定為<strong>過帳</strong>。</td>
</tr>
<tr>
<td>牌照裝載</td>
<td>第一次設定倉庫時，請&#39;使用此選項。 掃描倉庫所有位置的所有牌照。 這些位置必須由牌照控制。 如果在庫存保留階層結構中<strong>序號</strong>或<strong>批號</strong>列在<strong>地點</strong>上方，不&#39;可使用此選項。</td>
</tr>
<tr>
<td rowspan="3">週期盤點</td>
<td>調整進</td>
<td>增加庫存中的品項數量。 指定位置、牌照、品項、數量、測量單位和狀態。</td>
</tr>
<tr>
<td>調整出</td>
<td>減少庫存中的品項數量。 指定庫存的位置、牌照、品項、數量、測量單位和狀態。</td>
</tr>
<tr>
<td>抽樣週期盤點</td>
<td>開始位置盤點。 工作人員必須盤點該位置的所有品項。 當盤點結果小於預期數量時，缺失的數量被視為損失。</td>
</tr>
</tbody>
</table>

## <a name="configure-menu-items-to-process-existing-work"></a>設定可處理現有工作功能表項目
除了設定功能表項目建立倉庫工作之外，您還可以設定功能表項目來處理已經建立的工作。 設定 **模式** 欄位為 **工作**，並選取 **使用現有工作** 選項。 然後有一些其他選項在 **一般** 索引標籤變得可用。您可以在 **工作類型** FastTab 指定一個以上的類型，便能控制功能表項目存取。 工作類型定義了功能表項目可以處理的工作。 工作類型還可用於授與存取權限給特定使用者角色或對不同類型的作業進行單獨處理。 下表說明可用的選項。 此選項可以在 **行動裝置功能表項目** 頁面的 **導向方式** 欄位中選擇。 

<table>




<thead>
<tr class="header">
<th>選項</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>無</td>
<td>此預設值不&#39;處理工作。</td>
</tr>
<tr class="even">
<td>系統導向</td>
<td>Supply Chain Management 控制指派給工作人員的工作類型以及工作人員執行工作的順序。 選取此選項時，您可以在動作窗格上選取<strong>系統導向工作</strong>打開<strong>系統導向的排序順序</strong>頁面，您可以在其中設定工作的排序準則。 排序準則控制工作人員執行工作的順序。 您可以根據需要新增任意數量的準則。</td>
</tr>
<tr class="odd">
<td>使用者導向</td>
<td>工作人員選取要執行的工作和執行它的順序。</td>
</tr>
<tr class="even">
<td>使用者分組</td>
<td>工作人員手動分組工作。 此選項很有用，例如在工作人員在一個位置同時揀選多個品項的時候。 工作人員揀選完所有需要的物品，就可以把物品存放起來了。</td>
</tr>
<tr class="odd">
<td>系統分組</td>
<td>Supply Chain Management 根據指定的欄位為工作人員分組工作。 例如，當工作人員掃描裝運識別碼、負載識別碼或任何可以連結每個工作單位的值時，揀選工作會被分組。 若要選取此選項，則以下欄位為必要的：
<ul>
<li><strong>系統分組欄位</strong>–選取工作人員要分組工作時掃描的欄位。</li>
<li><strong>系統分組標籤</strong>–輸入文字以指示工作人員在分組工作時需掃描哪些內容。</li>
</ul></td>
</tr>
<tr class="even">
<td>驗證的使用者導向</td>
<td>當工作與更大的實體 (例如負載或裝運) 相關聯時，工作人員會選取要執行的工作。 工作人員選定揀選品項的順序。 若要選取此選項，則以下欄位為必要的：
<ul>
<li><strong>驗證使用者導向欄位</strong>–選取工作人員要分組工作時掃描的欄位。</li>
<li><strong>驗證的使用者導向標籤</strong>–輸入文字指示工作人員，若揀選工作由系統分組時要掃描的內容。</li>
</ul>
例如，當一個負載暫存在多個棧板時，此選項很有用。 如果在<strong>驗證的使用者導向</strong>欄位中選取<strong>LoadId</strong>，工作人員可以揀選與負載相關的任何棧板。 如果工作人員掃描的品項與負載無&#39;關聯，他們會收到一條錯誤消息。</td>
</tr>
<tr class="odd">
<td>叢集揀選</td>
<td>工作人員將工作分組為叢集。 叢集讓工作人員可以同時從一個位置為多個工單揀選物品。</td>
</tr>
<tr class="even">
<td>週期盤點群組</td>
<td>工作人員選取區域、工作池或位置，Supply Chain Management 根據其選取內容指派工作。 如果選取此選項，您可以在動作窗格上按一下<strong>週期盤點</strong>指定要顯示的其他資訊，您還可以指定工作人員在發現差異時必須重複盤點的次數。</td>
</tr>
 <tr class="odd">
<td>運輸裝載</td>
<td>此功能允許多個倉庫工作人員從相同或不同負載將庫存裝載到同一輛卡車上，且負載可以是全部或部分運送。</td>
</tr>
</tbody>
</table>

## <a name="additional-menu-item-options"></a>其他功能項目選項
其他功能表項目選項可在 **功能表項目** 頁面選取。 依照您設定功能表項目的過程，選項會有所不同。 

下表說明這些選項。

<table>




<thead>
<tr class="header">
<th>欄位</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>允許分割工作</td>
<td>選取此選項可讓使用者將工單的品項放入多個目標牌照中。 例如，當目標牌照已滿，並且工作人員必須將剩餘品項新增到另一個牌照時，此選項很有用。 工人可以選取<strong>滿的</strong>，指示牌照已滿並停止該牌照的接收揀選工作。 然後顯示揀選品項的放置位置，並將已完成的揀選工作移至新的工單。 目標牌照的剩餘揀選工作保留在原始工單上。</td>
</tr>
<tr class="even">
<td>錨定</td>
<td>選取此選項可讓工作人員指定的位置覆寫建議的暫存或裝載位置。 所有剩餘的存放工作都被定導向新位置。 例如因先前的負載尚未清除，工作人員在必須將訂單 1 的品項放置在裝卸站 1 旁的暫存位置卻無法時，此選項很有用。 工作人員可以決定到裝卸站 2 的暫存位置，而不是等待裝卸站 1 的暫存位置可用。 在這個案例中，工作人員會覆寫建議的暫存位置。 然後將工單的所有剩餘品項的放置位置更新為裝卸站 2 的暫存位置。 如果選擇此選項，則必須設定<strong>錨定方式</strong>欄位。</td>
</tr>
<tr class="odd">
<td>錨定方式</td>
<td>如果你&#39;使用錨定，您必須指定是透過裝運還是通過負載進行錨定。</td>
</tr>
<tr class="even">
<td>稽核範本識別碼</td>
<td>選取工作稽核範本，這將中斷此功能表項目的工作流程，以可以執行另一個作業。 例如，如果此功能表項目用於入庫工作，則稽核範本可能要求工作人員檢查交貨容器溫度。 在稽核範本上指定流程斷點。 例如，這個點可以在工作開始或完成，或者其狀態發生變化的時間。</td>
</tr>
<tr class="odd">
<td>叢集設定檔識別碼</td>
<td>選擇要用於叢集揀選的叢集設定檔。 叢集設定檔包括是否自動創叢集、位置名稱和可以指派的工作單位數量、何時將叢集拆散為單個單位以及是否需要驗證等設定。 此欄位僅在<strong>導向方式</strong>欄位中選取<strong>叢集揀選</strong>時可以使用。</td>
</tr>
<tr class="even">
<td>首先盤點品項總數量</td>
<td>選取此選項以要求工作人員在盤點期間首先盤點總數量。 如果發現差異，工作人員必須提供更多資訊，例如盤照號碼、批號和序號。</td>
</tr>
<tr class="odd">
<td>建立移動</td>
<td>選取此選項可讓工作人員建立移動工作，但不要求工作人員立即執行工作。 例如，如果品質檢驗已完成，並且檢驗員希望將品項從品質檢驗區域中移出，則此選項很有用。</td>
</tr>
<tr class="even">
<td>指令代碼</td>
<td>若要使用特定的位置指令，請選取與位置指令關聯的指令代碼。 當您建立工作並且工作建立過程為<strong>依範本移動</strong>，此選項可用。</td>
</tr>
<tr class="odd">
<td>停用週期盤點閾值</td>
<td>選取此選項可忽略週期盤點閾值。 如果您選擇此選項，則週期盤點工作不會&#39;在超過閾值時建立。</td>
</tr>
<tr class="even">
<td>顯示批次處置代碼</td>
<td>選取此選項可顯示批次處置代碼。 例如，您可以在收到退回批次時顯示批次處置代碼。 然後工作人員可以評估批次的狀態或品質，並選取適當的代碼。 批次處置代碼的規則會決定批次是否可用於其他倉庫流程。 如果你不&#39;選取此選項，將使用以下任一個批次處置代碼：
<ul>
<li>如果您收到新的批次編號，則在品項模型群組上指定的預設批次處置代碼。</li>
<li>已指派給批次的批次處置代碼。</li>
</ul></td>
</tr>
<tr class="odd">
<td>顯示處置代碼</td>
<td>選取此選項可顯示處置代碼。 例如，您可以在收到退回品項時顯示批次處置代碼。 然後工作人員可以評估品項的狀態或品質，並選取適當的代碼。 處置代碼的規則會確定品項是否可用於其他倉庫流程。</td>
</tr>
<tr class="even">
<td>顯示庫存狀態</td>
<td>選取此選項，以顯示庫存品項狀態。 此選項在所有使用現有工作的功能表項目都可使用，週期盤點除外。</td>
</tr>
<tr class="odd">
<td>顯示揀選畫面的摘要</td>
<td>選取此選項可顯示選定工單的揀選工作摘要。 在處理工單的第一個工作明細之前，將一直顯示摘要。</td>
</tr>
<tr class="even">
<td>產生牌照</td>
<td>選取此選項，會根據編號順序選擇產生唯一的牌照號碼。 例如，您可以為收到訂購單的品項生成牌照號碼。</td>
</tr>
<tr class="odd">
<td>分組存放</td>
<td>選取此選項可對存放工作進行分組。 當工作由工作人員或 Supply Chain Management 分組時，此選項可用。 當工作人員完成群組內的所有揀選工作後，為同一群組建立存放工作。</td>
</tr>
<tr class="even">
<td>庫存調整類型</td>
<td>選取的庫存調整類型，可決定用於過帳調整的庫存盤點日記帳，以及是否移除保留。 此欄位僅適用於<strong>調整進</strong>或<strong>調整出</strong>工作建立過程。</td>
</tr>
<tr class="odd">
<td>覆寫批號</td>
<td>選取此選項，則將生產訂單報告數量為已完成的工作人員，可輸入與生產訂單批號不同的批號。</td>
</tr>
<tr class="even">
<td>覆寫目標牌照</td>
<td>選取此選項可讓工作人員指定與建議的目標牌照不同的目標牌照號碼。 當工單的第一個揀選指定牌照上品項的全部數量時，請使用此選項。 例如在重複使用棧板時，此選項很有用。</td>
</tr>
<tr class="odd">
<td>揀選和包裝</td>
<td>選取此選項可讓工作人員合併銷售訂單或負載的工作到單個工作單位中。 工作人員只能對銷售訂單或負載執行工作。 例如，在為銷售訂單建立負載、裝運和工作後，當您必須增加銷售訂單的數量時，此選項很有用。 當功能表項目使用現有工作並且工作由使用者或系統導向時，此選項可用。</td>
</tr>
<tr class="even">
<td>揀選最舊的批次</td>
<td>指示工作人員是否在位置中必須首先挑選最舊的批次。 可以使用以下選項：
<ul>
<li><strong>無</strong>–工作人員可以在該位置揀選任何批次。 工作人員不會收到任何訊息。</li>
<li><strong>警告</strong>–工人可以在該位置揀選任何批次，但如果批次不&#39;是最舊的批次，他們會收到警告訊息。</li>
<li><strong>強制</strong>–工人必須揀選位置中最舊的批次。 如果批次不&#39;是最舊的批次，工作人員會收到錯誤訊息。 <strong>注意：</strong>此選項僅在指派給品項的保留階層結構中<strong>批次號碼</strong>低於<strong>地點</strong>才有意義。</li>
</ul></td>
</tr>
<tr class="odd">
<td>列印標籤</td>
<td>選取此選項可讓工作人員列印牌照標籤。</td>
</tr>
<tr class="even">
<td>系統分組欄位</td>
<td>選取此欄位決定 Supply Chain Management 如何為工作人員分組揀選工作。 例如，如果您選擇<strong>運送識別碼</strong>欄位，工作人員將掃描運送識別碼，對揀貨工作進行分組。 然後將所有的裝運工作分配給工人。 此欄位會要求您建立一個選單品項，以使用由系統分組的現有工作。 您必須在<strong>系統分組標籤</strong>欄位輸入文字以指示工作人員在分組工作時需掃描哪些內容。</td>
</tr>
<tr class="odd">
<td>系統分組標籤</td>
<td>輸入文字指示若工作按 Supply Chain Management 進行分組時，工人揀選時需掃描的內容。 例如，如果您&#39;使用 <strong>ShipmentId</strong>欄位，依照運送對揀貨工作進行分組，您可以在該欄位中輸入 <strong>裝運識別碼</strong>。 此欄位會要求您建立一個選單品項，以使用由系統分組的現有工作。 您也必須在<strong>系統分組</strong>欄位中選擇要分組的欄位。</td>
</tr>
<tr class="even">
<td>使用預設資料</td>
<td>選擇此選項在動作窗格上啟用<strong>預設資料</strong>按鈕，在其中可以選取欄位以顯示工作人員在日常工作中通常需要的資料。 例如，如果工作人員經常從同一位置揀選物品，則此選項很有用。 您可以選取<strong>起始位置</strong>欄位，以顯示預設位置。</td>
</tr>
<tr class="odd">
<td>驗證的使用者導向欄位</td>
<td>選取工作人員將掃描的欄位以對工作進行分組。 例如，如果您選取<strong>LoadId</strong>，工作人員可以選擇與選定負載相關聯的任何工作。 您必須在<strong>驗證的使用者導向標籤</strong>欄位輸入文字以指示工作人員在分組工作時需掃描哪些內容。</td>
</tr>
<tr class="even">
<td>驗證的使用者導向標籤</td>
<td>輸入文字指示工作人員，若揀選工作由驗證的使用者導向欄位分組時要掃描的內容。 例如，如果您使用 <strong>LoadId</strong> 欄位，為負載分組揀選工作，您可以在該欄位中輸入<strong>裝運識別碼</strong>。</td>
</tr>
<tr class="odd">
<td>工作範本代碼</td>
<td>選取工作範本為流程建立工作。 例如，如果您為訂購單接收一個品項，則將根據工作範本產生存放工作。 如果你不&#39;選取工作範本，Supply Chain Management 會根據查詢準則指派範本。 如需更多工作範本詳細資訊，請參閱<a href="control-warehouse-location-directives.md">使用工作範本和位置指令控制倉庫工作</a>。</td>
<tr class="even">
<td>顯示工作明細清單</td>
<td>選取一個選項，指定工作人員將如何查看目前選定的揀選工作明細並互動。 有關此選項的更多資訊，請參閱<a href="pick-line-overview.md">設定行動裝置功能表項目以提供揀選明細摘要</a>。</td>
</tr>
</tbody>
</table>

## <a name="require-workers-to-confirm-the-product-location-or-quantity-when-they-pick-items"></a>要求工作人員在揀選品項時確認產品、位置或數量

您可以設定工作確認，要求工作人員在倉庫中執行工作時使用行動裝置登記位置或數量。 工作確認有助於確保工作人員在正確的位置或正在處理正確數量的品項。 您還可以啟用 Supply Chain Management 以自動確認工作人員的登記。 如果您啟用自動確認，您不能也要求確認位置或數量。 工作確認還包括產品和產品變型。 此外，您可以通過掃描條碼來登記確認。 若要確認產品和產品變型，您必須輸入產品或產品變型的識別碼。 此識別碼可以是產品識別碼、產品搜尋識別碼、外部識別碼、GTIN 或條碼。 輸入識別碼或掃描條碼後，產品變型的維度將顯示在行動裝置上。 

下表說明可以使用工作確認的各種工作類型。

| 選項 | 描述 |
|------------------------|----------------------------------------------------------------------------|
| 揀選 | 揀選品項時需要確認。 |
| 放置 | 將物品放入某個位置時需要確認。 |
| 盤點 | 在週期盤點期間需要確認。 |
| 調整 | 調整庫存數量時需要確認。 |
| 自訂 | 需要確認自訂工作。 |
| 隔離 | 將品項移至隔離區時需要確認。 |
| 牌照組建 | 合併項目以組建牌照時需要確認。 |
| 列印 | 列印牌照標籤時需要確認。 |
| 狀態變更 | 當庫存狀態發生變化時需要確認。 |

> [!NOTE]
> 您可以要求僅對揀選工作類型進行產品確認。

## <a name="additional-resources"></a>其他資源

- [設定行動裝置功能表項目以完成訂購單類型的工作](tasks/set-up-mobile-device-menu.md)
- [設定行動裝置功能表項目以登記已接收品項](tasks/set-up-mobile-device-menu-item-register-received-items.md)
- [庫存狀態](../inventory/inventory-statuses.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]