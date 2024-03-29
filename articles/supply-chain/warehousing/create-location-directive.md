---
title: 使用位置指令
description: 本主題介紹如何使用位置指令。 位置指令是使用者定義的規則，可以幫助識別移動庫存的挑選和放置位置。
author: Mirzaab
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 84ff0a466c037db05aecaff14aa2e17990ce8799
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449958"
---
# <a name="work-with-location-directives"></a>使用位置指令

[!include [banner](../includes/banner.md)]

位置指令是幫助識別庫存移動的揀選和放置位置的規則。 例如在銷售訂單交易中，位置指令決定將在哪裡揀貨，以及將揀貨放在哪裡。 位置指令由標題和相關行組成。 它們是為特定的 *工單類型* 所創建。

> [!NOTE]
> 本主題適用於 **倉庫管理** 模組中的功能。 不適用於[庫存管理](../inventory/inventory-home-page.md)模組中的功能。

您可以使用位置指令執行以下任務：

- 放置接收到的項目。
- 為傳出的交易挑選和暫存項目。
- 為生產挑選和放置原材料。
- 補貨各個位置。

## <a name="prerequisites"></a>先決條件

在創建位置指令之前，您必須按照以下步驟確保具備先決條件。

1. 確保所需的授權金鑰已打開。 前往 **系統管理\>設定\>授權設定**，展開 **貿易** 授權金鑰，然後選擇 **倉儲和運輸管理** 設定金鑰。 備註﹔此步驟需要管理員訪問權限。
1. 前往 **倉庫管理 \> 設定 \> 倉庫 \> 倉庫**。
1. 創建倉庫。
1. 在 **倉庫** FastTab，將 **使用倉庫管理流程** 選項設定為 *是*。
1. 創建位置、位置類型、位置設定檔和位置格式。 如需詳細資訊，請參閱[在啟用 WMS 的倉庫中設定位置](./tasks/configure-locations-wms-enabled-warehouse.md)。
1. 創建地點、區域和區域群組。 如需詳細資訊，請參閱[倉庫設定](../../commerce/channels-setup-warehouse.md)和[在啟用 WMS 的倉庫中設定位置](./tasks/configure-locations-wms-enabled-warehouse.md)。

## <a name="work-order-types-for-location-directives"></a>位置指令的工單類型

位置指令中許多可設定的欄位，對所有工單類型都是通用的。 但是，其他特殊欄位，針對特定工單類型。

![位置指令工單類型。](media/Location_Directives_Work_Order_Types.png "位置指令工單類型")

> [!NOTE]
> 有兩種工單類型僅供系統使用，分別為 *取消的工作* 和 *週期盤點*。 因此，無法為這些工單類型創建位置指令。

以下小節中的表格，列出設定位置指令時可用的通用欄位，和特定工單類型欄位。

### <a name="fields-that-are-common-to-all-work-order-types"></a>所有工單類型通用的欄位

下表列出所有工單類型通用的欄位。

| FastTab | 欄位 |
|---|---|
| 位置指令 | 工作類型 |
| 位置指令 | 網站 |
| 位置指令 | 倉庫 |
| 位置指令 | 指令代碼 |
| 位置指令 | 多個 SKU |
| 行 | 序號 |
| 行 | 起始數量 |
| 行 | 最終數量 |
| 行 | 單位 |
| 行 | 查找數量 |
| 行 | 單位限制 |
| 行 | 四捨五入到單位 |
| 行 | 查找包裝數量 |
| 行 | 允許拆分 |
| 位置指令動作 | 序號 |
| 位置指令動作 | 姓名 |
| 位置指令動作 | 固定位置使用 |
| 位置指令動作 | 允許負庫存 |
| 位置指令動作 | 批次啟用 |
| 位置指令動作 | 策略 |

### <a name="fields-that-are-specific-to-work-order-types"></a><a name="fields-specific-types"></a>特定工作的特殊欄位

下表列出特定工單類型的特殊欄位。

| FastTab | 欄位 | 工單類型 |
|---|---|---|
| 位置指令 | 位置依據 | 購買訂單 |
| 位置指令 | 可用的處置代碼 | 購買訂單 |
| 位置指令 | 處置代碼 | 購買訂單 |
| 位置指令 | 可用的處置代碼 | 成品入庫 |
| 位置指令 | 處置代碼 | 成品入庫 |
| 位置指令 | 可用的處置代碼 | 退回訂單 |
| 位置指令 | 處置代碼 | 退回訂單 |
| 位置指令 | 可用的處置代碼 | 看板收起 |
| 位置指令 | 可用的處置代碼 | 看板挑選 |
| 行 | 即時補貨範本 | 銷售訂單 |
| 行 | 即時補貨範本 | 原料挑選 |
| 行 | 即時補貨範本 | 傳輸問題 |
| 行 | 即時補貨範本 | 看板挑選 |

## <a name="open-the-location-directives-page"></a>打開位置指令頁面

若要打開 **位置指令** 頁面，請前往 **倉庫管理 \> 設定 \> 位置指令**。

從那裡，您可以使用動作窗格上的命令查看、創建和編輯您的位置指令。 有關如何使用頁面上所有可用欄位的資訊，請參閱本主題的其餘部分。

## <a name="action-pane"></a>動作窗格

**位置指令** 上的動作窗格頁面，包含可用於創建、編輯和刪除指令的按鈕 (**編輯**、**新增** 和 **刪除**)。 它還包含以下按鈕，可讓您調整位置指令的處理順序，並設定可定義位置指令應用條件的查詢：

- **上移** – 向上移動選定的位置指令順序。 例如，您可以將其從序列號 4 移動到序列號 3。
- **下移** – 向下移動選定的位置指令順序。 例如，您可以將其從序列號 4 移動到序列號 5。
- **編輯查詢** – 打開一個對話框，您可以在其中定義所選位置指令的處理條件。 例如，您可能希望它僅適用於特定倉庫。

## <a name="location-directives-header"></a>位置指令標題

位置指令標題包括以下欄位，用於位置指令的序列號和描述性名稱的：

- **序列號** – 此欄位代表系統嘗試將每個位置指令應用於所選工單類型的順序。 會先應用較小的數字。 您可以使用動作窗格上的 **上移** 和 **下移** 按鈕變更順序。
- **名稱** – 輸入位置指令的描述性名稱。 此名稱應有助於識別指令的一般用途。 例如，輸入 *從 24 倉庫挑選的銷售訂單*。

## <a name="location-directives-fasttab"></a>位置指令 FastTab

**位置指令** 上的欄位，FastTab 屬於特定於在 **工單類型** 列表窗格中的字段。

- **工作類型** – 選擇必須執行的工作類型。 可用值取決於您在 **工單類型** 欄位中所選的庫存交易。 選擇下列其中一個值：

    - **放置** – 位置指令將嘗試找到最理想的位置，來放置或查找從接收、生產或庫存調整進入系統的庫存。 它還可用於定義放置到暫時位置，或是放置到最終艙門的運輸位置。
    - **挑選** – 位置指令將嘗試找到最理想的位置來實際保留庫存 (即創建工作)。 即使工作沒有完成，也可以完成挑選 (代表可以關閉挑選工作線)。 使用者可以完成實物挑選。 在系統中，該動作是挑選步驟。 然後，使用者可以從行動裝置上取消並稍後再完成工作。 但是，當最終放置完成時，首先會關閉工作標題。

    > [!IMPORTANT]
    > **工作類型** 中的其他欄位的值，與位置指令無關。 會出現只是因為沒有篩選該欄位以匹配選定的工單類型。

- **地點** – 此欄位是強制性的，因為位置指令必須能夠確定其有效的位置和倉庫。
- **倉庫** – 此欄位是強制性的，因為位置指令必須能夠確定其有效的位置和倉庫。
- **指令代碼** – 選擇與工作範本或補貨範本關聯的指令代碼。 在 **指令代碼** 頁面，您可以創建將工作範本或補貨範本連接到位置指令的新代碼。 指令代碼還可以建立任何工作範本行和位置指令 (例如艙門或暫時位置) 之間的連結。

    > [!TIP]
    > 如果設定指令代碼，系統在產生工作時，將不會按序列編號搜尋位置指令。 相反，將通過指令代碼進行搜索。 通過這種方式，您可以更具體地了解用於工作範本中特定步驟的位置指令，例如暫存材料的步驟。

- **多個 SKU** – 將此選項設定為 *是* 允許在一個位置使用多個庫存單位 (SKU)。 例如，必須為艙門位置啟用多個 SKU。 如果您啟用多個 SKU，您的放置位置將按預期於工作中指定。 但是，放置位置只能處理一個多項目放置 (如果工作包括多個不同 SKU，則必須經過挑選和放置)。 無法處理單一 SKU 的放置。 如果您將此選項設定為 *否*，則只有當您放置一種 SKU 時，才會指定您的放置位置。

    > [!IMPORTANT]
    > 為了能夠同時進行多項目放置和單一 SKU 放置，您必須指定兩行，且具有相同結構和設定，但您必須將 **多個 SKU** 選項的其中一行設定為 *是*，另一行設定為 *否*。 因此，對於放置作業，即使您不必區分工作 ID 上的單個 SKU 和多個 SKU，也必須有兩個相同的位置指令。 通常，如果您不設定這兩個位置指令，應用的位置指令會產生意外的業務流程位置。 如果您需要處理包含多個 SKU 的訂單，對於有 *挑選***工作類型** 的位置指令，您必須使用類似的設定。

    使用工作行的 **多個 SKU** 選項，處理多個項目編號。 (工作詳細資料中的項目編號將是空白，並且在 Warehouse Management 行動應用程式的處理頁面上會顯示為 **多個**。)

    在典型的範例場景中，會設定一個工作範本，使其具有多個挑選/放置配對。 在這種情況下，您可能希望以 *放置***工作類型** 行來搜尋特定暫存位置。

    > [!NOTE]
    > 如果 **多個 SKU** 選項設定為 *是*，則您不能選擇動作窗格上的 **編輯查詢**，因為當有多個項目時，查詢無法在項目級別上進行評估。 為了確保選擇所需的位置指令，請使用 **指令代碼** 欄位來引導位置指令的選擇，該指令代碼與放置行關聯，由工作範本所指派。

    除非您總是使用單個項目或混合項目進行作業，否則必須為 *放置* 工作類型定義兩個位置：一個是將 **多個 SKU** 選項設定為 *是*，另一個設定為 *否*。

- **適用處置代碼** – 指定位置指令的處置代碼是否必須與接收項目時應用的處置代碼匹配，或者是否可以基於任何處置代碼選擇位置指令。 如果您選擇 *完全符合*，並且 **處置代碼** 欄位為空白，則此位置指令僅會考慮空白處置代碼。

    > [!NOTE]
    > 此欄位僅適用於允許補貨的工單類型。 如需完整列表，請參閱本主題前面部分的[特定工單類型欄位](#fields-specific-types)。

- **查找依據** – 指定入庫數量應為牌照上的整體數量，還是逐項入庫。 使用此欄位，有助於確保將牌照上的所有內容放在同一個位置，並且系統不建議您將內容拆分到多個位置，以便 **ASN** (牌照領取)、**混合牌照** 接收，和 **叢集** 進行接收過程。 (**叢集** 需要接收過程中開啟[叢集放置功能](putaway-clusters.md)功能。) 根據您所選的值，位置指令查詢、行和位置指令動作的行為會有所不同。 **行** FastTab 僅會在 **查找依據** 設定為 *項目* 時使用。

    > [!NOTE]
    > 此欄位僅適用於允許補貨的工單類型。 如需完整列表，請參閱[特定工單類型欄位](#fields-specific-types)的部分。

- **處置代碼** – 此欄位用於 *訂購單*、*成品入庫* 或 *退貨單*，及 *放置* 工作類型的工單類型，用於位置指令。 根據工人在 Warehouse Management 行動應用程式中所選的處置代碼，來指導使用特定位置指令的流程。 例如，您可以在退回庫存之前，直接將退回的貨物送到檢驗地點。 處置代碼可以連結到庫存狀態。 通過這種方式，可於接收過程中更改庫存狀態。 例如，您有一個處置代碼 *品質保證*，可將庫存狀態設定為 *品質保證*。 然後，您可以使用單獨的位置指令，將該庫存移動到隔離位置。

    > [!NOTE]
    > 此欄位僅適用於允許補貨的工單類型。 如需完整列表，請參閱[特定工單類型欄位](#fields-specific-types)的部分。

## <a name="lines-fasttab"></a>FastTab 行

使用 FastTab **行**，為特定 **位置指令操作** FastTab 的相關動作建立應用條件。 對每一行，您可以指定應用的最小數量和最大數量。 您還可以指定應用於特定庫存單位的特定動作。

- **序列號** – 為所選的工作類型輸入每個位置指令處理的順序。 您可以視需要使用工具列上的 **上移** 和 **下移** 按鈕變更順序。
- **起始數量** – 指定該行適用的數量範圍的起點。 指定在 **單位** 欄位中所選的測量單位數量。
- **最終數量** – 指定該行適用的數量範圍的終點。 指定在 **單位** 欄位中所選的測量單位數量。
- **單位** – 選擇項目的測量單位。 您可以指定該指令應適用的最小數量和最大數量，而且您可以指定該指令應適用於特定的庫存單位。 **單位** 欄位 *只能* 用於數量評估。 為了確定位置指令行是否適用，系統會使用在該行指定的單位數量。 每當達到位置指令行時，系統都會嘗試將需求單位轉換為行中指定的單位。 如果測量單位轉換不存在，系統將轉到下一行。
- **查找數量** – 此欄位僅在於倉庫中嘗試放置或查找項目時使用。 (因此，它僅適用於設定為 *放置* 的 **工作類型** 欄位)。 從下方選擇一個值，以指定評估數量的範圍是否在 **起始數量** 到 **最終數量** 之間：

    - **牌照數量** – 使用正在接收中牌照上的數量。
    - **統一數量** – 交易期間使用的數量。 例如，您在倉庫中收到數量為 1,000 的貨物，並將其分解為 10 個牌照，每個牌照的數量為 100。 在這種情況下，您可以使用 1,000 個項目的數量，而不是 100 的牌照數量。
    - **剩餘數量** – 正在處理的訂購單行中，還必須收到的數量。
    - **預期數量** – 訂購單行中應該收到的總數量，無論是否已經收過。

- **單位限制** – 此核取方塊可讓您將位置指令行指定到一個或多個測量單位。 若勾選，則限制測量單位，位置指令行只會考慮有效的挑選條件。 此功能僅適用於 **工作類型** 欄位設定為 *挑選* 的位置指令。

    例如，當您要保留數量時，您只想從一組特定位置中保留數個托盤數量。 在這種情況下，指令行會將順序限制為托盤，這樣位置指令就不會選到任何少於一個托盤的數量。

    請注意，**單位限制** 核取方塊，無法控制不同工作行之間的單位。 單位限制僅適用於通過單位序列群組提供的單位。 例如，一個項目與單位序列群組關聯，而該單元序列群組中，包含 *托盤* 單位和 *件* 單位。 測量單位的定義為 1 個托盤 = 100 件，則位置指令使用 **單位限制** 的功能僅適用於托盤。 此外，工作範本還將創建工作標題的數量限制為 50 件。 在這種情況下，將創建 50 件工作行。 要指定測量單位的限制，請遵循以下步驟：

    1. 在 **行** FastTab 上，選擇工具列上的 **單位限制**。 (此按鈕只有在您選擇 **單位限制** 核取方塊，然後選擇 **儲存**，之後方可使用。)
    1. 在 **單位限制** 頁面上的 **單位** 欄位，選擇挑選和放置過程中，您要限制的測量單位。

- **四捨五入到單位** – 此欄位與 **單位限制** 核取方塊一併使用。 例如，如果選擇了位置指令行上的 **單位限制** 和 **四捨五入到單位**，由指令產生的原物料挑選工作，應四捨五入到 **單位限制** 頁面中指定的承辦單位的倍數。

    > [!NOTE]
    > **四捨五入到單位** 設定，僅適用於 *原物料挑選* 工單類型，並且僅適用於 **工作類型** 欄位設定為 *挑選* 的位置指令。

- **查找包裝數量** – 如果您在銷售訂單、轉移訂單或生產訂單上指定包裝數量，此復選框可讓您限制系統，使其只能選擇至少具有該包裝數量的位置。

    > [!NOTE]
    > 此功能僅適用於 *挑選* 類型的位置指令。

- **允許拆分** – 指定位置指令是否可以將接收或保留的數量，拆分到多個倉庫位置，或者整體數量是否必須位於單個位置，或從單個位置保留才能創建工作。
- **立即補貨範本** – 使用此欄位創建連接到補貨範本，以便在沒有分配項目時立即開始補貨。 如果您將此欄位留空，則在處理完所有位置指令行之前，不會開始補貨。

    > [!NOTE]
    > 此欄位僅適用於允許補貨的工單類型。 如需完整列表，請參閱[特定工單類型欄位](#fields-specific-types)的部分。

## <a name="location-directive-actions-fasttab"></a>位置指令動作 FastTab

您可以為每一行定義多個位置指令動作。 序號再次用於決定評估動作的順序。 在此級別，您可以設置查詢來定義如何找到倉庫中的最佳位置。 您還可以使用預定義的 **策略** 值以找到最佳位置。

- **序列號** – 此欄位顯示所選工作類型處理動作的順序。 您可以使用工具列上的 **上移** 和 **下移** 按鈕變更順序。
- **名稱** – 輸入位置指令動作的名稱。 務必具體，以便從名稱中清楚地看出所執行的動作。
- **固定位置使用** – 指定位置指令應考慮的位置。 選擇下列其中一個值：

    - **固定和非固定位置** – 位置指令將考慮所有位置。
    - **僅產品的固定位置** – 位置指令將僅考慮產品的固定位置。
    - **僅產品變形的固定位置** – 位置指令將僅考慮產品變形的固定位置。

- **允許負庫存** – 選擇此核取方塊，允許在位置指令中的指定倉庫位置出現負庫存。
- **啟用批次** – 選擇此核取方塊，對啟用批次處理的項目使用批次處理策略。 對於使用位置指令查找位置，以從中挑選批次編號追蹤項目的流程，選擇此核取方塊非常重要。 透過這種方式，可以搜尋包含批次編號追蹤項目的位置。 如果選擇此核取方塊，並且 **策略** 欄位設定為 *無*，則系統將移動到下一個動作行。
- **策略** – 若要更輕鬆快速地定義個位置指令行之間關聯的動作，您可以選擇以下預定義策略之一：

    - **無** – 不會使用任何策略。
    - **匹配包裝數量** – 此策略會驗證挑選地點是否具有指定的包裝數量。 此策略僅在 **工作類型** 欄位設定為 *挑選* 時有效。
    - **合併** – 當類似的項目可合併時，此策略會將項目合併到特定位置。 此策略僅在 **工作類型** 欄位設定為 *放置* 時有效。 通常會再第一行動做設定嘗試合併放置，在第二行動作，嘗試不合併放置。 貨物合併可以讓後續挑選更有效率。
    - **FEFO 批次保留** – 此策略會使用先到先出 (FEFO) 批次保留。 透過使用批次到期日，和分配批次保留以使用此策略。 您只能將此策略用於啟用批次的項目。 此策略僅在 **工作類型** 欄位設定為 *挑選* 時有效。
    - **四捨五入到完整的 LP 和 FEFO 批次** – 此策略結合 *FEFO 批次保留* 和 *四捨五入到完整的 LP* 策略的要素。 此策略僅對批次啟用的項目，以及工作類型為 *挑選* 的位置指令有效。 必須啟用批次的行，才能使用 *FEFO 批量預訂* 策略，而 *四捨五入到完整的 LP* 的策略只適用於補貨。 如果將此策略與位置庫存限制一配置，則可能會導致選定的放置工作位置超載，並忽略庫存限制。
    - **四捨五入到完整的 LP** – 此策略用於對庫存數量進行四捨五入，使其與分配給必須揀貨的項目的牌照數量相匹配。 您只能將此策略用於 *挑選* 類型的補貨位置指令。 如果將此策略與位置庫存限制一配置，則可能會導致選定的放置工作位置超載，並忽略庫存限制。
    - **牌照引導** – 當您將訂單下達到倉庫，創建挑選工作時，可使用此策略。 您可以將此方法用於多個牌照。 此策略會針對與傳送訂單行相關，持有請求牌照的位置，進行保留並創建挑選工作。 但是，如果無法完成這些動作，但您仍想創建挑選工作，則應該回到位置指令動作，使用另一種策略。 根據您的業務流程要求，您可能需要在另一個區域的另一個倉庫搜尋庫存。
    - **清空沒有工作的位置** – 可以使用此策略查找空的位置。 如果位置沒有實際的庫存，也沒有可預期的傳入工作，則應視為空的位置。 您只能將此策略用於 *放置* 類型的位置指令。
    - **位置帳齡先進先出** – 根據庫存進入倉庫的日期，使用先進先出 (FIFO) 策略運送批次追蹤項目和非批次追蹤項目。 此功能對於非批次追蹤庫存特別有用，在這些庫存中沒有可用於分類的到期日期。 先進先出策略查找包含最早帳齡日期的位置，然後根據該帳齡日期分配挑選。
    - **位置帳齡後進先出** – 根據庫存進入倉庫的日期，使用後進先出 (LIFO) 策略運送批次追蹤項目和非批次追蹤項目。 此功能對於非批次追蹤庫存特別有用，在這些庫存中沒有可用於分類的到期日期。 後進先出策略查找包含最近帳齡日期的位置，然後根據該帳齡日期分配挑選。

## <a name="example-using-location-directives"></a>範例：使用位置指令

在此範例中，訂購單程序的位置指令，必須在倉庫中找到可用容量，以儲存剛剛在收貨碼頭。 首先，您需要通過合併現有的庫存，來找到倉庫內的可用容量。 如果無法合併，則需要找到一個空位置。

對於這種情況，您必須定義兩個位置指令動作。 序列中的第一個動作必須使用 *合併* 策略，第二個應該使用 *沒有輸入工作的空位* 策略。 除非您定義第三個動作來處理溢出場景，否則當倉庫中沒有更多容量時可能會出現兩種結果：即使未定義位置也可以創建工作，或者工作創建過程可能會失敗。 結果由上的設置決定 **位置指令失敗** 頁面，您可以在其中選擇是否選擇 **停止位置指令失敗的工作** 每個工單類型的選項。

## <a name="next-step"></a>下一步

創建位置指令後，您可以將每個指令代碼與創建工作的工作範本代碼建立關聯。 如需更多詳細資訊，請參閱[使用工作模板和位置指令控制倉庫工作](./control-warehouse-location-directives.md)。

## <a name="additional-resources"></a>其他資源

- 影片：[倉庫管理設定深入探討](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- 幫助主題：[使用工作範本和位置指令控制倉庫工作](control-warehouse-location-directives.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]