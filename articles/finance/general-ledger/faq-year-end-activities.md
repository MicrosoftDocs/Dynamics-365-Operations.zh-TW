---
title: 年末活動常見問題
description: 本文章列出了年末結帳時可能出現的問題，以及有助於年終結帳活動的答案。
author: moaamer
ms.date: 12/01/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2e33c1dcbfa4da74f2e8acc6e29f04fda3abd185
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853032"
---
# <a name="year-end-activities-faq"></a>年末活動常見問題 

[!include [banner](../includes/banner.md)]

本文章列出了年末結帳時可能出現的問題，以及有助於年終結帳活動的答案。 本文章的資訊主要集中於總帳和應付帳款的年終結帳活動問題。

## <a name="general-ledger-year-end-enhancements"></a>總帳年終增強功能

Microsoft Dynamics 365 Finance 10.0.20 版引入了年終結算增強功能。 此增強功能自 10.0.25 版開始預設啟用，並自 10.0.29 版開始強制啟用。 如果貴組織使用的是 10.0.25 以前的版本，建議您先啟用此功能，再開始年終結算程序。 您必須先在系統中開啟此功能，才能使用它。 管理員可以使用 **功能管理** 工作區檢查功能的狀態，並在需要時開啟此功能。 在此，功能會以下方式列出：

- **模組：** 總帳
- **功能名稱：** 總帳年終增強功能

年終結帳範本設定已移至新的設定頁面：**年終結算範本設定**。 現有的年終結算頁面將變成類似 **總帳的外幣重估** 頁面，表列顯示每次執行或沖銷的年終結算。 該頁面不會顯示有關啟用該功能之前完成的年終結算的歷程記錄資訊。 會計主管可以從新的頁面啟動年終結算。

若要沖銷年終結算，請選取相應法律實體最近的會計年度，然後選取 **沖銷年終結算**。 沖銷會刪除上一個年終結算的會計分錄，但不會自動重新執行年終結算。 如果您在完成年終結算後啟用 **總帳年終增強** 功能，並且您想要沖銷歷史年終結果，請在啟用 **為年度重新結算時刪除現有的年終結算分錄** 總帳參數之後，再次執行歷史年終結算。

您可以重新啟動會計年度和法律實體的流程，藉以重新執行年終結算。 此流程會繼續使用總帳參數設定，確定年終結算重新執行是否僅考慮新的或變更的交易，或該流程是否將針對所有交易重新執行並完全沖銷上次的結算。

## <a name="general-ledger-the-general-ledger-year-end-enhancements-feature-is-enabled-why-cant-i-view-my-previous-year-closings-in-the-history-section-of-the-year-end-close-page"></a>總帳：啟用總帳年終增強功能。 為什麼我無法在年終結算頁面的 [歷程記錄] 區段中檢視上一年的結算？

在啟用 **總帳年終增強** 功能之前，會追蹤上一次年終結算流程的執行日期和時間。 它不會追蹤每次執行年終結算的歷程記錄。 因此，無法顯示每個年終結算執行的詳細資料。 啟用該功能後，便會維護後續年終結算流程資訊。 **憑單交易** 頁面上可以檢視所有來自年終結算流程的憑單，甚至包括啟用該功能之前執行的流程憑單。 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-cant-be-run-because-one-or-more-ledger-transactions-posted-into-the-fiscal-year-that-you-are-closing-were-settled-to-a-ledger-transaction-in-a-different-fiscal-year-what-does-this-error-mean"></a>總帳：年終結算流程因為發生以下錯誤而失敗：「無法執行年終結算，因為一或多個過帳至您要結算之會計年度的分類帳交易已結算至不同會計年度的分類帳交易。」 這個錯誤代表什麼意思？

由於已啟用 **區分分類帳結算與年終結算**，只有要結算之會計年度的已結算分類帳交易會從期初餘額中排除。 這項行為會導致借方和貸方的餘額不足。 如需詳細資訊，請參閱[區分分類帳結算與年終結算](awareness-between-ledger-settlement-year-end-close.md)。

## <a name="general-ledger-reversal-of-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-for-112022-cant-be-reversed-because-beginning-balance-transaction-have-been-ledger-settled-in-fiscal-year-112023-what-does-this-error-mean"></a>總帳：年終結算流程的沖銷由於發生以下錯誤而失敗：「1/1/2022 的年終結算無法沖銷，因為期初餘額交易已在會計年度 1/1/2023 中結算分類帳。」 這個錯誤代表什麼意思？

由於已啟用 **區分分類帳結算與年終結算** 功能，如果已在新會計年度中結算了未結餘額交易，則不允許進行年終處理沖銷。 在您沖銷 2022 年 1 月 1 日的年終結算之前，請先沖銷新的 2023 會計年度的分類帳結算。 或者，重新結算 2022 年 1 月 1 日的年度，但僅限於新的調整分錄。 若僅針對調整分錄重新結算年度，請停用 **為年度重新結算時刪除現有的年終分錄** 總帳參數。

## <a name="general-ledger-why-isnt-the-ledger-settlement-automation-processing-decembers-ledger-settlement-transactions"></a>總帳：為什麼分類帳結算自動化並未處理 12 月的分類帳結算交易？

**自動化分類帳結算** 功能將對自會計年度的第一天到例項執行的當前日期之間所發生的交易執行自動化。 對於在 12 月 31 日結束的會計年度，您可能必須調整例項的執行日期以確保它在 12 月執行。 例如，自動化已設定為在每個月的第一天執行。 此自動化將於 2022 年 12 月 1 日執行，並已排程於 2023 年 1 月 1 日執行。 我們建議您變更 2023 年 1 月 1 日的例項，讓它能改在 2022 年 12 月 31 日執行。 此項變更將確保日期範圍在 12 月 2 日至 31 日的交易均會進行自動結算。

## <a name="general-ledger-whats-the-difference-between-the-reverse-year-end-close-action-and-the-delete-existing-year-end-entries-when-reclosing-parameter-for-year-end-close"></a>總帳：年終結算適用的沖銷年終結算動作和重新結算時刪除現有的年終分錄參數之間有何差別？

您可能會對 **沖銷年終結算** 動作和總帳中的 **重新結算時刪除現有的年終分錄** 參數 (**總帳 \> 分類帳設定 \> 總帳參數**) 之間的差別產生混淆。

在執行年終結算流程時，選取 **沖銷年終結算** 動作可刪除所有期末餘額和期初餘額分錄，就好像從未執行過年終結算一樣。 在這種情況下，憑單將會被刪除。 年終結算將不會再次自動執行。 若要執行年終結算，請選取 **執行年終結算** 動作。

總帳中的 **為年度重新結算時刪除現有的年終分錄** 參數只有在您執行 (而不是沖銷) 年終結算時使用。 如果參數設定為 **是**，將會刪除所有期末餘額和期初餘額分錄，並再次執行年終結算。 當組織希望所有交易 (包括自去年年終結算以來的調整分錄) 能以期末餘額和期初餘額分錄的單一會計分錄過帳時，就會使用此選項。 如果參數設定為 **否**，即保留所有期末餘額和期初餘額分錄。 這些分錄不會被刪除。 但只會針對該會計年度自去年年終結算以來已過帳的差異或新交易，建立新的期末餘額和期初餘額分錄。

> [!NOTE]
> 期末餘額分錄會建立在要結算的年度中。 只有在總帳參數 **在轉帳期間建立期末交易** 設為 **是** 時才會發生。 期初餘額分錄一定會建立，因為這是下一年度的期初餘額。

## <a name="general-ledger-what-is-the-difference-between-close-all-and-close-single-options-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process"></a>總帳：年終結算流程的 [轉移損益維度] 區段中 [全部結算] 和 [單筆結算] 選項有什麼區別？

**全部結算** 會維持來自已過帳交易的原始財務維度值，並使用它們為保留盈餘科目建立期初餘額。 將為財務維度值的每個唯一組合建立單獨的保留盈餘期初餘額。 如果選取了 **單筆結算**，具有該財務維度的所有已過帳交易都將匯總到保留盈餘期初餘額，提供已輸入至出現在 **單筆結算** 後之欄位的維度值使用。 

例如，會計年度的所有交易都使用科目結構主科目 - 部門過帳。 對於範本上的部門財務維度，選取了 **單筆結算**，並輸入 100 做為維度值。 如果過帳到部門 200、300 和 400 的所有交易的總收入為 $100,000，將建立一筆期初餘額做為保留盈餘 - 100。 如果您選取 **單筆結算** 但將財務維度值留白，所有交易都將過帳到保留盈餘，並且維度值將留白。

## <a name="general-ledger-when-i-select-close-single-option-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process-will-my-detailed-transactional-information-be-lost"></a>總帳：當我在年終結算流程的 [轉移損益維度] 區段中選取 [單筆結算] 選項時，我的詳細交易資訊會遺失嗎？

**全部結算** 和 **單筆結算** 選項用於指定交易中過帳到損益科目的哪些財務維度將轉移至保留盈餘主科目。 過帳到損益科目的詳細歷程記錄不會受到影響，將保持詳細資訊。 該選項會影響做為新年度期初餘額轉移到保留盈餘科目的詳細程度。 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-the-reporting-currency-for-the-year-does-not-balance-what-does-this-mean"></a>總帳：年終結算流程失敗，因為當年的報表貨幣不平衡。 這個訊息代表什麼意思？

啟用 **區分分類帳結算與年終結算** 功能 ([感知] 功能) 後，可能會發生此錯誤。 啟用該功能後，在執行總帳年終結算時，已結算的分類帳交易將不再計入下一會計年度的期初餘額。 如果分類帳使用報表貨幣進行定義，則在年終結算時排除已結算的分類帳交易可能會給客戶帶來挑戰。   
分類帳結算僅針對會計貨幣執行。  結算分類帳交易時，驗證只會確保會計貨幣借方等於會計貨幣貸方。 這些分類帳交易的報表貨幣金額未經驗證，借方 = 貸方可能不成立。  此外，分類帳結算不會自動計算和過帳報表貨幣的損益。  由於這些限制，在執行分類帳結算時，損益交易必須以報表貨幣存在。  如果分類帳結算中未包含損益，則年終結算將導致餘額不足的訊息。  如需詳細資訊，請參閱[區分分類帳結算功能和報表貨幣餘額不足](reporting-currency-yec.md)。

## <a name="general-ledger-what-can-be-changed-to-help-enhance-the-performance-of-year-end-processing"></a>總帳：變更什麼設定有助於增強年終處理流程的效能？

您可以執行數項變更，協助改善年終結算的效能。 建議您評估這些建議的變更，以確定這些變更是否適合您的組織。

### <a name="optimize-year-end-close-service"></a>最佳化年終結算服務

**最佳化年終結算** 服務使 Microsoft Dynamics 365 Finance 客戶能夠透過將繁重的年終處理轉移到微服務的方式來加速年終結算。 透過有效率的年終結算所節省的時間讓每個 Finance 團隊能夠對所需的調整進行及時反應，最終產生財務報表。 透過在微服務上處理年終結算，可以釋出寶貴的資源。 處理提升可將 SQL Server 上的負載降至最低，並為客戶提供了加速年終結算處理的機會。

**最佳化年終結算** 服務可於 10.0.31 版中提供使用，讓更多客戶可在 2022 年終旺季使用該項新服務。 此外，該服務已向後移植到 10.0.30 版和 10.0.29 版。 如需詳細資訊，請參閱[最佳化年終結算](optimize-year-end-close.md)。

### <a name="dimension-sets"></a>維度集

當您執行年終結算時，將重建每個維度集餘額。 此行為會直接影響效能。 有些組織不必要地建立了一些維度集，因為有時候會用到，或者可能有時候用得到。 因為這些不必要的維度集仍會在年終結算時重建，會增加處理的時間。 請花一點時間評估您的維度集，並刪除任何不必要的維度集。

不必要的維度集也會影響批次工作 **BudgetDimensionFocusInitializeBalance** (**總帳 \> 會計科目表 \> 維度 \> 財務維度集**)。

[![財務維度集。](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>年終結算範本設定

年末結帳範本讓組織在將損益餘額轉移到保留盈餘時，可選擇要維護的財務維度等級。 這些設定讓組織能在將餘額轉移到保留盈餘時維護詳細的財務維度 (**全部結算**)，或選擇將金額匯總為單一維度值 (**單筆結算**)。 每個財務維度皆可定義此設定。 如需有關這些設定的詳細資訊，請參閱[年末結帳](year-end-close.md)文章。

建議您評估組織的要求，如果可以，請盡可能多關閉維度，使用 **單筆結算** 年末結帳選項提高效能。 通過以單一維度值結帳 (也可以是空白值)，系統在確定保留盈餘科目分錄的餘額時，可以少計算一些詳細資訊。

### <a name="degenerate-dimensions"></a>退化維度

退化維度本身以及與其他維度的組合對不重複使用幾乎沒什麼作用。 退化維度有兩種類型。 第一種類型是各自退化的維度。 這種類型的退化維度一般只會出現在單一交易中，或出現在小型的交易集中。 第二種類型是結合其他一或多個維度一起退化的維度，這些維度根據可以產生的可能排列展現相同的潛力。 退化維度對年末結帳流程的效能有重大影響。 為將效能問題減至最輕，請將上節所述之年終結算設定中的所有退化維度定義為 **單筆結算**。

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2022"></a>應付帳款：為支援 2022 年的年末 1099 報表進行了哪些變更？

#### <a name="update-to-all-1099-forms"></a>更新至所有 1099 表單

2022 納稅年度的所有 1099 表單進行了以下變更：

- 2021 年時，1099 表單上的年度為固定。 從 2022 年開始，會依報告填入年度。

#### <a name="1099-misc"></a>1099-MISC

2022 納稅年度的表單 1099-MISC 上進行了以下變更：

- 方塊 13：現在表示外國帳戶稅收合規性法案 (FATCA) 歸檔要求。
- 方塊 14：現在用於報告超額的黃金降落傘付款。
- 方塊 15：現在用於報告非合格遞延補償 (NQDC) 計劃下的付款。
- 方塊 16：現在用於報告州預扣稅。
- 方塊 17：現在用於報告付款人的州別編號。
- 方塊 18：現在用於報告州所得。

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>應付帳款：1099 – 我該如何變更全年未追蹤 1099 資訊之廠商的 1099 方塊和值？

使用 **更新 1099** 功能來檢查之前支付的發票交易，並根據 **廠商** 頁面的 **稅務 1099** 索引標籤上的設定，以適當的方式重新指派 1099 資料。 若要使用 **更新 1099** 功能，請移至 **應付帳款 \> 廠商 \> 所有廠商**，選取廠商，然後在 **廠商** 索引標籤上的 [執行窗格] 選取 **更新 1099**。

## <a name="can-i-run-the-update-1099-functionality-for-all-my-vendors-at-once"></a>我可以一次對所有廠商執行更新 1099 功能嗎？

您可以使用 **為多個廠商更新 1099 資訊** 頁面來更新廠商記錄上的 1099 方塊，並使用取自 1099 方塊的資訊更新交易。 若要開啟此頁面，請移至 **應付帳款 \> 定期工作 \> 稅務 1099**。 若要存取該頁面，您必須被指派為 **更新多個廠商的 1099 方塊和交易** 安全性權限。

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>應付帳款：1099 – 重新計算現有的 1099 金額與更新 1099 公用程式的全部更新

搭配 **全部更新** 核取方塊一起使用時，**重新計算現有的 1099 金額** 核取方塊會將 1099 金額重設為總支付金額。

[![稅務 1099 交易記錄：在執行更新常式之前。](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

僅在發票上有部分 1099 金額，或在稅務 1099 表單上已修改發票時，**重新計算現有的 1099 金額** 核取方塊才會作用。 例如，假設您有一張發票價值 $1,000.00 美元，但使用者在發票上將 1099 金額手動輸入為 $500.00 美元。

[![稅務 1099 交易記錄：標記全部更新和重新計算現有的 1099 金額。](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

支付此發票後，支付的 1099 金額即為 $500.00 美元。 如果執行重新計算常式，1099 金額將變更為 $1,000.00 美元，這才是已支付的總額。

[![稅務 1099 交易記錄：執行 1099 常式後。](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>應付帳款：1099 – 手動建立 1099 交易記錄

組織可能需要手動建立與發票無關的 1099 交易記錄。 您可以前往 **應付帳款 \> 定期任務 \> 稅 1099 \> 1099 的廠商結算**，手動新增 1099 交易記錄。 選取 **手動建立 1099 交易記錄** 按鈕。

使用 **更新 1099** 公用程式的 **全部更新** 程序或 **重新計算現有的 1099 金額** 程序無法更新手動建立的 1099 交易記錄。

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>應付帳款：1099 – Dynamics 365 Finance 是否支援 1096 表單？

Dynamics 365 Finance 不會列印 1096 表單 (美國稅務資料申報表年度摘要與傳送)。

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>應付帳款：1099 – 是否有任何支援公部門申報 1099 表的新功能？

已新增一個新公部門功能 **按主科目更新 1099 資訊**，您可以在 **功能管理** 工作區中啟用此功能。 此功能可讓您透過會計分配的主科目建立與廠商 1099 值的關聯，而不是廠商記錄的預設科目。

如需詳細資訊，請參閱[設定申報 1099 表的廠商 ](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
