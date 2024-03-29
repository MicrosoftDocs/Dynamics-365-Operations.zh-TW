---
title: 管理工程產品的變更
description: 本主題提供有關工程變更管理的資訊。 工程變更管理提供結構化流程來管理工程產品的變更，從提議、要求和進行變更，到審查和核准變更，評估其對現有交易的影響，並對其進行跟進追蹤。
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9af5184da4f9507e3c06464a223f0debaea4430e
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2022
ms.locfileid: "8450090"
---
# <a name="manage-changes-to-engineering-products"></a>管理工程產品的變更

[!include [banner](../includes/banner.md)]

工程變更管理提供用於管理工程產品變更的結構化流程。 您可以使用 *工程變更要求* 流程以提出和要求變更，然後使用 *工程變更單* 流程實際進行變更。 使用者可以建立工程變更要求或工程變更單，然後會透過流程進行審查和核准，評估對現有交易的影響，並跟進追蹤。

## <a name="engineering-change-requests"></a>工程變更要求

工程變更要求流程讓您可以掌握公司所有相關部門的變更要求。 無論您是工程師，還是在製造、採購、倉庫或銷售部門工作都沒有關係：任何人都可以使用工程變更要求來要求變更。 此變更可能是針對新產品的構想、您在使用現有產品時發現的問題、改進現有產品的建議或其他內容。

有人提出變更要求後，由工作流程管理的 *審核及核准* 流程，就會確定必須由誰核准變更 (例如產品負責人)。

要為工程變更單或工程變更要求設定工作流程，請前往 **工程變更管理\>工程工作流程**。 選擇 **新增**，選擇工作流程是用於審查工程變更單還是工程變更請求，然後設定工作流程。

有關工作流程的更多資訊，請參閱[工作流程系統概觀](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md)。 有關產品負責人的更多資訊，請參閱[產品負責人](product-owner.md)。

### <a name="create-a-new-engineering-change-request"></a>建立新的工程變更要求

要建立工程變更要求，請執行以下步驟之一。

- 前往 **工程變更管理\>一般\>工程變更管理\>工程變更要求**，然後在動作窗格選擇 **新增**。
- 開啟現有工程產品的 **產品詳細資料** 頁面。 然後在動作窗格的 **工程師** 索引標籤，於 **工程變更管理** 群組中選擇 **工程變更要求 \> 新工程變更要求**。

隨即建立新的變更要求。 您現在可以在每個 FastTab 上設定欄位，如以下子節所述。

#### <a name="general-fasttab"></a>一般 FastTab

**一般** FastTab 允許您提供變更要求的基本說明。 下表說明了此 FastTab 上的欄位。

| 欄位 | 描述 |
|---|---|
| 變更要求 | 輸入工程變更要求的名稱。 |
| 標題 | 輸入文字以簡要說明或確認要求之中的變更。 |
| 優先順序 | 選擇一個值以表示變更的優先順序有多高。 您可以根據需要為您的公司自訂可用值。 (詳細資訊請參閱[建立工程變更管理的通用值](engineering-change-management-setup.md)。) |
| 類別 | 選擇一個值來說明您要求的變更類型。 您可以根據需要為您的公司自訂可用值。 (詳細資訊請參閱[建立工程變更管理的通用值](engineering-change-management-setup.md)。) |
| 嚴重性 | 選擇一個值來表示應透過實作要求解決之問題的嚴重性。 您可以根據需要為您的公司自訂可用值。 (詳細資訊請參閱[建立工程變更管理的通用值](engineering-change-management-setup.md)。) |
| 要求者 | 建立要求使用者的姓名。 |
| 開啟 | 建立要求的日期。 |
| 狀態 | 要求的狀態。 首次建立要求時，狀態為 *已建立*。 要求獲得核准後，狀態變為 *已核准*。 如果已為要求建立了相關的變更單，則狀態將變更為 *跟進追蹤*。 |
| 變更單 | 變更單編號 (如果透過變更單跟進追蹤變更要求)。 |

#### <a name="information-fasttab"></a>資訊 FastTab

**資訊** FastTab 允許您新增有關要求的更多資訊。

要將列新增到網格，請選擇網格上方工具列的 **新增**，然後選擇以下選項之一：

- **檔案** – 上傳檔案。
- **影像** – 上傳影像檔案。
- **註釋** – 直接在網格中輸入註釋。
- **網址** – 直接在網格中輸入網址。

下表說明每個列的欄位。

| 欄位 | 描述 |
|---|---|
| 建立日期和時間 | 建立列的日期與時間。 |
| 類型 | 建立列的資訊類型 (文件、影像、註釋或網址)。 |
| 描述 | 輸入列的說明。 |
| 限制 | 透過一個值表示已新增的資訊是來自內部還是外部來源。 |
| 附件 | 選取核取方塊表示該列包含附件 (檔案或影像)。 要下載附件，請選擇該列，然後在網格上方的工具列選擇 **開啟**。 |

#### <a name="products-fasttab"></a>產品 FastTab

**產品** FastTab 允許您列出受變更要求影響的每個產品。 您可以使用工具列的按鈕將產品新增到網格中，或刪除產品。

此清單僅供參考。 因此，您可以任意新增您認為相關的產品。 如果您從 **產品詳細資料** 頁面建立現有產品的變更要求，您儲存要求記錄後，該產品應列在 **產品** FastTab。

#### <a name="source-fasttab"></a>來源 FastTab

**來源** FastTab 可讓您追蹤變更請求的起點。 例如，如果您想查看變更要求是否是從銷售訂單建立的、是誰建立的，以及是在哪個公司建立的，這會很有用。

### <a name="evaluate-the-business-impact-of-a-change-request-and-send-notifications"></a>評估變更要求的業務影響並發送通知

您檢閱變更要求時，您可以搜尋相依性。 通過這種方式，您可以評估要求的變更對未完成交易的影響，例如銷售訂單、生產訂單和現有庫存。 在檢閱變更要求時，您可以向負責履行各種類型相關訂單的人員發送通知。

#### <a name="review-affected-transactions-block-selected-transactions-and-send-notifications"></a>檢閱受影響的交易、阻止選定的交易並發送通知

如欲檢閱受影響的交易、阻止選定的交易並發送通知，請遵循以下步驟。

1. 前往 **工程變更管理\>一般\>工程變更管理\>工程變更要求**。
1. 開啟現有的變更請求，或在動作窗格選擇 **新增** 以建立新的變更要求。
1. 在動作窗格上，在 **變更要求** 索引標籤的 **業務影響** 群組中，選擇以下按鈕之一：

    - **搜尋** – 掃描所有未完成的交易，然後開啟 **對未完成交易的業務影響** 對話方塊，其中列出了將受變更影響的所有交易。
    - **查看以前的搜尋** - 開啟 **對未完成交易的業務影響** 對話方塊，其中列出了先前搜尋的結果。 (未進行新的搜尋。)

1. **對未完成交易的業務影響** 對話方塊提供了一組索引標籤，每個索引標籤會顯示受影響的特定類型交易清單 (**銷售訂單**、**訂購單**、**生產訂單**、**庫存** 等等)。 每個索引標籤還顯示一個數字，表示該類型受影響交易的數量。 選擇一個索引標籤以檢視相關清單。
1. 如欲處理清單中的交易，請選取該項交易，然後選擇工具列的以下按鈕之一：

    - **檢視交易** – 開啟選取的交易記錄。
    - **阻止訂單** – 此按鈕僅在 **銷售訂單** 索引標籤可用。選擇此按鈕以阻止選取的銷售訂單。
    - **阻止品項** – 此按鈕僅在 **訂購單** 索引標籤可用。選擇此按鈕以阻止選取的銷售訂單品項。
    - **通知負責人** – 此按鈕僅在 **銷售訂單** 索引標籤可用。選擇此按鈕以向設定為負責所選銷售訂單的使用者發送變更通知。 有關誰可以查看通知以及如何查看通知的詳細資訊，請參閱[查看和處理交易的變更通知](#review-notifications)。
    - **通知訂購人** – 此按鈕僅在 **訂購單** 索引標籤可用。選擇此按鈕以向設定為所選訂購單訂購人的使用者發送變更通知。 有關誰可以查看通知以及如何查看通知的詳細資訊，請參閱[查看和處理交易的變更通知](#review-notifications)。
    - **通知生產** – 此按鈕僅在 **生產訂單** 索引標籤可用。與銷售訂單和訂購單不同，生產訂單沒有設定為全程負責的單一使用者。 取而代之的是通常由各種主管或規劃人員，對特定站點或生產的特定部分 (例如特定資源或資源群組) 負責。 因此您選擇此按鈕時，負責所選生產訂單相關任何資源的所有使用者都會收到變更通知。 有關誰可以查看通知以及如何查看通知的詳細資訊，請參閱[查看和處理交易的變更通知](#review-notifications)。
    - **通知準備者** – 此按鈕僅在 **採購申請** 索引標籤可用。選擇此按鈕以向設定為所選採購申請準備者的使用者發送變更通知。 有關誰可以查看通知以及如何查看通知的詳細資訊，請參閱[查看和處理交易的變更通知](#review-notifications)。
    - **通知銷售負責人** – 此按鈕僅在 **報價** 索引標籤可用。選擇此按鈕以向設定為負責所選報價的使用者發送變更通知。 有關誰可以查看通知以及如何查看通知的詳細資訊，請參閱[查看和處理交易的變更通知](#review-notifications)。
    - **廢料** – 此按鈕僅在 **庫存** 索引標籤可用。選擇此按鈕以報廢選定的庫存。
    - **檢視記錄** – 使用 **對未完成交易的業務影響** 對話方塊，開啟對所選交易進行動作的記錄。 (例如記錄顯示通知是否已發送或交易是否已阻止。) 
    - **檢視所有交易** – 開啟所有交易的完整清單，而不僅是開啟的交易。

> [!IMPORTANT]
> **通知生產** 按鈕僅在 *生產工程通知* 功能已為您的系統開啟時可用。 有關如何開啟或關閉此功能及其先決條件的說明，請參閱[工程變更管理概述](product-engineering-overview.md)。

#### <a name="review-and-process-change-notifications-for-transactions"></a><a name="review-notifications"></a>檢閱和處理交易的變更通知

您可以透過以下方式閱讀和處理收到的變更通知：

- 除生產訂單外，您負責交易的變更通知會顯示在動作中心。 **顯示訊息** 按鈕位在導覽列右側 (鐘形符號)，表示動作中心有提供給您的訊息。 選擇 **顯示訊息** 按鈕開啟動作中心並檢閱訊息。
- 要查看已發送工程通知的所有生產訂單，請前往 **生產訂單\>生產訂單\>所有生產訂單**。 然後在動作窗格上，在 **產品訂單** 索引標籤的 **工程變更要求** 群組中，選擇 **工程通知** 以開啟 **工程通知** 頁面。
- 對於生產訂單，您可以選擇僅查看適用於您管理生產資源的變更通知。 在 **生產車間管理** 工作區，在動作窗格選擇 **設定我的工作區** 以篩選頁面，使其僅顯示您管理的生產單位、群組及/或資源的相關資訊。 在 **摘要** 區段有一個磚名為 **變更產品的生產訂單**，顯示與您的篩選設定相符的通知數。 選擇此磚以開啟 **工程通知** 頁面，其中顯示了符合篩選條件的完整交易清單。

您在 **工程通知** 頁面檢閱生產訂單通知時，可以透過搜尋欄值或使用動作窗格的相關命令，來追蹤相關變更單或生產訂單的連結。 在您完成評估變更並根據需要取消或修改生產訂單後，您可以將通知標記為已解決。 選擇通知，然後在動作窗格中選擇 **解決**。 該通知將從所有使用者的視圖中移除。

> [!IMPORTANT]
> 如果要能發送生產訂單通知，就需要為系統開啟 *生產工程通知* 功能。 有關如何開啟或關閉此功能及其先決條件的說明，請參閱[工程變更管理概述](product-engineering-overview.md)。

### <a name="create-a-change-order-from-a-change-request"></a>從變更要求建立變更單

正在審查工程變更要求的工程師，可以直接從 **工程變更要求** 頁面建立工程變更單。 在動作窗格上，在 **變更要求** 索引標籤上的 **工程變更單** 群組中，選擇 **複製連結及產品**。

## <a name="engineering-change-orders"></a>工程變更單

工程變更單提供用於管理工程產品變更的結構化流程。 您可以使用工程相關資料複本來提議變更。 真正的主資料不受影響。 有關工程相關資料的詳細資訊，請參閱[工程版本和工程產品類別](engineering-versions-product-category.md)。

您可以依據核准的工程變更要求建立工程變更單。 工程師還可以從頭開始建立工程變更單。 您可以按照以下任何步驟在單個工程變更單中包含多個產品：

- 手動選擇產品。
- 使用物料清單 (BOM) 納入產品結構中層次較低的產品 (即子級)。
- 利用使用處 (Where-Used) 搜尋納入產品結構中層次較高的產品 (即父級)。

變更提案完成後，將透過工作流程處理審核與核准流程。 您可以根據優先順序和嚴重性設定不同的工作流程。

要為工程變更單或工程變更要求設定工作流程，請前往 **工程變更管理\>工程工作流程**。 選擇 **新增**，選擇工作流程是用於審查工程變更單還是工程變更請求，然後設定工作流程。

有關工作流程的更多資訊，請參閱[工作流程系統概觀](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md)。

以下是一些可能必須核准工程變更單的典型利害關係人：

- **產品負責人** – 有關產品負責人的更多資訊，請參閱[產品負責人](product-owner.md)。
- **負責團隊主管** - **標題** 工程變更單視圖中的 **工程師** 欄位，可顯示建立工程變更單的工程師。 如果工程師屬於系統中定義的團隊，則 **負責** 欄位將顯示該團隊的領導者。
- **財務部門** – 財務部門可能必須審查變更涉及高成本的個案。

您可以選擇工程變更單是否應在核准後直接作為工作流程的一部分進行處理，或者是否應稍後以手動步驟進行處理。 在處理工程變更單的過程中，會更新實際產品的工程資料。

在您查看變更要求時，在動作窗格中的 **變更要求** 索引標籤的 **業務影響** 群組選擇 **搜尋**，以評估提議的變更對未完成交易的影響，例如銷售訂單、生產訂單和現有庫存。 結果顯示在 **對未完成交易的業務影響** 對話方塊，您可以在其中選擇受影響的交易，然後使用工具列中的命令查看更多資訊、通知負責使用者或阻止交易。

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>工程或營運公司的工程變更單

如[工程公司和資料所有權規則](engineering-org-data-ownership-rules.md)所述，您可以編輯的產品資料會有所不同，取決於您工作的法律實體類型 (工程公司對比營運公司)。 資料所有權規則也適用於工程變更單。 因此，視您建立工程變更單的法律實體而定，可以進行不同類型的變更。 這裡有些範例：

- 對於 *工程公司* 的工程變更單，您可以對工程資料進行基本變更。 例如，您可以建立產品的新版本、透過 BOM 變更產品結構，以及變更工程屬性值。 對於每個受影響的產品，在 **影響** 欄位選擇下列其中一項值：

    - **無** – 更新現有產品版本 (版本內更新)。
    - **新版本** – 依據所選產品版本建立的新版本。
    - **新產品** – 依據所選產品版本建立的全新產品。
    - **新類型** – 依據所選產品版本建立的新類型。 將會複製其 BOM 和路線資訊。

- 對於 *營運公司* 工程變更單，您可以變更產品的物流資料。 例如，您可以使用採購設定擴充現有 BOM、新增本地路線或本地 BOM，甚至可以為本地包裝材料、潤滑液或本地語言說明新增新的 BOM 行來擴充 BOM。 工程公司發送新的更新時，使用者在營運公司中所做的擴充將獲得保留。 如需詳細資訊，請參閱[工程公司和資料所有權規則](engineering-org-data-ownership-rules.md)。

    在工程公司中處理工程變更單時，產品只會在工程公司中建立和/或更新。 因此，如果產品主資料也需要更新，您還必須將產品發佈給營運公司。

- 您可以直接從工程變更單發佈產品。 開啟變更單，然後在動作窗格的 **變更單** 索引標籤，於 **產品發佈** 群組中選取 **發佈產品結構**。 該流程的運作方式與您從 **發佈產品** 頁面發佈產品一樣。 如需更多資訊，請參閱[發布產品結構](release-product-structure.md)。
- 您可以根據以下因素從工程變更單中自動發佈產品：

    - 重新發佈給之前發佈產品的公司。 選擇 **搜尋** 掃描所有以前的版本，然後選擇 **檢視** 以檢視結果。 **檢視** 頁面顯示之前的產品發佈，您可以選擇要重新發佈的產品。 然後關閉 **檢視** 頁面，選擇 **處理** 以重新發佈選定的產品。
    - 工程產品類別發佈控制中的自動發佈設定。 您可以將此發佈作為工作流程的一部分進行。 使用 **收集發佈提案** 區塊時，發佈提案將填入重新發佈提案 (參見上一個清單項目)；如果在工程產品類別發佈控制中選取了 **自動發佈** 核取方塊，就會將產品發佈給公司。 你可以選擇 **檢視** 以查看結果，如上一個清單項目所述。 產品也將在使用 **處理發佈提案** 區塊時發佈。 如果您選擇僅收集發佈提案作為工作流程的一部分，您可以透過選擇 **處理** 以手動開始發佈，如上一個清單項目所述。

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>透過工程變更單跟進追蹤工程變更要求

工程變更單獲得核准後，您可以透過工程變更單加以跟進追蹤。 您可以將多個工程變更要求合併到一個工程變更單中。 一個工程變更單甚至可以包括多個產品。 (一般來說，如果必須將相同變更應用於多個產品時，您會使用此方法。) 但是，您不能從單個工程變更要求建立多個工程變更單。

要透過變更單跟進追蹤變更要求，請開啟變更要求，然後在動作窗格中的 **變更單** 索引標籤，在 **工程變更單** 群組選擇 **複製連結和產品**。 然後，您可以選擇現有工程變更單以連結變更要求，或者您可以為該特定要求建立新的工程變更單。

## <a name="engineering-change-order-report"></a>工程變更單報告

工程變更單報告描述了在工程變更單中所做的變更。 它們在審核和核准過程期間和之後都很有用。

要查看工程變更單報告，請開啟相關的變更單，然後在動作窗格中的 **變更單** 索引標籤，在 **檢視** 群組選擇 **工程變更單報告**。

## <a name="fields-on-an-engineering-change-order"></a>工程變更單欄位

工程變更單的大部分欄位與已發佈產品、工程版本、文件、BOM (行) 和路線 (作業) 的欄位相同。 但是，下表中的欄位只出現在變更單之中。

| 欄位 | 描述 |
|---|---|
| 工程變更原因 | 選擇變更受影響產品的原因。 |
| 變更說明 | 輸入變更說明。 |
| 所需的特殊工具 | 指定是否需要特殊工具來進行變更。 |
| 工程材料處置 | 為應用變更時產生的任何廢棄物選擇材料處置代碼。 |
| 需要獲得客戶核准 | 指定是否需要客戶核准才能應用變更。 |
| 獲得客戶核准 | 指定客戶狀態原因。 |
| 環境健康與安全 | 指定環境健康和安全規則是否適用於變更。 如果是，您可以選擇適用的規則。 |

您可以使用 **維護/複製變更資訊** 按鈕，複製受影響產品之間的變更資訊。

## <a name="use-electronic-signatures-to-approve-and-active-boms-and-routes"></a>使用電子簽章來核准和啟動 BOM 和路線

要使用電子簽章來核准和/或啟動物料清單 (BOM) 和/或路線變更，請轉到 **組織管理\>設定\>電子簽章\>電子簽章要求**。 然後確保以下每個項目都將 **需要簽章** 設定為 *是*：

- 啟動工程變更單產品物料清單
- 啟動工程變更單產品路線
- 核准工程變更單產品物料清單
- 核准工程變更單產品路線
- 核准工程版本 BOM 和 BOM 版本
- 核准工程版本和路線版本

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
