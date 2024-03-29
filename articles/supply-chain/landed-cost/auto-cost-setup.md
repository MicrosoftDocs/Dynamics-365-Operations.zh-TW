---
title: 自動成本設定
description: 本主題說明如何為各種入庫航程層級設定成本規則。 根據這些規則，系統計算成本並自動新增。 因此，使用者不必手動新增成本。
author: sherry-zheng
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostAutoSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0fe795127300ac99c3f5ee65cb1f6e0841ad4d95
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448842"
---
# <a name="auto-costs-setup"></a>自動成本設定

[!include [banner](../../includes/banner.md)]

您可以使用 **自動成本** 頁面為各種成本領域 (例如航程、運輸貨櫃、貨櫃組、訂購單、品項或調撥訂單明細) 設定成本規則。 根據規則以及使用者在任一成本領域建立記錄時選擇的欄位，系統會計算成本並自動新增。 因此，使用者不必手動新增成本。

要處理自動成本，請移至 **到岸成本\>成本設定\>自動成本**。 接著依照本主題其他部分所述，設定您的自動成本規則。

## <a name="work-with-cost-areas"></a>使用成本領域

自動成本的運作方式類似於貿易合約或自動雜費。 每個自動成本記錄都屬於一個特定的成本等級。 請使用 **自動成本** 頁面中清單窗格的 **成本領域** 欄位，選擇您要使用的成本領域。 目前選取的成本領域，將在清單窗格上顯示自動成本。 您建立的任何自動成本都將屬於目前選取的成本領域。

成本領域使系統能夠在成本領域中跨訂購單明細分攤成本。 例如，一個運送貨櫃的成本會將其值分配給該運送貨櫃中的所有產品。 如果有兩個或多個貨櫃，可以為每個貨櫃指定相同的成本類型。 因此，貨櫃類型可用於查找正確的自動成本。

## <a name="buttons-on-the-action-pane"></a>動作窗格上的按鈕

下表說明了在 **自動成本** 頁面中，動作窗格裡的可用按鈕。

| 按鈕 | 描述 |
|---|---|
| 編輯 | 編輯現有的自動成本。 |
| 新產品 | 建立自動成本。 |
| 刪除 | 刪除自動成本。 |
| 複製自 | 基於現有記錄建立新的自動成本記錄。 然後您可以自由編輯新記錄。 此按鈕可幫助您快速建立新的自動成本。 |
| 顯示維度 | 打開一個對話方塊，為正在查看成本交易記錄，選取要顯示的庫存維度。 如果清除核取方塊，成本交易記錄上將顯示更少的庫存維度。 因此，將顯示較少的交易細節。 如果自動成本有指定庫存維度，則當指定的庫存維度用於在航程中的品項時，才會套用自動成本。 |

## <a name="settings-on-the-header"></a>標頭上的設定

標頭部分中的設定組合決定了何時以及如何將特定的自動成本新增到航程中。 僅在自動成本的詳細資料與該成本領域標頭中的詳細資料相符時，才會將自動成本應用於航次、運送貨櫃或貨櫃組。 所有相符的自動成本的總和決定了航程的預估到岸成本。 這筆費用由船舶或航程中的所有品項分攤。

下表說明了可以出現在標頭部分的所有欄位。 但是，可用的指定欄位會有所不同，具體取決於目前選取的成本領域和顯示維度。

| 欄位 | 描述 |
|---|---|
| **客戶代碼** | <p>選擇下列其中一個值：</p><ul><li>**資歷表**–成本規則僅適用於特定供應商。</li><li>**群組**–成本規則適用於特定供應商群組。 系統會尋找與供應商記錄相關聯的[供應商成本類型群組](costing-parameters-setup.md)。</li><li>**全部**–成本規則適用於所有供應商。 |
| **運輸公司** | 選取成本規則套用到的供應商或供應商群組。 此欄位僅在您在 **科目代碼** 欄位裡面選擇 *資料表* 或 *群組* 時可用。 |
| **報關行** | 選取成本規則套用到的供應商或供應商群組。 此欄位僅在您在 **科目代碼** 欄位裡面選擇 *資料表* 或 *群組* 時可用。 |
| **品項代碼** | <p>選擇下列其中一個值：</p><ul><li>**資料表**–成本規則僅適用於特定品項。</li><li>**群組**–成本規則適用於特定品項群組。 系統會尋找與品項記錄相關聯的[品項成本類型群組](costing-parameters-setup.md)。</li><li>**全部**–成本規則適用於所有品項。|
| **品項關係** | 選取成本規則適用的品項或品項群組。 此欄位僅在您在 **品項代碼** 欄位裡面選擇 *資料表* 或 *群組* 時可用。 |
| **交貨模式** | 選擇成本規則適用的交貨模式 (例如空運或海運)。 |
| **貨櫃類型** | 裝運貨物的貨櫃類型。 僅當自動成本設定的貨櫃類型與航程的貨櫃類型相符時，才能將自動成本套用在航程。 |
| **起始港口** 和 **抵達港口** | 航程的起點 (「起始」)港口和目的地(「抵達」)港口。 (因為航程可能會在多個港口停靠，一些運送貨櫃可能有不同的抵達港口。) 只有當自動成本設設定中的「起始」和「抵達」港口與航程的「起始」和「抵達」港口相符時，才能套用自動成本。 |
| **自動成本編號** | 自動成本規則的唯一識別碼。 該欄位的值是以 **到岸成本參數** 頁面上設定的編號規則來自動生成。 |
| **庫存維度** | 某些成本領域允許您在標頭中包含一個或多個品項維度 (例如尺寸、顏色、倉庫和批次編號)。 在「動作窗格」上選取 **顯示維度**，以選擇應包含的維度。 |

## <a name="settings-on-the-lines-fasttab"></a>快速索引標籤上的設定

在 **明細** 快速索引標籤，新增一列，指定在航程的訂購單明細上套用成本時可以使用的每種貨幣。 

對於品項和訂購單，系統會將每個訂購單明細上的貨幣比對 **明細** 快速索引標籤上指定的貨幣。 它將僅為相符明細或品項套用設定好的成本值。 如果沒有為明細或品項的貨幣設置明細，則自動成本不會套用在該明細或品項。

對於其他類型的成本範領域，**明細** 快速索引標籤上的明細，將套用在標頭上建立的值相符的每個航程、運輸貨櫃、貨櫃組或調撥單明細。

下表說明了可以出現在每一個明細的所有欄位。 但是，可用的指定欄位會有所不同，具體取決於目前選取的成本領域。

| 欄位 | 描述 |
|---|---|
| **貨幣** | 選取該明細套用的貨幣。 該貨幣與訂購單相關。 當系統試圖查找套用在航程及其航程明細的自動成本時，它將選擇與訂購單具有相同貨幣的明細。 此欄位僅在 **成本領域** 欄位設定為 *訂購單* 或 *品項*。 |
| **成本類型代碼** | 成本類型。 |
| **分攤方式** | <p>將成本分配到明細的方法。 可以使用以下選項：</p><ul><li><p>**百分比**–**成本價值** 欄位的值是套用於商品總價值的百分比。</p><p>例如，如果 **成本價值** 欄位設定為 *10*，商品總價值為 $800，成本價值為$80 (= $800 × 10%)。</p></li><li>**數量**– 費用將根據貨物數量分攤。</li><li>**總值**– 費用將根據貨物總價值分攤。</li><li>**體積**– 費用將根據貨物體積分攤。 體積在品項型錄上指定。</li><li>**重量**– 費用將根據貨物重量分攤。 重量在品項型錄上指定。</li><li>**體積測量**– 費用將根據貨物體積測量分攤。</li><li><p>**測量**–該選項允許在 **到岸成本** 模組指定測量。 不知道貨物的單個體積或重量的組織經常使用它，但需要比 **總量** 和 **數量** 選項更精準的分攤。 貨運業者或代理商將向組織提供品項層級或訂購單層級的重量或立方測量值。</p><p>例如，海運等於 $900。 品項 A 的重量為 800 公斤 (kg)，體積為 2 立方公尺 (m³)。 品項B 的重量為 100 公斤 (kg)，體積為 1 立方公尺 (m³)。 以下是按重量分配成本時的結果：</p><ul><li>品項 A = $800</li><li>品項 B = $100</li></ul><p>以下是按體積分配成本時的結果：</p><ul><li>品項 A = $600</li><li>品項 B = $300</li></ul><p>**請注意：** 當 **分攤方式** 欄位設為 *測量*，系統使用在成本領域 (運送貨櫃) 和明細輸入的測量值。 這些測量結果總和不一定要等於預期的總數。 但是，如果您要求它們的總和等於預期的總數，您可以通過使用統計數據來檢閱總測量值進行檢查。 貨件或貨櫃層級的測量提示設定和自動更新測量可在航程標頭上進行設定。</p></li></ul> |
| **開始日期** | 如果有日期範圍，請指定成本計算日期範圍何時開始。 此日期是套用自動成本的第一天。 |
| **結束日期** | 如果有日期範圍，請指定成本計算日期範圍何時結束。 此日期是套用自動成本的最後一天。 |
| **類別** | <p>選取要套用在計算成本上的方法。 可以使用以下選項：</p><ul><li>**固定**–成本將根據固定的方式分攤。</li><li>**件**–成本將分配到每件上。 因此，分攤方法不會被使用。</li><li>**百分比**–將增加多少百分比的貨物價值。 因此，分攤方法不會被使用。</li><li>**比例**–如果存在數量拆分，請選擇此選項。 此明細的 **分攤方式** 欄位必須設定為 *測量*。</li><ul> |
| **按數量拆分** | <p>勾選此核取方塊，以使 **明細** 快速索引標籤上的 **按數量拆分** 按鈕可用。 數量拆分使成本能夠被拆分並且不同的成本可以依航程訂購單明細上的數量變化。 當交付方式為空運時，通常會使用此功能。 此明細的 **分類** 欄位必須設定為 *比例*。</p><p>數量與 **分攤方式** 欄位選取的選項有關。 成本值總和將不超過 **成本價值** 欄位輸入的數字。<p>例如，45–100 kg 的數量根據測量(如 kg/m³) 產生 $6.00 的費用。 超過 100 kg 的數量根據測量(如 kg/m³) 產生 $5.50 的費用。</p> |
| **成本值** | 輸入成本值。 |
| **成本貨幣代碼** | 選取成本的貨幣。 |
| **品項銷售稅群組** | 選擇成本的稅碼。 |
| **最低成本** | <p>此欄位僅適用於已勾選 **按數量拆分** 核取方塊。 如果測量結果未達到此值，則取最小值，而不管在 **按數量拆分** 頁面已指定的成本。<p>例如，0–45 kg 的數量根據測量(如 kg/m³) 產生 $6 的費用。 46–100 kg 的數量根據測量(如 kg/m³) 產生 $5.50 的費用。 如果運送 2 公斤，則按數量拆分將建立 $12 的成本值。 但是，如果 **最低成本** 欄位設定為 *100 美元*，最終成本將為 100 美元。</p> |
| **彙總值** | 選取此核取方塊以允許用戶將此成本從運送貨櫃等級移至航程等級。 在這種情況下，可以在運送貨櫃等級自動計算成本。 但是，它們也可以組合並分攤給航程中所有貨櫃中的所有品項，而非單個運送貨櫃中的所有品項。 |
| **連結成本類型** | <p>藉由在 **成本類型代碼** 指定您想要連接的明細的值，把目前明細連結到在相同自動成本記錄的另一個明細。 此功能僅在目前明細的 **類別** 欄位設定為 *百分比* 時可用。 在當前明細連結到另一段明細時，當前明細的費用將建立在另一段明細的費用上。</p><p>例如，運費為 $1,000，您希望燃油附加費為運費的 10%。 在這種情況下，明細中 **類別** 值必須為 *百分比*；**成本值** 的值為 *10%*；**連結成本類型** 的值為 *貨運*。</p> |
| **值調整** 和 **調整總額** | <p>使用這些欄位來調整各種百分比值的值和總數。 它們僅在 **成本領域** 欄位設定為 *品項* 時可用。</p><p>可以為品項中的不同組件設定不同的成本計算。 品項的一個組件可以與其他組件有不同的成本百分比。 這種方法常被用在必須以不同的費率對貨物的特定部分進行估價。</p><p>例如，手錶的關稅按兩種稅率計算：手錶的一個組件的稅率為 10%，第二個組件的稅率為 2%。 在這種情況下，成本計算將拆分到兩個組件。</p><p>為品項計算成本，但根據不同成本類別的組件的值來調整成本值。 然後計算剩餘組件的成本，可以使用先前計算時用的調整總量。</p><p>例如，手錶的組件 A 的成本為 $9.50，關稅為 10%，組件 B 的成本為 $0.50，關稅為 2%。 因此，總成本為$10.00。 第一個登錄是 10% 明細。 它使用的值如下：</p><ul><li>**類別：** *百分*</li><li>**成本值：** *10*</li><li>**調整值：** *調整依據*</li><li>**調整值：** *-0.50*</li></ul><p>此設定指定在計算 10% 的關稅費用之前，必須將品項的成本 (10 美元)減少 $0.50 (組件 B 的價格)。 因此，10% 將套用在$9.50。</p><p>第二個登錄是 2% 明細 (前一個登錄中調整的 $0.50)。 它使用的值如下：</p><ul><li>**類別：** *百分*</li><li>**成本值：** *2*</li><li>**調整值：** *使用*</li><li>**調整：** *0.50*</li></ul><p>此設定計算組件 B 上應該支付的剩餘關稅。</p> |
