---
title: 總帳的外幣重估
description: 本主題的總帳外幣重估流程概觀如下 - 設定、執行流程、流程計算以及必要時如何沖銷重估交易。
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.reviewer: roschlom
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 49f724eb31904c7fd745864c9d71f401a4d539e29b5ff01814334adf6f0ebc37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450765"
---
# <a name="foreign-currency-revaluation-for-general-ledger"></a>總帳的外幣重估

[!include [banner](../includes/banner.md)]

本主題的總帳外幣重估流程概觀如下 - 設定、執行流程、流程計算以及必要時如何沖銷重估交易。 

屬於期末一部分的會計慣例會要求外幣的總帳科目餘額使用不同的匯率類型 (當前、歷史、平均等) 重估。 例如，一則會計慣例要求資產和負債按當前匯率重估，固定資產按歷史匯率重估，損益科目按月平均重估。 總帳外幣重估可用來重估資產負債表和損益科目。 

> [!NOTE]
> 應付帳款 (AR) 和應收帳款 (AP) 也可執行外幣重估。 如果您正在使用這些模組，則應使用當中的外幣重估未結的交易。 AR 和 AP 外幣重估將在總帳建立會計分錄，以反映未實現損益，確保子分類帳可以和總帳對帳。 由於 AR 和 AP 外幣重估會在總帳建立會計分錄，因此應將應收帳款和應付帳款主科目排除在總帳外幣重估範圍之外。 

當您執行重估流程時，將會一併重估以外幣過帳的每個主科目餘額。 在重估流程中建立的未實現損益交易是系統產生的。 此時可能會建立兩筆交易，一筆用於會計貨幣，另一筆用於報表貨幣 (以相關為主)。 每項會計分錄將過帳到未實現損益和正在重估的主科目。

## <a name="prepare-to-run-foreign-currency-revaluation"></a>準備執行外幣重估
在執行重估流程之前，需要進行以下設定。

-   在 **主科目** 頁面：
-   如果應在總帳重估主科目，請選取 **外幣重估**。 如果不應重估主科目 (例如在子分類帳重估的 AR 和 AP)，請清除此選項。
-   如果主科目被標記為重估，請輸入 **匯率類型**。 此匯率類型將用於重估主科目。 財務報表可以使用分開的欄位，**Financial Reporting 的匯率類型**。 這兩個欄位不保持同步，允許重估和 Financial Reporting  使用不同的匯率類型。

-   請在 **總帳** 頁上：
-   指明 **匯率類型**。 如果主科目沒有定義匯率類型，將在外幣重估期間使用此匯率類型。
-   指明貨幣重估的已實現收益、已實現損失、未實現收益和未實現損失科目。 結算 AR 和 AP 交易時會使用已實現收益和已實現損失科目，未實現收益和未實現損失科目則用於重估未結交易和總帳主科目。

-   請在 **貨幣重估科目** 頁上：
-   為每種貨幣和公司選取不同的貨幣重估科目。 如果沒有定義任何科目，則使用 **分類帳** 頁面中的科目。

## <a name="process-foreign-currency-revaluation"></a>處理外幣重估
設定完成後，使用 **外幣重估** 頁重估主要科目餘額。 您可以即時執行這段流程，也可以使用批次處理排入時間表執行。 

**外幣重估** 頁將顯示每個重估流程的歷史記錄，包括執行時間、定義標準、重估建立憑單的連結以及是否沖銷前次重估的記錄。 若要執行重估流程，請選取 **外幣重估** 按鈕。 

**開始日期** 和 **結束日期** 值定義計算將重估外幣餘額的日期間隔。 當您重估損益科目時，會一併重估日期間隔內發生的所有交易總和。 當您重估資產負債表科目時，會忽略開始日期。 相反地，要重估的餘額會藉由從會計年度開始到截止日期判定。 

**匯率日期** 可用來定義匯率應為預設值的日期。 例如，您可以重估一月 1 日到一月 31 日日期範圍之間的餘額，但使用為二月 1 日定義的匯率。 

選取要重估的主科目：全部、資產負債表或損益。 只會重估標記為重估的主科目 (主科目頁)。 如果您想進一步限制主科目範圍，請使用記錄的 **包括** 索引標籤定義一系列主科目或個別主科目。 

可以對一個或多個法律實體執行重估流程。 查閱功能只會顯示您可以存取的法人實體。 請選取您要執行重估流程的法人實體。 

可以執行一種或多種外幣的重估。 查閱被選取要重估的法人實體範圍將包括與主科目類型 (資產負債表或損益表) 相關日期範圍內過帳的所有貨幣。 會計貨幣將納入清單，但如果選取，將不會重估任何分項。 

如果您想要審視總帳重估結果，請將 **過帳前預覽** 設定為 **是**。 總帳預覽不同於 AR 和 AP 外幣重估的模擬。 AR 和 AP 模擬是一份報表，但總帳可以預覽已經過帳的資料，不必再執行重估流程。 預覽結果可以匯出到 Microsoft Excel 保留金額計算方式的歷史記錄。 如果您想要預覽重估結果，不能使用批次處理。 用戶預覽時有使用 **過帳** 按鈕過帳所有法人實體結果的選項。 如果法人實體結果有問題，用戶也有使用 **選取要過帳的法人實體** 按鈕過帳法人實體子集合的選項。 

外幣重估流程完成後，將建立記錄追蹤每次執行的歷史記錄。  將為每個法人實體和過帳層分開建立記錄。

## <a name="calculate-unrealized-gainloss"></a>計算未實現收益/損失
在總帳重估和 AR 和 AP 重估流程之間建立未實現損/益交易的方式不同。 AR 和 AP 重估流程會完全沖銷前次的重估結果 (假設交易尚未結算)，並按照新匯率基礎針對未實現損益建立新重估交易。 這是因為我們重估 AR 和 AP 的個別交易。 總帳中的前次重估不會進行沖銷。 相反地，會為主科目餘額 (包括前次任何重估金額) 與以匯率日期當天匯率為主的新值之間 Delta 差額建立交易。 

**範例** 主科目 110110 存在餘額如下。

| 日期   | 總帳| 交易金額 | 會計金額 |
|------------|--------------------|------------------------|-----------------------|
| 一月 20 日 | 110110 (現金)      | 500 EUR (借)        | 1000 USD (借)      |

主科目於一月 31 日重估。  未實現收益/損失計算如下。

| 交易幣別的當前餘額 | 會計幣別的當前餘額 | 重估時的匯率 | 新會計幣別金額 | 未實現收益/損失    |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| 500 EUR                                     | 1000 USD                                   | 166.6667                         | 833.33 USD (500 x 1.666667)        | 166.67 損失 (833.33 – 1000) |

將建立下列會計分錄。

| 日期   | 總帳       | 借 | 貸 |
|------------|--------------------------|-----------|------------|
| 一月 31 日 | 110110 (現金)            |           | 166.67     |
| 一月 31 日 | 801400 (未實現損失) | 166.67    |            |

二月份沒有過帳新交易。  主科目於二月 28 日重估。

| 交易幣別的當前餘額 | 會計幣別的當前餘額 | 重估時的匯率 | 新會計幣別金額 | 未實現收益/損失    |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| 500 EUR                                     | 833.33 USD (1000 - 166.67)                 | 250.0000                         | 1250 USD (500 x 2.5)               | 416.67 收益 (1250–833.33) |

將建立下列會計分錄。

| 日期    | 總帳       | 借 | 貸 |
|-------------|--------------------------|-----------|------------|
| 二月 28 日 | 110110 (現金)            | 416.67    |            |
| 二月 28 日 | 801600 (未實現收益) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>沖銷外幣重估
如果您需要沖銷重估交易，請選取 **外幣重估** 頁上的 **沖銷交易** 按鈕。 將建立新外幣重估歷史記錄維護重估發生或撤消時的歷史稽核線索。 

您可以沖銷逾期訂單的重估結果，但您可能也需要沖銷更當前的重估結果，確保每個重估主科目的餘額正確無誤。 沖銷會發生逾期訂單，因為無法控制重估的主科目以及重估的頻率。 例如，組織可能選擇按季重估其現金主科目，但按月重估所有其他主科目。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]