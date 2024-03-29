---
title: 修改列定義儲存格
description: 本主題描述財務報表列定義中每個儲存格所需的資訊，並說明如何輸入該資訊。
author: ShylaThompson
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80df992ce14577ba78587648f8af2c35b382a589
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "8460443"
---
# <a name="modify-row-definition-cells"></a>修改列定義儲存格

[!include [banner](../includes/banner.md)]

本主題描述財務報表列定義中每個儲存格所需的資訊，並說明如何輸入該資訊。

## <a name="specify-a-row-code-in-a-row-definition"></a>在列定義中指定列代碼

在列定義中，**列代碼** 儲存格中的數字或標籤標識列定義中的每一行。 您可以指定列代碼以參考計算和總計中的資料。

### <a name="row-code-requirements"></a>列代碼要求

所有資料列都需要列代碼。 您可以在列定義中混合使用數字、字母數字和未設定 (空白) 的列代碼。 列代碼可以是任何正整數 (低於 100,000,000) 或標識該資料列的描述性標籤。 描述性標籤必須遵循以下規則：

- 標籤必須以字母字元 (a 到 z 或 A 到 Z) 開頭，並且可以是最多 16 個字元的數字和字母的任意組合。

    > [!NOTE]
    > 標籤可以包含下劃線字元 (\_)，但不允許使用其他特殊字元。

- 標籤不能使用以下任何保留字：AND、OR、IF、THEN、ELSE、PERIODS、TO、BASEROW、UNIT、NULL、CPO 或 RPO。

以下範例是有效的列代碼：

- 320
- TL\_NET\_INCOME
- TL\_NET\_94

### <a name="change-a-row-code-in-a-row-definition"></a>在列定義中更改列代碼

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 在相應的資料列中，在 **列代碼** 欄的儲存格中輸入新值。

### <a name="reset-numeric-row-codes"></a>重設數字列代碼

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 在 **編輯** 選單上，點選 **重新編號資料列**。
3. 在 **重新編號資料列** 對話方塊中，為起始列代碼和列代碼增量指定新值。 您可以將數字列代碼重設為等距值。 但是，Report Designer 僅重新編號以數字開頭的列代碼 (例如，130 或 246)。 它不會重新編號以字母開頭的列代碼 (例如，INCOME\_93 or TP0693)。

> [!NOTE]
> 當您重新編號列代碼時，Report Designer 具會自動更新 **TOT** 和 **CAL** 參考。 例如，如果 **TOT** 資料列是指以列代碼 100 開頭的範圍，並且您對資料列重新編號，那麼從 90 開始，**TOT** 參考值會從 100 變為 90。

## <a name="add-a-description"></a>新增描述
描述儲存格提供報表資料列中財務資料的描述，例如「收入」或「淨收入」。 **描述** 儲存格中的文字出現在報表上的方式與您在列定義中輸入的完全相同。

> [!NOTE]
> 報表上描述資料欄的寬度在欄定義中設定。 如果列定義中 **描述** 欄中的文字很長，請驗證 **DESC** 欄的寬度。 當您使用 **插入資料列來源** 對話方塊時，**描述** 欄中的值是財務資料中的區段值或維度值。 您可以插入資料列以新增描述性文字，例如部分標題或部分總計，以及新增格式，例如在總計行之前新增一行。 如果報表包含報表樹狀結構，您可以在報表樹狀結構中包含為報表單位定義的附加文字。 您還可以將附加文字限制為特定的報表單位。

### <a name="add-the-description-for-a-line-on-a-report"></a>為報表上的一行新增說明

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 選取 **描述** 儲存格，然後輸入報表資料列的名稱。
3. 套用格式。

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>在描述中新增來自報表樹狀結構的附加文字

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 在相應的 **描述** 儲存格中輸入附加文字代碼和任何其他文字。
3. 套用格式。

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>將附加文字限制為特定報表單位

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 找到應建立附加文字的資料列，然後按兩下點選 **相關公式/資料列/單位** 欄。
3. 在 **報表單位選取** 對話方塊的 **報表樹狀結構定義** 欄位中，選取報表樹狀結構。
4. 在 **選取限制用的報表單位** 欄位，展開或摺疊報表樹狀結構，然後選取報表單位。

## <a name="add-a-format-code"></a>新增格式代碼
**格式代碼** 儲存格為該資料列的內容提供了一系列預先格式化的選項。 如果 **格式代碼** 儲存格為空白，則該資料列被解釋為財務資料詳情資料列。

> [!NOTE]
> 如果報表包含與已被抑制的金額資料列相關的非金額格式資料列 (例如，由於餘額為零)，您可以使用 **相關公式/資料列/單位** 欄以防止列印標題和格式資料列。

### <a name="add-a-format-code-to-a-report-row"></a>向報表資料列新增格式代碼

1. 在 Report Designer 中，點選 **列定義**，然後選取要修改的列定義。
2. 按兩下點選 **格式代碼** 儲存格。
3. 在清單中選取格式代碼。 下表描述了格式代碼及其操作。

    | 格式代碼                   | 格式代碼解讀 | 動作 |
    |-------------------------------|-----------------------------------|--------|
    | (無)                        |                                   | 清除 **格式代碼** 儲存格。 |
    | TOT                           | 總計                             | 識別在 **相關公式/資料列/單位** 欄中使用數學運算子的資料列。 總計包含簡單的運算子，例如 **+** 或  **-**。 |
    | CAL                           | 計算                       | 識別在 **相關公式/資料列/單位** 欄中使用數學運算子的資料列。 計算包含複雜的運算子，例如 **+**、**-**、**\**_、_*/**，和 **IF/THEN/ELSE** 陳述式。 |
    | DES                           | 描述                       | 識別報表中的標題行或空行。 |
    | LFT RGT CEN                   | 左 右 中                 | 對齊報表頁面上的資料列描述文字，無論文字在欄定義中的位置如何。 |
    | CBR                           | 更改基準資料列                   | 識別為資料欄計算設定基準列的資料列。 |
    | COLUMN                        | 分欄                      | 在報表上開始一個新資料欄。 |
    | PAGE                          | 分頁符號                        | 在報表上開始一個新頁面。 |
    | \---                          | 單下劃線                  | 在報表的所有金額欄下放置一行。 |
    | ===                           | 雙下劃線                  | 在報表的所有金額欄下放置兩行。 |
    | LINE1                         | 細線                         | 在頁面上繪製一條細線。 |
    | LINE2                         | 粗線                        | 在頁面上繪製一條粗線。 |
    | LINE3                         | 虛線                       | 在頁面上繪製一條虛線。 |
    | LINE4                         | 粗線和細線          | 在頁面上繪製一條粗線。 頂線為粗線，底線為細線。 |
    | LINE5                         | 細線和粗線          | 在頁面上繪製一條粗線。 頂線為細線，底線為粗線。 |
    | BXB BXC                       | 方塊列                         | 在以 **BXB** 列開始並以 **BXC** 列結束的報表資料列周圍繪製一個方塊。 |
    | REM                           | 備註                            | 識別作為註解列且不應列印在報表上的資料列。 例如，備註資料列可能會解釋您的格式化技術。 |
    | SORT ASORT SORTDESC ASORTDESC | 排序                              | 對費用或收入進行排序，按最大差異對實際或預算差異報表進行排序，或按字母順序對資料列說明進行排序。 |

## <a name="specify-related-formulasrowsunits"></a>指定相關公式/資料列/單位
**相關公式/資料列/單位** 儲存格有多種用途。 根據資料列的類型，**相關公式/資料列/單位** 儲存格可以執行以下其中一項功能：

- 當您使用 **TOT** 格式代碼或 **CAL** 格式代碼時，定義要包含在計算中的資料列。
- 將格式列連結到金額列，以便僅在列印相關金額時列印格式。
- 將列限制為特定的報表單位。
- 使用 **BASEROW** 格式代碼時定義計算的基準列。
- 當您使用任何排序格式代碼時，定義要排序的資料列。

### <a name="use-a-row-total-in-a-row-definition"></a>在列定義中使用資料列總計

使用資料列合計公式來增加或減少其他資料列中的金額。 用於建立資料列總計的公式可以包含 + 和 - 運算子以組合各個列代碼和範圍。 範圍用冒號 (:) 表示。 該公式最多可包含 1,024 個字元。 以下是標準合計公式的範例：400+420+430+450+460LIABILITIES+EQUITY520:546520:546-LIABILITIES

### <a name="components-of-a-row-total-formula"></a>資料列合計公式的組成部分

建立資料列合計公式時，必須使用列代碼指定在現行列定義中要新增或減去哪些資料列，並且必須使用運算子指定資料列的組合方式。 總列和金額列可以任意組合使用。

> [!NOTE]
> 排除範圍內的所有總列數。 若要建立總計，您可以指定資料列的範圍。 如果範圍的第一列是總計列，則該資料列將包含在新總計中。 下表描述了如何在資料列合計公式中使用運算子。

| 運算子 | 範例公式 | 描述                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | 將第 100 列中的金額與第 330 列中的金額相加。        |
| :        | 100:330         | 將第 100 列和第 330 列之間的所有資料列的總數相加。    |
| -        | 100-330         | 從第 330 列的金額中減去第 100 列的金額。 |

### <a name="create-a-row-total"></a>建立資料列總計

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 按兩下點選列定義中的 **格式代碼** 儲存格，然後選取 **TOT**。
3. 在 **相關公式/資料列/單位** 儲存格中，輸入總計公式。

### <a name="relate-a-format-row-to-an-amount-row"></a>將格式列與金額列相連結

在列定義中的 **格式代碼** 欄，**DES**、**LFT**、**RGT**、**CEN**、**---**，和 **===** 格式代碼將格式套用於非金額列。 為了防止在相關金額列被隱藏時列印此格式 (例如，因為金額列包含零值或沒有期間活動)，您必須將格式列與相應的金額列相連結。 當您想要在沒有要列印的期間的明細時防止列印與小計相關的標題或格式時，此功能很有用。

> [!NOTE]
> 您還可以透過清除顯示沒有金額的資料列的選項來防止列印詳細的金額列。 此選項位於報表定義的 **設定** 索引標籤上。 在預設情況下，餘額為零或沒有期間活動的交易明細會計科目在報表中被禁止。 若要顯示這些交易明細會計科目，請選取報表定義 **設定** 索引標籤上的 **顯示沒有金額的資料列** 核取方塊。

### <a name="relate-a-format-row-to-an-amount-row"></a>將格式列與金額列相連結

1. 在 Report Designer 中，點選 **列定義**，然後選取要修改的列定義。
2. 在格式列中，在 **相關公式/資料列/單位** 儲存格，輸入要隱藏的金額列的列代碼。

    > [!NOTE]
    > 若要抑制金額列，該資料列的餘額必須為 0 (零)。 不隱藏具有餘額的金額列。

3. 在 **檔案** 選單上，點選 **儲存**。

### <a name="example-of-preventing-printing-of-rows"></a>防止列印資料列的範例

在以下範例中，使用者希望阻止列印報表的 **總現金** 列中的標題和下劃線，因為兩個現金會計科目中都沒有活動。 因此，在第 220 列 (其中，作為 **---** 格式代碼表示，是一個格式列)，在 **相關公式/資料列/單位** 儲存格中，使用者輸入 **250**，這是使用者想要隱藏的金額列的列代碼。

[![RelatedRowsRowDefinition.](./media/relatedrowsrowdefinition-1024x144.png)](./media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>選取資料欄計算的基準列
在關係報表中，您可以使用 **CBR** (更改基準列) 格式代碼在列定義中指派一個或多個基準列。 然後，欄定義中的計算會參考基準列。 以下是 CBR 計算的一些典型範例：

- 與單個收入項目相關的總收入百分比
- 與單個費用項目相關的總費用百分比
- 與部門或部門詳情相關的毛利率百分比。

在列定義中定義一個或多個基準列，然後欄定義確定報表基準列的關係。 資料欄公式中使用的代碼是 **BASEROW**。 **BASEROW** 使用以下基本數學運算：除法、乘法、加法或減法。 最常使用的運算是除以 **BASEROW**，結果顯示為百分比。 在公式中使用 **BASEROW** 的資料欄計算使用相關基準列代碼的列定義。 **CBR** 列具有以下特徵：

- **CBR** 列不會列印在已完成的報表上。
- **CBR** 格式代碼及其相關的列代碼位於顯示相關計算的資料列或部分的上方。

在欄定義中，**CALC** 欄類型表示在 **公式** 列中指定公式的資料欄。 此公式對報表的此資料欄的資料進行運算，並使用 Baserow 關鍵字根據資料列中的 **CBR** 格式代碼進行計算。 在列定義中，**CBR** 格式代碼可定義資料欄的基準列，該資料欄會計算報表中每一資料列的基準列的百分比或乘以報表中每一資料列的基準列。 您可以在一個資料列格式中有多個 **CBR** 格式代碼，例如一個用於淨銷售額，一個用於總銷售額，一個用於總費用。 在通常情況下，**CBR** 格式代碼用於建立與總行比較的會計科目的百分比。 一個基準列用於所有計算，直到定義另一個基準列。 您必須定義一個起始 **CBR** 格式代碼和一個結束 **CBR** 格式代碼。 例如，要將費用確定為淨銷售額的百分比，您可以將每個費用資料列中的值除以淨銷售額資料列中的值。 在這種情況下，淨銷售額列是基準列。 您可以定義一個列定義來報表現行和年初至今的結果，以及每個結果的基本百分比，如下面的範例所示。 從詳細的損益表開始。

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>為資料欄計算選取列定義中的基準列

1. 在 Report Designer 中，點選 **欄定義**，然後開啟損益表的欄定義。
2. 在欄定義中新增一個新資料欄，並將欄類型設定為 **CALC**。
3. 在新資料欄的 **公式** 儲存格中，輸入公式 **X/BASEROW**，其中 **X** 是要查看百分比的 **FD** 欄類型。
4. 按兩下點選 **格式/貨幣覆寫** 儲存格。
5. 在 **格式覆寫** 對話方塊的 **格式類別** 清單中，選取 **百分比**，然後點選 **確定**。
6. 在 **檔案** 選單上，點選 **另存為** 以新名稱儲存欄定義。 將 **CBR** 附加到現行檔案名稱 (例如，**CUR\_YTD\_CBR**)。 此欄定義是您的基準列欄定義。
7. 在 Report Designer 中，點選 **列定義**，然後透過使用基準列計算開啟要修改的列定義。
8. 在應該開始基準列計算的資料列上方插入一個新資料列。
9. 按兩下點選列定義的 **格式代碼** 儲存格，然後選取 **CBR**。
10. 在 **相關公式/資料列/單位** 儲存格中，輸入基準列的列代碼編號。

### <a name="example-of-base-row-calculation"></a>基準列計算範例

在以下列定義範例中，第 100 列顯示計算的基準列是第 280 列。

[![基準列計算範例。](./media/cbrrowdefinition.png)](./media/cbrrowdefinition.png)

在以下欄定義範例中，計算使用 **CBR** 格式代碼。 C 欄中的計算將報表 B 欄中的值除以 B 欄第 280 列中的值。B 欄中的格式覆寫將計算結果列印為百分比。 同樣，E 欄中的每個金額都是 D 欄中的金額占淨銷售額的百分比。

[![欄定義範例。](./media/cbrcolumndefinition2.png)](./media/cbrcolumndefinition2.png)

以下範例顯示了可能基於先前計算產生的報表。

[![基於先前範例計算的範例報表。](./media/cbrreport-1024x272.png)](./media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>為列定義選取排序代碼
排序代碼對會計科目或值進行排序，按最大差異對實際或預算差異報表進行排序，或按字母順序對資料列描述進行排序。 以下是可用排序代碼：

- **SORT** – 根據指定列中的值按升序對報表進行排序。
- **ASORT** – 根據指定列中值的絕對值，按升序對報表進行排序。 換句話說，在對值進行排序時，將忽略每個值的符號。 此格式代碼按方差的大小對值進行排序，而不管方差是正數還是負數。
- **SORTDESC** – 根據指定列中的值按降序對報表進行排序。
- **ASORTDESC** – 根據指定列中值的絕對值，按降序對報表進行排序。

### <a name="select-a-sorting-code"></a>選取排序代碼

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 按兩下點選 **格式代碼** 儲存格，然後選取一個排序代碼。
3. 在 **相關公式/資料列/單位** 儲存格，指定要排序的列代碼範圍。 若要指定範圍，請輸入第一列代碼、冒號 (:)，然後輸入最後一列代碼。 例如，輸入 **160:490** 指定範圍是第 160 列到第 490 列。
4. 在 **欄限制** 儲存格，輸入用於排序的報表列的字母。

    > [!NOTE]
    > 在排序計算中僅包括金額列。

### <a name="examples-of-ascending-and-descending-column-values"></a>升序和降序欄值的範例

在以下範例中，報表 D 欄中的值將按升序排列，從第 160 列到第 490 列。 此外，報表 G 欄中的絕對值將按第 610 到 940 列的遞減排序。

| 列代碼 | 描述                                         | 格式代碼 | 相關公式/列/單位 | 正常餘額 | 欄限制 | 連至財務維度 |
|----------|-----------------------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | 按月度差異昇冪排列       | DES         |                             |                |                    |                              |
| 130      |                                                     | SORT        | 160:490                     |                | D                  |                              |
| 160      | 銷售                                               |             |                             | C              |                    | 4100                         |
| 190      | 銷售退貨                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 490      | 利息收入                                     |             |                             | C              |                    | 7000                         |
| 520      |                                                     | DES         |                             |                |                    |                              |
| 550      | 按 YTD 絕對差異遞減排序 | DES         |                             |                |                    |                              |
| 580      |                                                     | ASORTDESC   | 610:940                     |                | G                  |                              |
| 610      | 銷售                                               |             |                             | C              |                    | 4100                         |
| 640      | 銷售退貨                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 940      | 利息收入                                     |             |                             | C              |                    | 7000                         |


## <a name="specify-a-format-override-cell"></a>指定格式覆寫儲存格
**格式覆寫** 儲存格指定列印報表時用於資料列的格式。 此格式會覆寫在欄定義和報表定義中指定的格式。 在預設情況下，這些定義中指定的格式是貨幣。 如果報表的一列列出了資產的數量，例如建築物的數量，而另一列列出了這些資產的貨幣價值，您可以覆寫貨幣格式並為指定建築物數量的資料列輸入數字格式。 您可以在 **格式覆寫** 對話方塊中指定此資訊。 可用選項取決於您選取的格式類別。 **樣本** 對話方塊區域顯示範例格式。 可以使用以下格式類別：

- 貨幣格式化
- 數字格式化
- 百分比格式化
- 自訂格式化

### <a name="override-cell-formatting"></a>覆寫儲存格格式化

1. 在 Report Designer 中，打開列定義做修改。
2. 在覆寫蓋其格式的資料列中，按兩下點選 **格式覆寫** 欄。
3. 在 **格式覆寫** 對話方塊中，選取用於報表中該資料列的格式選項。
4. 點選 **確定**。

### <a name="currency-formatting"></a>貨幣格式化

貨幣格式適用於會計金額並包括貨幣符號。 可以使用以下選項：

- **貨幣符號** – 報表的貨幣符號。 此值覆寫公司資訊的 **區域選項** 設定。
- **負數** – 負數可以有一個減號 (-)，它們可以出現在括號中，或者它們可以有一個三角形 (Δ)。
- **小數位** – 小數點後顯示的位數。
- **零值覆寫文字** – 當金額為 0 (零) 時要包含在報表中的文字。 此文字顯示為 **樣本** 區域中的最後一行。

    > [!NOTE]
    > 如果針對零值或無期間活動禁止列印，則禁止列印此文字。

### <a name="numeric-formatting"></a>數字格式化

數字格式適用於任何金額，不包括貨幣符號。 可以使用以下選項：

- **負數** – 負數可以有一個減號 (-)，它們可以出現在括號中，或者它們可以有一個三角形 (Δ)。
- **小數位** – 小數點後顯示的位數。
- **零值覆寫文字** – 當金額為 0 (零) 時要包含在報表中的文字。 此文字顯示為 **樣本** 區域中的最後一行。

    > [!NOTE]
    > 如果針對零值或無期間活動禁止列印，則禁止列印此文字。

### <a name="percentage-formatting"></a>百分比格式化

百分比格式包括百分號 (%)。 可以使用以下選項：

- **負數** – 負數可以有一個減號 (-)，它們可以出現在括號中，或者它們可以有一個三角形 (Δ)。
- **小數位** – 小數點後顯示的位數。
- **零值覆寫文字** – 當金額為 0 (零) 時要包含在報表中的文字。 此文字顯示為 **樣本** 區域中的最後一行。

    > [!NOTE]
    > 如果針對零值或無期間活動禁止列印，則禁止列印此文字。

### <a name="custom-formatting"></a>自訂格式化

使用自訂格式類別建立自訂格式覆寫。 可以使用以下選項：

- **類型** – 自訂格式。
- **零值覆寫文字** – 當金額為 0 (零) 時要包含在報表中的文字。 此文字顯示為 **樣本** 區域中的最後一行。

    > [!NOTE]
    > 如果針對零值或無期間活動禁止列印，則禁止列印此文字。

類型應先表示正值，然後表示負值。 通常，您輸入區分正值和負值的類似格式。 例如，若要指定正值和負值都有兩位小數，但負值出現在括號中，請輸入 **0.00;(0.00)**。 下表顯示了可用於控制值格式的自訂格式。 所有範例都從值 1234.56 開始。

| 格式                         | 正   | 負     | 零    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);""       | 1,235      | (1,235)      | (空白) |
| \#,\#\#0.00;(\#,\#\#0.00);zero | 1,234.56   | (1,234.56)   | 零    |
| 0.00%;(0.00%)                  | 123456.00% | (123456.00%) | 0.00%   |

## <a name="specify-a-normal-balance-cell"></a>指定一個正常的餘額儲存格
列定義中的 **正常餘額** 儲存格控制資料列中金額的符號。 若要沖銷資料列的符號，或者如果會計科目的正常餘額是貸方，請在該資料列的 **正常餘額** 儲存格中輸入 **C**。 Report Designer 沖銷該資料列中所有貸方餘額會計科目的符號。 當 Report Designer 轉換這些會計科目時，它會從所有金額中刪除借方/貸方特徵，因此使總計變得簡單。 例如，要計算淨收入，您可以從收入中減去費用。 通常，總計和計算的資料列不受 **C** 代碼的影響。 但是，欄定義中的 **XCR** 列印控制項沖銷任何在 **正常餘額** 欄中包含 **C** 的資料列符號。 當您想要將所有不利差異顯示為負數時，此格式尤其重要。 如果總計或計算的數字元號錯誤，請在該列的 **正常餘額** 儲存格中輸入 **C** 以沖銷符號。

## <a name="specify-a-row-modifier-cell"></a>指定列修飾詞儲存格
列定義中的 **列修飾詞** 儲存格的內容會覆寫在該列的欄定義中指定的會計年度、期間和其他資訊。 選定的修飾詞適用於該列中的每個會計科目。 您可以使用以下一種或多種類型的修飾詞來修改每一列：

- 會計科目修飾詞
- 帳簿代碼修飾詞
- 會計科目和交易屬性

### <a name="override-a-column-definition"></a>覆寫欄定義

1. 在 Report Designer 中，打開列定義做修改。
2. 在要覆寫欄定義的資料列中，按兩下點選 **列修飾詞** 儲存格。
3. 在 **列修飾詞** 對話方塊中，選取 **會計科目修飾詞** 欄位中的選項。 如需該選項的相關說明，請參閱「會計科目修飾詞」區塊。
4. 在 **帳簿代碼修飾詞** 欄位中，選取要用於該列的帳簿代碼。
5. 在 **屬性** 下方，請按照以下步驟為應包含在列代碼中的每個屬性新增一個條目：

    1. 按兩下點選 **屬性** 儲存格，然後選取一個屬性名稱。

        > [!IMPORTANT]
        > 將數字元號 (\#) 替換為數字值。

    2. 按兩下點選 **來源** 儲存格，然後輸入範圍的第一個值。
    3. 按兩下點選 **目的地** 儲存格，然後輸入範圍的最後一個值。

6. 點選 **確定**。

### <a name="account-modifiers"></a>會計科目修飾詞

當您選取特定會計科目時，Report Designer 通常會結合該會計科目和您在欄定義中指定的會計年度、期間和其他資訊。 您可以為特定資料列使用不同的資訊，例如不同的會計期間。 下表顯示了可用的會計科目修飾詞。 將數字元號 (\#) 替換為等於或小於會計年度期間數的值。

| 會計科目修飾詞 | 列印出了什麼                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | 會計科目的期初餘額。                                                     |
| /\#              | 指定期間的餘額。                                                     |
| /-\#             | 現行期間之前的 \# 個期間的期間的餘額。                  |
| /+\#             | 現行期間之後的 \# 個期間的期間的餘額。                   |
| /C               | 現行期間的餘額。                                                       |
| /C-\#            | 現行期間之前的 \# 個期間的期間的餘額。                  |
| /C+\#            | 現行期間之後的 \# 個期間的期間的餘額。                   |
| /Y               | 現行期間的年初至今餘額。                                      |
| /Y-\#            | 現行期間之前的 \# 個期間內的年初至今餘額。 |
| /Y+\#            | 在現行期間之後的 \# 個期間內的年初至今餘額。  |

### <a name="book-code-modifiers"></a>帳簿代碼修飾詞

您可以將資料列限制為現有的帳簿代碼。 欄定義必須包含至少一個具有帳簿代碼的 **FD** 欄。

> [!NOTE]
> 某資料列的帳簿代碼限制會覆寫該列的欄定義中的帳簿代碼限制。

### <a name="account-and-transaction-attributes"></a>會計科目和交易屬性

一些會計系統支援財務資料中的會計科目屬性和交易屬性。 這些屬性的函數類似於虛擬會計科目區段，可以攜帶有關會計科目或交易的附加資訊。 此附加資訊可能是科目 ID、批次 ID、郵遞區號或其他屬性。 如果您的會計系統支援屬性，您可以使用會計科目屬性或交易屬性作為列定義中的列修飾詞。 如需如何覆寫列資訊的資訊，請參閱本文前面的「覆寫欄定義」區塊。

## <a name="specify-a-link-to-financial-dimensions-cell"></a>指定指向財務維度儲存格的連結
**連結到財務維度** 儲存格包含指向應包含在報表每一列中的財務資料的連結。 此儲存格包含維度值。 若要開啟 **維度** 對話方塊，按兩下點選 **連結到財務維度** 儲存格。

> [!NOTE]
> Report Designer 無法從 Microsoft Dynamics ERP 系統中選取包含以下任何保留字元的科目、維度或欄位：&、\*、\[、\]、{ 或 }。 若要為列定義中已經存在的資料列指定資訊，請將資訊新增到 **連結到財務維度** 儲存格。 若要新增連結到財務資料的新資料列，請使用 **插入資料列來源** 對話方塊以在報表定義中建立新資料列。 欄標題會根據資料欄的設定方式發生變化，如下表所示。

| 選取的連結類型       | 連結欄的描述變成了這個 |
|----------------------------------|----------------------------------------------------|
| 財務維度             | 連至財務維度                       |
| 報表工作表                 | Financial Reporting Report                         |

### <a name="specify-a-dimension-or-range"></a>指定維度或範圍

1. 在 Report Designer 中，打開列定義做修改。
2. 按兩下點選 **連結到財務維度** 欄中的儲存格。
3. 在 **維度** 對話方塊中中，按兩下點選維度名稱下的儲存格。
4. 在維度對話方塊中，選取 **個人或範圍**。
5. 在 **來源** 欄位中，輸入起始維度，或點選![瀏覽。](media/browse.gif "瀏覽 ") 搜尋可用維度。 若要輸入維度範圍，請在 **目的地** 欄位。
6. 點選 **確定** 關閉維度對話方塊。 **維度** 對話方塊顯示更新的維度或範圍。
7. 點選 **確定** 關閉 **維度** 對話方塊。

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>在列定義中顯示零餘額科目
在預設情況下，Report Designer 不會列印財務資料中沒有相應餘額的任何資料列。 因此，您可以建立一個包含所有自然區段值或所有維度值的列定義，然後將該列定義用於您的任何部門。

### <a name="modify-zero-balance-settings"></a>修改零餘額設定

1. 在 Report Designer 中，打開報表定義做修改。
2. 在 **設定** 索引標籤的 **其他格式** 下，為報表定義中使用的列定義選取選項。
3. 在 **檔案** 選單上，點選 **儲存** 儲存您的更改。

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>在列定義中使用萬用字元和範圍
在 **維度** 對話方塊中輸入自然區段值時，可以在區段的任何位置 放置萬用字元 (? 或 \*)。 Report Designer 提取定義位置的所有值，而不考慮萬用字元。 例如，列定義只包含自然區段值，自然區段有四個字元。 透過在資料列輸入 **6???** 您可以指示 Report Designer 加入所有以 6 開頭自然區段值的帳戶。 如果您輸入 **6\**_，回傳相同的結果，但結果還包括變數寬度值，例如_* 60** 和 **600000**。 Report Designer 將每個萬用字元 (?) 替換為可能值的完整範圍，其中包括字母和特殊字元。 例如，在 **12?0** 到 **12?4** 的範圍內，**12?0** 的萬用字元被替換為字元集中的最低值，**12?4** 的萬用字元被替換為字元集中的最高值。

> [!NOTE]
> 您應該避免使用萬用字元作為範圍內的開始和結束科目。 如果您在起始科目或結束科目中使用萬用字元，您可能會收到意外的結果。

### <a name="single-segment-or-single-dimension-ranges"></a>單區段或單維度範圍

您可以指定一系列區段值或維度值。 指定範圍的好處是您不必在每次將新的區段值或維度值新增到財務資料時都更新列定義。 例如，範圍 **+Account=\[ 6100:6900\]** 將科目 6100 到 6900 中的值提取到列金額中。 當範圍包含萬用字元 (?) 時，Report Designer 不會逐個字元地評估範圍。 而是確定範圍的低端和高端，然後包括結束值和它們之間的所有值。

> [!NOTE]
> Report Designer 無法從 Microsoft Dynamics ERP 系統中選取包含以下任何保留字元的科目、維度或欄位：&、\*、\[、\]、{ 或 }。 僅當您使用 **從維度插入資料列** 對話方塊自動構建列定義時，才能新增 & 符號。

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>多區段或多維度範圍

當您透過使用多個維度值的組合輸入範圍時，該範圍比較將在 ..\\financial-dimensions\\dimension-by-dimension 的基礎上進行。 該範圍比較不能在逐個字元的基礎上或部分段的基礎上進行。 例如，範圍 **+Account=\[5000:6000\], Department=\[1000:2000\], Cost center=\[00\]** 僅包括與每個區段相符的科目。 在這種情況下，第一個維度必須在 5000 到 6000 的範圍內，第二個維度必須在 1000 到 2000 的範圍內，最後一個維度必須是 00。 例如，**+Account=\[5100\], Department=\[1100\], Cost center=\[01\]** 未包含在報表中，因為最後一段超出了指定範圍。 如果區段值包含空格，請將該值括在方括號 (\[\]) 內。 以下值對四字元區段有效：**\[234\]，\[123\]，\[1 34\]**。 維度值應括在方括號 (\[\]) 中，Report Designer 會為您新增這些括號。 當多區段或多維度範圍包括萬用字元 (?  或 \*)時，整個多區段或多維範圍的低端和高端將被確定，然後末端值和它們之間的所有值都被包括在內。 如果您的範圍很大，例如從 40000 到 99999 的整個科目範圍，則應盡可能指定有效的起始科目和結束科目。

> [!NOTE] 
> Report Designer 無法從 Microsoft Dynamics ERP 系統中選取包含以下任何保留字元的科目、維度或欄位：&、\*、\[、\]、{ 或 }。 僅當您使用 **從維度插入資料列** 對話方塊自動構建列定義時，才能新增 & 符號。

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>在列定義中新增或減去其他科目
若要從另一個科目中的金額新增或減去一個科目中的金額，您可以在 **連結到財務維度** 儲存格中使用加號 (+) 和減號 (-)。 下表顯示了新增和減去財務資料連結的可接受格式。

| 作業                                                                               | 使用此格式                                                                                              |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| 新增兩個完整會計科目。                                                       | +Division=\[000\], Account=\[1205\], Department=\[00\]+Division=\[100\], Account=\[1205\], Department=\[00\] |
| 新增兩個區段值。                                                                 | +Account=\[1205\]+Account=\[1210\]                                                                           |
| 新增包含萬用字元的區段值。                                    | +Account=\[120?+Account=\[11??\]                                                                             |
| 新增一系列完整會計科目。                                                | +Division=\[000:100\], Account=\[1205\], Department=\[00\]                                                   |
| 新增一系列區段值。                                                          | +Account=\[1200:1205\]                                                                                       |
| 新增一系列包含萬用字元的區段值。                         | +Account=\[120?:130?\]                                                                                       |
| 從另一個完整會計科目中減去一個完整會計科目。              | +Division=\[000\], Account=\[1205\], Department=\[00\]-Division=\[100\], Account=\[1205\], Department=\[00\] |
| 從另一個區段值中減去一個區段值。                                  | +Account=\[1205\]-Account=\[1210\]                                                                           |
| 從另一個區段值中減去包含萬用字元的區段值。 | +Account=\[1200\]-Account=\[11??\]                                                                           |
| 減去一系列完整會計科目。                                           | -Division=\[000:100\], Account=\[1200:1205\], Department=\[00:01\]                                           |
| 減去一系列區段值。                                                     | -Account=\[1200:1205\]                                                                                       |
| 減去一系列包含萬用字元的區段值。                    | -Account=\[120?:130?\]                                                                                       |

雖然您可以直接修改會計科目，但您也可以使用 **維度** 對話方塊將正確的格式應用於您的財務資料連結。 任何值都可以包含萬用字元 (?  或 \*)。 但是，Report Designer 無法從 Microsoft Dynamics ERP 系統中選取包含以下任何保留字元的會計科目、維度或欄位：&、\*、\[、\]、{ 或 }。

> [!NOTE]
> 若要減去值，您必須在這些值周圍加上括號。 例如，如果您輸入 **450?-(4509)**，顯示為 **+Account=\[4509\] -Account=\[450?\]**，並且您指示 Report Designer 從以 450 開頭的任何會計科目區段的金額中減去會計科目段 4509 的金額。

### <a name="add-or-subtract-accounts-from-other-accounts"></a>從其他會計科目中新增或減去會計科目

1. 在 Report Designer 中，打開列定義做修改。
2. 在相應的資料列中，按兩下點選 **連結到財務維度** 欄中的儲存格。
3. 在 **維度** 對話方塊的第一列中，執行以下步驟：

    1. 在第一個欄位中，選取所有維度 (預設)，或點選開啟 **管理維度集** 對話方塊，您可以在其中建立、修改、複製或刪除集合。
    2. 按兩下點選 **運算子 +/-** 儲存格，然後選取加號 (**+**) 或減號 (**-**) 運算子，適用於該列中的一個或多個維度值或集合。
    3. 在相應的維度值欄中，按兩下點選儲存格以開啟 **維度** 對話方塊，然後選取此維度值是針對個人還是范圍、維度值集還是總計科目。 如需 **維度** 對話方塊中欄位的描述，請參閱「維度對話方塊的描述」區塊。
    4. 在 **來源** 欄和 **目的地** 欄中輸入區段值。

4. 重複步驟 2 到 3，以加入更多作業。

> [!NOTE]
> 運算子適用於該列中的所有維度。

## <a name="description-of-the-dimensions-dialog-box"></a>描述對話方塊的描述
下表描述了 **維度** 對話方塊中的欄位。

| 項目                | 描述 |
|---------------------|-------------|
| 個人或範圍 | 在 **來源** 欄位中，輸入會計科目名稱，或點選 **瀏覽** 按鈕![瀏覽。](media/browse.gif "瀏覽 ") 瀏覽會計科目。 若要選取一個範圍，請在 **目的地** 欄位中輸入或瀏覽一個值。 |
| 維度值集 | 請在 **名稱** 欄位中，輸入維度值集的名稱。 若要建立、修改、複製或刪除某集，請點選 **管理維度值集**。 **公式** 欄位由 **連結到財務維度** 儲存格中的公式填入，用於在列定義中設定此維度值。 |
| 總計會計科目   | 在 **名稱** 欄位中，輸入或瀏覽總計會計科目的維度。 **公式** 欄位由報表定義中此總計科目的 **財務維度連結** 儲存格中的公式填入。 |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>在列定義中新增維度值集
維度值集是一組命名的維度值。 維度值集只能包含單個維度中的值，但您可以在多個列定義、欄定義、報表樹狀結構定義和報表定義中使用維度值集。 您還可以在報表定義中組合維度值集。 當對財務資料的更改要求您更改維度值集時，您可以更新維度值集定義，並且該更新適用於使用維度值集的所有區域。 例如，如果您經常指定一個值範圍以連結到您的財務資料，例如從 5100 到 5600 的值，您可以將此範圍指派給名為 Sales 的科目集。 建立一組維度值後，您可以選取該組作為您的財務資料連結。 作為另一個範例，如果將 5100 到 5600 的值範圍指派給 Sales，並將 4175 指派給 Discounts，則可以透過從 Sales 中減去 Discounts 來確定總銷售額。 該作業表示為 **(5100:5600)-4175**。

### <a name="create-a-set-of-dimension-values"></a>建立一組維度值

1. 在 Report Designer 中，開啟要修改的資料列、資料欄或樹狀結構定義。
2. 在 **編輯** 選單，點選 **管理維度值集**。
3. 在 **管理維度值集** 對話方塊的 **維度** 欄位中，選取要建立的維度值集的類型，然後點選 **新建**。
4. 在 **新建** 對話方塊中，輸入集合的名稱和描述。
5. 在 **來源** 欄，按兩下點選儲存格。
6. 在 **會計科目** 對話方塊中，選取清單中的會計科目名稱，或在 **搜尋** 欄位中搜尋條目。 然後點選 **確定**。
7. 在 **目的地** 欄中重複步驟 5 到 6，為該運算子設計一個公式。
8. 公式完成後，點選 **確定**。
9. 在 **管理維度集** 對話方塊，點選 **關閉**。

### <a name="update-a-set-of-dimension-values"></a>更新一組維度值

1. 在 Report Designer 中，開啟要修改的資料列、資料欄或樹狀結構定義。
2. 在 **編輯** 選單，點選 **管理維度值集**。
3. 在 **管理維度值集** 對話方塊，在 **維度** 欄位，選取維度類型。
4. 在清單中，選取要更新的維度值集，然後點選 **修改**。
5. 在 **修改** 對話方塊中，修改公式值以包含在集合中。

    > [!NOTE]
    > 如果新增新會計科目或維度，請確保修改現有維度值集以合併更改。

6. 按兩下點選儲存格，然後選取相應的運算子，**來源** 會計科目，以及 **目的地** 會計科目。
7. 點選 **確定** 關閉 **修改** 對話方塊並儲存更改。

### <a name="copy-a-dimension-set"></a>複製維度集

1. 在 Report Designer 中，開啟要修改的資料列、資料欄或樹狀結構定義。
2. 在 **編輯** 選單，點選 **管理維度值集**。
3. 在 **管理維度值集** 對話方塊，在 **維度** 欄位，選取維度類型。
4. 在清單中，選取要複製的集合，然後點選 **另存為**。
5. 輸入複製集合的新名稱，然後點選 **確定**。

### <a name="delete-a-dimension-set"></a>刪除維度集

1. 在 Report Designer 中，開啟要修改的資料列、資料欄或樹狀結構定義。
2. 在 **編輯** 選單，點選 **管理維度值集**。
3. 在 **管理維度值集** 對話方塊，在 **維度** 欄位，選取維度類型。
4. 選取要刪除的集，然後點選 **刪除**。 點選 **是** 永久刪除維度值集。

## <a name="additional-resources"></a>其他資源

[財務報表](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
