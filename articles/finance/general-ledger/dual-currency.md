---
title: 雙貨幣
description: 本主題提供雙貨幣的相關資訊，其中報表貨幣作為 Microsoft Dynamics 365 Finance 的第二記帳貨幣.
author: kweekley
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, Ledger, AssetTransReportingCurrencyAmountsWizard,BankAccountTransReportingCurrencyAmountsWizard, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: b20c45952d2c0c28a1b785fd92bf47cfb25251fa3a3308d14130ad0f1c78305d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450642"
---
# <a name="dual-currency"></a>雙貨幣

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations 8.1 版 (2018 年 10 月) 中引入的功能，使報表貨幣能夠重新調整用途並用作第二記帳貨幣。 此功能稱為 *雙貨幣*。 無法透過設定金鑰或參數關閉雙貨幣的變更。 由於報表貨幣作為第二記帳貨幣，因此在過帳邏輯中計算報表貨幣的方式發生了變化。

此外，還增強了幾個模組，以在各種流程中追蹤、報告和使用報表貨幣。 受影響的模組包括：

- 總帳 
- 財務報表 
- 應付帳款
- 應收帳款 
- 現金和銀行管理 
- 固定資產 
- 合併

升級後，您必須完成現金和銀行管理以及固定資產的特定步驟。 因此，請務必閱讀並理解本主題的相關部分。

## <a name="posting-process"></a>過帳處理

已變更所有生成總帳會計分錄交易的過帳邏輯。 以下是之前計算報表貨幣的方式：

交易貨幣金額 \> 記帳貨幣金額 \> 報表貨幣金額

例如，以加元 (CAD) 貨幣輸入交易。 加元金額轉換為記帳貨幣，即美元 (USD)。 美元金額轉換為報表貨幣，即歐元 (EUR)。 因此，匯率必須存在於 CAD 和 USD 之間，以及 USD 和 EUR 之間。

新的計算方式如下：

交易貨幣金額 \> 記帳貨幣金額

交易貨幣金額 \> 報表貨幣金額

受到此變更影響，目前匯率必須存在於 CAD 和 USD 之間，以及 CAD 和 EUR 之間。

## <a name="reports-and-inquiries"></a>報告和查詢

各種報告和查詢現在顯示報表貨幣金額和記帳貨幣+金額。 並非所有報告和查詢都已更新。 例如，僅以交易貨幣顯示金額的報告沒有改變。

變更遵循下列兩種模式之一：

- 如果報表或查詢有足夠的空間以記帳貨幣和報表貨幣顯示金額，則會新增報表貨幣金額。
- 如果報告或查詢沒有足夠的空間來顯示兩種貨幣的金額，則新增了一個選項，以便使用者可以選擇顯示哪種貨幣。

對於各種報告和查詢，如果申報貨幣與記帳貨幣相同，或者如果申報貨幣未在法人的分類帳上定義，則還新增了邏輯以隱藏申報貨幣金額。

## <a name="financial-journals"></a>財務日記帳

財務日記帳 (例如普通日記帳和廠商發票日記帳) 已更新，以便它們包含有關報表貨幣的附加資訊。 憑證和日記帳的總計現在以報表貨幣顯示。 此外，有關報表貨幣匯率的資訊現在顯示在 **一般** 日記帳行的索引標籤。 因此，您可以在輸入交易時覆寫報表貨幣的匯率。

## <a name="vendor-invoices-sales-orders-and-sales-agreements"></a>廠商發票、銷售訂單和銷售協議
廠商發票、銷售訂單和銷售協議已更新為包括報表貨幣的固定匯率。 當交易貨幣不同時，可以為報表貨幣和報告貨幣定義固定匯率。 當記帳本位幣和記帳本位幣相同時，以記帳本位幣的固定匯率作為記帳本位幣的固定匯率，使固定匯率保持同步。 無法更改此設定的報告貨幣固定匯率。 當記帳本位幣和報告貨幣不同時，可以在交易輸入時為記帳本位幣和報告貨幣定義固定匯率。 如果未在分類帳中定義報表貨幣，則 **報表貨幣固定匯率** 欄位未啟用，並且不計算報表貨幣金額。

## <a name="module-changes"></a>模組變更

以下模組使用報告貨幣作為第二報表貨幣：

- [總帳](#general-ledger)
- [財務報表](#financial-reporting)
- [應付帳款](#accounts-payable-and-accounts-receivable)
- [應收帳款](#accounts-payable-and-accounts-receivable)
- [現金和銀行管理](#cash-and-bank-management)
- [固定資產](#fixed-assets)
- [合併](#consolidations)

### <a name="general-ledger"></a>總帳

如果在分類帳上定義了申報貨幣，則總帳已在每個會計分錄上追蹤申報貨幣金額。 但是，這些金額現在是從交易貨幣金額轉換而來的。

在 **總帳** 模組中進行了以下附加變更：

- 可以在分類帳上定義報表貨幣的獨立匯率類型。 如果組織不想使用不同的匯率類型，您可以將報表貨幣的匯率類型欄位留空。 或者，您可以選擇與記帳貨幣相同的匯率類型。 如果將該欄位留空，系統將使用記帳貨幣的匯率類型。
- 新的日記帳，即報表貨幣調整日記帳，允許僅以報告貨幣將調整過帳到分類帳。 此日記帳僅允許過帳到分類帳。 這不支持內部公司，並且貨幣必須是過帳日記帳法人的報表貨幣。 過帳日記帳時，交易貨幣和記帳貨幣金額為 0 (零)，申報貨幣金額與在交易記錄中輸入的金額一起過帳。 因為報表貨幣的使用方式 **應付帳款**、**應付帳款** 和 **固定資產** 模組已更改，此日記帳可用於升級後的調整。 有關顯示如何使用此日記帳的範例，請參閱這些模組的部分。
- 期間分配流程已更新，以便以交易、會計和報表貨幣分配金額。 以前，金額以交易和記帳貨幣分配，然後將記帳貨幣金額換算為報表貨幣。 這種行為可能會導致餘額以報表貨幣保留在分類帳戶中。 現在，在會計分錄中計算和使用金額時，不會發生轉換。
- 外幣重估程序已經重估了以報表貨幣表示的金額。 但是，報表貨幣金額現在透過交易貨幣金額計算，如本主題前面的[過帳程序](#posting-process)部分所述。
- 總帳中的許多報表和查詢已經具有報告貨幣，但少數沒有。 一個例子是 **試算表** 列表頁面。 此列表頁面現在包括記帳貨幣和報表貨幣的資料列。 請注意，如果記帳貨幣和申報貨幣相同，或者在分類帳上未定義申報貨幣，則申報貨幣的列將被隱藏。

### <a name="financial-reporting"></a>財務報表

對 **財務報告** 模組允許您以兩種方式在財務報表中包含報表貨幣金額。 在欄定義中，您可以直接報告過帳到分類帳的申報貨幣金額 (新功能)。 或者，您可以繼續將金額從記帳貨幣換算為報表貨幣 (現有功能)。

此更改可透過 **貨幣顯示** 在欄定義中設定。 如果您選擇 **從分類帳報表貨幣**，資料行中的金額未換算。 相反，它們會直接從總帳中報告。 如果您希望該列顯示已換算的金額，請選擇 **翻譯成 XXX** 選項，*XXXX* 是該列應顯示的報表貨幣。 在這種情況下，會計貨幣金額將使用現有的換算功能換算為所選的貨幣。

### <a name="accounts-payable-and-accounts-receivable"></a>應付帳款和應收帳款

這 **應付帳款** 和 **應收帳款** 模組已經追蹤報表貨幣金額。 然而，這些數量沒有顯示或用於各種程序。 進行了下列變更：

- 報表貨幣金額現在顯示在客戶和廠商的交易中。 每筆交易的未結餘額也會顯示報表貨幣金額。
- 帳齡流程已更新，因此組織可以以記帳貨幣或報表貨幣查看帳齡桶。
- 更新了各種查詢和報告，以便它們顯示報表貨幣金額。 範例包括 **客戶對帳對帳** 和 **廠商到分類帳對帳** 報告。
- 外幣重估程序已經重估了以報表貨幣表示的金額。 但是，報表貨幣金額現在透過交易貨幣金額計算，如[過帳程序](#posting-process)部分所述。
- **升級考慮：** 在升級之前，文件 (發票、付款等) 的報告貨幣金額透過記帳貨幣計算。 例如，在組織升級之前過帳發票，並且未支付發票。 在升級過程中，發票的會計分錄不會改變。 但是，升級後，雙貨幣變更生效。 因此，當為發票付款時，付款的報告貨幣金額現在透過交易貨幣金額計算。 結算付款和發票時，可能會在已實現的損益金額中計算出細微的差異，因為現在計算報表貨幣金額的方式有所不同。 如果計算出的差異被認為是重大的，則新的報告貨幣調整日記帳可用於僅以報告貨幣調整已實現損益和應付帳款/應收帳款分類帳的餘額。

### <a name="cash-and-bank-management"></a>現金和銀行管理

以前，**現金和銀行管理** 模組不會追蹤針對每個銀行帳戶過帳交易的任何報表貨幣金額。 升級後，系統會自動追蹤已過帳的任何新交易的報表貨幣金額。 但是，必須將申報貨幣金額新增到子分類帳中先前過帳的交易記錄中。

- **升級考慮：** 因為銀行帳戶交易之前沒有追蹤子分類帳中的申報貨幣金額，所以新增了一個精靈，以便您可以將申報貨幣金額新增到銀行帳戶交易中。 這個精靈 **不會** 再次過帳到總帳。 相反，它從總帳中獲取申報貨幣金額並在子帳表中更新它們。

    - 要啟動精靈，請選擇 **現金和銀行管理** \> **設定** \> **將報表貨幣金額新增到銀行帳戶交易記錄**。
    - 該精靈會顯示目前公司中申報貨幣金額為 0 (零) 的所有銀行帳戶的交易記錄。 僅包括升級前過帳的交易。
    - 對於每個銀行帳戶交易，精靈會在總帳中查找相應的會計分錄並輸入預設申報貨幣金額。 雖然金額可以編輯，但我們建議您 **不要** 編輯它們。 否則，您可能無法將銀行帳戶餘額與總帳對帳。 您應該只有在總帳中找不到申報貨幣金額時編輯金額。 在這種情況下，精靈將顯示申報貨幣的金額 0 (零)。
    - 如果您在精靈中選擇 **取消**，銀行帳戶交易和對申報貨幣金額的任何更改都會保存到您下次執行精靈時。 但是，報表貨幣金額不會在銀行帳戶交易中更新。 該更新僅在您在精靈中選擇 **結束** 時發生。 您可以多次執行該精靈。 因此，如果您犯了錯誤，您可以更正任何不正確的報表貨幣金額。

- 現金和銀行管理中的流程沒有改變，但各種報告和查詢已更新，以便它們顯示報表貨幣金額。 現金流量預測報告是一個例外。 它們未更新以加入報表貨幣金額。

### <a name="fixed-assets"></a>固定資產

此前，該 **固定資產** 模組沒有追蹤針對每個固定資產帳本過帳的交易的任何報表貨幣金額。 升級後，系統會自動追蹤已過帳的任何新交易的報表貨幣金額。 但是，必須將申報貨幣金額新增到子分類帳中先前過帳的交易記錄中。

此外，折舊過程也發生了重大變化。 這些更改需要使用者在升級後進行操作。 即使您尚未使用固定資產，閱讀並理解以下更改也很重要。

- 折舊流程確定申報貨幣金額的方式發生了變化。 以下方案比較了折舊以前如何確定申報貨幣金額和它現在如何確定申報貨幣金額。



    **折舊方案**

    使用以下金額取得和過帳資產。 請注意，申報貨幣金額在總帳中過帳，但不會儲存在固定資產分類帳表中。

    | 交易類型 | 交易金額 | 匯率 | 會計貨幣金額 | 匯率 | 報表貨幣金額 |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | 購置      | 1,000,000 丹麥克朗      | 2.0           | 500,000 美元                | 2.5           | 200,000 歐元               |

    **報表貨幣的先前折舊**

    在年底，折舊建議執行並計算下列金額。

    | 交易類型 | 交易金額 | 匯率 | 會計貨幣金額 | 匯率 | 報表貨幣金額 |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | 折舊     | 50,000 美元         | 1.0           | 50,000 美元                 | 2.6           | 19,230.77 歐元             |

    執行折舊建議時，它使用折舊方法計算記帳貨幣金額。 然後，它使用美元和歐元之間的當前匯率將該金額轉換為報表貨幣。 這種換算會導致問題，因為當使用即期匯率時，資產無法以報表貨幣完全折舊。

    **報表貨幣的新折舊**

    折舊流程已更改，因此也使用折舊方法計算報表貨幣金額。 以下是對資產進行折舊時的結果。

    | 交易類型 | 交易金額 | 匯率 | 會計貨幣金額 | 匯率                                                       | 報表貨幣金額 |
    |------------------|--------------------|---------------|----------------------------|---------------------------------------------------------------------|---------------------------|
    | 折舊     | 50,000 美元         | 1.0           | 50,000 美元                 | 2.5<blockquote>[!NOTE] 儘管顯示了此匯率，但它並未用於換算為報表貨幣。</blockquote> | 20,000 歐元                |

    執行折舊建議時，它使用折舊方法計算記帳貨幣金額和報告貨幣金額。 然後在總帳的會計分錄中使用這些金額。 不進行換算以確定報表貨幣金額。

- **升級考慮：** 由於固定資產帳簿交易以前沒有追蹤申報貨幣，因此新增了一個精靈，以便您可以將申報貨幣金額新增到固定資產帳簿交易記錄。 這個精靈 **不會** 再次過帳到總帳。 因為折舊建議計算申報貨幣金額的方式發生了變化，所以精靈 **必須** 在組織可以輸入任何折舊交易之前，為每家公司執行和完成。

    - 若要啟動精靈，請選擇 **固定資產** \> **設定** \> **將申報貨幣金額新增到固定資產帳簿**。
    - 該精靈會顯示目前公司中申報貨幣金額為 0 (零) 的所有固定資產的交易記錄。 僅包括升級前過帳的交易。
    - 精靈會 **不是** 從總帳中提取報告貨幣金額。 如前一個場景中所述，最初過帳到總帳的報告貨幣金額錯誤地使用了即期匯率。 這些金額不應出現在固定資產分類帳中，因為下一次折舊計算將使用不正確的金額。 相反，精靈會查找第一次獲取日期的匯率。 然後，它使用該匯率來推薦應在子分類帳中過帳的申報貨幣金額。 例如，這裡是精靈可能會針對前一個場景顯示的內容。

        | 固定資產 | 預約      | 交易類型 | 交易日期 | 貨幣 | 以交易貨幣計價的金額 | 金額  | 匯率 | 報表貨幣金額 |
        |-------------|-----------|------------------|------------------|----------|--------------------------------|---------|-----------|---------------------------|
        | BUIL-00001  | 200\_ SLLT | 購置      | 6/3/2016         | 丹麥克朗      | 1,000,000                      | 500,000 | 2.5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | 折舊     | 6/3/2016         | 美元      | 50,000                         | 50,000  | 2.5       |  25,000                   |
        | BUIL-00001  | 200\_SLLT | 折舊     | 6/3/2016         | 美元      | 50,000                         | 50,000  | 2.5       |  25,000                   |
        | BUIL-00001  | 200\_SLLT | 折舊     | 6/3/2016         | 美元      | 50,000                         | 50,000  | 2.5       |  25,000                   |

    - 許多客戶在工作簿中追蹤他們的資產交易詳情。 這些詳細資訊包括匯率和金額。 如果您在工作簿中有此資料，則可以建立自訂匯率類型並使用工作簿中的匯率對其進行更新。 然後，此匯率類型將用於輸入購置日期的預設匯率併計算報表貨幣金額。 如果未選擇變更匯率類型，精靈會使用分類帳上定義的匯率類型。。
    - 可以變更匯率和報表貨幣金額。 如果匯率發生更改，則使用新匯率重新計算申報貨幣金額。
    - 如果您在精靈中選擇 **取消**，固定資產帳簿交易記錄以及對匯率或報告貨幣金額的任何更改都會保存到您下次執行精靈時。 但是，報表貨幣金額不會在報表貨幣交易中更新。 該更新僅在您在精靈中選擇 **結束** 時發生。 您可以多次執行該精靈。 因此，如果您犯了錯誤，您可以更正任何不正確的報表貨幣金額。
    - 當子分類帳中的申報貨幣金額完全更新時，您 **必須** 設定 **您是否更新了固定資產帳簿交易記錄的所有申報貨幣金額？** 選項 **是的** 然後選擇 **結束**。 在您設定折舊計算之前，無法完成折舊計算 **您是否更新了固定資產帳簿交易的所有申報貨幣金額？** 選項為 **是的** 將該選項設置為 **是的**，精靈不再可用。
    - 使用申報貨幣金額更新子分類帳中的固定資產交易記錄後，這些金額將與最初過帳到總帳的金額不匹配。 但是，報告貨幣調整日記帳可用於更新總帳中折舊分類帳科目的餘額，以使其與最初過帳的金額相匹配。
    - 一個新的 **資產交易報表貨幣金額** 已新增的實體 **資料管理** 工作區允許您從精靈中匯出資料。 然後，您可以使用這些資料來確定固定資產分類帳中折舊交易記錄的餘額。 然後可以使用該餘額來確定總帳中報表貨幣調整的金額。

- **升級考慮：** 新設定欄位已新增至固定資產並用於折舊計算。 您可能必須在下一次折舊計算之前更新這些欄位。

    - 在固定資產帳簿上 (**固定資產** \> **帳簿**)，**一般的** FastTab 有一個新的 **以報表貨幣顯示的收購價格** 欄位。
    - 在固定資產帳簿上 (**固定資產** \> **帳簿**)，**折舊** FastTab 有一個新的 **以報表貨幣顯示的預期廢棄價值** 欄位。
    - 在固定資產參數 (**固定資產** \> **設定** \> **固定資產參數**)，**一般** FastTab 有一個新的 **以報表貨幣計的最低折舊額** 欄位。
    - 在帳本上 (**固定資產** \> **設定** \> **圖書**)，**一般的** FastTab 有兩個新欄位：**報表貨幣折舊進位** 和 **將帳面淨值保留為報表貨幣**。

- 由於折舊建議現在以記帳貨幣和報表貨幣計算金額，固定資產日記帳已更新，以便以報表貨幣顯示折舊金額。 對於折舊交易，交易貨幣始終是記帳貨幣。 因此，這些金額將繼續出現在 **借方** 和 **貸方** 資料行。 兩個新列，**以報表貨幣借記** 和 **以報表貨幣計的貸方**，已新增到網格中。

    - 僅當交易類型是四種折舊類型之一時，新欄位才可用：**棄用**、**折舊調整**、**異常折舊** 或 **特別折舊津貼**
    - 如果在固定資產日記帳中輸入折舊交易類型，申報貨幣金額將出現在新資料行中。 這些金額可以變更。
    - 如果帳本上的報表貨幣和報告貨幣相同，則金額將保持同步。如果你改變 **借方** 金額，**以報表貨幣計的貸方** 金額將自動更改以匹配。
    - 如果在固定資產日記帳中輸入了任何其他交易類型，則 **以報表貨幣借記** 和 **以報表貨幣貸記** 無論是在發布之前還是發布之後，都不會顯示金額。 記帳幣別和報告貨幣金額仍可在過帳到總帳的憑證上使用。
    
### <a name="consolidations"></a>合併
    
Dynamics 365 Finance 版本 10.0.5 (2019 年 10 月) 中引入的功能透過功能管理啟用功能，以增強合併和雙貨幣的靈活性。 要啟用此功能，請轉到 **功能管理** 工作區並選擇 **在總帳合併中啟用雙幣別功能**。

在總帳合併中，新增了一個新選項來合併來源公司的會計或報表貨幣金額。 如果會計或報表貨幣與合併公司的會計或報表貨幣相同，則金額將直接複製而不是換算。

-  您現在可以選擇是使用來源公司的記帳貨幣還是報表貨幣作為合併公司的交易貨幣。

- 如果其中一種貨幣相同，源公司的會計或報表貨幣金額將直接複製到合併公司的會計或報表貨幣金額。 如果兩種貨幣都不相同，則合併公司的會計和報表貨幣金額使用匯率計算。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]