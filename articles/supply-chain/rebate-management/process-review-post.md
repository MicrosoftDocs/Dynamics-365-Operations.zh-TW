---
title: 處理、審查和過帳回扣
description: 本主題描述如何處理您的回扣管理交易、計算其折扣、審查產生的交易、過帳交易及審查過帳。
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 803b4d8b287f2b0dc523654e3e1852209f4ea039
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448623"
---
# <a name="process-review-and-post-rebates"></a>處理、審查和過帳回扣

[!include [banner](../includes/banner.md)]

本主題描述如何處理您的回扣管理交易、計算其折扣、審查產生的交易、過帳交易及審查過帳。

## <a name="change-the-status-of-a-deal"></a>變更交易狀態

您可以為每個交易指配一個狀態，以有助於追蹤交易。 該狀態僅供參考。

1. 選擇一個交易 (例如，在 [**所有回扣管理交易** 頁面](rebate-management-deals.md))。
1. 在 [動作窗格] 上，在 **回扣管理交易** 索引標籤上的 **維護** 群組中，選取 **變更狀態**。
1. 在 **變更狀態** 對話方塊中，將 **回扣狀態** 欄位設定為新的狀態。
1. 選取 **確定**。

## <a name="calculate-fifo-purchase-prices"></a>計算先進先出採購價格

必須執行 **計算先進先出採購價格** 定期工作，才能為 **價格基礎** 欄位設定為 *先進先出* 的[交易](rebate-management-deals.md)計算回扣。 系統將使用先進先出 (FIFO) 規則來計算已售庫存的價值。 然後，此值將用於計算廠商回扣。

移至 **回扣管理 \> 定期工作 \> 計算先進先出採購價格**。 在出現的對話方塊中，選擇 **確定** 執行計算。

## <a name="create-source-transactions"></a>建立來源交易

您可以在建立適用的回扣管理交易之前或之後，建立具有來源交易的銷售訂單或採購訂單。

您可以設定每個交易行，以便藉由過帳銷售訂單或採購訂單的交貨或發票來自動建立回扣準備金。 將交易行的 **交易類型** 欄位設定為 *交貨* 或 *發票*，並將 **過帳時處理** 選項設定為 *是*。 如果 **交易類型** 欄位設定為 *訂單*，則會停用過帳時處理。 對於在啟用交易後建立的來源交易，您仍可以處理準備金，如本主題稍後[處理回扣管理交易](#process-deals)一節中所述。

### <a name="enable-price-details"></a>啟用價格詳細資料

您必須先啟用應收帳款的 **啟用價格詳細資料** 選項，才能建立來源交易。

1. 前往 **應收帳款 \> 設定 \> 應收帳款參數**。
1. 在 **價格詳細資料** FastTab 上的 **價格** 索引標籤，將 **啟用價格詳細資料** 選項設定為 *是*。

### <a name="create-a-source-transaction"></a>建立來源交易

若要建立來源交易，請按照以下步驟操作。

1. 前往 **銷售和行銷\>銷售訂單\>所有銷售訂單**。
1. 選取 **新增**。

    為了模仿回扣索賠產生的方式，現在您必須建立銷售訂單，訂單的產品和數量將使相關客戶有資格獲得回扣。

1. 在 **客戶帳戶** 欄位中，輸入或選擇有資格獲得回扣交易的客戶。
1. 選擇 **確定** 建立銷售訂單。
1. 在 **銷售訂單行** FastTab 上新增一行，並為該行設定以下欄位：

    - **品項編號** – 指定有資格獲得回扣的品項。
    - **數量** – 指定一個有資格進行回扣交易的數量，其中某一行的 **基礎** 欄位設定為 *數量*。
    - **單價** – 指定一個有資格進行回扣交易的價格，其中某一行的 **基礎** 欄位設定為 *值*。
    - **站點** – 選擇產品可用且有資格進行回扣交易的站點。
    - **倉庫** – 選擇產品可用且有資格進行回扣交易的倉庫。

1. 在 **銷售訂單行** FastTab，在工具列上，選擇 **銷售訂單行 \> 價格詳細資料**。 只有在您已如上一節所述啟用價格詳細資料，此命令才可供使用。
1. 在 **價格詳細資料** 頁面上，選擇 **回扣管理** FastTab。 此 FastTab 列出會套用到目前訂單行的所有回扣管理交易，並以訂單的貨幣顯示預估的回扣金額。 請注意，這些金額只是未來回扣索賠的估計金額。 實際回扣金額可能有所不同。 以下是可能影響實際金額的一些因素：

    - 客戶在定期回扣合約下達成的總銷售量。
    - 客戶是退回全部數量還是部分數量。
    - 適用的銷售訂單是否達到為回扣管理交易定義的交易類型 (*訂單、交貨* 或 *發票*)。
    - 交易的 **輸出** 值。 對於 **輸出** 欄位設定為 *品項* 的交易將顯示空白的回扣金額。

1. 請注意在 **詳細資料** FastTab 上，**保證金估計** 區段包括以下欄位。 這些欄位是由回扣管理新增的。 這些欄位都會顯示每單位的值 (而 **回扣管理** FastTab 上的欄位會顯示該行的總值)。

    - **回扣管理回扣金額** (僅限銷售訂單)
    - **回扣管理權利金金額** (僅限銷售訂單)
    - **回扣管理廠商回扣金額** (銷售訂單與採購訂單)

1. 關閉 **價格詳細資料** 頁面。
1. 如果銷售訂單不符合您剛剛檢視的回扣條件，請按照以下步驟排除回扣。 (但是，您通常不會排除回扣。)

    1. 在 **銷售訂單行** FastTab上，選擇第一個相關行項。
    1. 在 **行項詳細資料** FastTab 上的 **價格與折扣** 索引標籤，將 **排除在回扣管理之外** 選項設定為 *是*。 此選項不適用於採購訂單。 此外，當此選項設定為 *是* 時，只有客戶回扣會遭到排除。 客戶權利金回扣與廠商回扣仍然適用。

1. 在動作窗格上 **揀貨與包裝** 索引標籤的 **產生** 群組中，選擇 **過帳裝箱單**。
1. 在 **參數** FastTab 上的 **數量** 欄位中，選擇 *全部*。
1. 選取 **確定**。
1. 如果系統提示您確認作業，請選擇 **確定**。
1. 在動作窗格的 **發票** 索引標籤上，在 **產生** 群組中選取 **發票**。
1. 在 **參數** FastTab 上的 **數量** 欄位中，選擇 *全部* 或 *裝箱單*。
1. 選取 **確定**。
1. 如果系統提示您確認作業，請選擇 **確定**。

## <a name="process-rebate-management-deals"></a><a name="process-deals"></a>處理回扣管理交易

當您處理交易時，系統會計算設定的所有相關回扣和權利金。 只會處理所選具有已準備好可供計算的計算期間且狀態為 *使用中* 的交易。 處理完成後，系統會產生一組交易，您可以審查然後過帳這些交易。

> [!NOTE]
> 在所有情況下，會在每個交易其 **對帳依據** 設定所指定的層級 (*交易* 或 *行項*) 處理回扣。 您只能為 **對帳依據** 欄位設定為 *行項* 的交易進行單行計算。

### <a name="process-all-lines-for-one-or-more-deals"></a>處理一或多個交易的所有行項

1. 針對您要處理的交易類型開啟適當的[回扣交易清單頁面](rebate-management-deals.md)。
1. 為您要處理的每個交易選擇資料列 (或開啟您要處理的交易)。
1. 在動作窗格上，在 **回扣管理交易** 索引標籤的 **產生** 群組中，選擇以下命令之一：

    - **處理 \> 準備金** – 為每個相關回扣交易準備一組應計項目，但不過帳。 此功能表項目不適用於 **回扣輸出** 欄位設定為 *品項* 的交易。
    - **處理 \> 回扣管理** – 處理一系列可為每個交易提供回扣值的交易。
    - **處理 \> 沖銷** – 對於回扣交易與指定期間的每個來源交易，處理已針對準備金過帳的金額與回扣管理金額之間的差異。 此功能表項目不適用於 **回扣輸出** 欄位設定為 *品項* 的交易。

1. 在顯示的對話方塊中，設定 **開始日期** 與 **結束日期** 欄位，以定義計算的日期範圍。
1. 選擇 **確定** 以執行計算。

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>為所選的交易處理一或多個特定交易行

1. 針對您要處理的交易類型開啟適當的[回扣交易清單頁面](rebate-management-deals.md)。
1. 開啟您要處理其行項的交易。
1. 選擇右上角的 **行項** 索引標籤。
1. 在 **回扣管理** FastTab 上，選擇所要處理每個交易行的資料列。
1. 在 **回扣管理** FastTab 的工具列上，選擇以下其中一個命令。 (這些命令僅適用於 **對帳依據** 欄位設定為 *行項* 的交易。)

    - **處理 \> 準備金** – 為每個相關交易行準備一組應計項目，但不過帳。 此功能表項目不適用於 **回扣輸出** 欄位設定為 *品項* 的交易。
    - **處理 \> 回扣管理** – 處理一系列可為每個交易行提供回扣值的交易。
    - **處理 \> 沖銷** – 對於回扣交易與指定期間的每個來源交易，處理已針對準備金過帳的金額與回扣管理金額之間的差異。 此功能表項目不適用於 **回扣輸出** 欄位設定為 *品項* 的交易。 

1. 在顯示的對話方塊中，設定 **開始日期** 與 **結束日期** 欄位，以定義計算的日期範圍。
1. 選擇 **確定** 以執行計算。

### <a name="process-deals-using-a-batch-job"></a>使用批次作業處理交易

您可以執行批次作業來同時處理數個交易，而不是處理特定的交易或交易行。 您可以選擇性地套用記錄篩選條件和/或設定週期性排程。 若要使用批次作業處理交易，請執行以下步驟。

1. 請執行以下其中一個步驟：

    - 移至 **回扣管理 \> 定期工作 \> 處理 \> 準備金**，為每個相關交易準備一組應計項目，但不過帳應計項目。
    - 移至 **回扣管理 \> 定期工作 \> 處理 \> 回扣管理**，以處理一系列為每個交易提供回扣值的交易。
    - 移至 **回扣管理 \> 定期工作 \> 處理 \> 沖銷**，以註銷先前過帳的交易來將其沖銷，讓系統可以計算新的回扣交易。

1. 在出現的對話方塊中，在 **參數** FastTab 的 **期間** 區段中，設定 **開始日期** 和 **結束日期** 欄位，為計算的交易定義日期範圍。
1. 在 **保證期間** 區段中設定 **開始日期** 與 **結束日期** 欄位，為計算的保證定義日期範圍。
1. 在 **要包括的記錄** FastTab 上，您可以設定篩選條件以限制批次作業將處理的交易集。 這些設定會以與針對其他類型批次作業運作相同的方式運作。
1. 於 **在背景執行** FastTab 上，您可以視需要設定批次處理與排程選項。 這些設定會以與針對其他類型批次作業運作相同的方式運作。
1. 選擇 **確定** 以執行和/或排程計算。

### <a name="process-deals-by-using-the-rebate-workbench"></a>使用回扣工作台處理交易

您可以使用 *回扣工作台* 同時處理多個交易，而非處理特定的交易或交易行。 您可以選擇性地套用記錄篩選條件和/或設定週期性排程。 您不必選擇任何資料列。 系統將處理所有符合您所設定日期與篩選條件需求的行項。

若要使用回扣工作台處理延遲，請執行以下步驟。

1. 移至 **回扣管理 \> 回扣管理交易 \> 回扣工作台**。
1. 在動作窗格上，在 **回扣工作台** 索引標籤的 **處理** 群組中，選擇以下命令之一：

    - **處理 \> 準備金** – 為每個相關交易行準備一組應計項目，但不過帳應計項目。
    - **處理 \> 回扣管理** – 處理一系列可為每個交易行提供回扣值的交易。
    - **處理 \> 沖銷** – 針對各回扣交易與指定期間的每個來源交易，處理已過帳的準備金與回扣管理之間的差異。

1. 在 **回扣管理** 對話方塊的 **期間** 區段中，設定 **開始日期** 與 **結束日期** 欄位，以定義計算的日期範圍。
1. 在 **保證期間** 區段中設定 **開始日期** 與 **結束日期** 欄位，為計算的保證定義日期範圍。
1. 在 **要包括的記錄** FastTab 上，您可以設定篩選條件以限制批次作業將處理的交易集。 這些設定會以與針對其他類型批次作業運作相同的方式運作。
1. 於 **在背景執行** FastTab 上，您可以視需要設定批次處理與排程選項。 這些設定會以與針對其他類型批次作業運作相同的方式運作。
1. 選擇 **確定** 以執行和/或排程計算。

## <a name="view-and-edit-rebate-management-transactions"></a>檢視與編輯回扣管理交易

當您處理一或多項交易時，系統會建立您可以查檢視的交易，或許您在過帳之前還可以編輯這些交易。

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-deals-list-page"></a>使用回扣交易清單頁面檢視與編輯回扣管理交易

若要使用回扣交易清單頁面檢視與編輯回扣管理交易，請按照以下步驟操作。

1. 請執行以下其中一個步驟：

    - 選擇要檢視其交易的交易 (例如，在 [**所有回扣管理交易** 頁面上](rebate-management-deals.md))。 在動作窗格上，在 **回扣管理交易** 索引標籤的 **交易** 群組中，視您想要檢視的交易類型，選擇 **交易** 或 **保證交易**。
    - 開啟要檢視其詳細資料的交易 (例如，在 [**所有回扣管理交易** 頁面上](rebate-management-deals.md))。 在 **回扣管理** FastTab 上，選擇要檢視其交易的交易行。 然後視您想要檢視的交易類型，在工具列上選擇 **交易** 或 **保證交易**。 (這些按鈕僅適用於 **對帳依據** 欄位設定為 *行項* 的交易。)

1. **回扣管理日期交易** 或 **回扣管理保證交易** 頁面隨即出現。 它包含一個格線，其中每一行皆代表單一回扣或保證期間的交易集合。 在格線中選擇一列，然後在動作窗格中選擇 **來源交易**，以檢視屬於該列的交易。
1. 出現的頁面會顯示一個交易清單，其中列出屬於所選資料列的所選類型的交易。 每筆交易都會視交易類型提供相關的詳細資料。 對於保證交易，您只能檢視清單。 對於其他類型的交易，您可以在此頁面上執行以下動作：

    - 若要驗證頁面上所有已索賠交易的總值，請檢視 **索賠金額** 欄位。
    - 若要檢視任何交易的更多資訊，請選擇該交易，然後選擇 **一般**、**財務維度** 或 **維度** 索引標籤。
    - 若要檢視任何適用的減少，請選擇動作窗格上的 **減少交易**。 如需詳細資訊，請參閱[回扣減少原則](rebate-reduction-principle.md)。
    - 如果您正在使用索賠流程，要將交易標記為已索賠或未索賠，請選擇相關行項，然後在動作窗格上選擇以下命令之一。 (您可在 [**回扣管理參數** 頁面](rebate-management-parameters.md)上啟用索賠流程。)

        - **設定已索賠 \> 全部** – 將所有交易標記為已索賠。
        - **設定已索賠 \> 已選擇** – 將所選的交易標記為已索賠。
        - **設定未索賠 \> 全部** – 將所有交易標記為未索賠。
        - **設定未索賠 \> 已選擇** – 將所選的交易標記為未索賠。

    - 選擇動作窗格上的 **過帳**，將所有相關行項的索賠過帳。 如果您使用的是索賠流程 (當 **回扣管理參數** 頁面上的 **使用索賠流程** 選項已啟用時)，則只會過帳標記為 **已索賠** 的行項。 若不是，則會過帳所選回扣交易的所有來源交易。 **過帳** 按鈕僅用於回扣交易。 不適用於準備金與沖銷交易。 在 **過帳** 對話方塊中，會自動設定 **開始日期** 與 **結束日期** 欄位。 設定 **過帳日期** 欄位，然後選擇 **確定**。
    - 若要調整為任何未結或未過帳交易顯示的金額，請選擇該交易，然後執行以下步驟之一：

        - 編輯 **更正金額** 欄位中的值。
        - 在動作窗格上，選擇 **設定更正**。 然後在出現的下拉式對話方塊中，在 **更正金額** 欄位中輸入一個值。

> [!NOTE]
> 如果您使用索賠流程，當您處理下一個期間時，交易清單將包含上一個過帳中的所有未索賠交易，以及所選期間的任何新交易。

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-workbench"></a>使用回扣工作台檢視與編輯回扣管理交易

若要使用回扣工作台檢視與編輯回扣管理交易，請按照以下步驟操作。

1. 移至 **回扣管理 \> 回扣管理交易 \> 回扣工作台**。
1. 將 **顯示** 欄位設定為 *未過帳*。
1. **回扣工作台** 頁面會顯示交易清單。 每筆交易都會提供相關詳細資料。 這些詳細資料會視交易類型而異。 您可以在此頁面上執行以下動作：

    - 若要檢視任何交易的更多資訊，請選擇該交易，然後選擇 **一般**、**財務維度** 或 **維度** 索引標籤。
    - 如果您使用索賠流程，您可以將交易標記為已索賠或未索賠。 選擇相關資料列，然後在動作窗格的 **回扣工作台** 索引標籤上，選擇以下命令之一。 (您在 [**回扣管理參數**](rebate-management-parameters.md)頁面上啟用索賠流程。)

        - **設定已索賠** – 將所選的交易標記為已索賠。
        - **設定未索賠** – 將所選的交易標記為未索賠。

    - 若要過帳一或多個行項的索賠，請選擇相關行項。 然後在動作窗格上，在 **回扣工作台** 索引標籤上選擇 **過帳**。 **過帳** 按鈕用於準備、回扣和沖銷交易。 在 **過帳** 對話方塊中，會自動設定 **開始日期** 與 **結束日期** 欄位。 設定 **過帳日期** 欄位，然後選擇 **確定**。
    - 若要調整為任何未結或未過帳交易顯示的金額，請選擇該交易，然後執行以下步驟之一：

        - 編輯 **更正金額** 欄位中的值。
        - 在動作窗格上，在 **回扣工作台** 索引標籤上選擇 **設定更正**。 然後在出現的下拉式對話方塊中，在 **更正金額** 欄位中輸入一個值。

> [!NOTE]
> 如果您使用索賠流程，當您處理下一個期間時，交易清單將包含上一個過帳中的所有未索賠交易，以及所選期間的任何新交易。

## <a name="post-rebates-transactions"></a>過帳回扣交易

若要過帳已處理準備金、回扣管理金額和沖銷的值，您必須執行過帳流程。 過帳流程會將準備金、回扣管理或沖銷交易標記為已過帳，並建立目標交易。 如果您不必審查目標交易，則可以設定這些交易以使其自動過帳。

### <a name="set-up-the-system-to-post-all-target-transactions-automatically"></a>設定系統以自動過帳所有目標交易

若要設定系統只要過帳準備金、回扣管理金額與沖銷產生目標交易，便會過帳所有的目標交易，請開啟 **回扣管理參數** 頁面上的 **自動過帳日記帳** 和/或 **自動過帳普通發票** 選項。 如需詳細資訊，請參閱[回扣管理參數](rebate-management-parameters.md)。

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>過帳一或多個交易其所有行項的交易

處理完相關交易後，請按照以下步驟審查並過帳為一或多個交易其所有行項產生的交易。

1. 針對您要處理的交易類型開啟適當的[回扣交易清單頁面](rebate-management-deals.md)。
1. 為您要過帳的每個交易選擇資料列 (或開啟您要過帳的交易)。
1. 在動作窗格上，在 **回扣管理交易** 索引標籤的 **產生** 群組中，選擇以下命令之一：

    - **過帳 \> 準備金** – 過帳您已建立的可用應計交易。
    - **過帳 \> 回扣管理** – 過帳您已建立的可用回扣交易。
    - **過帳 \> 沖銷** – 過帳您已建立的可用沖銷交易。

1. 在出現的對話方塊中，設定 **過帳日期** 欄位。 然後設定 **開始日期** 與 **結束日期** 欄位，以定義必須過帳的交易其日期範圍。
1. 選擇 **確定** 以過帳交易。

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>為所選的交易過帳一或多個特定交易行的交易

處理完相關交易後，請按照以下步驟審查並過帳為所選交易的一或多個特定交易行產生的交易。 此程序僅適用於 **對帳依據** 欄位設定為 *行項* 的交易。

1. 針對您要處理的交易類型開啟適當的[回扣交易清單頁面](rebate-management-deals.md)。
1. 開啟具有您想要過帳其交易的行項的交易。
1. 選擇右上角的 **行項** 索引標籤。
1. 在 **回扣管理** FastTab 上，選擇所要過帳每個交易行的資料列。
1. 在 **回扣管理** FastTab 的工具列上，選擇以下其中一個命令。 (這些命令僅適用於 **對帳依據** 設定為 *行項* 的交易。)

    - **過帳 \> 準備金** – 過帳您已建立的可用應計交易。
    - **過帳 \> 回扣管理** – 過帳您已建立的可用回扣交易。
    - **過帳 \> 沖銷** – 過帳您已建立的可用沖銷交易。

1. 在出現的對話方塊中，設定 **過帳日期** 欄位。 然後設定 **開始日期** 與 **結束日期** 欄位，以定義必須過帳的交易其日期範圍。
1. 選擇 **確定** 以過帳交易。

### <a name="post-transactions-using-a-batch-job"></a>使用批次作業過帳交易

您可以執行批次作業來同時過帳數個交易的交易，而不是過帳特定交易的交易。 您可以選擇性地套用記錄篩選條件和/或設定週期性排程。 若要使用批次作業過帳交易，請執行以下步驟。

1. 請執行以下其中一個步驟：

    - 移至 **回扣管理 \> 定期工作 \> 過帳 \> 準備金**，以過帳您已建立的可用應計交易。
    - 移至 **回扣管理 \> 定期工作 \> 過帳 \> 回扣管理**，以過帳您已建立的可用回扣交易。
    - 移至 **回扣管理 \> 定期工作 \> 過帳 \> 沖銷**，以過帳您已建立的可用沖銷交易。

1. 在出現的對話方塊中，在 **參數** FastTab 上的 **期間** 區段中，設定 **過帳日期** 欄位。 然後設定 **開始日期** 與 **結束日期** 欄位，以定義必須過帳的交易其日期範圍。
1. 在 **保證期間** 區段中設定 **開始日期** 與 **結束日期** 欄位，為必須過帳的保證定義日期範圍。
1. 在 **要包括的記錄** FastTab 上，您可以設定篩選條件以限制批次作業將處理的交易集。 這些設定會以與針對其他類型批次作業運作相同的方式運作。
1. 於 **在背景執行** FastTab 上，您可以視需要設定批次處理與排程選項。 這些設定會以與針對其他類型批次作業運作相同的方式運作。
1. 選擇 **確定** 以執行和/或排程計算。

### <a name="post-transactions-by-using-the-rebate-workbench"></a>使用回扣工作台過帳交易

在您處理準備金、回扣或沖銷交易後，請按照以下步驟使用回扣工作台來審查與過帳為所有交易的一或多個特定交易行產生的交易。

1. 移至 **回扣管理 \> 回扣管理交易 \> 回扣工作台**。
1. 在格線中，為您要過帳的每個交易行選擇資料列。 您可以選擇未過帳的準備金、回扣和/或沖銷交易。 適用於以下規則：

    - 系統也會過帳所有具有與您所選行項相同 **回扣交易編號** 值的行項。
    - 系統將不會過帳未標記為已索賠的 *回扣* 交易類型其所有行項。
    - 如果您選擇已過帳的行項，則系統將略過已過帳的行項。
    - **過帳** 按鈕僅適用於您選取的行項至少有一個未過帳時。

1. 在動作窗格的 **回扣工作台** 索引標籤上，在 **處理** 群組中選取 **過帳**。
1. 在 **過帳** 對話方塊中，設定 **過帳日期** 欄位。 系統會根據所選資料列的最早 **開始日期** 值與最晚 **結束日期** 值，自動設定 **開始日期** 與 **結束日期** 欄位。
1. 選擇 **確定** 以過帳交易。

## <a name="review-rebate-management-journals"></a><a name="review-journals"></a>審查回扣管理日記帳

您已過帳交易後，便可以審查產生的日記帳、文件或品項。 回扣和權利金的目標交易是根據在過帳設定檔與回扣輸出類型中設定的付款類型而定。 例如，如果回扣輸出設定為 *品項*，則將為客戶回扣建立銷售訂單，為廠商回扣建立採購訂單。 這些訂單可以透過目標交易檢視。 或者，如果付款設定為使用應付帳款，則將為客戶回扣建立對客戶設定的廠商其廠商發票。

### <a name="review-journals-by-using-the-rebate-deals-list-page"></a>使用回扣交易清單頁面審查日記帳

若要審查與回扣管理交易相關聯的日記帳分錄，請按照以下步驟操作。

1. 針對您要處理的交易類型開啟適當的[回扣交易清單頁面](rebate-management-deals.md)。
1. 選擇要檢查其日記帳分錄的交易。
1. 在動作窗格上，在 **回扣管理交易** 索引標籤的 **交易** 群組中，視您想要查看的交易類型，選擇 **交易** 或 **保證交易**。
1. 將 **顯示** 欄位設定為 *全部* 或 *已過帳*。
1. 尋找並選擇您要檢查的交易集合，然後在動作窗格上選擇下列按鈕之一。 (這些按鈕僅適用於所選交易集合具有相關的過帳時。)

    - **目標交易** – 審查為所選交易產生的相關日記帳及其他類型的文件。
    - **品項** – 審查所選交易產生的相關銷售訂單或採購訂單。

1. 相關日記帳、文件或品項清單隨即顯示。 若要檢視與任何日記帳、文件或品項相關的更多資訊，請選擇其資料列，然後在動作窗格上，選擇 **檢視詳細資料**。

### <a name="review-journals-by-using-the-rebate-workbench"></a>使用回扣工作台審查日記帳

若要使用回扣工作台審查日記帳，請執行以下步驟。

1. 移至 **回扣管理 \> 回扣管理交易 \> 回扣工作台**。
1. 將 **顯示** 欄位設定為 _全部_ 或 _已過帳_。
1. 尋找並選擇所要檢查的行項。 然後在動作窗格的 **回扣工作台** 索引標籤上，在 **檢視** 群組中選取 **目標交易**。 此按鈕僅適用於所選行項具有相關過帳時。
1. 相關日記帳、文件或品項清單隨即顯示。 若要檢視與任何日記帳、文件或品項相關的更多資訊，請選擇其資料列，然後在動作窗格上，選擇 **檢視詳細資料**。

## <a name="rebate-management-transactions-on-the-deduction-workbench"></a>減項工作台上的回扣管理交易

當您過帳的回扣管理交易具有以下其中一個 **付款類型** 值時，系統會為相關客戶帳戶建立客戶減項日記帳或普通發票：

- 客戶減項
- 稅務發票客戶扣除
- 貿易費用
- 報告

建立目標交易並將其過帳後，將會位於 **減項工作台** 頁面 (**銷售和行銷 \> 經銷商折讓 \> 減項 \> 減項工作台**) 上作為未結交易。 未結交易具有 *回扣管理* 的 **索賠類型** 值，且 **回扣交易編號** 值可用於啟用可追溯性。 此日期會設定為回扣管理目標交易的過期日期。 若要使用減項工作台將未結交易結算至相同客戶帳戶的現有減項，請選擇動作窗格上的 **維護 \> 比對**。

如需詳細資訊，請參閱[使用減項工作台管理減項](deduction-workbench.md)。

## <a name="purge-unposted-transactions"></a>清除未過帳的交易

在您處理完準備金、回扣或沖銷交易後，請按照以下步驟清除所選的未過帳交易。

1. 移至 **回扣管理 \> 回扣管理交易 \> 回扣工作台**。
2. 將 **顯示** 欄位設定為 *未過帳*。
3. 尋找並選取要刪除的交易。 接著在動作窗格的 **回扣工作台** 索引標籤上，在 **處理** 群組中選擇 **清除**。
4. 選擇 **確定** 以刪除未過帳交易。

## <a name="cancel-a-posted-provision"></a>取消已過帳的準備金

在您已處理準備金並將其過帳後，請按照以下步驟取消已過帳的準備金交易。

1. 移至 **回扣管理 \> 回扣管理交易 \> 回扣工作台**。
2. 將 **顯示** 欄位設定為 *已過帳*。
3. 尋找並選取要取消的準備金交易。 接著在動作窗格的 **回扣工作台** 索引標籤上，在 **處理** 群組中選擇 **取消準備金**。
4. 選擇 **確定** 以註銷交易。

這些準備金註銷也將在相關的[回扣管理日記帳](#review-journals)中顯示。