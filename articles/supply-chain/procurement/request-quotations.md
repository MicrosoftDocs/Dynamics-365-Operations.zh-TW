---
title: 詢價 (RFQ) 概觀
description: 本主題將概述詢價 (RFQ)。 當組織希望從多個廠商取得必須購買的產品或服務的競爭性報價時，就會簽發 RFQ。
author: Henrikan
ms.date: 10/05/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage, BOMExpandPurchRFQ, PurchRFQReplyFollowupItem, PurchRFQCaseVend, PurchRFQReplyFollowup, PurchRFQCaseAmendmentInfo, PurchRFQReplyFollowupCase, PurchRFQReplyStatus, PurchRFQCaseReplyFields, PurchRFQAddQuestionnaire, PurchRFQAmendmentWizard, PurchRFQReplyTableStatus, PurchRFQReplyTableListPage, PurchRFQCancelWizard
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2154"
- intro-internal
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7338897feb2c3a28350d366f26eecc56f8eeb3fb
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449700"
---
# <a name="requests-for-quotation-rfqs-overview"></a>詢價 (RFQ) 概觀

[!include [banner](../includes/banner.md)]

本主題將概述詢價 (RFQ)。 當組織希望從多個廠商取得必須購買的產品或服務的競爭性報價時，就會簽發 RFQ。 在 RFQ 中，您會要求廠商提供您指定產品數量的價格和交貨時間。
您還可以要求廠商指定是否有任何雜費，例如運費、大量訂單的任何折扣或廠商發票提前付款。

RFQ 程序包括以下工作：

1. 建立 RFQ 並將其傳送給一個或多個廠商。
1. 接收和登記出價 (RFQ 回覆)。
1. 將您接受的出價轉移到訂購單、採購合約或採購申請。

下圖顯示了 RFQ 程序的概觀。

[![RFQ 程序。](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

您可以從計劃訂單、採購申請或手動輸入建立 RFQ 案例。 RFQ 案例是用於向每個廠商簽發 RFQ 的基本文件。

準備 RFQ 案例並新增廠商後，在 RFQ 案例上選擇 **傳送**(公共部門的 **傳送並發佈**)。 為您傳送 RFQ 的每個廠商產生 RFQ 日記帳。 您可以為「傳送」動作設定 [列印] 選項，以便列印每個廠商的報告以進行封存，或將報告傳送到每個廠商的電子郵件地址。 此外，您可以使用每個廠商的 RFQ 日記帳產生報告，以稍後傳送或重新傳送給廠商。 您還可以設定「傳送」動作，以便其產生廠商可以填寫的回覆表。

本主題涵蓋不使用廠商共同作業時處理 RFQ 的程序。 如果您的系統設定為廠商共同作業，廠商可以直接在 Supply Chain Management 中輸入出價。 有關詳細資訊，請參閱[廠商與客戶共同作業](/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations)和[廠商與外部廠商共同作業](vendor-collaboration-work-external-vendors.md)。

如果在傳送 RFQ 後必須進行修改，您可以在完成後使用以下兩個修改動作將 RFQ 重新傳送給廠商：建立和完成。

當您透過電子郵件收到出價時，您可以從 **詢價** 頁處理這些出價。

如果需要廠商的第二次回覆，請在 **詢價** 頁面上選取 **傳回**。 「傳回」動作會產生新的日記帳和報告，這些報告將根據您的列印設定進行列印、封存和傳送。

如果您在 RFQ 案例中新增了評分標準，RFQ 將會有評分面板讓您在其中輸入分數。 當您在 **比較回覆** 頁面上比較回覆時，總分將顯示在 RFQ 上。 在 **比較回覆** 頁面上，您還可以比較其他回覆資料，例如細項價格、交貨日期和總價。

在您選擇出價或出價中的多個細項後，您可以接受全部或部分細項並拒絕其餘細項。 產生接受日記帳、拒絕日記帳和相應的報告，並將根據您的列印設定進行列印、封存和傳送。 當您接受出價或出價中的特定細項時，將產生採購合約或訂購單，或更新採購申請，依 RFQ 的採購類型而定。 您可以建立一個適用於未來任何回覆的貿易合約，無論您是接受還是拒絕它們。

RFQ 案例有兩種狀態：最低和最高，您可以在清單頁面查看 **所有詢價** 的狀態。 最低狀態是 RFQ 案例中任何細項最不進階的階段，最高狀態是 RFQ 案例中任何細項最進階的階段。 例如，假設將一個包含三個細項的 RFQ 案例傳送給兩個廠商，因此有兩個 RFQ，每個 RFQ 包含三個細項。 所有細項都是 **傳送**。 現在有其中一家廠商輸入出價，且 RFQ 細項的狀態為 **已收到**。 這代表在 RFQ 案例的三個細項中，一個 RFQ 的細項都是 **傳送**，而另一個 RFQ 的細項都是 **已接收**。 最低狀態為 **傳送**，最高狀態為 **已接收。**

這些狀態將在本主題之後的內容中更詳細說明。

## <a name="setting-up-rfq-functionality"></a>設定 RFQ 功能

在建立 RFQ 案例之前，您必須在 **採購和開源參數** 頁上設定 RFQ 資訊。 建立 RFQ 案例時，您可以指定要複製到 RFQ 的預設值。 您可以指定以下預設值：

- 新 RFQ 的採購類型：**訂購單** 貨 **採購合約**
- 自 RFQ 案例建立之日起的到期日和時間位移。
- 徵集類型，可能預設為 RFQ 案例的特定評分方法。
- 交貨資訊和付款條件。

您可以為特定的 RFQ 案例覆寫這些值。

您也應該設定修改程序。 作為此設定的一部分，您可以打開欄位鎖定。 打開欄位鎖定後，想修改 RFQ 的採購專業人員必須先在 RFQ 案例 **報價** 索引標籤的 **修改** 區段中選擇 **建立**。 然後，在 RFQ 案例透過修改更新後，採購專業人員必須選取 **完成** 來完成流程。 「完成」動作會產生一封電子郵件，通知廠商修改 RFQ 的相關資訊。

在 **採購和開源參數** 頁面上，選擇要用於傳送給廠商的電子郵件通知範本。 在 **電子郵件範本** 中建立範本時，其可以包含以下取代權杖：

- %RFQ case%
- %Reason for bid return%
- %Reason for amendment%
- %Amendment prepared by%
- %Company%
- %RFQ case name%
- %Expiry Date Time%
- %Date%

%Reason for bid return% 和 %Reason for modify% 權杖被取代為採購專業人員在 **修改** 精靈中完成修改時可以輸入的文字。 %Amendment prepared by% 和 %Company% 權杖的值會自動從 RFQ 中取得。 %Date% 權杖會由目前的日期取代。

如果您想在傳送 RFQ 後取消它，您可以從 RFQ 案例中執行此作業。 對於取消，需要電子郵件範本以將取消通知傳送給廠商的連絡人。 範本必須在 **採購和開源參數** 頁面上選取。 在建立範本時，其可以包含以下取代權杖：

- %Reason for cancellation%
- %RFQ case%
- %RFQ cancelled by%
- %Company%
- %RFQ case name%
- %Date%

%Reason for cancel% 權杖會由採購專業人員在 **取消** 精靈中輸入的文字取代。 %Date% 權杖會由目前的日期取代。

如果您想在出價中使用原因代碼來表明出價遭到拒絕或接受的原因，您必須在 **廠商原因** 頁面上設定原因代碼。

在採購和開源中的 **表單設定** 頁面上，您可以設定列印或儲存 RFQ 文件的外觀。

> [!NOTE]
> 對於公共部門設定，您必須使用修改程序來變更已傳送的 RFQ。 傳送 RFQ 後，將鎖定欄位。
因此，若要變更 RFQ，您必須選取 **建立** 以開始修改程序，如前所述。 鎖定行為由 **採購和開源參數** 頁面上的 **傳送 RFQ 時鎖定**。 根據預設，此參數設為 **是**，對於公共部門設定，該預設設定無法變更。 因此，雖然修改程序可以在非公共部門設定中手動處理，但其必須用於公共部門設定。

當您建立訂購單類型的 RFQ 案例並將庫存品項新增到 RFQ 時，將產生庫存交易，其收貨狀態為 **報價收據**. 使用主計劃計算供應時，僅考慮具有此狀態的 RFQ 案例細項。 如果您希望主計劃包含 RFQ 案例細項做為預期收據，則必須在主計劃設定中設定此行為。

採購經理或代理人可以建立和維護徵集類型以滿足組織的採購要求。 每個徵集類型都可以與一個評分方法相關聯。 評分方法由一組準則組成，您可以在評分出價時使用這些準則。 您必須在 **徵集類型** 和 **評分方法** 頁面上設定徵集類型、評分方法和評分標準。

## <a name="choose-default-fields-to-include-in-vendor-rfq-reply-forms"></a><a name="default-reply-fields"></a>選擇要包含在廠商 RFQ 回覆表單中的預設欄位

當廠商回覆 (出價) 詢價 (RFQ) 時，您可以指定希望廠商回覆的特定類型資訊。 您標記為預設的欄位會包含在為廠商共同作業提供的線上表單中。 若要進行這些設定：

1. 如果您還沒有這樣做，請使用 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)頁面以啟用 *選取要包含在廠商 RFQ 回覆表單中的 RFQ 欄位* 功能。
1. 移至 **採購和開源 > 設定 > 採購和開遠參數**。
1. 打開 **詢價** 索引標籤。
1. 選取 **設定報價要求的預設值** 標題下的 **預設報價要求** 回覆欄位連結。
1. 隨之開啟 **預設詢價回覆欄位** 對話方塊。
1. **廠商 RFQ 回覆表單中包含的 RFQ 欄位** 區段包含可用於 RFQ 回覆表單的每個欄位滑桿。 此區段中設為 *是* 的欄位將包含 (連同其值) 在 RFQ 回覆表單中。 對於要防止廠商在檢閱出價時看到資料的任何欄位，將滑桿設為 *否*。 這可您在 RFQ 輸入期間為內部用途輸入估計值或預期值，又不會讓廠商看到輸入的內容。

您可以根據需要為個別 RFQ 案例覆寫這些設定。

## <a name="creating-and-sending-an-rfq"></a>建立和傳送 RFQ

建立 RFQ 案例，選擇要在 RFQ 案例中出價的廠商，然後將 RFQ 傳送給廠商。 您可以使用 [列印] 設定將 RFQ 報告和回覆表報告傳送到您的慣用目的地。

您可以手動建立 **訂購單** 採購類型或 **採購合約** 採購類型的 RFQ 案例。

如果 RFQ 案例屬於 **訂購單** 類型，則會出現以下與其他類型的 RFQ 案例不同的行為：

- 建立 RFQ 案例細項時，將產生收據狀態為 **報價收據** 的庫存交易。
- 當您接受出價時，會產生訂購單。

如果 RFQ 案例屬於 **採購合約** 類型，則會出現以下與其他 RFQ 案例不同的行為：

- RFQ 案例用於在一段時間內購買特定數量或價值之產品的合約。 您必須選擇適用於採購合約的日期範圍以及管理採購合約人員的姓名。
- 當您接受出價時，會產生採購合約。

如果 RFQ 案例是從採購申請產生的，則會自動指派 **採購申請** 類型。 您無法手動建立 **採購申請** 類型的 RFQ 案例。

只有當採購申請的狀態為 **檢閱中** 且您被指派執行下一個工作流程工作時，您才可以從採購申請建立 RFQ 案例。 當您接受來自廠商的出價 (RFQ 回覆) 中的細項時，採購申請中的細項會自動更新。 在使用已接受的 RFQ 細項更新申請細項或取消 RFQ 案例之前，您無法完成、拒絕、核准或對採購申請執行任何其他動作。

建立 RFQ 案例時，您可以選取徵集類型。 徵集類型決定了一組評分準則，用於對 RFQ 案例的 RFQ 回覆進行評分。

您可以將問卷新增到 RFQ 案例。 在您傳送 RFQ 後，此問卷將出現在所有 RFQ 回覆中。 完成問卷是提交出價之前的一項強制性工作。

儘管提供了預設值，但您可以根據需要為個別的 RFQ 案例變更 **廠商 RFQ 回覆表單中包含的 RFQ 欄位** 設定。 若要這樣做，請建立或打開 RFQ 案例。 然後，在「動作」窗格中，打開 **報價** 索引標籤，並在 **回覆** 區段選取 **設定 RFQ 回覆預設值**。 隨即打開 **預設詢價回覆欄位** 對話方塊，其運作方式與設定廠商 RFQ 回覆表單的預設值時相同，只不過您在此處的變更只會影響目前的 RFQ 案例。 有關如何啟用此功能及其運作方式的詳細資料，請參閱[選擇要包含在廠商 RFQ 回覆表單中的預設欄位](#default-reply-fields)。

有三種方法可以選取要新增到 RFQ 案例的廠商：

- 一一新增廠商。
- 搜尋所有符合特定條件的廠商。
- 自動新增所有核准用於 RFQ 案例細項之採購類別的廠商。

RFQ 案例準備就緒後，選取 **傳送**。 「傳送」動作會產生日記帳和報告，這些報告將根據您的列印設定進行列印、封存和傳送。

如果在將詢價傳送給廠商時，在 **傳送詢價** 頁面上將 **使用廠商重新計算價格** 和 **使用廠商特定項目資訊** 設為 **是**，則某些特定廠商資訊會自動輸入到該廠商的 RFQ 中。

## <a name="amending-an-rfq-case"></a>修改 RFQ 案例

有時，您必須在傳送 RFQ 案例後對其進行變更。 例如，如果交貨日期已變更，或您需要更多產品或不同數量的產品，您可能必須變更 RFQ 案例。 您可以設定修改程序，以提升或降低其限制性。

如果您將修改程序設定為更具限制性，則在修改已傳送 RFQ 案例上的欄位之前，您必須在 RFQ 案例上選擇 **建立** 以進行修改。 變更完成後必須選取 **完成**。 然後，將引導您完成為已傳送電子郵件新增資訊的程序，該電子郵件用於通知廠商有關修改的資訊。 更新後的 RFQ 報告 (包括修改附註) 會自動附加到電子郵件中。

如果您將修改程序設定為更少限制性，則無需選擇 **建立** 即可修改已傳送 RFQ 案例上的欄位。 但是，您必須在 RFQ 上手動新增修改附註並再次傳送案例。 請注意，只有在未編輯任何回覆 (出價) 時才能使用此方法。 如果您輸入了回覆且其處於 **已接收** 狀態，則 **傳送** 按鈕無法使用。 在這種情況下，您必須選取 **建立**，然後選取 **完成**，因為您必須在更嚴格的程序中執行此作業。 然後重設回覆以反映對 RFQ 案例的變更。

如果廠商使用廠商共同作業介面輸入開價，則必須一律使用修改程序通知廠商有關 RFQ 案例的變更。 此程序有助於防止廠商在開價過程中對已過期的 RFQ 案例進行開價。 如需廠商共同作業的詳細資訊，請參閱[廠商與外部廠商共同作業](/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors)。

如果您想邀請更多廠商開價，且沒有對 RFQ 案例進行任何變更，您可以使用 **傳送** 按鈕。 您新增的廠商會出現在 **傳送** 頁面上，並會收到電子郵件邀請。

## <a name="receiving-and-registering-rfq-replies"></a>接收和登記 RFQ 回覆

傳送 RFQ 時會自動產生回覆表。 收到 RFQ 的開價時，必須按一下 **編輯詢價回覆** 動作，透過 **詢價** 頁面輸入開價。 這可讓您在專用開價表單中輸入開價資訊。 一開始的 **回覆進度** 會是 **未開始**。 當您點選 **編輯 RFQ 回覆** 時，進度狀態會是 **購買者正在更新**，直到提交開價。 當您輸入出價資訊後點選 **提交**。 回覆進度狀態將變更為 **購買者已提交**。 同樣地，啟用廠商共同作業後，**回覆進度** 將隨著廠商與開價的互動而更新。 然後狀態從 **廠商正在更新** 變更為 **廠商已提交**。 提交開季後，會建立名為 **已接收** 的日記帳。 必須提交回覆 (出價) 才能登記為已接收，然後才能進一步處理為接受或拒絕。

如果需要更新出價，則應按照與上述相同的程序重新提交。

請注意，只有與處理開價相關的資訊才允許編輯 **詢價** 表單，而不能用於輸入出價。 若要輸入或修改出價，請按一下 **編輯 RFQ 回覆**。

當您輸入出價資訊時，如果 RFQ 案例允許替代細項，您可以為僅具有採購類別且未指定目錄項目的細項新增替代細項。 點選 **新增替代** 以新增替代細項。

如果您已輸入回覆但需要廠商提供新報價，您可以傳回 RFQ。 這會產生新的日記帳和報告，可以將其傳送給廠商。

您可以在 **詢價跟進** 頁面上查看所有 RFQ 及其狀態的概觀：**已傳送、已接收、已接受、已拒絕、已取消、已回絕**。

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>接受和拒絕出價，並將接受的出價轉移到下游文件

在確定最佳出價 (例如提供最佳總價的出價) 後，您會接受該出價。 您可以接受開價中的某些細項並拒絕其他細項。
您還可以接受來自不同廠商的細項。 請注意，如果您接受某些細項，系統會提示您拒絕所有其他細項。 因此，如果要接受其他細項，則必須在出現提示時選取 **取消**。 您接受廠商開價或細項後，其各廠商的 RFQ 回覆狀態會更新為 **已接受**。

如果您在準備訂購單或採購合約時需要將額外細項新增至 RFQ，您可以按一下 **詢價** 頁面細項格線上的 **新增細項** 來進行。 您只能在 **詢價** 頁面中檢視和編輯此細項。 當細項被接受時，將顯示在開價頁面上。

當您接受開價或開價中的一個或多個細項時，會自動產生訂購單或採購合約。 然後，您可以拒絕所有其他廠商的開價。

在回覆中，您可以新增原因代碼來解釋您接受或拒絕出價的原因。

當您接受 **採購申請** 類型的出價時，採購申請細項將更新以下資訊，其反映已接受開價的資訊：

- 單價
- 折扣百分比
- 折扣金額
- 購買費用
- 細項費用
- 廠商
- 外部數字
- 外部描述

下表顯示當您接受和拒絕廠商開價時，RFQ 狀態如何變化。

## <a name="statuses--highest-and-lowest"></a>狀態 - 最高和最低

在 RFQ 案例的廠商索引標籤上，您可以查看特定廠商狀態最高和最低的細項。 已新增廠商時且未傳送任何細項時，最低和最高狀態都是<strong>已建立</strong>。 當 RFQ 連同所有細項傳送給廠商時，這兩個細項的狀態將會是<strong>已傳送</strong>。 如果廠商開價中的某些細項被接受而其他行被拒絕，則被拒絕的細項將為最低狀態，即<strong>已拒絕</strong>，而接受的細項將獲得最高狀態，即<strong>已接受</strong>。

在 RFQ 案例細項中，您可以查看所有廠商每個細項的最高和最低狀態。 如果您已向 RFQ 案例中的所有廠商傳送了細項，但沒有人回覆，那麼最低和最高狀態都會是 **已傳送**。 至少有一個廠商回覆時，最高狀態將變更為 **已接收**。 如果您將新廠商新增到案例中，則最低狀態將變更為 **已建立**

RFQ 案例的最高和最低狀態是\<廠商索引標籤和細項索引標籤的彙總。

狀態會依以下方式從低到高排列：已建立、已傳送、已接收、已拒絕、已接受、已回絕、已取消。

下表顯示了當您建立具有細項的 RFQ 案例然後將其傳送給廠商時，RFQ 案例狀態如何變化。

| **動作**                                | **最低 RFQ 案例狀態** | **最高 RFQ 案例狀態** | **最低 RFQ 案例細項狀態** | **最高 RFQ 案例細項狀態** |
|-------------------------------------------|----------------------------|-----------------------------|---------------------------------|----------------------------------|
| 建立 RFQ 案例標題和細項。      | 已建立                    | 已建立                     | 已建立                         | 已建立                          |
| 將 RFQ 傳送給 RFQ 案例中的所有廠商。 | 已送出                       | 已送出                        | 已送出                            | 已送出                             |
| 新增其他廠商。                       | 已建立                    | 已送出                        | 已建立                         | 已送出                             |
| 將 RFQ 傳送給第二個廠商。        | 已送出                       | 已送出                        | 已送出                            | 已送出                             |

RFQ 上與 RFQ 案例相關的所有細項都將處於 **已傳送** 狀態。

下表顯示了當您收到開價並在 RFQ 回覆表上登記資訊時，RFQ 狀態如何變化。

| **動作**                                               | **所有詢價中所有細項的最低狀態** | **所有詢價中所有細項的最高狀態** | **最低 RFQ 案例標題狀態** | **最高 RFQ 案例標題狀態** | **最低 RFQ 案例細項狀態** | **最高 RFQ 案例細項狀態** |
|----------------------------------------------------------|------------------------------------------------|-------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------|----------------------------------|
| 將一個廠商的開價登記到 RFQ，然後儲存。        | 已送出                                           | 已收到                                        | 已送出                              | 已收到                           | 已送出                            | 已收到                         |
| 將第二個廠商的開價登記到 RFQ，然後儲存。 | 已收到                                       | 已收到                                        | 已收到                          | 已收到                           | 已收到                        | 已收到                         |


在以下範例中，您可以看到 RFQ 案例的最高和最低狀態，其中一個開價為已接收，另一個開價為已接受。 當接收的開價被拒絕時，RFQ 案例標題和細項上的最低狀態將從已接收變更為已拒絕。


|            <strong>動作</strong>             | <strong>所有詢價中所有細項的最低狀態</strong> | <strong>所有詢價中所有細項的最高狀態</strong> | <strong>最低 RFQ 案例標題狀態</strong> | <strong>最高 RFQ 案例標題狀態</strong> | <strong>最低 RFQ 案例細項狀態</strong> | <strong>最高 RFQ 案例細項狀態</strong> |
|------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------------------------|
| 接受其中一個開價。 (或至少一個細項) |                          已收到                           |                           已接受                           |                    已收到                    |                    已接受                     |                   已收到                   |                   已接受                    |
|           拒絕所有其他出價。           |                          已拒絕                           |                           已接受                           |                    已拒絕                    |                    已接受                     |                   已拒絕                   |                   已接受                    |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]