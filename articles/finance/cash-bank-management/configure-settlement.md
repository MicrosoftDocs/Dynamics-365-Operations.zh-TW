---
title: 設定結算
description: 交易的結算方式和時間可能非常複雜，因此您必須了解並正確定義參數以滿足您的業務需求。 本主題介紹用於結算應付帳款和應收帳款的參數。
author: kweekley
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 323a1e6d426208a880a72dd89f7be04bacbf13a8e6c5d8ab7599217cfc18f2c0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450192"
---
# <a name="configure-settlement"></a>設定結算

[!include [banner](../includes/banner.md)]

交易的結算方式和時間可能非常複雜，因此您必須了解並正確定義參數以滿足您的業務需求。 本主題介紹用於結算應付帳款和應收帳款的參數。 

以下參數會影響 Microsoft Dynamics 365 Finance 中處理結算的方式。 結算是根據付款或貸方通知單結算發票的流程。 這些參數位於 **應收帳款參數** 和 **應付帳款參數** 頁面的 **結算** 區域。

- **自動結算** – 如果交易應在過帳時自動針對其他未結交易進行結算，則將此選項設定為 **是**。 如果此選項設定為 **否**，使用者可以使用 **結算交易** 頁面在輸入付款或者稍後時手動結算交易。
- **現金折扣管理** – 指定[當發票超額支付時如何處理現金折扣](cash-discount-handling-overpayments.md)。 對於超額支付，可以減少現金折扣，可以將其視為差額，也可以為廠商或客戶在帳戶中保留。
  -   **不指定** – 現金折扣金額減去超額支付金額。 一律使用此行，無論超額支付金額是高於還是低於在 **最大超額支付或支付不足** 欄位中輸入的金額。
  -   **使定** - 超額支付金額會過帳到現金折扣差額分類帳科目，或作為餘額留在客戶或廠商帳戶上。 該特定行為取決於超額支付金額是否介於 0.00 和在 **最大超額支付或支付不足** 欄位中輸入的金額之間，或超額支付金額是否大於 **最大超額支付或支付不足**。
- **最大分值差** – 輸入已結算交易的最大允許分值差額。 如果差額等於或小於在此欄位中指定的分值差額，則將差額過帳到 **自動交易帳戶** 頁面中指定的分值差額分類帳科目。
- **最高超額支付或支付不足** – 輸入接受超額支付和支付不足的金額。 要計算超額支付或支付不足的稅款，請在 **總帳參數** 頁面，點擊 **銷售稅**，然後選擇 **超額支付或支付不足銷售稅** 選項。
  -   如果超額支付或支付不足產生的差額小於 **最大分值差** 欄位中定義的差額，該分值差額將過帳到分值差額科目。
  -   如果超額支付或支付不足產生的差額大於 **最大分值差** 欄位中定義的差額，差額金額將過帳到為 **自動交易帳戶** 頁面 **客戶現金折扣** 或 **廠商現金折扣** 選擇的差額科目。
- **計算部分付款的現金折扣** – 將此選項設定為 **是**，使現金折扣能夠自動計算部分付款。
  -   此選項的影響取決於 **結算交易** 頁面的 **使用現金折扣** 欄位的值。 如果此選項設定為 **是**，折扣將在 **使用現金折扣** 欄位設定為 **標準** 時執行。 當 **使用現金折扣** 欄位設定為 **永遠** 時，無論該欄位的設定如何，將始終採用現金折扣。 當 **使用現金折扣** 欄位設定為 **永不** 時，無論該欄位的設定如何，將始終不採用現金折扣。
  -   如果此選項設為 **是**，而且使用者變更 **結算未結交易** 頁面中 **要結算的金額** 欄位的值，則會自動計算折扣，並在 **可獲得的現金折扣金額** 欄位中顯示為預設分錄。
  -   如果此選項設為 **否**，但使用者變更 **結算未結交易** 頁面中 **要結算的金額** 欄位的值，則會 **可獲得的現金折扣金額** 欄位中的預設分錄為 **0** (零)。
- **計算貸方通知單的現金折扣** – 將此選項設定為 **是** 以自動計算貸方通知單的現金折扣。 在應收帳款中，貸方通知單交易記錄是在 **普通發票** 頁面的 **發票** 欄位中具有值的負交易記錄，或在 **銷售訂單** 頁面上的退貨。
  - 此選項的此影響取決於<strong>結算交易</strong>頁面的<strong>使用現金折扣</strong>欄位的值。 如果此選項設定為 <strong>是</strong>，折扣將在 *<strong><em>使用現金折扣</em></strong>* 欄位設定為<strong>標準</strong>時執行。 當 *<strong><em>使用現金折扣</em></strong>* 欄位設定為<strong>永遠</strong>時，無論該欄位的設定如何，將始終採用現金折扣。 當 *<strong><em>使用現金折扣</em></strong>* 欄位設定為<strong>永不</strong>時，無論該欄位的設定如何，將始終不採用現金折扣。
  - 如果此選項設為 **是**，並且在 **結算未結交易** 頁面中標記了貸方通知單，則折扣將自動計算，並在 **可獲得的現金折扣金額** 中顯示為預設分錄。
  - 如果此選項設為 **否**，並且在 **結算未結交易** 頁面中標記了貸方通知單，則折扣將自動計算，並在 **可獲得的現金折扣金額** 欄位中的預設分錄為 **0** (零)。

- **折扣沖銷帳戶 (僅限 AP)** – 定義應用於現金折扣會計分錄的預設現金折扣分類帳科目。
  -   **使用廠商折扣的主科目** – 現金折扣過帳到在 **現金折扣設定** 頁面上定義的主科目。
  -   **發票行上的科目** – 現金折扣過帳到原始發票上的分類帳科目。
- **在普通發票和利息單上標記行 (僅限 AR)** – 將此選項設定為 **是**，以啟用 **輸入客戶付款**、**付款日記帳憑證** 和 **結算交易** 頁面的 **標記發票行** 按鈕。 此按鈕允許使用者標記單獨的行以進行結算。
- **優先結算 (僅限 AR)** – 將此選項設定為 **是**，以啟用 **輸入客戶付款** 和 **結算交易** 頁面的 **按優先順序標記** 按鈕。 此按鈕允許使用者將預定的結算訂單分配給交易。  將結算訂單應用於交易後，可以在過帳前修改訂單和付款分配。
- **使用優先順序進行自動結算** – 將此選項設定為 **是**，在交易自動結算時使用定義的優先順序。 僅在 **優先結算** 和 **自動結算** 選項設定為 **是** 時，才可使用此欄位。

## <a name="fixed-dimensions-on-accounts-receivableaccounts-payable-main-accounts"></a>應收帳款/應付帳款主科目的固定維度

當在應收帳款/應付帳款主科目上使用固定維度時，結算流程將過帳額外的會計分錄和兩個額外的廠商交易。 結算比較發票和付款中的應收帳款/應付帳款分類帳。  當付款和結算一起完成時，這是典型的場景，直到結算流程也完成後，付款的會計分錄才會過帳到總帳。 由於處理事件的順序，結算無法從付款的會計分錄中確定實際的應收/應付帳款分類帳。 結算會重建分類帳科目用於付款的內容。 當應收帳款/應付帳款主科目使用固定維度時，這將成為一個問題。

要重建分類帳科目，應從過帳設定文件中檢索應收帳款/應付帳款主科目，並從付款日誌中定義的廠商交易記錄中檢索財務維度。 固定維度不預設用於付款日記帳，而是作為過帳流程的最後一步應用到主科目。 因此，固定維度值可能不包含在廠商交易中，除非它預設來自其他來源，例如廠商。 重構的帳戶將不包括固定維度。 結算處理將確定必須建立調整分錄，因為使用固定維度值過帳的發票和重建的付款帳戶沒有。  隨著結算繼續過帳調整分錄，過帳的最後一步是應用固定維度。 透過將固定維度新增到調整分錄，將其與借方和貸方一起過帳到同一分類帳科目。 結算不能回滾會計分錄。

為避免額外的會計分錄、借方和貸方到同一個分類帳戶，應根據您的業務需求考慮以下變通方法。 

-   組織經常使用固定維度對不需要的財務維度進行零填充。 這通常是資產負債表帳戶的情況，例如應收帳款/應付帳款。 帳戶結構可用於不追蹤通常為零填充的財務維度。  您可以刪除資產負債表科目的財務維度，從而無需使用固定維度。
-   如果您的組織在應收帳款/應付帳款主科目上需要固定維度，請找到一種方法將固定維度預設為付款，以便將固定維度值存儲在付款的廠商事務中。 這將允許系統重構應收帳款/應付帳款主科目以包含固定維度值。 可以將固定維度值定義為廠商或付款日記帳的日記帳名稱的預設值。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]