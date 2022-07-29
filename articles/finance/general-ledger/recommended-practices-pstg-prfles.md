---
title: 過帳設定檔的推薦實務做法
description: 本主題說明配置過帳設定檔的推薦實務做法。
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 097d1c6d1fbe64dadc69cdb275a0aef38922036d
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2022
ms.locfileid: "8451482"
---
# <a name="recommended-practices-for-posting-profiles"></a>過帳設定檔的推薦實務做法

當您在整套系統配置過帳設定檔時，您應該遵循幾個推薦的實務做法。 本主題說明不同的設想情況和對應的推薦實務做法。

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>設定不允許手動輸入標誌

**主科目** 頁面上的 **不允許手動輸入** 勾選方塊應選取任何用在過帳設定檔的主科目。 本項設定可防止使用者手動將日記帳分錄過帳到主科。 因此，它有助於確保子分類帳與總帳保持平衡，並有助於簡化對帳流程。

如果需要調整系統控制的科目並且自動過帳，您可以使用下列其中一種方法：

- 建立可過帳調整項目的輔助主科目。 接著使用科目總計或財務報表上的特定列將科目分成一組並加總。
- 沖銷適當子分類帳的原始交易、進行任何必要的更正，接著透過相同子分類帳重新過帳交易。

## <a name="changing-posting-profiles-after-transactions-exist"></a>更改交易存在後的過帳設定檔

如果您在交易存在後更改過帳設定檔，對帳會失敗，而且您的子分類帳和分類帳會失衡。 一般來說，我們建議您交易存在後 **不** 更改過帳設定檔。

如果需要更改，請使用下列指南協助確保系統的一致性：

- 關閉期間更改。
- 當系統未發生其他交易時更改。
- 在您更改前後驗證分類帳並與子分類帳對帳。
- 如果您更改過帳設定檔，就不會更新過帳後的交易。 請仔細思考您的更改是否需要任何調整分錄。
- 如果您正在更改庫存過帳設定檔，請思考這些更改將如何影響您的現貨庫存和分類帳餘額。 某些更改可能需要您將庫存值帶入 0 (零)、關閉庫存，接著更改後恢復庫存值。
- 正式執行前，請務必在非正式執行環境測試您的更改。

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>使用資料庫記錄功能稽核過帳設定檔的更改

請考慮為每個過帳設定檔和控制過帳的參數表設定資料庫記錄功能。 接著如果更改參數或設定檔，您將有整份稽核記錄，包括更改值、更改人員、更改時間及先前值的內容。 本項資訊對您的對帳流程具有關鍵地位，而您的稽核人員可能需要佐證文件。

更多資訊，請參閱[組態資料庫記錄](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md)。

請把下表當作與過帳設定檔和過帳參數有關的常用資料表名稱的參考。

| 頁面名稱 | 導覽路徑 | 表格名稱 |
|-----------|-----------------|------------|
| 應付帳款參數 | 應付帳款&gt;設定&gt;應付帳款參數 | VendParm |
| 廠商過帳設定檔 | 應付帳款&gt;設定&gt;廠商過帳設定檔 | VendPosting |
| 收費代碼 | 應付帳款&gt;收費設定&gt;收費代碼或應收帳款&gt;收費設定&gt;收費代碼 | MarkupTable |
| 付款方式 | 應付帳款&gt;付款設定&gt;付款方式 | VendPaymMode |
| 現金折扣 | 應付帳款&gt;付款設定&gt;現金折扣或應收帳款&gt;付款設定&gt;現金折扣 | CashDisc |
| 付款費用 (廠商) | 應付帳款&gt;付款設定&gt;付款費用 | VendPaymFee |
| 應收帳款參數 | 應收帳款&gt;設定&gt;應收帳款參數 | CustParm |
| 客戶過帳設定檔 | 應收帳款&gt;設定&gt;客戶過帳設定檔 | CustPosting |
| 付款方式 | 應收帳款&gt;付款設定&gt;付款方式 | CustPaymMode |
| 付款費用 (客戶) | 應收帳款&gt;付款設定&gt;付款方式 | CustPaymFee |
| 資產租賃參數 | 資產租賃&gt;設定&gt;資產租賃參數 | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| 銀行帳戶 | 現金和銀行管理&gt;銀行帳戶&gt;銀行帳戶 | BankAccountsTable |
| 銀行交易類型 | 現金和銀行管理&gt;設定&gt;銀行交易類型 | BankTransType |
| 消除規則 | 合併&gt;設定&gt;消除規則 | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| 支出類別 | 支出管理&gt;設定&gt;一般&gt;支出類別 | ProjCategories |
| 固定資產參數 | 固定資產&gt;設定&gt;固定資產參數 | AssetParameters |
| 固定資產過帳設定檔 | 固定資產&gt;設定&gt;固定資產過帳設定檔 | AssetLedgerAccounts<br>AssetDisposalParameters |
| 貨幣重估科目 | 總帳&gt;貨幣&gt;貨幣重估科目 | CurrencyLedgerGainLossAccount |
| 自動交易科目 | 總帳&gt;過帳設定&gt;自動交易科目 | LedgerSystemAccounts |
| 公司間會計 | 總帳&gt;過帳設定&gt;公司間科目 | LedgerIntercompany |
| 交易過帳定義 | 總帳&gt;過帳設定&gt;交易過帳定義 | JournalizingDefinitionTrans |
| 過帳定義 | 總帳&gt;過帳設定&gt;過帳定義 | JournalizingDefintion |
| 過帳 (庫存) | 庫存管理&gt;設定&gt;過帳&gt;過帳 | InventPosting |
| 成本類型代碼 | 到岸成本&gt;成本設定&gt;成本類型代碼 | ITMCostTypeTable |
| 資源 | 正式執行控制&gt;設定&gt;資源&gt;資源 | WrkCtrTable |
| 資源群組 | 正式執行控制&gt;設定&gt;資源&gt;資源群組 | WrkCtrResourceGroup |
| 正式執行群組 | 正式執行控制&gt;設定&gt;正式執行&gt;正式執行群組 | ProdGroup |
| 成本類別 | 生產控制&gt;設定&gt;路線&gt;成本類別 | ProjCategory |
| 專案群組 | 專案管理和會計&gt;設定&gt;過帳&gt;專案群組 | ProjGroup |
| 分類帳過帳設定 (專案) | 專案管理和會計&gt;設定&gt;過帳&gt;分類帳過帳設定 | ProjPosting |
| 預設支出沖銷科目 | 專案管理和會計&gt;設定&gt;過帳&gt;支出預設沖銷科目 | ProjDefaultOffsetSetup |
| 回扣管理過帳設定檔 | 回扣管理&gt;回扣管理過帳設定&gt;回扣管理過帳設定檔 | TAMRebatePosting |
| 分類帳過帳群組 (稅) | 稅&gt;設定&gt;銷售稅&gt;分類帳過帳群組 | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>更改交易存在後的群組

更改主資料的群組時請小心。 如果您正在使用群組定義您的過帳設定檔，對主記錄的群組如有任何更改，會對分類帳與子分類帳對帳的能力產生負面影響。 例如，您可以為銷售訂單營收配置庫存過帳設定檔，如此一來每個項目群組便能使用不同的營收科目。 如果您更改交易存在後指派給某個項目的項目群組，則新交易營收將過帳到更新的科目。 不過更改前過帳的任何營收都將保留在原始科目。

## <a name="testing-posting-profiles"></a>測試過帳設定檔

在您上線直播前以及您更改或新增過帳設定檔或相關參數後，您都應該測試每個設想情況。 至少您應該測試每種過帳類型才能驗證過帳工作是否正確。 不過，推薦的方法是測試每個過帳設定檔交易和組合。

例如，您有兩個客戶過帳設定檔，每個都有三筆特定客戶群組的記錄。 此時，您應該測試每種交易類型。

**過帳設定檔：**

- **GEN** – 有一個群組用於員工、一個用於客戶和一組用於公司間的一般過帳設定檔。 每個群組都指向不同的應收帳款貿易科目。
- **PRE** – 預付款過帳設定檔，其中一筆記錄指向客戶預付款科目的所有預付款。

### <a name="testing-scenarios"></a>測試設想情況

- 在 **員工** 群組中使用 **GEN** 過帳設定檔的客戶普通發票
- 在 **員工** 群組中使用 **PRE** 過帳設定檔的客戶普通發票
- 在 **員工** 群組中使用 **GEN** 過帳設定檔的銷售訂單發票
- 在 **員工** 群組中使用 **PRE** 過帳設定檔的銷售訂單發票
- 在 **員工** 群組中使用 **GEN** 過帳設定檔的客戶付款日記帳
- 在 **員工** 群組中使用 **PRE** 過帳設定檔的客戶付款日記帳

以前例而言，為每個客戶群組重複一個測試設想情況，並為每個額外的交易類型 (例如專案發票和服務管理) 重複每組測試設想情況。

## <a name="reconciling-the-ledger-to-the-subledger"></a>分類帳與子分類帳對帳

分類帳應與每段期間的子分類帳對帳。 許多模組包含開箱即用的報表，可用來幫助這類對帳。 不過您可能必須根據當地要求，開發自訂報表或擴充既有報表以符合您的報表編製要求。

我們建議您上線直播前關閉模擬期間並將您的每個子分類帳與分類帳對帳。 我們也建議您在首次上線直播前模擬轉換所有未結餘額和未結交易。 您應該執行完整的對帳動作，確保餘額移轉且未結交易與舊版系統平衡，以及所有子分類帳在建立新交易之前，與分類帳平衡。
