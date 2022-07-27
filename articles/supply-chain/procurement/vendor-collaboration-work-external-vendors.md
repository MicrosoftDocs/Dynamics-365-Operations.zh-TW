---
title: 與外部廠商的廠商共同作業
description: 本主題說明採購專員如何與外部廠商協作以交換關於訂購單和寄售庫存的資訊。
author: Henrikan
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, VendVendorPortalInvoicePart, PurchaseOrderResponseActionRemarks, PurchVendorPortalAllResponse, PurchOrderInExternalReview, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3b679f8daed1e09c832a5d138473cccba03552f6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448956"
---
# <a name="vendor-collaboration-with-external-vendors"></a>與外部廠商的廠商共同作業

[!include [banner](../includes/banner.md)]

**廠商協作** 模組面向未與 Microsoft Dynamics 365 Supply Chain Management 進行電子資料交換 (EDI) 整合的廠商。 這能讓廠商處理訂購單 (PO)、發票、寄售庫存資訊和詢價請求 (RFQ)，也可以讓他們存取部分廠商主資料。 本主題說明如何與使用廠商協作界面處理 PO、RFQ 和寄售庫存的外部廠商協作。 這也解釋了如何使特定廠商能夠使用廠商協作，以及如何定義所有廠商在回應 PO 時看到的資訊。

關於外部廠商可以在廠商協作界面中執行作業的更多資訊，請參閱[廠商與客戶的協作](vendor-collaboration-work-customers-dynamics-365-operations.md)。

> [!NOTE]
> 本主題中關於廠商協作的資訊僅適用於目前版本的 Supply Chain Management。 在 Microsoft DynamicsAX 7.0 (2016 年 2 月) 和 Microsoft Dynamics AX 應用程式版本 7.0.1 (2016 年 5 月)，您可以使用 **廠商入口網站** 模組。 關於 **廠商入口網站** 模組資訊，請見[使用廠商入口網站與廠商協作](collaborate-vendors-vendor-portal.md)。

關於廠商如何在開票流程中使用廠商協作的更多資訊，請參閱[廠商協作開票工作區](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md)。 關於如何設定新的廠商協作使用者的資訊，請參考[管理廠商協作使用者](manage-vendor-collaboration-users.md)。

## <a name="defining-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>定義在廠商回應訂購單時向廠商顯示的資訊

當廠商回應您發送給他們的 PO 時，他們會看到三個訊息框之一，他們必須在其中確認他們想要接受 PO、拒絕或接受並進行更改。 由於此時必須向廠商顯示的資訊可能專屬於您的業務，因此您可以指定顯示在每條確認訊息中的文字。 例如，文本可以告知廠商流程中的後續步驟或條款和條件。

若要定義 PO 回應中顯示的文字，請執行以下步驟

1. 在 **廠商回應 PO 的資訊** 頁面選擇回應類型，然後選擇 **編輯**。
2. 在 **資訊訊息** 方塊中，輸入應在訊息框中顯示給廠商的資訊。

如果您必須以一種以上的語言增添訊息，請建立獨立的訊息，並為每種語言指定適當的語言代碼。 顯示給每個廠商的訊息將以廠商使用的語言顯示。

## <a name="setting-the-vendor-collaboration-options-for-a-specific-vendor"></a>為特定廠商設定廠商協作選項

管理員會設定廠商協作的常規設定，例如可用於與您協作的所有廠商的安全角色。 但是，每個廠商帳戶的設也可能不同。 您應該配置這些設定。

- 啟用廠商協作。
- 指定廠商是否應查看價格資訊。

### <a name="enabling-vendor-collaboration"></a>啟用廠商協作

在為外部廠商建立使用者帳戶之前，您必須設定廠商帳戶，以便廠商可以使用廠商協作。 在 **廠商** 頁面、在 **一般** 索引標籤，設定 **協作啟用** 欄位。 可以使用以下選項：

- **啟用 (PO 會自動確認)** – 如果廠商在沒有要求變更的情況下接受 PO，則會自動確認 PO。
- **啟用 (訂購單未自動確認)** – 您的組織必須在廠商接受 PO 後手動確認訂購單。

### <a name="specifying-whether-the-vendor-should-see-price-information"></a>正在指定廠商是否應查看價格資訊

若要透過廠商協作界面分享 PO 的價格資訊，您必須為廠商帳戶將 **訂購單價格/金額** 選項上的 **訂購單預設值** 選項索引標籤設定為 **是**。 此價格資訊包括單價、折扣和費用。

## <a name="working-with-pos-when-vendor-collaboration-is-used"></a>使用廠商協作時使用 PO

### <a name="sending-a-po-to-a-vendor"></a>向廠商發送 PO

PO 是在 Supply Chain Management 中準備。 當 PO 的狀態為 **經核准**，您可以在 **訂購單** 頁面選擇 **發送供確認**，將其發送給廠商確認。 然後 PO 狀態更改為 **正在外部審查**。 PO 發送後，廠商可以在廠商協作界面中的 **待審核的 PO** 頁面中查看。 然後，廠商可以接受、拒絕或建議對其進行變更。 廠商也可以新增註釋來傳達資訊，例如對 PO 的變更。 如果您想引起廠商對新 PO 的關注，您也可以使用列印管理系統，透過電子郵件發送 PO。

### <a name="confirmation-and-acceptance-of-a-po-by-a-vendor"></a>廠商確認和接受 PO

廠商接受 PO 後，可以自動確認 PO，也可以手動確認 PO。 行為取決於是否將廠商的 **協作啟用** 欄位設定為 **啟用 (PO 自動確認)** 或 **啟用 (PO 未自動確認)**。

下方資料表中顯示了典型的資訊交換，具體取決於您發送 PO 進行確認時廠商的回應。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>廠商回應</th>
<th>結果</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>廠商能<strong>接受</strong>訂單，Supply Chain Management 會設定為自動確認廠商接受的訂購單。</td>
<td>訂單狀態會更新為<strong>已確認</strong>。 如果訂單因某種原因無法&#39;更新，廠商回應仍記錄為<strong>接受</strong>，但 PO 的狀態保持<strong>在外部審查中</strong>。 

發送給廠商且狀態為<strong>在外部審查中</strong>更新為確認的交貨日期。 此更新會啟動一個新版本，該版本會自動設定為<strong>已確認</strong>的狀態。 PO 確認後，會出現在廠商協作界面中。</td>
</tr>
<tr class="odd">
<td>廠商能<strong>接受</strong>訂單，但是 Supply Chain Management 不會&#39;設定為自動確認廠商接受的訂購單。</td>
<td>廠商回應記錄為<strong>已接受</strong>，但 PO 的狀態保持<strong>在外部審查中</strong>。

發送給廠商且狀態為<strong>在外部審查中</strong>更新為確認的交貨日期。 此更新會啟動一個新版本，該版本會自動設定為<strong>在外部審查中</strong>的狀態。 然後您可以手動確認 PO。</td>
</tr>
<tr class="even">
<td>廠商<strong>拒絕</strong>訂單。</td>
<td>廠商回應記錄為<strong>已拒絕</strong>，且 PO 的狀態保持<strong>在外部審查中</strong>。 同時收到拒絕與廠商&#39;的註釋。</td>
</tr>
<tr class="odd">
<td>廠商<strong>接受</strong>訂單<strong>變更</strong>。 建議在行等級進行變更。 廠商可以接受或拒絕獨立行。 下列是廠商可以建議的其他一些變更：
<ul>
<li>變更日期或數量。</li>
<li>為不同的交貨日期或數量拆分行。</li>
<li>替代品項。</li>
</ul>
廠商可以&#39;變更價格資訊和收費。 但是，廠商可以透過使用註釋來建議這些變更。</td>
<td>廠商回應記錄為<strong>已接受變更</strong>，且 PO 的狀態保持<strong>在外部審查中</strong>。 狀態會顯示廠商建議的變更類型。 關於自動使用變更的資訊，請查看當廠商建議變更&quot;時&quot;更新 PO 本主題後方的段落。 </td>
</tr>
</tbody>
</table>

您可以使用 **訂購單準備** 工作區以監控廠商回應了哪些 PO。 此工作區包含兩個清單，其中包含狀態為 **在外部審查中**：

- 在外部審查中需要採取行動
- 在等待廠商回應的外部審查中

### <a name="changing-a-po"></a>變更 PO

若要變更廠商已回應的 PO，您必須向廠商發送新版本的 PO。 PO 將有版本尾碼，表明它是先前已發送 PO 的修改版本。 **訂購單廠商確認記錄** 頁面可讓您和廠商追蹤每個訂單的歷史記錄。 在新的 PO 被確認之前，之前確認的 PO 版本將保留在確認 PO 清單中。

### <a name="canceling-a-po"></a>正在取消 PO

當您取消 PO 時，狀態將更改為 **已核准**。 您必須將 PO 發回給廠商，以便廠商確認或拒絕取消。 確認取消後，PO 會在廠商確認 PO 清單中顯示為 **取消**。

### <a name="adding-attachments-to-a-po"></a>向 PO 新增附件

您可以使用文件管理系統向 PO 增添文件、影像和註解等附件。 當您發送 PO時，廠商將能看見 **外部** 類型的附件。

## <a name="updating-a-po-when-a-vendor-suggests-changes"></a>當廠商建議變更時更新 PO

如果廠商已回應 PO 並提出變更建議，下一步就是處理回應。

在 **訂購單準備** 工作區中，**在外部審查中需要採取行動** 清單中，您可以識別廠商已接受更改的 PO。 從此清單中，您也可以瀏覽廠商的回應。

在回應中，廠商可以更改標題上的下列資訊：
 
- 廠商文件參考
- 交貨模式
- 交貨條件
- 已確認交貨日期

廠商也可以新增註釋或附件。

在行上，廠商可以變更數量和交貨日期、新增註釋和附件、拒絕行、用作為文字輸入的另一個產品替換生產線，以及將行拆分為多次交貨。 行的狀態會有所不同，具體取決於廠商建議的變更：
    
- **已接受變更**
- **已拒絕**
- **替代** – 在這種情況下，將新增一個額外的行，其狀態為 **代替**。
- **已確認**
- **拆分為排程** – 在這種情況下，將新增額外的行，其狀態為 **排程行**。

如果行沒有變化，則行狀態為 **已接受**。

在回應中，行狀態會告訴您廠商所做的變更類型。 此外，所有已變更的欄位都會顯示為粗體，協助您識別變更。

您可以透過在回應或一次一行中選擇 **處理 PO 更新**，更新 PO。 **是否處理 PO 更新？** 標題上的欄位和行指示系統是否已處理標題或行，以使用源自回應變更的更新 PO。 你可以執行 **處理 PO 更新** 動作，每個標題或行僅動作一次。

並非所有建議的變更都可以在 PO 上更新。 只有標題的更新，以及行的日期和數量的更新，才能在 PO 上自動更新。 對於其他變更，您必須手動更新 PO。 在這種情況下，**是否處理 PO 更新？** 欄位為 **手動更新**。 例如，如果廠商建議將生產線拆分為排程，則必須手動進行此變更。

每行狀態為 **已接受**，將有一個確認的交貨日期。 當你執行 **處理 PO 更新** 動作，此日期會在 PO 上更新。 註解和附件不會自動轉移到目前的 PO。 此外，當您透過 **處理 PO 更新** 動作更新目前的 PO 時，不會在 PO 行上重新評估貿易合約。

## <a name="po-statuses-and-versions"></a>PO 狀態和版本

本節描述了 PO 在確認之前可能具有的各種狀態。 這也描述了何時向廠商提供新版本的 PO。 行為會有所不同，具體取決於您是否對 PO 使用變更管理。 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>不使用變更管理時的版本和狀態

下方資料表顯示了 PO 可能經歷的狀態和版本更改的範例。

| 動作 | 狀態和版本 |
|--------|--------------------|
| PO 的初始版本是在 Supply Chain Management 中建立的。 | 狀態 **已經過核准**。 |
| PO 會被發送給廠商。 | 在廠商協作界面註冊了一個版本，狀態變為 **在外部審查中**。 |
| 廠商會發送一個 **接受變更** 回應。 | 狀態依舊 **在外部審查中**。 |
| 您進行了廠商要求的一些變更。 | 狀態變為 **已核准**。 |
| 您將新版本的 PO 發送給廠商。 | 在廠商協作界面註冊了一個新版本，狀態變為 **在外部審查中**。 |
| 廠商會接受新版本的 PO。 | 狀態依舊 **在外部審查中**，除非廠商帳戶設定為自動將 PO 設定為 **已確認** 廠商接受它們時的狀態。 |

廠商不必使用廠商協作界面來確認 PO。 他們還可以通過其他管道發送電子郵件或傳達他們對 PO 的接受。 然後您可以手動確認訂單。 在這種情況下，即使廠商沒有回應，您也會收到一條警告，指出訂單正在確認中。 然後， PO 會作為沒有任何回應的未結確認訂單出現在確認記錄中。 此時，廠商不再具有確認或拒絕 PO 的選項。

> [!NOTE]
> Supply Chain Management 中其他流程可用的 PO 版本永遠是最新版本，即使該版本尚未在廠商協作界面中註冊也是如此。

### <a name="versions-and-statuses-if-you-use-change-management"></a>使用變更管理時的版本和狀態

如果為 PO 啟用變更管理，PO 將透過核准工作流程達到 **經核准** 狀態。 廠商無法看到此程序。

下方資料表顯示了開啟變更管理時 PO 可能經歷的狀態和版本更改的範例。 版本在 PO 被核准時註冊，而不是在 PO 發送給廠商或確認時註冊。

| 動作 | 狀態和版本 |
|--------|--------------------|
| PO 的初始版本是在 Supply Chain Management 中建立的。 | 狀態 **已經過草擬**。 |
| PO 會提交到核准程序。 (核准程序是廠商不參與的內部流程。) | 如果訂購單在審批過程中沒有被拒絕，狀態從 **草擬** 到 **審查中** 到 **核准**。 經核准的 PO 會登記為版本。 | 
| PO 會被發送給廠商。 | 在廠商協作界面註冊了一個版本，狀態變為 **在外部審查中**。 |
| 您可以手動或透過對回應使用 **處理 PO 更新** 動作來更新 PO 進行廠商請求的一些變更。 | 狀態會改回 **草擬**。 |
| PO 會再次提交到核准程序。 | 如果訂購單在審批過程中沒有被拒絕，狀態從 **草擬** 到 **審查中** 到 **核准**。 或者，可以對系統進行設定，以便特定欄位變更不需要重新核准。 在這種情況下，首先將狀態更改為 **草擬**，然後自動更新為 **經核准**。 經核准的 PO 會登記為新版本。 |
| 您將新版本的 PO 發送給廠商。 | 在廠商協作界面註冊了一個新版本，狀態變為 **在外部審查中**。 |
| 廠商會核准新版本的 PO。 | 當您收到廠商的回應，然後確認 PO 時，狀態會變為 **確認** 或自動變更。 |

## <a name="sharing-information-about-consignment-inventory"></a>正在分享有關寄售庫存的相關資訊

如果使用寄售庫存，廠商可以使用廠商共同作業介面查看以下頁面上的資訊：

- **使用寄售庫存的訂購單** – 當庫存的擁有權從廠商變更為您的公司時，寄售庫存的訂購單是在獲得庫存所有權時產生的。 同時過帳產品收據。 這些寄售單 PO 僅顯示在 **消耗寄售庫存的訂購單** 頁面。 它們不包括在 **所有確認的訂購單** 頁面中的 **廠商協作** 模組。
- **從寄售庫存接收的產品** – 此頁面列出了產品所有權已從廠商轉移到貴公司的所有交易。 廠商可以使用此資訊為客戶開立發票。
- **現有寄售庫存** – 此頁面顯示已在您的倉庫收到的廠商擁有的現有寄售庫存。

## <a name="working-with-rfqs-when-you-use-vendor-collaboration"></a>使用廠商協作時使用 RFQ

本段落描述了 RFQ 程序中客戶和廠商之間的互動。 這也會解釋如何將資訊傳達給廠商。 關於 RFQ 程序支援的基本概述，請參考[詢價 (RFQ) 概覽](request-quotations.md)。

### <a name="alternates-attachments-amendments-and-returns"></a>替代品、附件、增修條款和退貨

- **替代品** – 在 RFQ 案例的標題上，您可以指定非目錄項目行允許替代品。 啟用替代品時，廠商可以為每個請求的行新增備用行。
- **附件** – 可以在 RFQ 案例的標題等級和行等級新增附件。 附件可以分為內部或外部。 內部附件只能在客戶端查看，而廠商可以在發送後查看外部附件。

    廠商也可以在他們的投標回覆中新增附件。 廠商提交投標答復後，可以在客戶端查看這些附件。 廠商新增的附件永遠會歸類為外部附件。 若要存取廠商連同投標一起提交的附件，請選擇 **投標附件** 或 **投標行附件**。
    
    若要打開與 RFQ 案例一起發送的附件，請使用回應上的文件處理迴紋針符號。

- **增修條款** – 當增修條款最終確定時，現有的投標回覆將被刪除，方便它們被更新的值替換。 可以透過詢價案例上的日誌，查看先前投標回應中的行價格和數量等資訊。

    為了執行增修條款處理，在 **採購和採購參數** 頁面，在 **詢價** FastTab，設定 **發送詢價時鎖定 RFQ** 選項為 **是**。 (此選項是公共部門必設。)

- **退貨**–如果廠商已提交投標，但 RFQ 案例需要更多或修改的資訊，客戶可以將投標退回給廠商。 保留先前提交的投標資料，廠商可以進行請求的修改，而無需重新啟動投標過程。

## <a name="public-sector-extensions"></a>公共部門擴充

對於公共部門，擴充功能可以將 RFQ 案例發送給廠商並發布。 當您發布 RFQ 時，任何申請資訊的人都可以查看符合大多數公共部門法規的工作。 所有可用的工作都反映在 **未結的已發布詢價請求** 清單頁面上，已取消、待處理或授予的 RFQ 可以在 **關閉的已發布詢價請求** 清單頁面上查看。 透過與下列資料實體的整合，也可以在 Supply Chain Management 之外的站點上查看這些文件：

- 已發佈的詢價
- 已發佈的詢價明細
- 已發佈的詢價標題附件

這些實體允許在 Supply Chain Management 中，非預配使用者但對外部站點具有匿名訪問權限的人員查看可用和已關閉的工作。 此外，擴充功能在 **發送和發佈** 允許為 RFQ 流程設定參數的使用者定義電子郵件範本。 然後，當採購專業人員建立 RFQ 案例時，他們必須選擇電子郵件模板以將所需資訊發送給 RFQ 案例上的廠商。 

為 RFQ 流程設定參數的使用者可以建立多個電子郵件範本。 這些電子郵件範本可以包含靜態文字和下列替換標記。 建立電子郵件時，這些標記將替換為內文值。

- %RFQCase%
- %RFQCaseName%
- %bidType%
- %inviteOnly%
- %expiryDateTime%
- %requester%
- %requestingDepartment%
- %accountnum%
- %todaysdate%
- %createddate%

如果需要修改並在發送 RFQ 後發送，RFQ 將重新發送給所有受邀廠商。 發布的文件也將在 **未結的已發布詢價請求** 頁面更新。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]