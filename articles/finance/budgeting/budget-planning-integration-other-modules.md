---
title: 預算計劃與其他模組的整合
description: 預算計劃可以從幾個不同的資源中產生。 所有資源的週期性流程的基本元素都是相同的。
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 64443
ms.assetid: f9a94db5-906c-404a-9ca5-91528d67c490
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ceae7296ef6d8a0f181c306bd533694c0219e467
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8450999"
---
# <a name="budget-planning-integration-with-other-modules"></a>預算計劃與其他模組的整合

[!include [banner](../includes/banner.md)]

預算計劃可以從幾個不同的資源中產生。 所有資源的週期性流程的基本元素都是相同的。 



## <a name="periodic-processes-for-generating-budget-plans"></a>產生預算計劃的週期性流程

預算計劃可以從以下資源產生：

-   總帳交易
-   固定資產
-   預測職位
-   專案預測
-   供應預測
-   需求預測
-   預算登記分錄
-   其他預算計劃

所有流程的週期性流程的基本元素都是相同的。 索引標籤可讓您定義資料來源、目標 (預算計劃) 屬性以及在後台作為批次處理執行流程的選項。 本文後面的小節將介紹在每個流程中可能不明顯的項目。

### <a name="actions"></a>動作

對於每個產生流程，有三個動作可使用：

-   **建立新的預算計劃** 會建立具有在 **目標** 區段選擇的屬性的新計劃。 這些屬性不必是唯一的。 因此，兩個計劃可以具有相同的名稱和其他值。
-   **替換現有的預算計劃方案** 會刪除所選預算計劃方案中目標預算計劃中的所有資料，並建立使用所選來源資料的新行。
-   **更新現有預算計劃方案，並追加新資料** 會更新目標計劃中與來源行相符的現有行，並為新資料新增行。 比對根據分類帳科目、日期、預算類別和各種其他欄位。 例如，當您從預測職位產生預算計劃時，職位編號會是一個重要欄位。 具有與該來源職位編號相符的職位編號的所有行都將替換為來源中的新行。

### <a name="source"></a>來源

對於所有流程，**來源** 索引標籤允許您使用 **篩選** 按鈕。 根據預設，特定欄位會新增到每個流程的篩選中。 例如，對於 **從總帳產生預算計劃** 流程、**分類帳** 和 **主科目** 類別可用，並顯示在產生頁面上。 您新增到篩選的任何欄位也會與您新增的任何條件一起新增到頁面中。

### <a name="target"></a>目標

**目標** 索引標籤上的 **歷史** 選項可讓您使用來源資料中的日期作為預算計劃中的生效日期。 通常，生效日期必須在計劃的預算週期內。 將 **歷史** 選項設定為 **是** 時，使用來源的日期 (甚至年份)，以便您可以使用過去的資料作為比較的基礎。 您無法修改預算計劃中的歷史資料，和計劃設定為已核准的工作流程狀態。 但是，如果計劃中有其他方案需要變更，您可以重設狀態。

頁面頂端的 **彙總總計** 欄位還確定要使用的日期。 此欄位會合計金額，並可選擇將生效日期設定為會計年度或會計期間的第一天。 

<strong>目標</strong>索引標籤上的許多欄位變為可編輯或唯讀，具體取決於您選擇的動作。 當您從建立新預算計劃變更為更新現有計劃時，**預算方案名稱** 欄位將變為不可用，與選擇現有計劃相關的欄位將變為可用。 **目標** 索引標籤和 **資源** 索引標籤上，**分類帳** 欄位始終不可用，因為該值由選定的預算計劃流程確定。 

**預算類別** 欄位可讓您將預算計劃行設定為費用交易或收入交易。 通常，收入交易會記入分類帳的貸方，因此儲存為負金額。 通常，這些交易在預算計劃中也顯示為負金額。 但是，透過將預算類別新增為計劃版面配置中的欄位，您可以使收入顯示為正金額。

### <a name="generation-rules"></a>產生規則

三個欄位提供其他功能：**係數**、**最小值** 和 **進位****規則**。 

**係數** 欄位中的值乘以來源金額以設定預算計劃中的金額。 然後，您可以在建立預算計劃行時進行調整。 例如，可以提高 3% 輸入 **1.03**。 係數必須為正數。 

**最小值** 欄位可讓您設定建立預算計劃行的閾值金額。 如果來源金額小於此數字，則不會建立預算計劃行。 **0.00** 值允許所有金額，但不限制行是否為正金額。 (沒有值限制行必須為正金額。 負金額永遠包括在內，且通常代表貸方分錄。)

**進位規則** 欄位可讓您設定建立的預算計劃行的精度。 您可以將金額四捨五入到最接近貨幣的 1.00、10.00、100.00，依此類推。

## <a name="notes-for-specific-processes"></a>特定流程的附註
### <a name="generate-budget-plan-from-general-ledger"></a>從總帳產生預算計劃

當您從總帳資料建立預算計劃時，如果 **歷史** 選項設定為 **否**，必須將 **彙總總計** 欄位設定為 **會計年度**。 來源中的期間和日期可能與目標中日期的期間不相符。 因為該流程沒有可靠的方法來對應這些值，所以您必須將該流程限制在一年中的第一天。 

在目標中，**預算類別** 欄位設定為 **費用** 或 **收入**。 此設定用於當行上的主科目不屬於 **收入** 或 **費用** 類型時，選擇建立的行的 **預算類型** 屬性。

### <a name="generate-budget-plan-from-fixed-assets"></a>從固定資產產生預算計劃

**從固定資產產生預算計劃** 流程不具有按時間段或日期彙總的選項。 也沒有將計劃設定為歷史的選項。 您可以使用此週期性流程將固定資產的預算交易包括在預算計劃中。

### <a name="generate-budget-plan-from-forecast-positions"></a>從預測職位產生預算計劃

**從預測職位產生預算計劃** 流程會將來源預測職位分配給預算計劃行。 您可以透過將預測職位新增為預算計劃版面配置中的一列或，使用 **預算計劃行** 查詢來查看職位。 如果您不希望將預測職位分配給預算計劃行，請將 **在預算計劃行中包括職位** 選項設定為 **否**。

預算計劃中的行按分類帳科目和職位彙總。 但是，您可以排除職位編號，以便僅按分類帳科目彙總行。 在 **目標** 索引標籤上，將 **在預算計劃中包括職位** 選項設定為 **否**。

在 **預算計劃 FTE 方案** 欄位中，可以選擇一個方案以在預算計劃中包含全職等量 (FTE) 的方案。 此欄位僅限於包含在目標預算計劃版面配置中的數量類型方案。 如果選擇 FTE 方案，則還必須選擇 FTE 主科目。 該科目用於建立數量預算計劃行。 

來源中選擇的預算計劃流程和預算計劃方案設定目標方案預算計劃流程和方案。 因為這些屬性分配給預測職位，所以它們必須與預算計劃相符。 因此，無法在目標上修改這些屬性。

### <a name="generate-budget-plan-from-project-forecasts"></a>從專案預測產生預算計劃

**從專案預測產生預算計劃** 流程如同 **從預測職位產生預算計劃** 流程，可以選擇在數量方案中包含專案數量 (工時、費用和品項)。 對於預算計劃版面配置中的欄，這兩個流程也有類似的篩選。 

在 **來源** 索引標籤上，**包括報表** 區段中的三個選項確定建立哪些預算計劃行。 這些選項與直接從專案預測建立預算登記分錄時可用的選項相同。 將 **收益與損失** 選項設定為 **是** 以建立成本行和收入行。 將 **WIP** 選項設定為 **是** 以建立在製品分錄。 將 **工資分配** 選項設定為 **是** 以建立工時交易的工資沖銷帳戶的行。 

沒有 **預算類別** 欄位，因為預算類別 (**費用** 或 **收入**) 由來源決定。 

您可以透過選擇包含專案預算金額的預測模型將專案預算作為來源。 請記住，專案預算在獲得核准時會建立專案預測分錄。

要僅選擇預算計劃行的成本或收入，請使用篩選器來選擇<strong>預算更新：金額類型 = 成本</strong>。 要僅選擇一種類型的預測，請使用篩選來選擇 <strong>預算更新：交易類型 =*xxx</strong>*。 

只能使用一種預測模型來產生預算計劃方案。 如果您為一個預測模型執行該流程，然後進行更新並嘗試指定另一個模型，那麼當套用相同的專案和分類帳科目時，將覆寫第一個模型。 要從多個預測模型產生預算計劃方案，請產生不同的預算計劃方案，並使用分配選項將它們新增到另一個方案中。 

**從專案預測產生預算計劃** 流程也將來源預測職位分配給預算計劃行。

### <a name="generate-budget-plan-from-supply-forecast"></a>從供應預測產生預算計劃

**從供應預測產生預算計劃** 流程中的來源篩選選項是根據 **將採購預算轉移到分類帳** 功能中的選項建模的，因為該流程和該功能之間有相似之處。

### <a name="generate-budget-plan-from-demand-forecast"></a>從需求預測產生預算計劃

對於 **從需求預測產生預算計劃** 流程，可以將 **銷售訂單** 選項設定為 **是**，以在預算計劃中產生收入行，將 **消耗** 設定為 **是** 以建立費用行，或將這兩個選項皆設定為 **是**。

### <a name="generate-budget-plan-from-budget-register-entries"></a>從預算登記分錄產生預算計劃

對於 **從預算登記分錄產生預算計劃** 流程中，來源必須指定一個子模型、一個預算代碼和一個分錄編號。 換言之，您一次只能為一個預算登記分錄建立預算計劃行。 透過為每個來源分錄執行一次流程，您可以在同一預算計劃中使用其他分錄。

### <a name="generate-budget-plan-from-budget-plan"></a>從預算計劃產生預算計劃

對於 **從預算計劃產生預算計劃** 流程，**目標** 索引標籤上的其他選項設定可讓您分配新的財務維度。 如果選擇了財務維度，則該值將用於所有預算計劃行。 因此，您可以將一個預算計劃作為其他預算計劃的基礎，但也可以將不同的部門或成本中心分配給新的預算計劃等。

## <a name="looking-back-from-the-budget-plan"></a>從預算計劃回顧
### <a name="budget-plans-by-dimension-set-inquiry"></a>按維度集排列的預算計劃查詢

**按維度集排列的預算計劃** 查詢包括多個選項，可讓您執行查詢以幫助確定預算計劃資料來源的選項。 

選擇一行並點擊 **預算計劃行** 按鈕執行 **預算計劃行** 查詢。 結果將針對所選行的維度值進行篩選。 然後，您可以套用其他參數。 

使用 **供應預測** 和 **需求預測** 按鈕執行這些查詢。 在這兩種情況下，查詢都會搜尋可能已建立預算計劃行的預測行。 

可用的其他報表包括 **按預算計劃預測職位** 報表。 當您要確定職位是否已正確分配到預算計劃時，此報表特別有用。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]