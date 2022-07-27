---
title: 財務 Report Designer 中的列定義
description: 列定義是一個報表組件或建構元素，它指定財務報表中每一列的內容。
author: aprilolson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e175d1e3de1f5db31de9c4600c8a5935f0cb11a9d39bc0f4e142edf5fc00ce86
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460278"
---
# <a name="row-definitions-in-financial-report-designer"></a>財務 Report Designer 中的列定義

[!include [banner](../includes/banner.md)]

列定義是一個報表組件或建構元素，它指定財務報表中每一列的內容。 列定義可以與欄定義、報表樹狀結構定義和報表定義相結合，以建立可供多家公司使用的建構元素組。

## <a name="create-a-row-definition"></a>建立列定義

1. 在 Report Designer 中的瀏覽窗格，點選 **列定義**。
2. 在 **檔案** 選單上，點選 **新增**，然後點選 **列定義**。 如需每個儲存格內容的相關資訊，請參閱[修改列定義儲存格](modify-row-definition-cells-financial-reporting.md)。

## <a name="open-a-row-definition"></a>開啟列定義
1. 在 Report Designer 中的瀏覽窗格，點選 **列定義**。
2. 按兩下點選要打開的列定義名稱。
3. 若要查看與列定義關聯的任何建構元素，請按右鍵點選列定義，然後選取 **關聯**。

## <a name="contents-of-a-row-definition"></a>列定義的內容
列定義最多可以包含 20,000 個財務維度列，並且可以包含以下資訊：

- 透過建立章節標題、行和空格來為報表增加意義的描述性文字，例如 **現金** 或 **總收入**
- 財務資料的連結，其中可以包括 Microsoft Dynamics 365 Finance 中的維度值

    > [!NOTE]
    > 您可以設定列定義以在每次產生報表時從財務維度系統中提取資料。

- 基於連結財務資料的列總計和公式

通常，列定義中的每一列都包含以下類型的資訊之一：

- 參考財務維度系統
- 基於資料的總計或計算
- 格式設定

在列定義中輸入資訊有兩種方法：

- 在新的列定義中手動輸入行資訊。 如需相關資訊，請參閱[修改列定義儲存格](modify-row-definition-cells-financial-reporting.md)。
- 使用 Report Designer 直接從財務維度中提取列資訊。 如需相關資訊，請參閱[修改列定義儲存格](modify-row-definition-cells-financial-reporting.md)中的「相關公式/列/單位」章節。

## <a name="add-dimensions-in-a-row-definition"></a>在列定義中新增維度
維度是資料和值的交集。 您可以在 Report Designer 中對資料和值進行分組。 然後，您可以更詳細地對交易進行分類和分析。 您可以使用 **從維度插入列** 對話方塊同時將多列新增到列定義。 該對話方塊為每個維度顯示一欄。 下表描述了您可以為每個維度指定的資訊。

| 選項                | 描述 |
|-----------------------|-------------|
| 維度             | 識別要新增到列定義維度的模式。 此模式為維度中的每個位置包含一個 & 符號或數字元號 (\#)。 通常，對主科目維度使用所有 & 符號，對其他維度使用所有數字元號。 |
| 維度範圍開始 | 要新增到列定義的此維度的第一個值。 |
| 維度範圍結束   | 要新增到列定義的此維度的最後一個值。 |

若要將維度新增到列定義，請執行以下步驟。

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 在 **編輯** 選單上，點選 **從維度插入列**。
3. 在 **從維度插入列** 對話方塊，在 **維度** 列，選取要傳輸到列定義的維度的儲存格，然後點選 **All &&&**。
4. 若要將列定義限制為特定範圍的維度值，請在 **維度範圍開始** 儲存格，然後在 **維度範圍結束** 儲存格。 若要包含所選維度的所有值，請將這些儲存格留空。

    > [!NOTE]
    > 萬用字元 (\* 或 ?) 在維度範圍內可能不會回傳您想要的所有結果，具體取決於 ERP 資料庫整理資料的方式。

5. 在 **起始列代碼** 欄位，指定要新增到列代碼的第一個維度值的列代碼。
6. 在 **每行遞增** 欄位，指定連續列代碼之間的間隔。 例如，如果第一列代碼為 100，增量值為 30，則第一個新列的代碼為 100、130、160、190 和 220。 使用提供足夠空間來插入新格式和公式列的增量值。
7. 點選 **確定**。 對於每個選定的維度值，都會在列定義中新增一行。

## <a name="adjust-rounding-in-a-row-definition"></a>在列定義中調整進位
如果您有一個金額四捨五入的資產負債表，則總計可能不平衡。 例如，如果您在資產負債表報表上使用進位選項並且報表定義還指定了進位，則可能會出現此問題。 您可以使用列定義中的 **進位調整** 選項以平衡資產負債表中的金額。 您可以在報表定義的 **設定** 索引標籤上關閉或修改它。 下表顯示了金額的進位方式。 在此資料表中，打開進位時第 100 列和第 200 列的總數不同。

| 列代碼 | 未經進位的金額 | 進位到整數的金額 |
|----------|--------------------------|-----------------------------------------|
| 100      | 3,600                    | 4                                       |
| 200      | 3,700                    | 4                                       |
| 總計    | 7,300                    | 8                                       |

弱要調整資產負債表中的進位，請執行以下步驟。

1. 在 Report Designer 中，點選 **列定義**，然後打開要修改的列定義。
2. 在 **編輯** 選單上，點選 **進位調整**。
3. 在 **進位調整** 對話方塊中，輸入以下值：

    - **進位調整列** – 應調整以平衡資產負債表資料列的列代碼。
    - **總資產列** – 資產負債表中包含總資產列的列代碼。
    - **總負債和權益列** – 資產負債表中包含總負債和權益列的列代碼。
    - **調整金額限制** – 一個正整數，指定自動調整的限制。 將此金額與實際進位差異的絕對值進行比較。

    > [!NOTE]
    > 這些列代碼必須連結到您的財務資料。 換句話說，該列的 **連結到財務維度** 儲存格中必須有一個維度值。 **不要** 參考描述 (**DESC**)、計算 (**CALC**) 或總計 (**TOT**) 列。

啟用進位後，您的資產負債表中的金額現在將均勻平衡。

> [!NOTE]
> 根據為報表定義指定的 **進位精準度** 選項套用調整限制。 例如，如果您將報表進位到千位並在 **調整金額限制** 欄位中輸入 **2**，則當 **進位調整列** 欄位中的值增加或減少超過 2,000 時，您會收到一條警告訊息。

## <a name="format-row-and-column-text"></a>格式化資料列和資料欄文字
您可以透過更改字體和格式化文字來自訂報表的外觀。 以下章節說明了如何格式化報表中列和欄的外觀。

### <a name="manage-font-styles"></a>管理字體樣式

您可以為報表建立和修改字體樣式。 然後，您可以將這些樣式套用到文件或報表上的特定列或欄。

<table>
<tbody>
<tr>
<td><strong>建立字體樣式</strong></td>
<td>
<ol>
<li>在 Report Designer 中，在<strong>格式</strong>選單，點選<strong>樣式和格式</strong>。</li>
<li>在<strong>樣式和格式</strong>對話方塊，點選<strong>新建</strong>，然後輸入新樣式的唯一名稱。</li>
<li>進行字體選取，然後點選<strong>確定</strong>。</li>
</ol>
</td>
</tr>
<tr>
<td><strong>修改字體樣式</strong></td>
<td>
<ol>
<li>在 Report Designer 中，在<strong>格式</strong>選單，點選<strong>樣式和格式</strong>。</li>
<li>在<strong>樣式和格式</strong>對話方塊，選取要修改的樣式，然後點選<strong>修改</strong>。</li>
<li>進行字體選取，然後點選<strong>確定</strong>。</li>
</ol>
</td>
</tr>
<tr>
<td><strong>套用字體樣式</strong></td>
<td>
<ol>
<li>在 Report Designer 中，在定義或欄定義中，或者在頁頭和頁尾中，選取一個或多個儲存格。</li>
<li>在<strong>樣式</strong>在工具列上的清單中，選取一種字體樣式。</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>格式化行文字

在列定義中指定的格式會覆寫在欄定義和報表定義中指定的任何格式。 您可以使用格式工具列上的控制項來修改文字格式。 這些控制項是標準的 Microsoft Windows 控制項。

1. 在 Report Designer 中，打開列定義做修改。
2. 選取要格式化的儲存格。 若要選取多個儲存格，請在選取儲存格時按住 Ctrl 鍵。
3. 點選要套用的格式的工具列按鈕。 例如，若要縮進一列，選取該列，然後點選 **增加縮進**![增加縮進。](media/indent.gif "增加縮排") 在工具列上。

### <a name="adjust-columns-while-you-design-reports"></a>在設計報表時調整欄

為了更輕鬆地查看您在列定義中處理的資料欄，您可以調整欄寬，還可以在檢視表窗格中隱藏 (最小化) 或顯示欄。 您所做的修改僅影響資料欄的螢幕外觀。 它們不會影響報表上的欄格式。

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>更改檢視表窗格中欄寬

1. 在 Report Designer 中，打開列定義做修改。
2. 在 **格式** 選單，選取 **欄寬**。
3. 在 **欄寬** 對話方塊，輸入一個值，然後點選 **確定**。 或者，您可以拖曳欄標題儲存格的右邊界來更改欄寬。

### <a name="hide-columns-in-the-view-pane"></a>隱藏檢視表窗格中的資料欄

1. 在 Report Designer 中，打開列定義做修改。
2. 選取資料欄或要最小化的資料欄。
3. 按右鍵點選，然後點選 **隱藏**。

### <a name="show-all-hidden-columns-in-the-view-pane"></a>在檢視表窗格中顯示所有隱藏的資料欄

1. 在 Report Designer 中，打開列定義做修改。
2. 按右鍵點選要顯示的最小化資料欄，然後點選 **取消隱藏**。


## <a name="additional-resources"></a>其他資源

[財務報表](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]