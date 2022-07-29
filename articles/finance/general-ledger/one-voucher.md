---
title: One 憑單
description: One 財務日記帳的憑單 (總帳、固定資產日記帳、廠商付款日記帳等) 讓您依照 One 憑單上下文輸入多筆子分類帳交易。
author: kweekley
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: 978d0dc28f86860335a782bd2ddaa141ed639fe5
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "8450894"
---
# <a name="one-voucher"></a>One 憑單

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


## <a name="what-is-one-voucher"></a>什麼是 One 憑單？

財務日記帳的既有功能 (總帳、固定資產日記帳、廠商付款日記帳等) 讓您依照 One 憑單上下文輸入多筆子分類帳交易 (客戶、廠商、固定資產、專案和銀行)。 Microsoft 將此功能稱為 *One 憑單*。 您可以使用下列其中一種方法建立單張憑單：

- 設定日記帳名稱 (**總帳**\>**日記帳設定**\>**日記帳名稱**)，因此 **新憑單** 欄位設定為 **限 One 憑單號碼**。 您新增到日記帳的每一行現在都納入相同 One 憑單。 因此，憑單可以輸入為多行憑單、同一行的科目/沖銷科目或組合式輸入。

    [![單行。](./media/same-line.png)](./media/same-line.png)

    > [!IMPORTANT]
    > One 憑單的定義並 **不** 涵蓋日記帳名稱設定為 **限 One 憑單號碼**，但使用者接著輸入只包括分類帳科目類型的憑單。 本主題中的 One 憑單是指單張憑單包含多間廠商、客戶、銀行、固定資產或專案。

- 輸入沒有沖銷科目的多行憑單。

    [![多行憑單。](./media/Multi-line.png)](./media/Multi-line.png)

- 輸入憑證，其中科目和沖銷科目包含子分類帳科目類型，例如 **廠商**/**廠商**、**客戶**/**客戶**、**廠商**/**客戶** 或 **銀行**/**銀行**。

    [![子分類帳憑單。](./media/subledger.png)](./media/subledger.png)

## <a name="issues-with-one-voucher"></a>One 憑單的問題

One 憑單功能會在結算、稅賦計算、交易沖銷、子分類帳與總帳對帳、財務報表期間造成問題。 (更多有關結算期間會發生的問題資訊，請參閱，例如，[多名客戶或廠商記錄的單一憑單](../accounts-payable/single-voucher-multiple-customer-vendor-records.md)。) 為了正確工作和報告，這些流程和報告需要交易細節。 儘管某些設想情況可能仍須正確運作，但依照貴組織的設定，One 憑單輸入多筆交易時往往會有問題。

例如，您過帳下列多行憑單。

[![多行憑證範例。](./media/example.png)](./media/example.png)

接著您在 **Financial Insights** 工作區產生 **按廠商的費用** 報表。 此份報表的費用科目餘額先依照廠商分組，再按廠商分組。 報表產生時，系統無法判定招致 250.00 費用的廠商群組/廠商。 因為缺少交易細節，系統會假定全部 250.00 費用由憑單找到的第一間廠商招致。 因此，主科目 600120 餘額包括的 250.00 費用顯示在廠商群組/廠商下方。 不過，很有可能憑單的第一間廠商不正確。 因此，報表可能不正確。

[![按廠商的費用報表。](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>One 憑單的未來

由於使用 One 憑單時會有問題，此功能最終將會棄用。 不過，因為依照此功能會有功能差距狀況，因此不會一次性全部棄用。 反而將使用下列期程：

- **2018 年春季發行** – 本功能預設會透過 **總帳參數** 頁，**一般** 索引標籤上的 **允許 One 憑單內多筆交易** 參數關閉。 不過，如果貴組織有本主題稍候列出的其中一種功能落差情況，您可以回頭重新開啟。

    - 如果您的業務情況不需要 One 憑單，我們建議您關閉此功能。 如果即便有另一種解決方案，您仍然使用它的話，Microsoft 將不會修正本主題稍候指明區域中的 "BUG"。
    - 我們建議您停止使用 One 憑單整合，除非您需要此功能解決已經記錄的其中一種功能落差情況。

- **日後發行版本** – 使用 One 憑單就能滿足多項業務需求。 Microsoft 必須確保棄用此功能後，仍然能夠滿足系統中所有已經指明的所有業務需求。 因此，可能必須新增功能填補功能上的落差。 Microsoft 無法提供具體的解決方案，因為每項功能落差都不一樣，必須根據業務需求評估。 一些功能上的落差很可能被有助於滿足特定業務需求的功能取代。 不過，繼續允許日記帳分錄也許能填補其他落差情況，例如使用 One 憑單，但可以按需求強化系統追蹤更多細節的功能。

待所有功能落差填補後，Microsoft 將傳達該功能將被取代的訊息。 不過，取代須等到傳達後至少一年才會生效。 儘管 Microsoft 無法預估 One 憑單功能何時將被取代，但很有可能至少兩年後才會取代。 Microsoft 政策是宣布取代功能和實際取代之間至少留下 12 個月，以便客戶和獨立軟體廠商 (ISV) 有時間對更改做出反應。 例如，組織可能必須更新旗下業務流程、實體和整合。

One 憑單的取代是重大改變，將廣泛傳達。 Microsoft 將下列動作視為傳達的一部份，包括更新本主題、在 Microsoft Dynamics 365 Finance 部落格貼文、更新 "已移除或取代的功能" 主題、在適當的 Microsoft 視訊會議上傳達更改內容等。

## <a name="why-use-one-voucher"></a>使用 One 憑單的理由？

根據與客戶的對話內容，Microsoft 編譯客戶使用 One 憑證功能的設想情況清單或使用理由的清單，分列如下。 唯有 One 憑單才能滿足這些當中的一些業務需求。 不過以許多設想情況而言，替代方案可以滿足相同的業務需求。

### <a name="scenarios-that-require-one-voucher"></a>需要 One 憑單的設想情況

下列設想情況只能使用 One 憑單功能圓滿完成。 如果貴組織有任何一種設想情況，您必須先在 **總帳參數** 頁上更改 **允許一張憑單進行多筆交易** 參數設定，才能在憑單啟用輸入多筆交易功能。 這些功能落差將透過後續版本的其他功能填補。

> [!NOTE]
> 以下列每種設想情況而言，**總帳參數** 頁上的 **一般** FastTab 中，**允許一張憑單進行多筆交易** 欄位必須設定為是。

### <a name="post-vendor-or-customer-payments-in-summary-form-to-a-bank-account"></a>以摘要形式將廠商或客戶付款過帳到銀行科目

**設想情況** 組織向銀行傳達廠商清單和金額，而銀行使用此清單代表組織支付廠商款項。 銀行將付款總額在銀行科目上過帳為單次提款。

廠商付款摘要只透過 One 憑單支援。 每間廠商以分開明細輸入，以維護應付帳款分類帳的細節。 不過，所有付款的彙總金額會沖銷到單筆銀行科目明細。 因此，提款在銀行分類帳顯示為單筆彙總金額。

**設想情況** 組織存入客戶付款，或銀行代表組織存入客戶付款，而存款在銀行科目顯示為一次性付款。

客戶付款摘要典型透過存款功能支援。 不過，如果您在付款方式上使用 "橋接"，則只透過 One 憑單支援此種設想情況。 客戶付款的輸入方式與廠商付款摘要描述的方式相同。

### <a name="mechanism-to-group-transactions-from-a-business-event"></a>從商務活動轉為群組交易的機制

**設想情況** 組織有一件觸發多筆交易的商務活動。 不過，會計部門希望一起檢視會計分錄以取得更健全的稽核性。

如果組織必須一起檢視商務活動的會計分錄，它必須使用 One 憑單功能。 

### <a name="country-specific-features"></a>國家/地區特定功能

**設想情況** 波蘭的單一行政文件 (SAD) 功能目前要求使用單一憑單。 您必須繼續使用 One 憑單功能到此功能開放群組選項。 也許會有額外的國家/地區特定功能需要 One 憑單功能。

### <a name="customer-prepayment-payment-journal-that-has-taxes-on-multiple-lines"></a>有多條稅賦 "明細" 的客戶預付款日記帳

在這種設想情況下，單一憑單的客戶是同一位客戶，因為交易模擬客戶訂單的明細。 預付款必須輸入到單一憑單，因為必須在客戶的單筆付款 "明細" 上計算稅賦。

### <a name="customer-reimbursement"></a>客戶請款

**設想情況** 客戶對訂單進行預付款動作，而且訂單明細有不同稅賦必須為預付款清楚記錄。 預付客戶款項是模擬訂單明細的一筆交易，因此可以針對每條明細的金額記錄適當的稅賦。

如果定期請款任務是從應收帳款模組執行，它會建立一筆交易以將餘額從客戶移到廠商。 以這種設想情況而言，必須使用 One 憑單向客戶請款。

### <a name="fixed-asset-maintenance-catch-up-depreciation-split-asset-calculate-depreciation-on-disposal"></a>固定資產維護：追補折舊、分拆資產，計算處置的折舊
10.0.21 和後續版本中，追補折舊、分拆資產和計算資產處置折舊的固定資產交易將使用不同的憑單編號建立。

### <a name="bills-of-exchange-and-promissory-notes"></a>匯票和本票
匯票和本票需要使用 One 憑單，因為交易根據付款狀態將客戶或廠商餘額從一個應收帳款/應付帳款分類帳科目移到另一個科目。

## <a name="scenarios-that-dont-require-one-voucher"></a>不需要 One 憑單的設想情況

下列設想情況可透過其他方式完成，不應使用 One 憑單功能。

### <a name="post-customer-payments-in-summary-form-to-the-bank-account"></a>以摘要形式將客戶付款過帳到銀行科目

組織存入客戶付款，或銀行代表組織存入客戶付款，而存款在銀行科目顯示為一次性付款。

當付款方式未使用 "橋接" 時，客戶付款摘要會透過存款功能支援。

### <a name="netting"></a>淨額結算

淨額結算中，廠商和客戶餘額會互相結算淨額，因為廠商和客戶是同一邊的合作對象。 這種方法將組織與客戶/廠商之間的金錢兌換程度降到最低。

淨額結算可藉由在分開憑單中輸入增加和減少，然後將沖消過帳到清算分類帳科目完成。

### <a name="post-in-summary-to-the-general-ledger"></a>彙總過帳到總帳

組織往往希望彙總過帳到總帳，盡量減少資料量。 不過，這些組織通常仍會要求維護交易細節。 當透過單一憑單彙總過帳時，交易細節是未知且無法維護。

- 因為目前交易細節無法維護，我們建議組織 **不** 使用 One 憑單彙總過帳。
- 移除對 One 憑單的支援後，可以在日記帳落實來源文件和會計框架。 接著這些框架將維護交易細節並支援彙總到總帳。


### <a name="settle-multiple-unposted-payments-to-the-same-invoice"></a>將多筆未過帳付款結算到同一張發票

這種設想情況通常出現在客戶可以使用多種付款方式支付購買行為的組織。 這種設想情況下，組織必須能夠記錄多筆未過帳付款並按照客戶發票結算。

已經在 Microsoft Dynamics 365 for Operations 1611 版本 (2016 年十一月) 新增的功能允許多筆未過帳付款按照單一發票結算。 多筆客戶付款不再需要輸入單一憑單。

### <a name="import-bank-statement-transactions"></a>匯入銀行對帳單交易

銀行往往代表組織收付款項，而這些交易會透過從銀行收到的檔案記錄在 Finance。 組織往往希望使用檔案中的銀行對帳單編號將這些交易成分一組。 因為每筆交易細節都會在銀行對帳單顯示，所以銀行分類帳不需要彙總。

各筆交易可以使用日記帳上的其他欄位分組，例如日記帳批號本身或文件編號。


### <a name="transfer-balances"></a>轉移餘額

組織可能必須將餘額從一間廠商轉移到另一間廠商，因為錯誤或因為另一間廠商已經接收負債。 這類型移轉也發生在如 **客戶** 和 **銀行** 的科目類型。

餘額從一個科目 (廠商、客戶、銀行等) 轉移到另一個科目可透過分開憑單進行，而沖銷可過帳到結算分類帳科目。

### <a name="enter-beginning-balances"></a>輸入期初餘額

組織往往將分類帳科目 (廠商、客戶、固定資產等) 的期初餘額輸入為一筆憑單交易。 每個分類帳科目的期初餘額可輸入為分開的憑單，而沖銷可以過帳到結算分類帳科目。

### <a name="correct-the-accounting-entry-of-a-posted-customer-or-vendor-document"></a>改正已過帳的客戶或廠商文件的會計分錄

組織可能必須改正已過帳發票會計分錄的應收帳款或應付帳款分類帳科目，但此發票無法透過另一項機制沖銷或改正。

如果必須改正應收帳款或應付帳款分類帳科目，必須直接對調整分類帳科目。 調整無法藉由過帳廠商或客戶進行。 這套辧法要求在 "休整" 期間調整，分類帳戶才可暫時允許手動分錄。

### <a name="the-system-allows-it"></a>"系統允許"

組織往往使用 One 憑單功能的原因只是因為系統允許他們使用，其實不了解隱含用意。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
