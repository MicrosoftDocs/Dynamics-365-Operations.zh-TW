---
title: 收入認列重新配置
description: 本主題提供有關重新配置的資訊，這可讓組織在合約銷售條款發生變更時重新計算收入價格。 當中包括指向其他主題的連結，內容描述如何在多種情境下確認收入。
author: kweekley
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 53304842bdbe7dadb435ab3a0381f3835c2c443a
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "8452892"
---
# <a name="revenue-recognition-reallocation"></a>收入認列重新配置

[!include [banner](../includes/banner.md)]

重新配置可讓組織在合約銷售條款發生變更時重新計算收入價格。 就收入認列而言，銷售訂單文件即視為合約。

您的組織必須自行確定是否需要重新配置。 對銷售訂單新增明細或為客戶新增銷售訂單可能不構成更改合約。 以下情境可能需要重新配置：

- 在訂單全部或部分開票後，客戶將品項新增到銷售訂單或從銷售訂單中移除品項。
- 為同一份交涉合約輸入了多個銷售訂單，無論是已確認狀態或已開票狀態。
- 在原始銷售訂單全部或部分開具發票後，客戶退回或收到品項的信用額度。

重新配置程序有一些重要的限制：

- 該程序只能執行一次。 因此，只在完成所有變更後再執行該程序很重要。

    - 此限制在 10.0.17 及更高版本中已移除。

- 專案銷售訂單上不能執行該程序。

    - 此限制在 10.0.17 及更高版本中已移除。

- 如果涉及多個銷售訂單，則它們必須是針對同一個客戶帳戶。
- 所有重新配置的銷售訂單必須使用相同的交易貨幣。
- 該程序在執行後無法還原或復原。

    - 此限制在 10.0.17 及更高版本中已移除。

- 只能對銷售訂單或專案銷售訂單進行重新配置。 不能對銷售訂單和專案銷售訂單的組合進行此動作。

    - 此限制在 10.0.17 及更高版本中已移除。

## <a name="set-up-reallocation"></a>設定重新配置

有個參數會影響重新配置過程。

由於可以對部分或全部開票的銷售訂單進行重新配置，因此必須使用重新配置的新收入價格更正發票任何先前的會計分錄。 此更正是透過撤銷原始發票的會計分錄，並將基於重新配置的收入價格的新會計分錄過帳來完成的。

每個組織都必須決定更正是否應僅更新總帳，或者是否同時應更新應收帳款。 所達成的決策決定了 **總帳參數** 頁面的 **收入認列** 索引標籤上 **將發票更正過帳到應收帳款** 選項 (**收入認列 \> 設定 \> 總帳參數**) 的適當設定。 適當的設定取決於具體的情境。 有關可能的情境的詳細資訊，請使用本主題稍後的[重新配置的情境](#scenarios-for-reallocation)一節中的連結。

[![總帳參數頁面上的收入認列索引標籤。](./media/01_RevRecScenarios.png)](./media/01_RevRecScenarios.png)

如果 **將發票更正過帳到應收帳款** 選項設定為 **是**，重新配置程序產生以下結果：

- 在應收帳款中建立信用文件以撤銷需要更正的發票。

    - 信用文件會重複使用原始發票編號，但附加了「-1」。
    - 信用文件會自動根據原始發票結算。 如果原始發票已使用其他信用文件或付款進行結算，則將自動撤銷該結算。
    - 信用文件會過帳到總帳，以撤銷原始發票上過帳的會計分錄。 然而，不會撤銷庫存和銷貨成本 (COGS) 交易條目。

- 在應收帳款中會建立基於重新配置之新價格金額的新發票。

    - 新發票會重複使用原始發票編號，但附加了「-2」。
    - 新發票將自動根據之前使用原始發票結算的任何信用文件或付款進行結算。
    - 新發票會使用重新配置的新收入價格金額過帳到總帳。 它不會再次過帳到庫存和 COGS 科目，因為這些條目保留在原始發票的會計分錄中。

如果 **將發票更正過帳到應收帳款** 選項設定為 **否**，重新配置程序產生以下結果：

- 撤銷會計分錄僅過帳到總帳。 除庫存和 COGS 科目分錄外，原始發票的所有會計科目均已撤銷。
- 根據重新配置的新收入價格，僅將新會計分錄過帳到總帳。 它不會再次過帳到庫存和 COGS 科目，因為這些條目保留在原始發票的會計分錄中。
- **客戶交易** 頁面上的發票不受影響或更改，但仍反映原始會計分錄。 沒有對回轉或新會計分錄的參考。

如前所述，您可以只更新總帳，也可以同時更新總帳和應收帳款。 兩種方法各有優缺點。 我們建議您評估您組織的需求以確定應該使用哪個選項。 如果您同時更新總帳和應收帳款，正確的會計分錄將顯示在新發票上，並可從 **客戶交易** 頁面上的文件檢視。 此外，結算過程將使用更新的會計分錄來過帳任何現金折扣和收益或損失。 另一方面，信用文件和新發票將出現在客戶報表和帳齡報告中，就像其他信用文件和客戶發票一樣。 這些文件的描述將表明它們是透過會計更正建立的。

## <a name="run-the-reallocation-process"></a>執行重新配置程序

要開始重新配置程序，請在您必須重新配置的任何銷售訂單中選擇 **使用新訂單明細重新配置價格**。 或者，移至 **收入認列 \> 定期任務 \> 使用新訂單明細重新配置價格**，然後輸入適當的篩選條件，例如客戶帳戶。

[![使用新訂單明細重新配置價格頁面。](./media/02_RevRecScenarios.png)](./media/02_RevRecScenarios.png)

**使用新訂單明細重新配置價格** 頁面上方的格線名為 **銷售**。 它列出了客戶的銷售訂單。 選擇必須重新配置的銷售訂單。 如果銷售訂單具有重新配置識別碼，則它已被另一個使用者標記為重新配置。 如果一個或多個銷售訂單先前已重新配置並且必須包含在另一個重新配置中，則必須首先撤消該些銷售訂單的重新配置。 之後可以將其包含在新的重新配置中。 有關更多詳細資訊，請參閱本主題稍後的[復原重新配置](#undo-a-reallocation)和[多次重新配置](#reallocate-multiple-times)章節。

頁面下方的格線名為 **明細**。 在 **銷售** 格線中選擇一個或多個銷售訂單後，**明細** 格線會顯示銷售訂單明細。 選擇必須重新配置的銷售訂單明細。 如果您只選擇了一個銷售訂單，則必須重新配置同一銷售訂單上的明細。 當其中一個銷售訂單行先前已開票，然後加入了新明細，或者移除或取消了現有明細時，可能會發生這種情況。 如果移除了一條明細，它將不會出現在格線中。 因此，無法選擇它。 不過，在執行重新配置程序時仍會考慮它。

完成選擇所需的銷售訂單明細後，使用動作窗格上的按鈕，如下所述：

- **更新重新配置** – 計算選定銷售訂單明細的新收入價格金額。 如果移除或取消了一條明細，則僅對您選擇的現有明細進行重新配置。 下圖顯示了重新配置更新之前的銷售訂單明細範例。

    [![更新重新配置之前的銷售訂單明細。](./media/03_RevRecScenarios.png)](./media/03_RevRecScenarios.png)

    新的收入價格金額顯示在 **明細** 格線的 **重新配置的金額** 欄中。 此時，重新配置已處理完畢，但尚未計算。 下圖顯示了重新配置更新之後的銷售訂單明細範例。

    [![更新重新配置之後的銷售訂單明細。](./media/04_RevRecScenarios.png)](./media/04_RevRecScenarios.png)

- **處理** – 處理或將重新配置的收入價格過帳。 選擇此按鈕後，無法撤銷重新配置。 如果在選擇 **處理** 之前，您沒有選擇 **更新重新配置**，重新配置會自動執行。

    - 如果沒有為銷售訂單明細開票，會在選擇進行重新配置的任何銷售訂單上更新收入價格金額。
    - 如果一個或多個銷售訂單明細已開票，則會將更正會計分錄過帳，並更正為已開票銷售訂單明細建立的任何收益計畫表詳細資料。

- **預期憑單** – 顯示已為任何已開票的銷售訂單明細建立的會計分錄的預覽。 如果沒有任何明細已開票，則不顯示任何內容。 如果在選擇 **預期憑單** 之前，您沒有選擇 **更新重新配置**，重新配置會自動執行。
- **收入重新配置** – 打開一個頁面，當中顯示所有選定明細的收入價格配置。 您無法更改頁面上的任何資訊。 它會顯示用於進行重新配置的明細金額。

    [![用於重新配置的明細金額。](./media/05_RevRecScenarios.png)](./media/05_RevRecScenarios.png)

- **重設選定客戶的資料** – 如果重新配置程序已開始但未完成，則僅清除所選客戶的重新配置表中的資料。 例如，您將多個銷售訂單明細標記為重新配置，您將頁面保持開啟狀態而不選擇 **處理**，然後頁面逾時。在這種情況下，銷售訂單明細將保持標記狀態，而其他使用者無法完成重新配置程序。 頁面打開時甚至可能是空白的。 在這種情況下，**重設選定客戶的資料** 按鈕可用於清除未處理的銷售訂單，以便其他使用者完成重新配置程序。

## <a name="undo-a-reallocation"></a>復原重新配置

執行另一個重新配置會復原重新配置。 重新配置再次完成，而使用者選擇不同的銷售訂單明細以包括在第二次重新配置程序中。

如果在兩個或多個單獨的銷售訂單中進行了重新配置，則可以透過從重新配置中包含的任何銷售訂單選擇 **使用新訂單明細重新配置價格**。 您不能移至 **收入認列 \> 定期任務 \> 使用新訂單明細重新配置價格** 來復原重新配置，因為以這種方式打開的頁面僅會顯示沒有重新配置識別碼的銷售訂單。 文件在重新配置後才會指派重新配置識別碼。

在 **使用新訂單明細重新配置價格** 頁面上，取消標記應從合約協議中排除的任何銷售訂單。 使用動作窗格上的適當按鈕，例如 **更新重新配置** 和 **處理**，來處理重新配置。 如果除了活動銷售訂單外的所有銷售訂單均未標記，則在處理更改時將移除重新配置識別碼。

如果透過將新明細新增到完全或部分開票的銷售訂單來完成重新配置，則只能透過從銷售訂單中移除該明細然後再次執行重新配置來復原重新配置。 必須刪除銷售訂單明細，因為銷售訂單上的所有明細都假定為同一合約的一部分。 在 **使用新訂單明細重新配置價格** 頁面上時無法取消標記銷售訂單。

## <a name="reallocate-multiple-times"></a>多次重新配置

如果對合約進行了多次更改，則可以針對同一個銷售訂單進行多次重新配置。 每次重新配置都會觸發將重新配置識別碼指派給銷售訂單或銷售訂單群組，以將更改組成群組。 如果進行了多次重新配置，則每個額外的重新配置都會使用與第一次重新配置相同的重新配置識別碼。

例如，輸入了銷售訂單 00045 並具有多條明細。 在銷售訂單完全開票後，將在其中加入一個新的銷售訂單明細。 然後透過從銷售訂單 00045 或透過移至 **收入認列 \> 定期任務 \> 使用新訂單明細重新配置價格** 打開 **使用新訂單明細重新配置價格** 頁面，來執行重新配置。 將重新配置識別碼 **Reall000001** 指派至銷售訂單。

為同一合約建立第二個銷售訂單 00052。 可以透過從銷售訂單 00045，而不是銷售訂單 00052 打開 **使用新訂單明細重新配置價格** 頁面，再次執行重新配置。 如果您從銷售訂單 00052 打開 **使用新訂單明細重新配置價格** 頁面，將不會顯示銷售訂單 00045，因為已為其指派了重新配置識別碼。 該頁面僅顯示沒有重新配置別碼的銷售訂單。

有兩種方法可以進行第二次重新配置。 您可以復原重新配置銷售訂單 00045。 在這種情況下，會移除重新配置識別碼，然後您可以從銷售訂單 00045 或銷售訂單 00052 進行重新配置。 或者，您可以從銷售訂單 00045 打開 **使用新訂單名重新配置價格** 頁面，並新增第二個銷售訂單。 處理重新配置時，重新配置識別碼 **Reall000001** 將指派至銷售訂單 00045 和銷售訂單 00052。

## <a name="scenarios-for-reallocation"></a>重新配置的情境

以下主題介紹了收入認列的各種情境：

- [收入認列重新配置 – 情境 1](rev-rec-reallocation-scenario-1.md) – 輸入了兩個銷售訂單，但它們只經過確認。 如果兩個以上的銷售訂單處於確認狀態，相同的情境將產生類似的結果。
- [收入認列重新配置 – 情境 2](rev-rec-reallocation-scenario-2.md) – 輸入兩個銷售訂單，然後客戶在為第一個銷售訂單開票後將品項新增到合約中。
- [收入認列重新配置 – 情境 3](rev-rec-reallocation-scenario-3.md) – 將新明細新增到現有的已開票銷售訂單。
- [收入認列重新配置 – 情境 4](rev-rec-reallocation-scenario-4.md) – 從現有的已開票銷售訂單移除明細。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]