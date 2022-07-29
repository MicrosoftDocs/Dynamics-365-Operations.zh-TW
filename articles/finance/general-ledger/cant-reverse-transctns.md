---
title: 為什麼無法沖銷此交易？
description: 本主題將介紹無法沖銷交易的不同原因。 其中還列出了此問題的解決方案。
author: kweekley
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 869832f085ee91f6c1fee53dad508cf5e54535627dadd6fb59a7586b03c8ec3b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450186"
---
# <a name="why-cant-i-reverse-this-transaction"></a>為什麼無法沖銷此交易？

[!include [banner](../includes/banner.md)]

本主題將介紹無法沖銷交易的不同原因。 其中還列出了此問題的解決方案。

## <a name="symptom"></a>異常徵兆

組織可能會遇到必須沖銷已過帳的交易的情況。 有時，系統會阻止他們沖銷這些交易。 這種行為可能會引發兩個問題：

- 為什麼無法沖銷此交易？
- 大量沖銷功能如何影響此行為？

## <a name="resolution"></a>解決方法

交易必須滿足特定標準才能沖銷。 本主題的其餘區段提供對每個模組的驗證。 儘管本主題側重於 Microsoft Dynamics 365 Finance 中的交易，但某些概念和驗證可以套用於其他應用程式，例如 Dynamics 365 Supply Chain Management。

此外，沖銷交易的位置可能會影響它是否可以進行沖銷。 例如，只能從銀行帳戶的交易頁面上的 **支票** 區段沖銷作為支票過帳的廠商付款。 無法從總帳中的 **憑單交易** 頁面中沖銷它。

如果在 **功能管理** 工作區中啟用了 **多個文件的大量沖銷** 功能 (也稱為大量沖銷功能)，則將影響可沖銷交易數量以及可沖銷交易的位置。 此功能在啟用後會有兩個優點：

- 對於某些類型的交易，從其過帳的日記帳或從 **憑單交易** 頁面中一次可以選擇多個交易並進行沖銷。 但是，在啟用該功能之前，各個交易必須是可沖銷的。 在引入此功能之前，必須一次沖銷一個交易。
- 可以從日記帳 (普通日記帳) 或 **憑單交易** 頁面沖銷 *某些* 子分類帳交易。 不必從子分類帳頁面中沖銷它們。 例如，以前只能從 **廠商交易** 頁面中沖銷廠商發票日記帳。 但是，現在也可以從總帳、日記帳或 **憑單交易** 頁面沖銷。 本主題的每個章節都說明了不適用此優點的交易類型。

大量沖銷功能 **不會** 使更多類型的交易被沖銷。 如果某個交易類型之前無法沖銷，開啟該功能後仍無法沖銷。 例如，無論是否開啟大量沖銷功能，訂購單廠商發票都無法沖銷。

有關大量沖銷功能的詳細資訊，請參閱[沖銷日記帳過帳](reverse-journal-posting.md)。

## <a name="general-ledger"></a>總帳

只能透過使用分類帳科目來輸入總帳調整。 因此，他們只更新總帳。

如果關閉大量沖銷功能，則可以單獨從分類帳 (**LedgerTransAccount**) 的 **\<main account\> 的交易** 頁面中沖銷大多數總帳調整。 (頁面的確切標題會因所選的主科目有所不同。) 該頁面顯示已過帳到主科目的每筆交易。 它通常從 **試算表清單** 頁面開啟，或透過在 **憑單交易** 頁面上選擇 **交易** 來開啟。

如果開啟大量沖銷功能，現在可以從 **憑單交易** 頁面，以及從過帳交易的日記帳中沖銷一個或多個總帳憑單。 例外情況包括總帳外幣重估、合併和年終結算交易。 這些交易是從執行年終結算的頁面中沖銷的。

### <a name="reasons-why-transactions-cant-be-reversed"></a>無法沖銷交易的原因

由於以下原因，無法沖銷交易：

- 普通日記帳：

    - 會計期間處於暫停或永久關閉狀態：

        - 如果沖銷日期位於未打開的會計期間內，則無法沖銷交易。
        - 如果交易支援輸入沖銷日期，則仍可以透過將沖銷日期變更為未結期間來沖銷交易。

    - 已執行年終結算流程：

        - 交易的會計日期是經過年終結算的會計年度。 儘管會計年度中的某個期間可能仍處於未結狀態，但如果已為該會計年度執行年終結算流程，則無法沖銷交易。 會計年度的狀態與會計年度中的期間狀態不同。
        - 可以沖銷年終結帳，然後可以沖銷交易。 這種方法可能不是好選擇。 根據會計結算流程的狀態，在已結算會計年度或下一會計年度的未結期間手動輸入沖銷交易可能比較容易。 如果將新交易過帳到已通過年終結算流程的會計年度的未結期間，則必須再次執行年終結算。

    - 交易沖銷已在進行中：

        - 如果交易處於沖銷流程中，則必須完成該流程。 無法執行單獨的沖銷流程。 
        - 沖銷完成後，可以再次沖銷已沖銷的交易 (即可以沖銷此沖銷)。

    - 分類帳結算：

        - 如果已使用 **分類帳結算** 週期性工作 (**總帳 \> 週期性工作 \> 分類帳結算**) 對交易的一行或多行進行分類帳結算，使得該記錄存在於 LedgerTransSettlement 表中，則無法沖銷該交易。
        - 可以沖銷分類帳結算，然後可以沖銷該憑單。

    - 公司間：

        - 如果交易是公司間交易，則無法沖銷。
        - 該交易 **不是** 公司間交易，但已過帳到 **公司間設定** 頁面上定義的「應付」或「應收」主科目。

    - 應計項目：

        - 如果應計總帳憑單被沖銷，則應計分錄和所有相應的應計子交易都將被沖銷。
        - 單個應計子交易不能沖銷。

- 收入認列日記帳：

    - 無法沖銷收入認列交易。
    - 透過收入認列日記帳認列收入時，憑單僅過帳到分類帳科目。 因此，在 **憑單交易** 等頁面上，交易看起來好像只是總帳分錄。

- 外幣重估：

    - 外幣重估交易可以沖銷，但只能從執行重估所在的總帳 **外幣重估** 頁面中進行。
    - 只有沖銷已過帳到未結會計期間才能完成沖銷。

- 合併：

    - 合併交易可以沖銷，但只能從 **合併交易** 頁面中進行。
    - 只有沖銷已過帳到未結會計期間才能完成沖銷。

- 年終結算：

    - 年終結算交易 (包括期末交易和期初交易) 可以透過以下方式沖銷：

        - 如果關閉總帳年終結算增強功能，請在 **年終結算** 對話方塊中選擇 **沖銷先前的結算** 選項。
        - 如果啟用總帳年終增強功能，請在 **年終結算** 頁面上選擇為年終結算建立的公司和會計年度記錄，然後選擇 **沖銷年終結算**。

    - 請注意，年終結算的沖銷實際上會刪除期末和期初交易。 從未過帳沖銷憑單。

## <a name="accounts-payable"></a>應付帳款

多種交易類型會更新應付帳款子分類帳。 範例包括廠商發票、廠商發票日記帳和費用報表。

如果關閉大量沖銷功能，則可以從發票的 **廠商交易** 頁面或支票付款的 **銀行帳戶** 頁面單獨沖銷交易。

如果開啟大量沖銷功能，則可以從 **憑單交易** 頁面，以及從過帳交易的日記帳中沖銷一個或多個應付帳款交易。 但是，廠商付款仍只能從銀行帳戶沖銷。 此外，廠商交易無法從分類帳的 **\<main account\> 的交易** 頁面中沖銷。 它們只能從 **憑單交易** 頁面中進行沖銷。

請注意，某些交易根本無法沖銷。 範例包括訂購單廠商發票和電子廠商付款。

### <a name="reasons-why-vouchers-cant-be-reversed"></a>無法沖銷憑單的原因

由於以下原因，無法沖銷憑單：

- 會計期間處於暫停或關閉狀態：

    - 如果沖銷日期位於未打開的會計期間內，則無法沖銷交易。
    - 如果交易支援輸入沖銷日期，則仍可以透過將沖銷日期變更為未結期間來沖銷交易。

- 已執行總帳年終結算流程：

    - 交易的會計日期是在總帳中結算的會計年度。 儘管會計年度中的某個期間可能仍處於未結狀態，但如果已為該會計年度執行年終結算流程，則無法沖銷交易。 會計年度的狀態與會計年度中的期間狀態不同。
    - 可以沖銷年終結帳，然後可以沖銷交易。 這種方法可能不是好選擇。 根據會計結算流程的狀態，在已結算會計年度或下一會計年度的未結期間手動輸入沖銷交易可能比較容易。 如果將新交易過帳到已通過年終結算流程的會計年度的未結期間，則必須再次執行年終結算。

- 子分類帳日記帳分錄尚未轉移到總帳：

    - 此原因僅適用於非訂購單廠商發票。
    - 使用 **尚未轉移的子分類帳日記帳分錄** 頁面將分錄轉移到總帳。 然後可以從 **廠商交易** 頁面中沖銷非訂購單廠商發票。

- 結算：

    - 交易 (例如發票或付款) 已結算或標記為要結算。

        - 您可以透過在 **廠商交易** 頁面上選擇 **查看結算** 或 **結算 \> 結算歷史記錄** 來驗證交易是已結算還是標記為要結算。
        - 如果必須沖銷其中一項交易，也可以從 **廠商交易** 頁面 (**結算\>沖銷結算**) 中沖銷結算。

- 憑單包含多個使用相同憑單編號 (一張憑單簽發) 輸入的子分類帳交易。
- 尚未審核發票：

    - 如果未選取發票上的 **審核** 核取方塊，則無法沖銷發票。

        - 在這種情況下，審核不是指工作流流程中的審核，而是指發票上的 **審核** 選項。 此選項用於防止支付發票。 它通常用於廠商發票登記發票。

- 交易在發票集區中：

    - 無法直接從 **廠商交易** 頁面中沖銷集區中的發票。 相反，必須透過 **發票審核日記帳** 頁面上的取消流程來沖銷發票。

- 交易具有已更正的上層發票 (印度在地化)。
- 該交易的本票狀態為 **已匯出發票**。
- 該交易用於部分稅務結算。
- 交易包含廠商帳戶，但正在從不正確的頁面沖銷，例如 **\<main account\> 的交易** 頁面：

    - 正如這個原因所示，即使啟用大量沖銷功能，某些子分類帳交易也只能從特定頁面進行沖銷。

### <a name="types-of-transactions-that-cant-be-reversed"></a>無法沖銷的交易類型

無法沖銷以下類型的交易：

- 外幣重估：

    - 與總帳外幣重估不同，應收帳款和應付帳款外幣重估無法沖銷。 相反，必須使用發票日期再次執行重估。 在這種情況下，重估使用發票日期中的匯率，基本上將未實現的損益變為 0 (零)。 因此，結果會與沖銷先前重估的結果類似。 但是，請注意，如果發票上的預設匯率發生變更，則不會沖銷此金額。

- 訂購單廠商發票：

    - 必須建立貸方通知單才能沖銷廠商發票。 有關如何建立沖銷交易的更多資訊，請參閱[建立採購退貨單](../../supply-chain/procurement/tasks/create-purchase-return-order.md)。

- 本票
- 銀行信用狀出口裝運

## <a name="accounts-receivable"></a>應收帳款

多個交易類型會更新應收帳款子分類帳。 範例包括來自銷售訂單的客戶發票、透過普通日記帳輸入的客戶發票、普通發票、客戶付款和沖銷。

如果關閉大量沖銷功能，則可以從發票的 **客戶交易** 頁面或存款的 **銀行帳戶** 頁面單獨沖銷交易。 有關如何沖銷付款的資訊，請參閱本主題後文的[現金和銀行管理](cant-reverse-transctns.md#cash-and-bank-management)章節。

如果開啟大量沖銷功能，則可以從 **憑單交易** 頁面，以及從過帳交易的日記帳中沖銷一個或多個應收帳款交易。 但是，存款仍只能從銀行帳戶沖銷，普通發票只能從原始頁面沖銷 (如果已啟用允許更正的功能)。 此外，客戶交易無法從分類帳的 **\<main account\> 的交易** 頁面中沖銷。 但是，它們可以從 **憑單交易** 頁面中進行沖銷。

請注意，某些交易無法沖銷。 範例包括銷售訂單客戶發票和沖銷。

### <a name="reasons-why-transactions-cant-be-reversed"></a>無法沖銷交易的原因

由於以下原因，無法沖銷交易：

- 會計期間處於暫停或永久關閉狀態：

    - 如果沖銷日期位於未打開的會計期間內，則無法沖銷交易。
    - 如果交易支援輸入沖銷日期，則仍可以透過將沖銷日期變更為未結期間來沖銷交易。

- 已執行總帳年終結算流程：

    - 交易的會計日期是經過總帳年終結算的會計年度。 儘管會計年度中的某個期間可能仍處於未結狀態，但如果已為該會計年度執行年終結算流程，則無法沖銷交易。 會計年度的狀態與會計年度中的期間狀態不同。
    - 可以沖銷年終結帳，然後可以沖銷交易。 這種方法可能不是好選擇。 根據會計結算流程的狀態，在已結算會計年度或下一會計年度的未結期間手動輸入沖銷交易可能比較容易。 如果將新交易過帳到已通過年終結算流程的會計年度的未結期間，則必須再次執行年終結算。

- 子分類帳日記帳分錄尚未轉移到總帳：

    - 此原因僅適用於普通發票。
    - 使用 **尚未轉移的子分類帳日記帳分錄** 頁面將分錄轉移到總帳。 如果啟用了更正功能，則可以沖銷或更正普通發票。

- 結算：

    - 交易 (例如發票或付款) 已結算或標記為要結算。

        - 您可以透過在 **客戶交易** 頁面上選擇 **查看結算** 或 **結算 \> 結算歷史記錄** 來驗證交易是已結算還是標記為要結算。
        - 如果必須沖銷其中一項交易，也可以從 **客戶交易** 頁面 (**結算\>沖銷結算**) 中沖銷結算。

- 交易包含多個使用相同憑單編號 (一張憑單簽發) 輸入的子分類帳交易。
- 尚未審核發票：

    - 如果未選取發票上的 **審核** 核取方塊，則無法沖銷發票。

        - 在這種情況下，審核不是指工作流流程中的審核，而是指憑單行上的 **審核** 選項。 此選項用於防止支付發票。 儘管此選項通常用於應付帳款，但它也可用於透過日記帳輸入的應收帳款發票。

- 交易具有已更正的上層發票 (印度在地化)。
- 交易包含客戶帳戶，但正在從不正確的頁面沖銷，例如 **\<main account\> 的交易** 頁面：

    - 正如這個原因所示，即使啟用大量沖銷功能，某些子分類帳交易也只能從特定頁面進行沖銷。

### <a name="types-of-transactions-that-cant-be-reversed"></a>無法沖銷的交易類型

無法沖銷以下類型的交易：

- 外幣重估：

    - 與總帳外幣重估不同，應收帳款和應付帳款外幣重估無法沖銷。 相反，必須使用發票日期再次執行重估。 在這種情況下，重估使用發票日期中的匯率，基本上將未實現的損益變為 0 (零)。 因此，結果會與沖銷先前重估的結果類似。 但是，請注意，如果發票上的預設匯率發生變更，則不會沖銷此金額。

- 已調整扣繳稅款的交易
- 銷售訂單客戶發票：

    - 必須建立貸方通知單或退貨才能沖銷交易。 有關如何建立沖銷交易的資訊，請參閱[銷售退貨](../../supply-chain/warehousing/sales-returns.md)。

- 匯票
- 收銀機交易
- 進階調整
- 利息單
- 催款函
- 銀行信用狀
- 出口裝運
- 收入認列日記帳：

    - 透過收入認列日記帳認列收入時，憑單僅過帳到分類帳科目。 因此，它們看起來好像只是總帳分錄。 這些分錄無法沖銷，因為不會重新打開收入計劃以再次認列收入。

## <a name="cash-and-bank-management"></a>現金和銀行管理

多個交易類型透過普通日記帳更新銀行子分類帳。 範例包括廠商付款、客戶付款和銀行轉帳。

如果關閉大量沖銷功能，則可以則可以從支票和存款的 **銀行帳戶** 頁面，或客戶付款的 **客戶交易記** 頁面單獨沖銷交易。

如果開啟大量沖銷功能，則可以從 **憑單交易** 頁面，以及從過帳交易的日記帳中沖銷一個或多個付款交易。 但是，存款仍只能從銀行帳戶沖銷。 此外，銀行交易無法從分類帳的 **\<main account\> 的交易** 頁面中沖銷。 但是，它們可以從 **憑單交易** 頁面中進行沖銷。

請注意，某些交易無法沖銷。 範例包括電子廠商付款。

### <a name="reasons-why-transactions-cant-be-reversed"></a>無法沖銷交易的原因

由於以下原因，無法沖銷交易：

- 會計期間處於暫停或永久關閉狀態：

    - 如果沖銷日期位於未打開的會計期間內，則無法沖銷交易。
    - 如果交易支援輸入沖銷日期，則仍可以透過將沖銷日期變更為未結期間來沖銷交易。

- 已執行總帳年終結算流程：

    - 交易的會計日期是經過總帳年終結算的會計年度。 儘管會計年度中的某個期間可能仍處於未結狀態，但如果已為該會計年度執行年終結算流程，則無法沖銷交易。 會計年度的狀態與會計年度中的期間狀態不同。
    - 可以沖銷年終結帳，然後可以沖銷交易。 這種方法可能不是好選擇。 根據會計結算流程的狀態，在已結算會計年度或下一會計年度的未結期間手動輸入沖銷交易可能比較容易。 如果將新交易過帳到已通過年終結算流程的會計年度的未結期間，則必須再次執行年終結算。

- 結算：

    - 交易 (付款) 已結算或標記為要結算。

        - 您可以透過在 **客戶交易** 或 **客戶交易** 頁面上選擇 **查看結算** 或 **結算 \> 結算歷史記錄** 來驗證交易是已結算還是標記為要結算。
        - 如果必須沖銷其中一項交易，也可以從 **廠商交易** 或 **客戶交易** 頁面 (**結算\>撤銷結算**) 中沖銷結算。

- 交易包含多個使用相同憑單編號 (一張憑單簽發) 輸入的子分類帳交易。
- 過渡交易：

    - 如果交易與過渡付款有關，則無法沖銷該交易。
    - 如果必須沖銷過渡付款，則必須先從銀行過渡帳戶清除付款。 如果付款符合其他驗證條件，則可以沖銷該付款。

- 交易包含銀行帳戶，但正在從 **\<main account\> 的交易** 頁面或不正確的子分類帳中沖銷，例如應收帳款或應付帳款：

    - 正如這個原因所示，即使啟用大量沖銷功能，某些子分類帳交易也只能從特定頁面進行沖銷。

- 銀行外幣重估：

    - 銀行外幣重估可以沖銷。 但是，如果不按時間順序完成沖銷步驟，則可能會阻止沖銷。 例如，如果您在 3 月和 4 月執行重估，則在沖銷 4 月重估之前，無法沖銷 3 月重估。

### <a name="types-of-transactions-that-cant-be-reversed"></a>無法沖銷的交易類型

無法沖銷以下類型的交易：

- 作為電子資金轉帳 (EFT) 進行的廠商付款
- 本票
- 匯票

## <a name="fixed-assets"></a>固定資產

多個交易類型會更新固定資產子分類帳。 範例包括購置和折舊。

如果關閉大量沖銷功能，則可以根據交易類型，從 **廠商交易** 頁面、**固定資產交易** 頁面或資產租賃單獨沖銷交易。

如果開啟大量沖銷功能，則可以從 **憑單交易** 頁面，以及從過帳交易的日記帳中沖銷一個或多個固定資產交易。

### <a name="reasons-why-transactions-cant-be-reversed"></a>無法沖銷交易的原因

由於以下原因，無法沖銷交易：

- 會計期間處於暫停或永久關閉狀態：

    - 如果沖銷日期位於未打開的會計期間內，則無法沖銷交易。
    - 如果交易支援輸入沖銷日期，則仍可以透過將沖銷日期變更為未結期間來沖銷交易。

- 已執行總帳年終結算流程：

    - 交易的會計日期是在總帳中結算的會計年度。 儘管會計年度中的某個期間可能仍處於未結狀態，但如果已為該會計年度執行年終結算流程，則無法沖銷交易。 會計年度的狀態與會計年度中的期間狀態不同。
    - 可以沖銷年終結帳，然後可以沖銷交易。 這種方法可能不是好選擇。 根據會計結算流程的狀態，在已結算會計年度或下一會計年度的未結期間手動輸入沖銷交易可能比較容易。 如果將新交易過帳到已通過年終結算流程的會計年度的未結期間，則必須再次執行年終結算。

- 購置：

    - 如果訂購單廠商發票上存在購置，則必須透過輸入廠商貸方通知單進行沖銷。 有關如何輸入沖銷交易的更多資訊，請參閱[建立採購退貨單](../../supply-chain/procurement/tasks/create-purchase-return-order.md)。
    - 專案交易中存在購置。
    - 過帳資產折舊後，無法沖銷購置。 必須沖銷折舊，然後才能沖銷購置。
    - 如果固定資產的價值模型或折舊帳簿狀態未打開，則該交易不能沖銷。

- 處置：

    - 處置是透過普通發票完成的：

        - 如果普通發票包含固定資產，則會阻止其更正。 但是，如果透過日記帳處置資產，則可以從固定資產記錄中沖銷普通發票。

    - 如果固定資產的價值模型或折舊帳簿狀態未打開，則該交易不能沖銷。

- 折舊：

    - 如果後續折舊也已過帳，則 **可以** 沖銷折舊。 但是，您將收到警告，因為這種方法不是最佳做法。
    - 如果固定資產的價值模型或折舊帳簿狀態未打開，則該交易不能沖銷。

- 對於憑證的交易日期或之後的日期，存在特定資產和資產帳簿的交易記錄 (或沖銷交易)。
- 交易包含資產帳戶，但正在從 **\<main account\> 的交易** 頁面或不正確的子分類帳中沖銷，例如應收帳款或應付帳款：

    - 正如這個原因所示，即使啟用大量沖銷功能，某些子分類帳交易也只能從特定頁面進行沖銷。
    - 如果在非訂購單廠商發票或廠商發票日記帳上存在購置，則只能從應付帳款中的 **廠商交易** 頁面中沖銷該購置。
    - 如果是從資產租賃中購置資產，則可以從資產租賃中的 **負債交易** 頁面中沖銷該資產。