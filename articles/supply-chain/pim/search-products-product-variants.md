---
title: 在訂單登錄期間搜尋產品和產品變型
description: 當您手動建立銷售訂單行或訂購單行時，使用 **品項編號** 欄位搜尋產品和產品變型。 當您只有設定字串或一個產品維度可用時，這可讓您快速找到產品變型。
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, PurchTablePart, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9fea7f82ac7723d4cb83c5c8224251fd6c43a315
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447852"
---
# <a name="search-for-products-and-product-variants-during-order-entry"></a>在訂單登錄期間搜尋產品和產品變型

[!include [banner](../includes/banner.md)]

當您手動建立銷售訂單行或訂購單行時，使用 **品項編號** 欄位搜尋產品和產品變型。  當您只有設定字串或一個產品維度可用時，這可讓您快速找到產品變型。

有時，擁有太多東西並不是最好的情況，尤其是如果您銷售許多相似的產品，且您試圖記住品項編號或產品搜尋名稱以找到要放在銷售訂單上的正確產品時。 您可以使用銷售訂單行或訂購單行上的 **品項編號** 欄位做為搜尋欄位。 您可以輸入產品名稱的任何部分、編號或維度，取得顯示與搜尋詞相符的所有品項的查詢。

## <a name="how-search-works"></a>搜尋的運作方式
當您搜尋產品或產品變型時，了解搜尋功能如何找到與您輸入的文字相符的產品非常重要。 提供搜尋結果的關鍵搜尋規則是：

-   搜尋結果將傳回所有相符的記錄，無論在哪個欄位中輸入搜尋文字。
-   搜尋文字需要以完整長度顯示在相符記錄中。
-   即使在相符記錄中的文字字串的中間找到搜尋文字，也算相符。 其不必出現在文字字串的開頭。
-   搜尋文字視為單一文字字串，即使它包含空格。

### <a name="examples"></a>範例

以下範例使用產品和產品變型來說明如何在各種案例中處理搜尋。 **先決條件：** 在 **銷售和行銷 &gt; 設定 &gt; 搜尋&gt; 搜尋參數 &gt; 搜尋類型** 下，選擇 **完全符合** 選項。

| 產品類型     | 產品名稱    | 顯示產品編號 | 品項編號 | 組態 |
|------------------|-----------------|------------------------|-------------|---------------|
| 獨特產品 | SpeakerMidRange | D0001                  | D0001       | NA            |
| 產品變型  | 主動式喇叭  | D0010:::Black:         | D0010       | 000005        |
| 產品變型  | 主動式喇叭  | D0010:::White:         | D0010       | 白色         |

如果您在 **品項編號** 欄位中輸入「喇叭」，將在查詢結果中獲得上述所有產品。 如果您在 **品項編號** 欄位中輸入「黑色」，將在結果中得到第二個產品，因為它的顯示產品編號中有文字「黑色」。 這兩個例子說明了搜尋不僅發生在欄位的開頭，在相符記錄的文字字串中間找到搜尋文字時，也會發生相符。  

如果輸入 '05'，結果中將只會顯示第二個產品變型，因為它的設定中有 '05'。 這說明搜尋發生在 **搜尋條件** 頁面上的所有已啟用欄位中。  

如果您鍵入「喇叭 05」，將不會得到任何結果。 這是因為搜尋會查詢輸入的完整文字。 搜尋不會嘗試查詢「喇叭」，然後將結果縮小到包含 '05' 的結果。  

使用 **銷售和行銷 &gt; 設定 &gt; 搜尋 &gt; 搜尋參數** 頁面上的 **結果數目** 欄位可以限制搜尋結果的數量。 如果將此欄位設定為 0，則將傳回所有搜尋結果。 例如，如果將其設定為 10，它將傳回最多 10 個搜尋結果。

## <a name="configure-the-product-search"></a>設定產品搜尋
在您可以使用產品和產品變型搜尋功能之前，請按照以下步驟設定產品搜尋。 [![設定產品搜尋的 3 個步驟\_AXAppFall。](./media/3-steps-to-configure-product-search_axappfall.png)](./media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1-include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>步驟 1：在搜尋條件中包含所有相關的產品和產品變型識別碼和維度

例如，您在搜尋中可以使用的產品和產品變型識別碼和維度包括 **產品名稱、品項編號**、**顯示產品編號、設定、色彩、尺寸、款式、搜尋名稱等**。  

移至 **銷售和行銷 &gt; 設定 &gt; 搜尋 &gt; 搜尋條件** 頁面。 **搜尋條件** 頁面可讓您定義客戶、潛在客戶和產品搜尋的條件。 確保使用產品搜尋條件篩選頁面。 您可以切換到頁面功能表中的 **產品**。  

若要將顯示產品編號新增到搜尋條件，請點選頁面功能表中的 **新增**。 這將在 **搜尋條件** 格線中新增記錄。 打開 **欄位名稱** 資料行查詢並選擇 **DisplayProductNumber**。 若要將產品的設定新增到搜尋條件，請在 **搜尋條件** 格線中建立新記錄，並選擇 **欄位名稱** 資料行中的 **configId**。 同樣，使用 **欄位名稱** **InventColorId** 對顏色維度建立記錄，使用 **InventSizeId** 對尺寸維度建立記錄，使用 **InventStyleId** 對樣式維度建立記錄。

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>步驟 2：填入用於產品搜尋的資料庫資料表

在 **搜尋條件** 頁面中，點選 **更新搜尋資料** 按鈕。 在 **更新搜尋資料** 對話方塊，請確保 **資源** 設定為 **產品**，然後點選 **確定**。 系統將在一個資料表中彙總在步驟 1 中指定的所有選擇的搜尋條件。 如果您有很多產品和產品變型，此作業可能會非常冗長，而且您可能會收到警告。 建議您安排在伺服器不太忙的時候在批次伺服器上進行搜尋資料表填入。  

在填入資料表之前，產品搜尋不會提供正確的結果。 如果無法獲得任何搜尋結果，請確保已填入此資料表。  

僅當修改搜尋條件時才需要填入資料表。 新推出的產品和變型會自動新增到資料表中。 已刪除的產品和變型會自動從資料表中移除。

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>步驟 3：在銷售和訂購單行上啟用產品搜尋查詢

您可以移至 **銷售和行銷 &gt; 設定 &gt; 搜尋 &gt; 搜尋參數**，將 **一般** 索引標籤上的 **啟用搜尋查詢** 設為 **是**，來啟用此功能  

對於銷售訂單行輸入，預設行為是當您開始輸入 **品項編號** 欄位，然後按下 **Tab** 鍵時，打開 **產品搜尋** 頁面。 **產品搜尋** 頁面在建立訂單行期間變更內容，可能會被視為是不必要的干擾。 如果您希望在查詢中取得查詢中的搜尋結果，並且在訂單行輸入期間不遺失內容，則可以改用搜尋查詢。 如果您搜尋產品或產品變型，但未在查詢中選擇任何內容就按 **Tab** 鍵，將顯示 **產品搜尋** 頁面。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]