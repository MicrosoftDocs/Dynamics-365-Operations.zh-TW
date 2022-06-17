---
title: 驗證商店交易以進行報表計算
description: 本主題描述 Microsoft Dynamics 365 Commerce 中驗證商店交易的功能。
author: analpert
ms.date: 01/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: analpert
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: f51b1f39aa212fe8587761721194db7791bec5bc
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "8452955"
---
# <a name="validate-store-transactions-for-statement-calculation"></a>驗證商店交易以進行報表計算

[!include [banner](includes/banner.md)]

本主題描述 Microsoft Dynamics 365 Commerce 中驗證商店交易的功能。 驗證程序會識別並標記將導致過帳錯誤的交易，防止對帳單過帳過程接收到它們。

當您嘗試將對帳單過帳時，驗證程序可能會因為 Commerce 交易資料表中有不一致的資料而失敗。 以下是一些範例，呈現可能造成這些不一致性的因素：

- 標頭表中的交易總計與行上的交易總計不相符。
- 在標頭表中指定的項目數與交易表中的項目數不相符。
- 標頭表中的稅金與行上的稅金金額不相符。 

如果對帳單過帳過程所接收的交易不一致，則建立的銷售發票與付款日記帳可能會致使對帳單過帳失敗。 **驗證商店交易** 程序能確保只有通過交易驗證規則的交易能夠傳遞至交易對帳單計算程序，來防止這些問題發生。

下圖顯示了日間定期的上傳交易、驗證交易、計算和將交易對帳單過帳，以及日結的財務報表計算與過帳程序。

![圖例顯示了日間定期的上傳交易、驗證交易、計算和將交易對帳單過帳，以及日結的財務報表計算與過帳程序](./media/valid-checker-statement-posting-flow.png)

## <a name="store-transaction-validation-rules"></a>商店交易驗證規則

**驗證商店交易** 批次處理會根據以下驗證規則，檢查 Commerce 交易資料表的一致性。

> [!NOTE]
> 後續版本將會繼續追加更多驗證規則。

### <a name="transaction-header-validation-rules"></a>交易標頭驗證規則

下表列出零售交易傳遞至對帳單過帳前，會針對零售交易的標頭所檢查的交易標頭驗證規則。

| 規則 | 描述 |
|-------|-------------|
| 業務日期 | 這項規則會驗證交易的業務日期是否與分類帳中的開啟會計週期相關。 |
| 貨幣四捨五入 | 這項規則會驗證交易金額是否有根據貨幣四捨五入規則四捨五入。 |
| 客戶帳戶 | 這項規則會驗證在交易中使用的客戶是否存在於資料庫中。 |
| 折扣金額 | 這項規則會驗證標頭上的折扣金額是否等於各行折扣金額的總和。 |
| 會計文件過帳狀態 (巴西) | 這項規則會驗證會計文件是否能成功過帳。 |
| 毛額 | 這項規則會驗證交易標頭上的毛額是否與淨額相符，包含交易明細的稅金加上費用。 |
| 淨利 | 這項規則會驗證交易標頭上的淨額是否與淨額相符，不包含交易明細的稅金加上費用。 |
| 淨利 + 稅金 | 這項規則會驗證交易標頭上的毛額是否與淨額相符，不包含交易明細的稅金加上所有稅金與費用。 |
| 項目數 | 這項規則會驗證在交易標頭上指定的項目數是否與交易明細上的數量總和相符。 |
| 付款金額 | 這項規則會驗證交易標頭上的付款金額是否與所有付款交易的總合相符。 |
| 免稅計算 | 這項規則會驗證計算金額與計費行的免稅金額總和是否等於原始計算金額。 |
| 含稅價格 | 這項規則會驗證交易標頭與稅金交易之間的 **價格含稅** 旗標是否一致。 |
| 交易非空白 | 這項規則會驗證交易包含行，且沒有任何一行作廢。 |
| 少付/多付 | 這項規則會驗證毛額與付款金額之間的差額不會超過最大的少付/多付設定。 |

### <a name="transaction-line-validation-rules"></a>交易明細驗證規則

下表列出零售交易傳遞至對帳單過帳前，會針對零售交易的行詳細資料所檢查的交易明細驗證規則。

| 規則 | 描述 |
|-------|-------------|
| 條碼 | 這項規則會驗證用在交易明細上的所有項目條碼是否都存在於資料庫中。 |
| 計費行 | 這項規則會驗證計算金額與計費行的免稅金額總和是否等於原始計算金額。 |
| 禮品卡退貨 | 這項規則會驗證交易中沒有任何禮品卡退貨。 |
| 項目變體 | 這項規則會驗證用在交易明細上的所有項目與所有變體是否都存在於資料庫中。 |
| 行折扣 | 這項規則會驗證行折扣金額是否與折扣交易的總合相符。 |
| 行稅金 | 這項規則會驗證行稅金金額是否與稅金交易的總合相符。 |
| 負價 | 這項規則會驗證未對交易明細使用任何負價。 |
| 序號受控 | 這項規則會驗證序號是否有為序號受控的項目出現在交易明細上。 |
| 序號維度 | 這項規則會驗證如果項目的序號維度處於非使用中狀態，則不提供任何序號。 |
| 符號矛盾 | 這項規則會驗證數量的符號與淨額的符號在所有交易明細上均相同。 |
| 免稅 | 這項規則會驗證行項目價格與免稅金額的總和是否等於原始價格。 |
| 稅金群組指派 | 這項規則會驗證銷售稅群組與項目稅群組的組合會產生有效的稅金交集。 |
| 測量單位轉換 | 這項規則會驗證所有行的測量單位對庫存測量單位都具有有效的轉換。 |

## <a name="enable-the-store-transaction-validation-process"></a>啟用商店交易驗證程序

設定 **驗證商店交易** 工作以在 Commerce Headquarters 中定期執行 (**Retail 和 Commerce \> Retail 和 Commerce IT \> POS 過帳**)。 批次作業是根據商店的組織階層安排而成。 我們建議您設定此批次處理，以與您 **P-Job** 和 **交易對帳單計算** 批次工作相同的頻率執行。

## <a name="results-of-the-validation-process"></a>驗證程序的結果

您可以在每個零售商店交易上檢視 **驗證商店交易** 批次處理的結果。 交易記錄上的 **驗證狀態** 欄位設定為 **成功**、**錯誤** 或 **無**。 **上次驗證時間** 欄位會顯示上次驗證執行的日期。

下表描述每一個驗證狀態。

| 驗證狀態 | 描述 |
|-------------------|-------------|
| 成功 | 通過了所有啟用的驗證規則。 |
| 錯誤 | 一個啟用的驗證規則找到了錯誤。 您可以在動作窗格上選取 **驗證錯誤** 來檢視關於錯誤的更多詳細資料。 |
| 無 | 該交易類型不需要套用這些驗證規則。 |

![商店交易頁面顯示驗證狀態欄位與驗證錯誤按鈕。](./media/valid-checker-validation-status-errors.png)

交易對帳單只會包含驗證狀態為 **成功** 的交易。 若要檢視出現 **錯誤** 狀態的交易，請檢閱 **商店財務** 工作區中的 **現金自運驗證失敗** 圖標。

![商店財務工作區中的圖標。](./media/valid-checker-cash-carry-validation-failures.png)

如需關於如何修正現金自運驗證失敗的詳細資訊，請參閱[編輯和稽核現金自運與現金管理交易](edit-cash-trans.md)。

## <a name="additional-resources"></a>其他資源

[編輯和稽核現金自運及現金管理交易](edit-cash-trans.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]