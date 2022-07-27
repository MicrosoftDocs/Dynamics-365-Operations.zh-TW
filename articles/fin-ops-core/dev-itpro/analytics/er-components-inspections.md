---
title: 檢查設定的 ER 組件以防止執行階段問題
description: 本主題說明如何檢查已設定的電子報表 (ER) 組件以防止可能發生的執行階段問題。
author: NickSelin
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c63ffc6316d21d36bb2aad57194b8aa1c477607e
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460549"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>檢查設定的 ER 組件以防止執行階段問題

[!include[banner](../includes/banner.md)]

每一個設定[電子報表 (ER)](general-electronic-reporting.md)[格式](er-overview-components.md#format-components-for-outgoing-electronic-documents)和[模型對應](er-overview-components.md#model-mapping-component)組件可以在設計階段[驗證](er-fillable-excel.md#validate-an-er-format)。 在此驗證期間，將執行一致性檢查以幫助防止可能發生的執行階段問題，例如執行錯誤和效能下降。 對於發現的每個問題，檢查作業都會提供有問題元素的路徑。 對於某些問題，可以使用自動修復。

在預設情況下，對於包含前面提到的 ER 組件的 ER 設定，在以下情況下會自動套用驗證作業：

- 您將新[版本](general-electronic-reporting.md#component-versioning)的 ER 設定[匯入](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally)到您的 Microsoft Dynamics 365 Finance 執行個體中。
- 您將可編輯 ER 設定的 [狀態](general-electronic-reporting.md#component-versioning)從 **草稿** 更改到 **已完成**。
- 您透過套用新的基底版本[重訂基底](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase)可編輯的 ER 設定。

您可以顯式執行此驗證。 選取以下三個選項的其中一個，然後按照提供的步驟操作：

- 選項 1：

    1. 進入 **組織管理\>電子報表\>設定**。
    2. 在左側窗格的設定樹狀結構中，選取包含 ER 格式或 ER 模型對應組件的所需 ER 設定。
    3. 在 **版本** FastTab 上，選取所選 ER 設定的所需版本。
    4. 在動作窗格上，選取 **驗證**。

- 選項 2，用於 ER 格式：

    1. 進入 **組織管理\>電子報表\>設定**。
    2. 在左側窗格的設定樹狀結構中，選取包含 ER 格式組件的所需 ER 設定。
    3. 在 **版本** FastTab 上，選取所選 ER 設定的所需版本。
    4. 在動作窗格上，選取 **設計工具**。
    5. 在 **格式設計工具** 頁面上，在動作窗格上，選取 **驗證**。

- 選項 3，用於 ER 模型對應：

    1. 進入 **組織管理\>電子報表\>設定**。
    2. 在左側窗格的設定樹狀結構中，選取包含 ER 模型對應組件的所需 ER 設定。
    3. 在 **版本** FastTab 上，選取所選 ER 設定的所需版本。
    4. 在動作窗格上，選取 **設計工具**。
    5. 在 **對資料來源對應建模** 頁面上，在動作窗格上，選取 **設計工具**。
    6. 在 **對對應設計工具建模** 頁面上，在動作窗格上，選取 **驗證**。

若要在匯入設定時跳過驗證，請按照以下步驟操作。

1. 進入 **組織管理\>電子報表\>設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 將 **匯入後驗證設定** 選項設定為 **否**。

若要在更改或重訂基底版本狀態時跳過驗證，請按照以下步驟操作。

1. 進入 **組織管理\>電子報表\>設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 將 **在設定的狀態更改和重訂基底時跳過驗證** 選項設定為 **是**。

ER 使用以下類別對一致性檢查檢查分組：

- **可執行性** – 檢測執行時可能發生之關鍵問題的檢查。 這些問題大多在 **錯誤** 層級。 
- **效能** – 檢測可能導致已設定 ER 組件執行效率降低之問題的檢查。 這些問題大多在 **警告** 層級。
- **資料完整性** – 檢測可能導致資料遺失或執行階段出錯之問題的檢查。 這些問題大多在 **警告** 層級。

## <a name="list-of-inspections"></a>檢查清單

下表概述了 ER 提供的檢查。 如需這些檢查的相關資訊，請使用第一資料欄中的連結進入本主題的相關區段。 這些區段解釋了 ER 提供檢查的組件類型以及如何重新設定 ER 組件以幫助預防問題。

<table>
<thead>
<tr>
<th>姓名</th>
<th>類別</th>
<th>等級</th>
<th>訊息</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>類型轉換</a></td>
<td>可執行性</td>
<td>錯誤</td>
<td>
<p>無法將類型&lt;類型&gt;的運算式轉換到類型&lt;類型&gt;欄位。</p>
<p><b>執行階段錯誤：</b>類型例外狀況</p>
</td>
</tr>
<tr>
<td><a href='#i2'>類型相容性</a></td>
<td>可執行性</td>
<td>錯誤</td>
<td>
<p>已設定的運算式不能用作現行格式元素到資料來源的繫結，因為此運算式返回資料類型&lt;類型&gt;的值，其超出資料類型範圍，並由類型&lt;類型&gt;的現行格式元素支援。</p>
<p><b>執行階段錯誤：</b>類型例外狀況</p>
</td>
</tr>
<tr>
<td><a href='#i3'>缺少設定元素</a></td>
<td>可執行性</td>
<td>錯誤</td>
<td>
<p>找不到路徑&lt;路徑&gt;。</p>
<p><b>執行階段錯誤：</b>找不到設定&lt;路徑&gt;的元素</p>
</td>
</tr>
<tr>
<td><a href='#i4'>含 FILTER 函數運算式的可執行性</a></td>
<td>可執行性</td>
<td>錯誤</td>
<td>
<p>不可查找 FILTER 函數的運算式清單。</p>
<p><b>執行階段錯誤：</b>不支援篩選。 驗證設定以獲取此內容的相關詳情。</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>GROUPBY 資料來源的可執行性</a></td>
<td>可執行性</td>
<td>錯誤</td>
<td>路徑&lt;路徑&gt;不支援查找。</td>
</tr>
<tr>
<td>可執行性</td>
<td>錯誤</td>
<td>
<p>不能透過查找執行分組函數。</p>
<p><b>執行階段錯誤：</b>不能透過查找執行分組函數。</p>
</td>
</tr>
<tr>
<td><a href='#i6'>JOIN 資料來源的可執行性</a></td>
<td>可執行性</td>
<td>錯誤</td>
<td>
<p>無法加入清單&lt;路徑&gt;，那不是查找中的篩選。</p>
<p><b>執行階段錯誤：</b>Function Joined 資料來源應該是篩選條件運算式導出欄位被錯誤調用。</p>
</td>
</tr>
<tr>
<td><a href='#i7'>FILTER 與 WHERE 函數的合適性</a></td>
<td>效能</td>
<td>警告</td>
<td>從效能的角度來看，使用運算式的 FILTER 函數比 WHERE 更合適。 選取修復以自動替換它。</td>
</tr>
<tr>
<td><a href='#i8'>ALLITEMSQUERY 與 ALLITEMS 函數的合適性</a></td>
<td>效能</td>
<td>警告</td>
<td>從效能的角度來看，使用運算式的 ALLITEMSQUERY 函數比 ALLITEMS 更合適。 選取修復以自動替換它。</td>
</tr>
<tr>
<td><a href='#i9'>空白清單案例的考慮</a></td>
<td>可執行性</td>
<td>警告</td>
<td>
<p>清單&lt;路徑&gt;對空白清單案例沒有任何檢查，它可能會在執行階段產生錯誤。 新增對空白清單案例的檢查。</p>
<p><b>執行階段錯誤：</b>清單在&lt;路徑&gt;為空白</p>
<p><b><a href='#i9a'>潛在問題</a>：</b>該行已填入過一次，而填入的資料來源包含多條記錄</p>
</td>
</tr>
<tr>
<td><a href='#i10'>含 FILTER 函數運算式的可執行性 (快取)</a></td>
<td>可執行性</td>
<td>錯誤</td>
<td>
<p>FILTER 函數不能套用於所選類型的資料來源。 資料表記錄類型的資料來源只有在沒有快取且沒有手動新增的巢狀資料來源的情況下才適用。</p>
<p><b>執行階段錯誤：</b>不支援篩選。 驗證設定以獲取此內容的相關詳情。</p>
</td>
</tr>
<tr>
<td><a href='#i11'>缺少繫結程序</a></td>
<td>可執行性</td>
<td>警告</td>
<td>
<p>路徑&lt;路徑&gt;在使用模型的對應時沒有繫結到任何資料來源。</p>
<p><b>執行階段錯誤：</b>路徑&lt;路徑&gt;不受約束</p>
</td>
</tr>
<tr>
<td><a href='#i12'>未連結的範本</a></td>
<td>資料完整性</td>
<td>警告</td>
<td>檔案&lt;名稱&gt;未連結到任何檔案組件，並且在更改設定版本狀態後將被移除。</td>
</tr>
<tr>
<td><a href='#i13'>不同步格式</a></td>
<td>資料完整性</td>
<td>警告</td>
<td>Excel 工作表&lt;工作表名稱&gt;中的定義名稱&lt;組件名稱&gt;不存在</td>
</tr>
<tr>
<td><a href='#i14'>不同步格式</a></td>
<td>資料完整性</td>
<td>警告</td>
<td>
<p>&lt;標記的 Word 內容控制&gt;標記在 Word 範本檔案中不存</p>
<p><b>執行階段錯誤：</b>&lt;標記的 Word 內容控制&gt;標記在 Word 範本檔案中不存。</p>
</td>
</tr>
<tr>
<td><a href='#i15'>沒有預設對應</a></td>
<td>資料完整性</td>
<td>錯誤</td>
<td>
<p>設定&lt;由逗號分隔的設定名稱&gt;中的&lt;模型名稱 (根描述項) &gt;資料模型存在多個模型對應。 將其中一項組態設定為預設值</p>
<p><b>執行階段錯誤：</b>設定&lt;由逗號分隔的設定名稱&gt;中的&lt;模型名稱 (根描述項) &gt;資料模型存在多個模型對應。 將其中一項組態設定為預設值。</p>
</td>
</tr>
<tr>
<td><a href='#i16'>頁首或頁尾組件的設定不一致</a></td>
<td>資料完整性</td>
<td>錯誤</td>
<td>
<p>頁首/頁尾 (&lt;組件類型：頁首或頁尾&gt;) 不一致</p>
<p><b>執行階段：</b>如果執行已設定 ER 格式的草稿版本，則在執行階段使用最後設定的組件。</p>
</td>
</tr>
<tr>
<td><a href='#i17'>Page 組件設定不一致</a></td>
<td>資料完整性</td>
<td>錯誤</td>
<td>有兩個以上沒有複寫的範圍組件。 請移除不必要的組件。</td>
</tr>
<tr>
<td><a href='#i18'>含 ORDERBY 函數運算式的可執行性</a></td>
<td>可執行性</td>
<td>錯誤</td>
<td>
<p>不可查找 ORDERBY 函數的運算式清單。</p>
<p><b>執行階段錯誤：</b>不支援排序。 驗證設定以獲取此內容的相關詳情。</p>
</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>類型轉換

ER 檢查資料模型欄位的資料類型是否與設定為該欄位繫結的運算式的資料類型相容。 如果資料類型不相容，則 ER 模型對應設計工具中會出現驗證錯誤。 您收到的訊息指出 ER 無法將 A 類型的運算式轉換為 B 類型的欄位。

以下步驟顯示了此問題是如何發生的。

1. 開始同時設定 ER 資料模型和 ER 模型對應組件。
2. 在資料模型樹狀結構中，新增名為 **X** 的欄位，並選取 **整數** 作為資料類型。

    ![將 X 欄位和整數資料類型新增到資料模型頁面的資料模式樹狀結構中。](./media/er-components-inspections-01.png)

3. 在模型對應設計工具中，在 **資料來源** 窗格中，新增 **導出欄位** 類型的資料來源。
4. 將新資料來源名稱命名為 **Y**，並做設定好讓它包含運算式 `INTVALUE(100)`。
5. 將 **X** 繫結到 **Y**。
6. 在資料模型設計工具中，將 **X** 欄位的資料類型從 **整數** 更改為 **Int64**。
7. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件。

    ![驗證模型對應設計工具頁面上的可編輯模型對應組件。](./media/er-components-inspections-01.gif)

8. 選取 **驗證** 來檢查 **設定** 頁面上的所選 ER 設定的模型對應組件。

    ![檢查設定頁面上的模型對應組件。](./media/er-components-inspections-01a.png)

9. 請注意，發生了驗證錯誤。 該訊息指出，**整數** 類型的值，其 **Y** 資料來源的 `INTVALUE(100)` 運算式會返回，無法儲存在 **Int64** 類型的 **X** 資料模型欄位中。

下圖顯示了如果您忽略警告便會發生的執行階段錯誤，並選取 **執行** 來執行設定使用模型對應的格式。

![格式設計工具頁面上的執行階段錯誤。](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

透過更改資料模型欄位的資料類型來更新資料模型結構，使其與為該欄位繫結設定運算式的資料類型相符。 對於前面的範例，**X** 欄位的資料類型必須改回 **整數**。

#### <a name="option-2"></a>選項 2

透過更改與資料模型欄位繫結的資料來源的運算式來更新模型對應。 對於前面的範例，運算式 **Y** 資料來源必須改為 `INT64VALUE(100)`。

## <a name="type-compatibility"></a><a id="i2"></a>類型相容性

ER 檢查格式元素的資料類型是否與設定為該格式元素繫結的運算式的資料類型相容。 如果資料類型不相容，則 ER 作業設計工具中會出現驗證錯誤。 您收到的訊息表示已設定的運算式不能用作現行格式元素到資料來源的繫結，因為該運算式返回資料類型 A 的值，其超出資料類型範圍，並由類型 B 的現行格式元素支援。

以下步驟顯示了此問題是如何發生的。

1. 開始同時設定 ER 資料模型和 ER 格式組件。
2. 在資料模型樹狀結構中，新增名為 **X** 的欄位，並選取 **整數** 作為資料類型。
3. 在格式結構樹中，新增 **數字** 類型的格式元素。
4. 命名新格式元素 **Y**。在 **數字類型** 欄位中，選取 **整數** 作為資料類型。
5. 將 **X** 繫結到 **Y**。
6. 在格式結構樹中，將 **Y** 格式元素的資料類型從 **整數** 更改到 **Int64**。
7. 選取 **驗證** 來檢查 **格式設計工具** 頁面上的可編輯格式組件。

    ![在格式設計工具頁面上驗證類型相容性。](./media/er-components-inspections-02.gif)

8. 請注意，發生了驗證錯誤。 該訊息指出已設定的運算式只能接受 **Int64** 值。 因此，**整數** 類型的 **X** 資料模型欄位的值不能輸入至 **Y** 格式元素。

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

透過更改 **數字** 格式元素的資料類型來更新格式結構，使其與為該元素繫結設定運算式的資料類型相符。 在前面的範例中，**X** 格式元素的 **數字類型** 值必須改回 **整數**。

#### <a name="option-2"></a>選項 2

透過將運算式從 `model.X` 更改到 `INT64VALUE(model.X)`，更新 **X** 格式元素的格式對應。

## <a name="missing-configuration-element"></a><a id="i3"></a>缺少設定元素

ER 檢查繫結運算式是否僅包含在可編輯 ER 組件中設定的資料來源。 對於每個包含可編輯 ER 組件中缺少資料來源的繫結程序，在 ER 作業設計工具或 ER 模型對應設計工具中會發生驗證錯誤。

以下步驟顯示了此問題是如何發生的。

1. 開始同時設定 ER 資料模型和 ER 模型對應組件。
2. 在資料模型樹狀結構中，新增名為 **X** 的欄位，並選取 **整數** 作為資料類型。

    ![含 X 欄位的資料模型以及資料模型頁面上的整數資料類型。](./media/er-components-inspections-01.png)

3. 在模型對應設計工具中，在 **資料來源** 窗格中，新增 **導出欄位** 類型的資料來源。
4. 將新資料來源名稱命名為 **Y**，並做設定好讓它包含運算式 `INTVALUE(100)`。
5. 將 **X** 繫結到 **Y**。
6. 在模型對應設計工具中，在 **資料來源** 窗格，刪除 **Y** 資料來源。
7. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件。

    ![檢查模型對應設計工具頁面上的可編輯 ER 模型對應組件。](./media/er-components-inspections-03.gif)

8. 請注意，發生了驗證錯誤。 該訊息指出，**X** 資料模型欄位的繫結程序包含參考 **Y** 資料來源的路徑，但找不到此資料來源。

### <a name="automatic-resolution"></a>自動化解決方案

選取 **解開繫結**，透過移除遺失的資料來源繫結程序來自動修復此問題。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

解開 **X** 資料模型欄位的繫結以停止參考不存在的 **Y** 資料來源。

#### <a name="option-2"></a>選項 2

在模型對應設計工具中，在 **資料來源** 窗格，再次新增 **Y** 資料來源。

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>含 FILTER 函數運算式的可執行性

內建的[FILTER](er-functions-list-filter.md)ER 函數用於存取應用程式資料表、視圖或資料執行個體，方法是透過單次 SQL 調用來獲取所需資料作為記錄清單。 **記錄清單** 類型的資料來源用作此函數的引數並指定調用的應用程式來源。 ER 可檢查 SQL 直接查找是否可以建立到 `FILTER` 函數中所參考的資料來源。 如果無法建立直接查找，則 ER 模型對應設計工具中會出現驗證錯誤。 您收到的訊息指出包含 `FILTER` 函數的 ER 運算式不能在執行階段執行。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 模型對應組件。
2. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
3. 命名新資料來源 **Vendor**。 在 **資料表** 欄位中，選取 **VendTable** 以指定此資料來源將要求 VendTable 資料表。
4. 新增 **導出欄位** 類型的資料來源。
5. 將新資料來源命名為 **FilteredVendor**，並做設定好讓它包含運算式 `FILTER(Vendor, Vendor.AccountNum="US-101")`。
6. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件並驗證是否可以查找 **廠商** 資料來源中的 `FILTER(Vendor, Vendor.AccountNum="US-101")` 運算式。
7. 透過新增 **導出欄位** 類型的巢狀欄位來獲取調整後的廠商帳號，修改 **廠商** 資料來源。
8. 將新巢狀欄位命名為 **$AccNumber**，並做設定好讓它包含運算式 `TRIM(Vendor.AccountNum)`。
9. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件並驗證是否可以查找 **廠商** 資料來源中的 `FILTER(Vendor, Vendor.AccountNum="US-101")` 運算式。

    ![驗證是否可以在模型對應設計工具頁面上查找含 FILTER 函數的運算式。](./media/er-components-inspections-04.gif)

10. 請注意，驗證錯誤的發生是因為 **廠商** 資料來源包含 **導出欄位** 類型的巢狀欄位，其不允許 **FilteredVendor** 資料類型的運算式轉換到 SQL 直接查找陳述式。

下圖顯示了如果您忽略警告便會發生的執行階段錯誤，並選取 **執行** 來執行設定使用模型對應的格式。

![在格式設計工具頁面上執行可編輯格式時發生的執行階段錯誤。](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

將 **$AccNumber** 巢狀欄位新增至 **FilteredVendor** 資料來源，並做設定好讓它包含運算式 `TRIM(FilteredVendor.AccountNum)`，而不是將 **導出欄位** 類型的巢狀欄位新增至 **廠商** 資料來源。 這樣，`FILTER(Vendor, Vendor.AccountNum="US-101")`運算式可以在 SQL 層級執行並之後計算 **$AccNumber** 巢狀欄位。

#### <a name="option-2"></a>選項 2

將 **FilteredVendor** 資料來源的運算式從 `FILTER(Vendor, Vendor.AccountNum="US-101")` 變更至 `WHERE(Vendor, Vendor.AccountNum="US-101")`。 對於資料量大的資料表 (交易資料表)，我們不建議您更改運算式，因為會擷取所有記錄，並在記憶體中完成所需記錄的選擇。 因此，這種方法可能會導致效能不佳。 如需相關資訊，請參閱[WHERE ER 函數 ](er-functions-list-where.md)。

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>GROUPBY 資料來源的可執行性

**GROUPBY** 資料來源將查找結果分成多組記錄，通常是為了對每組進行一次或多次彙總。 每一個 **GROUPBY** 資料來源皆可以設定，使其在資料庫層級或記憶體中執行。 當 **GROUPBY** 資料來源已設定，使其在資料庫層級執行，ER 檢查是否可以針對該資料來源中參考的資料來源建立 SQL 直接查找。 如果無法建立直接查找，則 ER 模型對應設計工具中會出現驗證錯誤。 您收到的訊息指出已設定的 **GROUPBY** 資料來源不能在執行階段執行。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 模型對應組件。
2. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
3. 命名新資料來源 **Trans**。在 **資料表** 欄位中，選取 **VendTrans** 來指定此資料來源將要求 VendTrans 資料表。
4. 新增 **分組依據** 類型的資料來源。
5. 命名新資料來源 **GroupedTrans**，並透過以下方式設定：

    - 選取 **Trans** 資料來源作為應分組的記錄來源。
    - 在 **執行位置** 欄位，選取 **查找** 來指定您想要在資料庫層級執行此資料來源。

    ![在 Edit 'Group By' 參數頁面上設定資料來源。](./media/er-components-inspections-05a.gif)

6. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件並驗證是否可以查找已設定的 **GroupedTrans** 資料來源。
7. 透過新增 **導出欄位** 類型的巢狀欄位來獲取調整後的廠商帳號，修改 **Trans** 資料來源。
8. 將新資料來源命名為 **$AccNumber**，並做設定好讓它包含運算式 `TRIM(Trans.AccountNum)`。

    ![在模型對應設計工具頁面上設定資料來源。](./media/er-components-inspections-05a.png)

9. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件並驗證是否可以查找已設定的 **GroupedTrans** 資料來源。

    ![驗證 ER 模型對應組件並驗證是否可以在模型對應設計工具頁面上查找 GroupedTrans 資料來源。](./media/er-components-inspections-05b.png)

10. 請注意，驗證錯誤的發生是因為 **Trans** 資料來源包含 **導出欄位** 類型的巢狀欄位，其不允許調用 **GroupedTrans** 資料來源來轉換到 SQL 直接查找陳述式。

下圖顯示了如果您忽略警告便會發生的執行階段錯誤，並選取 **執行** 來執行設定使用模型對應的格式。

![在格式設計工具頁面上忽略警告時發生的執行階段錯誤。](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

將 **$AccNumber** 巢狀欄位新增將 **GroupedTrans** 資料來源的 **GroupedTrans.lines** 項目，並做設定好讓它包含運算式 `TRIM(GroupedTrans.lines.AccountNum)`，而不是將 **導出欄位** 類型的巢狀欄位新增至 **Trans** 資料來源。 在這情況下，**GroupedTrans** 資料來源可以在 SQL 層級執行並之後計算 **$AccNumber** 巢狀欄位。

#### <a name="option-2"></a>選項 2

將 **GroupedTrans** 資料來源的 **執行位置** 欄位的值從 **查找** 更改到 **在記憶體中**。 對於資料量大的資料表 (交易資料表)，我們不建議您更改值，因為會擷取所有記錄，並在記憶體中完成分組和彙總動作。 因此，這種方法可能會導致效能不佳。

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>JOIN 資料來源的可執行性

[JOIN](er-join-data-sources.md) 資料來源根據相關欄位結合來自兩個或多個資料庫資料表的記錄。 每一個 **JOIN** 資料來源皆可以設定，使其在資料庫層級或記憶體中執行。 當 **JOIN** 資料來源已設定，使其在資料庫層級執行，ER 檢查是否可以針對該資料來源中參考的資料來源建立 SQL 直接查找。 如果無法在至少有一個參考資料來源下建立 SQL 直接查找，則 ER 模型對應設計工具中會出現驗證錯誤。 您收到的訊息指出已設定的 **JOIN** 資料來源不能在執行階段執行。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 模型對應組件。
2. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
3. 命名新資料來源 **Vendor**。 在 **資料表** 欄位中，選取 **VendTable** 以指定此資料來源將要求 VendTable 資料表。
4. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
5. 命名新資料來源 **Trans**。在 **資料表** 欄位中，選取 **VendTrans** 來指定此資料來源將要求 VendTrans 資料表。
6. 將 **導出欄位** 類型的資料來源新增為 **廠商** 資料來源的巢狀欄位。
7. 將新資料來源命名為 **FilteredTrans**，並做設定好讓它包含運算式 `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`。
8. 新增 **加入** 類型的資料來源。
9. 將新資料來源命名為 **JoinedList**，並透過以下方式設定：

    1. 將 **廠商** 資料來源新增為要加入的第一組記錄。
    2. 將 **Vendor.FilteredTrans** 資料來源新增為要加入的第二組記錄。 選取 **INNER** 作為類型。
    3. 在 **執行** 欄位，選取 **查找** 來指定您想要在資料庫層級執行此資料來源。

    ![在加入設計工具頁面上設定資料來源。](./media/er-components-inspections-06a.gif)

10. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件並驗證是否可以查找已設定的 **JoinedList** 資料來源。
11. 將 **Vendor.FilteredTrans** 資料來源的運算式從 `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` 變更至 `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`。
12. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件並驗證是否可以查找已設定的 **JoinedList** 資料來源。

    ![驗證可編輯的模型對應組件並驗證是否可以在模型對應設計工具頁面上查找 JoinedList 資料來源。](./media/er-components-inspections-06b.png)

13. 請注意，發生了驗證錯誤，因為 **Vendor.FilteredTrans** 資料來源的運算式無法轉換為 SQL 直接調用。 此外，SQL 直接調用不允許調用 **JoinedList** 資料來源來轉換成 SQL 直接陳述式。

    ![模型對應設計工具頁面上的 JoinedList 資料來源驗證失敗導致執行階段錯誤。](./media/er-components-inspections-06c.png)

下圖顯示了如果您忽略警告便會發生的執行階段錯誤，並選取 **執行** 來執行設定使用模型對應的格式。

![在格式設計工具頁面上執行可編輯格式。](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

將 **Vendor.FilteredTrans** 資料來源的運算式從 `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` 改回至 `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`，如警告建議所述。

![在模型對應設計工具頁面上更新資料來源的運算式。](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>選項 2

將 **JoinedList** 資料來源的 **執行** 欄位的值從 **查找** 更改到 **在記憶體中**。 對於資料量大的資料表 (交易資料表)，我們不建議您更改值，因為會擷取所有記錄，並在記憶體中發生加入動作。 因此，這種方法可能會導致效能不佳。 將顯示驗證警告以通知您此風險。

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>FILTER 與 WHERE 函數的合適性

內建的[FILTER](er-functions-list-filter.md)ER 函數用於存取應用程式資料表、視圖或資料執行個體，方法是透過單次 SQL 調用來獲取所需資料作為記錄清單。 [WHERE](er-functions-list-where.md) 函數從給定的來源中擷取所有記錄並在記憶體中進行記錄選擇。 **記錄清單** 類型的資料來源用作兩個函數的引數並指定取得記錄的來源。 ER 可檢查 SQL 直接調用是否可以建立到 **WHERE** 函數中所參考的資料來源。 如果無法建立直接調用，則 ER 模型對應設計工具中會出現驗證警告。 您收到的訊息建議您使用 **FILTER** 函數而不是 **WHERE** 函數來提高效率。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 模型對應組件。
2. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
3. 命名新資料來源 **Trans**。在 **資料表** 欄位中，選取 **VendTrans** 來指定此資料來源將要求 VendTrans 資料表。
4. 將 **導出欄位** 類型的資料來源新增為 **廠商** 資料來源的巢狀欄位。
5. 將新資料來源命名為 **FilteredTrans**，並做設定好讓它包含運算式 `WHERE(Trans, Trans.AccountNum="US-101")`。
6. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
7. 命名新資料來源 **Vendor**。 在 **資料表** 欄位中，選取 **VendTable** 以指定此資料來源將要求 VendTable 資料表。
8. 新增 **導出欄位** 類型的資料來源。
9. 將新資料來源命名為 **FilteredVendor**，並做設定好讓它包含運算式 `WHERE(Vendor, Vendor.AccountNum="US-101")`。
10. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件。

    ![檢查模型對應設計工具頁面上的可編輯模型對應組件。](./media/er-components-inspections-07a.png)

11. 請注意，驗證警告建議您使用 **FILTER** 函數而不是 **WHERE** 函數供 **FilteredVendor** 和 **FilteredTrans** 資料來源使用。

    ![建議在模型對應設計工具頁面上使用 FILTER 函數而不是 WHERE 函數。](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>自動化解決方案

選取 **修復** 自動將 **WHERE** 函數替換為供此檢查類型使用並出現在 **警告** 索引標籤上的隔線，以及在所有資料來源的運算式中的 **FILTER** 函數。

或者，您可以在格線中選取單一警告資料列，然後選取 **選定修復**。 在這種情況下，運算式僅在所選警告中提到的資料來源中自動更改。

![選取修復以便在模型對應設計工具頁面上自動將 WHERE 函數替換為 FILTER 函數。](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>手動解決方案

您可以在驗證格線中手動調整所有資料來源的運算式，方法是將 **WHERE** 函數替換為 **FILTER** 函數。

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>ALLITEMSQUERY 與 ALLITEMS 函數的合適性

內建 [ALLITEMS](er-functions-list-allitems.md) 和 [ALLITEMSQUERY](er-functions-list-allitemsquery.md) ER 函數返回由記錄清單組成的展平 **記錄清單** 值，其中記錄清單表示與指定路徑相符的所有項目。 ER 可檢查 SQL 直接調用是否可以建立到 **ALLITEMS** 函數中所參考的資料來源。 如果無法建立直接調用，則 ER 模型對應設計工具中會出現驗證警告。 您收到的訊息建議您使用 **ALLITEMSQUERY** 函數而不是 **ALLITEMS** 函數來提高效率。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 模型對應組件。
2. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
3. 命名新資料來源 **Vendor**。 在 **資料表** 欄位中，選取 **VendTable** 以指定此資料來源將要求 VendTable 資料表。
4. 新增資料來源 **導出欄位** 類型以取得多筆廠商的記錄。
5. 將新資料來源命名為 **FilteredVendor**，並做設定好讓它包含運算式 `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))`。
6. 新增 **導出欄位** 類型的資料來源以取得所有已篩選廠商的交易。
7. 將新資料來源命名為 **FilteredVendorTrans**，並做設定好讓它包含運算式 `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')`。
8. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件。

    ![檢查模型對應設計工具頁面上的可編輯模型對應組件。](./media/er-components-inspections-08a.png)

9. 請注意，發生了驗證警告。 該訊息建議您使用 **ALLITEMSQUERY** 函數而不是 **ALLITEMS** 函數供 **FilteredVendorTrans** 資料來源使用。

    ![建議在模型對應設計工具頁面上使用 ALLITEMSQUERY 函數而不是 ALLITEMS 函數。](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>自動化解決方案

選取 **修復** 自動將 **ALLITEMS** 函數替換為供此檢查類型使用並出現在 **警告** 索引標籤上的隔線，以及在所有資料來源的運算式中的 **ALLITEMSQUERY** 函數。

或者，您可以在格線中選取單一警告資料列，然後選取 **選定修復**。 在這種情況下，運算式僅在所選警告中提到的資料來源中自動更改。

![選取模型對應設計工具頁面上選取的修復動作。](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>手動解決方案

您可以手動調整在驗證格線中提及的所有資料來源的運算式，方法是將 **ALLITEMS** 函數替換為 **ALLITEMSQUERY** 函數。

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>空白清單案例的考慮

您可以設定您的 ER 格式或模型對應組件以取得 **記錄清單** 類型資料來源的欄位值。 ER 檢查您的設計是否考慮了調用的資料來源不包含記錄 (即為空白) 的情況，以防止從無記錄的欄位中擷取值時出現執行階段錯誤。

以下步驟顯示了此問題是如何發生的。

1. 開始同時設定 ER 資料模型、ER 模型對應組件，以及 ER 格式組件。
2. 在資料模型樹狀結構中，新增一個名為 **Root3** 的根項目。
3. 修改 **Root3** 項目，方法是新增 **記錄清單** 類型的巢狀項目。
4. 命名新的巢狀項目 **廠商**。
5. 按照下列方式修改 **廠商** 項目：

    - 新增 **字串** 類型的巢狀欄位，並將其命名為 **Name**。
    - 新增 **字串** 類型的巢狀欄位，並將其命名為 **AccountNumber**。

    ![在資料模型頁面上新增巢狀欄位。](./media/er-components-inspections-09a.png)

6. 在模型對應設計工具中，在 **資料來源** 窗格中，新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
7. 命名新資料來源 **Vendor**。 在 **資料表** 欄位中，選取 **VendTable** 以指定此資料來源將要求 VendTable 資料表。
8. 新增 **一般\\使用者輸入參數** 類型的資料來源，在執行階段對話方塊中搜尋廠商帳戶。
9. 命名新資料來源 **RequestedAccountNum**。 在 **標籤** 欄位，輸入 **Vendor account number**。 在 **作業資料類型名稱** 欄位中，保留預設值，**描述**。
10. 新增 **導出欄位** 類型的資料來源以篩選被查找的廠商。
11. 將新資料來源命名為 **FilteredVendor**，並做設定好讓它包含運算式 `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`。
12. 透過以下方式將資料模型項目繫結到設定的資料來源：

    - 將 **FilteredVendor** 繫結到 **Vendor**。
    - 將 **FilteredVendor.AccountNum** 繫結到 **Vendor.AccountNumber**。
    - 將 **FilteredVendor.'name()'** 繫結到 **Vendor.Name**。

    ![在模型對應設計工具頁面上繫結資料模型項目。](./media/er-components-inspections-09b.png)

13. 在格式結構樹中，新增以下項目以產生包含廠商詳情的 XML 格式的輸出文件：

    1. 新增 **陳述式** 根 XML 元素。
    2. 針對 **陳述式** XML 元素，新增巢狀 **合作對象** XML 元素。
    3. 針對 **合作對象** XML 元素，新增以下巢狀 XML 屬性：

        - 姓名
        - AccountNum

14. 透過以下方式將格式元素繫結到提供的資料來源：

    - 將 **Statement\\Party\\Name** 格式元素繫結到 **model.Vendor.Name** 資料來源欄位。
    - 將 **Statement\\Party\\AccountNum** 格式元素繫結到 **model.Vendor.AccountNumber** 資料來源欄位。

15. 選取 **驗證** 來檢查 **格式設計工具** 頁面上的可編輯格式組件。

    ![在格式設計工具頁面上驗證您繫結到資料來源的格式元素。](./media/er-components-inspections-09c.png)

16. 請注意，發生了驗證錯誤。 該訊息指出，如果 `model.Vendor` 清單為空白，已設定的 **Statement\\Party\\Name** 和 **Statement\\Party\\AccountNum** 格式組件可能會在執行階段引發錯誤。

    ![有關已設定格式組件的潛在錯誤的驗證錯誤。](./media/er-components-inspections-09d.png)

下圖顯示了如果您忽略警告會發生的執行階段錯誤、選取 **執行** 來執行格式，以及選取不存在廠商的帳號。 由於要求的廠商不存在，`model.Vendor` 清單將為空白 (即，它將不包含任何記錄)。

![格式對應執行期間發生的執行階段錯誤。](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>自動化解決方案

對於在 **警告** 索引標籤上格線中的選定資料列，您可以選取 **解開繫結**。 在 **路徑** 資料欄中指向的繫結程序會自動從格式元素中移除。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

您可以將 **Statement\\Party\\Name** 格式元素繫結到 `model.Vendor` 資料來源項目。 在執行階段，此繫結程序先調用 `model.Vendor` 資料來源。 當 `model.Vendor` 返回空白的記錄清單，巢裝的格式元素不會執行。 因此，此格式設定不會出現驗證警告。

![將格式元素繫結到格式設計工具頁面上的資料來源項目。](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>選項 2

將 **Statement\\Party\\Name** 格式元素從 `model.Vendor.Name` 更改到 `FIRSTORNULL(model.Vendor).Name`。 更新後的繫結程序有條件地將 **記錄清單** 類型的 `model.Vendor` 資料來源的第一筆記錄轉換成 **記錄** 類型的新資料來源。 這個新資料來源包含相同的欄位集。

- 如果至少有一筆記錄在 `model.Vendor` 資料來源中，該記錄的欄位則填入上 `model.Vendor` 資料來源第一筆記錄的欄位的值。 在這種情況下，更新後的繫結程序會返回廠商名稱。
- 否則，建立記錄的每個欄位都將填入上該欄位資料類型的預設值。 在這種情況下，空白字串以 **字串** 資料類型的預設值返回。

因此，當 **Statement\\Party\\Name** 格式元素繫結至 `FIRSTORNULL(model.Vendor).Name` 運算式時，不會出現驗證警告。

![更改格式設計工具頁面上的繫結程序解決方案驗證警告。](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>選項 3

如果您想在 **記錄清單** 類型的 `model.Vendor` 資料來源不返回任何記錄 (此範例 **無法提供** 的文字) 時，明確指定已輸入至所產文件的資料，將 `model.Vendor.Name` **Statement\\Party\\Name** 的繫結程序更改為 `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")`。 您也可以使用運算式 `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")`。

### <a name="additional-consideration"></a><a id="i9a"></a>額外考慮

該檢查還警告您另一個潛在問題。 在預設情況下，當您將 **Statement\\Party\\Name** 和 **Statement\\Party\\AccountNum** 格式元素繫結到 **記錄清單** 類型的 `model.Vendor` 資料來源的相應欄位時，便會執行那些繫結程序，而且只要該記錄為空白，則將擷取 `model.Vendor` 資料來源第一筆記錄的相應欄位的值。

因為您沒有將 **Statement\\Party** 格式元素與 `model.Vendor` 資料來源繫結在一起，**Statement\\Party** 元素不會在格式執行過程為 `model.Vendor` 資歷來源的每個記錄反覆。 相反，如果該清單包含多筆記錄，則產生的文件將僅填入來自記錄清單的第一筆記錄的資訊。 因此，如果該格式旨在為產生的文件填入有關所有來自 `model.Vendor` 資料來源的廠商的資訊，則會出現問題。 若要解決此問題，請將 **Statement\\Party** 元素與 `model.Vendor` 資料來源繫結在一起。

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>含 FILTER 函數運算式的可執行性 (快取)

幾個內建的 ER 函數，包括 [FILTERER](er-functions-list-filter.md) 和 [ALLITEMSQUERY](er-functions-list-allitemsquery.md)，是用於存取應用程式資料表、視圖或資料執行個體，方法是透過單次 SQL 調用來獲取所需資料作為記錄清單。 **記錄清單** 類型的資料來源用作每個函數的引數並指定調用的應用程式來源。 ER 可檢查 SQL 直接調用是否可以建立到其中一個函數中所參考的資料來源。 如果因為資料來源被標記為 [cached](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace) 而無法建立直接調用，在 ER 模型對應設計工具中會發生驗證錯誤。 您收到的訊息指出包含其中一個函數的 ER 運算式不能在執行階段執行。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 模型對應組件。
2. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
3. 命名新資料來源 **Vendor**。 在 **資料表** 欄位中，選取 **VendTable** 以指定此資料來源將要求 VendTable 資料表。
4. 新增 **一般\\使用者輸入參數** 類型的資料來源，在執行階段對話方塊中搜尋廠商帳戶。
5. 命名新資料來源 **RequestedAccountNum**。 在 **標籤** 欄位，輸入 **Vendor account number**。 在 **作業資料類型名稱** 欄位中，保留預設值，**描述**。
6. 新增 **導出欄位** 類型的資料來源以篩選被查找的廠商。
7. 將新資料來源命名為 **FilteredVendor**，並做設定好讓它包含運算式 `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`。
8. 將已設定 **廠商** 資料來源標記為快取。

    ![將模型對應設計工具頁面上設定模型對應組件。](./media/er-components-inspections-10a.gif)

9. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件。

    ![在模型對應設計工具頁面上驗證套用於快取的廠商資料來源的 FILTER 函數。](./media/er-components-inspections-10a.png)

10. 請注意，發生了驗證錯誤。 該訊息指出，**FILTER** 函數不能套用於快取的 **廠商** 資料來源。

下圖顯示了如果您忽略警告便會發生的執行階段錯誤，並選取 **執行** 來執行格式。

![在格式設計工具頁面上執行格式對應過程發生的執行階段錯誤。](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

移除來自 **廠商** 資料來源的 **快取** 標幟。 **FilteredVendor** 資料來源之後將變為可執行，但在 VendTable 資料表中參考的 **廠商** 資料來源將在每次 **FilteredVendor** 資料來源被調用時存取。

#### <a name="option-2"></a>選項 2

將 **FilteredVendor** 資料來源的運算式從 `FILTER(Vendor, Vendor.AccountNum="US-101")` 變更至 `WHERE(Vendor, Vendor.AccountNum="US-101")`。 在這種情況下，在 VendTable 資料表中參考的 **廠商** 資料來源將僅在第一次調用 **廠商** 資料來源的過程中存取。 但是，記錄的選擇將在記憶體中完成。 因此，這種方法可能會導致效能不佳。

## <a name="missing-binding"></a><a id="i11"></a>缺少繫結程序

當您設定 ER 格式組件時，將提供基底 ER 資料模型作為 ER 格式的預設資料來源。 在執行已設定的 ER 格式時，基底模型的[預設模型對應](er-country-dependent-model-mapping.md) 會用來將應用程式資料填入在資料模型中。 如果您將格式元素繫結到未綁定到模型對應中的任何資料來源的資料模型項目，ER 格式設計工具會顯示警告，而該模型對應現行被選為可編輯格式的預設模型對應。 這種類型的繫結程序不能在執行階段執行，因為執行的格式不能用應用程式資料填入綁定的元素。 因此，執行階段會發生錯誤。

以下步驟顯示了此問題是如何發生的。

1. 開始同時設定 ER 資料模型、ER 模型對應組件，以及 ER 格式組件。
2. 在資料模型樹狀結構中，新增一個名為 **Root3** 的根項目。
3. 修改 **Root3** 項目，方法是新增 **記錄清單** 類型的巢狀項目。
4. 命名新的巢狀項目 **廠商**。
5. 按照下列方式修改 **廠商** 項目：

    - 新增 **字串** 類型的巢狀欄位，並將其命名為 **Name**。
    - 新增 **字串** 類型的巢狀欄位，並將其命名為 **AccountNumber**。

    ![將巢狀欄位新增到資料模型頁面上的廠商項目。](./media/er-components-inspections-11a.png)

6. 在模型對應設計工具中，在 **資料來源** 窗格中，新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
7. 命名新資料來源 **Vendor**。 在 **資料表** 欄位中，選取 **VendTable** 以指定此資料來源將要求 VendTable 資料表。
8. 新增 **一般\\使用者輸入參數** 類型的資料來源，在執行階段對話方塊中查找廠商帳戶。
9. 命名新資料來源 **RequestedAccountNum**。 在 **標籤** 欄位，輸入 **Vendor account number**。 在 **作業資料類型名稱** 欄位中，保留預設值，**描述**。
10. 新增 **導出欄位** 類型的資料來源以篩選被查找的廠商。
11. 將新資料來源命名為 **FilteredVendor**，並做設定好讓它包含運算式 `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`。
12. 透過以下方式將資料模型項目繫結到設定的資料來源：

    - 將 **FilteredVendor** 繫結到 **Vendor**。
    - 將 **FilteredVendor.AccountNum** 繫結到 **Vendor.AccountNumber**。

    > [!NOTE]
    > **Vendor.Name** 資料模型欄位保持未綁定。

    ![將資料模型項目綁定到已設定的資料來源和在模型對應設計工具頁面上未綁定的資料模式項目。](./media/er-components-inspections-11b.png)

13. 在格式結構樹中，新增以下項目以產生包含被查找廠商詳情的 XML 格式的輸出文件：

    1. 新增 **陳述式** 根 XML 元素。
    2. 針對 **陳述式** XML 元素，新增巢狀 **合作對象** XML 元素。
    3. 針對 **合作對象** XML 元素，新增以下巢狀 XML 屬性：

        - 姓名
        - AccountNum

14. 透過以下方式將格式元素繫結到提供的資料來源：

    - 將 **Statement\\Party** 格式元素繫結到 `model.Vendor` 資料來源項目。
    - 將 **Statement\\Party\\Name** 格式元素繫結到 **model.Vendor.Name** 資料來源欄位。
    - 將 **Statement\\Party\\AccountNum** 格式元素繫結到 **model.Vendor.AccountNumber** 資料來源欄位。

15. 選取 **驗證** 來檢查 **格式設計工具** 頁面上的可編輯格式組件。

    ![在格式設計工具頁面上驗證 ER 格式組件。](./media/er-components-inspections-11c.png)

16. 請注意，發生了驗證警告。 該訊息指出，**model.Vendor.Name** 資料來源欄位未綁定到模型對應中的任何資料來源，其中模型對應已設定按格式來使用。 因此，**Statement\\Party\\Name** 格式元素可能不會在執行階段填入，並且可能會發生執行階段例外狀況。

    ![在格式設計工具頁面上驗證 ER 格式組件。](./media/er-components-inspections-11d.png)

下圖顯示了如果您忽略警告便會發生的執行階段錯誤，並選取 **執行** 來執行格式。

![在格式設計工具頁面上執行可編輯格式。](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

透過新增 **model.Vendor.Name** 資料來源欄位的繫結程序來修改已設定的模型對應。

#### <a name="option-2"></a>選項 2

透過移除 **Statement\\Party\\Name** 格式元素的繫結程序來修改已設定的格式。

## <a name="not-linked-template"></a><a id="i12"></a>未連結的範本

當您 [手動](er-fillable-excel.md#manual-entry)設定 ER 格式組件以使用範本來產生輸出文件時，您必須手動新增 **Excel\\檔案** 元素、將所需的範本新增為可編輯組件的附件，並在新增的 **Excel\\檔案** 元素中選取該附件。 透過這種方式，您表明新增的元素將在執行階段填入所選範本。 當您在 **草稿**[狀態](general-electronic-reporting.md#component-versioning)中設定格式組件版本時，您可以將多個範本新增到可編輯組件中，然後在 **Excel\\檔案** 元素中選取每個範本來執行 ER 格式。 透過這種方式，您可以看到如何在執行階段填入不同的範本。 如果您有未在任何 **Excel\\檔案** 元素中選取的範本，ER 格式設計工具會警告您，當那些範本的狀態從 **草稿** 更改為 **已完成** 時，就會從可編輯 ER 格式組件版本中刪除。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 格式組件。
2. 在格式結構樹中，新增 **Excel\\檔案** 元素。
3. 對於您剛新增的 **Excel\\檔案** 元素，將 Excel 活頁簿檔案，**A.xlsx**，新增為附件。 使用在[ER 參數](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)設定的文件類型來指定 ER 格式範本的儲存體。
4. 對於 **Excel\\檔案** 元素，將另一個 Excel 活頁簿檔案，**B.xlsx**，新增為附件。 使用與活頁簿檔案 A 相同的文件類型。
5. 在 **Excel\\檔案** 元素中，選取活頁簿檔案 A。
6. 選取 **驗證** 來檢查 **格式設計工具** 頁面上的可編輯格式組件。

    ![在格式設計工具頁面上驗證活頁簿檔案的可編輯格式組件。](./media/er-components-inspections-12a.gif)

7. 請注意，發生了驗證警告。 該訊息指出活頁簿檔案 B.xlsx 未連結到任何組件，並且在設定版本的狀態更改後將被移除。

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

透過移除所有未連結到任何 **Excel\\檔案** 元素的範本來修改設定的格式。

## <a name="not-synced-format"></a><a id="i13"></a>不同步格式

當您 [設定](er-fillable-excel.md) ER 格式組件以使用 Excel 範本來產生輸出文件時，您可以手動新增 **Excel\\檔案** 元素、將所需的範本新增為可編輯組件的附件，並在新增的 **Excel\\檔案** 元素中選取該附件。 透過這種方式，您表明新增的元素將在執行階段填入所選範本。 由於新增的 Excel 範本是在外部設計的，因此可編輯的 ER 格式可能包含新增範本中缺少的 Excel 名稱。 ER 格式設計工具會針對參考未包含在新增的 Excel 範本中名稱的 ER 格式元素的屬性之間的任何不一致向您發出警告。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 格式組件。
2. 在格式結構樹中，新增 **Excel\\檔案** 元素 **報告**。
3. 對於您剛新增的 **Excel\\檔案** 元素，將 Excel 活頁簿檔案，**A.xlsx**，新增為附件。 使用在[ER 參數](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)設定的文件類型來指定 ER 格式範本的儲存體。

    > [!IMPORTANT]
    > 確保新增的 Excel 活頁簿不包含名稱 **ReportTitle**。

4. 將 **Excel\\儲存格** 元素 **標題** 新增為 **報告** 元素的巢狀元素。 在 **Excel 範圍** 欄位中，輸入 **ReportTitle**。
5. 選取 **驗證** 來檢查 **格式設計工具** 頁面上的可編輯格式組件。

    ![驗證格式設計工具頁面上的巢狀元素和欄位。](./media/er-components-inspections-13a.png)

6. 請注意，發生了驗證警告。 該訊息指出該名稱 **ReportTitle** 在您正在使用的 Excel 範本的工作表 **Sheet1** 上不存在。

    ![Excel 範本的 Sheet1 上不存在名稱 ReportTitle 的驗證警告。](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

透過移除參考範本中缺少的 Excel 名稱的所有元素來修改設定的格式。

#### <a name="option-2"></a>選項 2

透過匯入 Excel 範本[更新](er-fillable-excel.md#template-import)可編輯的 ER 格式。 可編輯 ER 格式的結構將與匯入的 Excel 範本的結構[同步](modify-electronic-reporting-format-reapply-excel-template.md)。

### <a name="additional-consideration"></a>額外考慮

若要了解如何在[商業文件管理](er-business-document-management.md)的範本編輯器中將格式結構與 ER 範本同步，請參閱[更新商業文件範本的結構](er-bdm-update-structure.md)。

## <a name="not-synced-with-a-word-template-format"></a><a id="i14"></a>未與 Word 範本格式同步

當您 [設定](er-fillable-excel.md) ER 格式組件以使用 Word 範本來產生輸出文件時，您可以手動新增 **Excel\\檔案** 元素、將所需的 Word 範本新增為可編輯組件的附件，並在新增的 **Excel\\檔案** 元素中選取該附件。

> [!NOTE]
> 附加 Word 文檔後，ER 格式設計工具將可編輯元素顯示為 **Word\\檔案**。

透過這種方式，您表明新增的元素將在執行階段填入所選範本。 由於新增的 Word 範本是在外部設計的，因此可編輯的 ER 格式可能包含新增範本中缺少的 Word 內容控制參考。 ER 格式設計工具會針對參考未包含在新增的 Word 範本中內容控制的 ER 格式元素的屬性之間的任何不一致向您發出警告。

如需顯示此問題如何發生的範例，請參閱[設定可編輯格式以隱藏摘要區段 ](er-design-configuration-word-suppress-controls.md#configure-to-suppress-control)。

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

修改已設定的格式，方法是刪除從已在驗證警告中提及的格式元素 **移除** 的公式。

#### <a name="option-2"></a>選項 2

修改使用中的 Word 範本，方法是將所需的標記[新增](er-design-configuration-word-suppress-controls.md#tag-control)到相關的 Word 內容控制。

## <a name="no-default-mapping"></a><a id="i15"></a>沒有預設對應

當[缺少繫結程序](#i11)檢查完成後，檢查好的格式繫結程序將根據相關模型對應組件的繫結程序評估。 由於您可以將[一些](./tasks/er-manage-model-mapping-configurations-july-2017.md) ER 模型對應設定匯入到您的 Finance 執行個體，並且每個設定可能會包含適用的模型對組件，因此您必須選取一個設定作為預設設定。 否則，當您嘗試執行、編輯或驗證檢查完的 ER 格式時，例外情外就會發生，並且您將收到以下訊息：「多個模型對應存在於設定 \<configuration names separated by comma\> 中的 \<model name (root descriptor)\> 資料模型。 將其中一項組態設定為預設值。」

如需有關顯示此問題如何發生以及如何解決的範例，請參閱[管理單個模型根的多個衍生對應 ](er-multiple-model-mappings.md)。

## <a name="inconsistent-setting-of-header-or-footer-components"></a><a id="i16"></a>頁首或頁尾組件的設定不一致

當您 [設定](er-fillable-excel.md) ER 格式組件以使用 Excel 範本產生輸出文件，您可以新增 **Excel\\標題** 組件來填入 Excel 活頁簿中工作表頂部的標題。 您還可以新增 **Excel\\頁尾** 組件來填入工作表底部的頁尾。 對於每個您新增的 **Excel\\頁首** 或 **Excel\\頁尾** 組件，您必須設定 **頁首/頁尾外觀** 屬性來指定組件執行的頁面。 因為您可以設定幾個 **Excel\\頁首** 或 **Excel\\頁尾** 組件供單個 **工作表** 組件使用，並且您可以為 Excel 工作表中不同類型的頁面產生不同的頁首或頁尾，您必須設定單個 **Excel\\頁首** 或 **Excel\\頁尾** 組件供 **頁首/頁尾外觀** 屬性的特定值使用。 如果多個 **Excel\\頁首** 或 **Excel\\頁尾** 組件被設定為 **頁首/頁尾外觀** 屬性的特定值，就會發生驗證錯誤，並且您會收到以下錯誤訊息：「頁首/頁尾 (&lt;組件類型：頁首或頁尾&gt;) 不一致。」

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

修改已設定的格式，方法式刪除其中一個不一致的 **Excel\\頁首** 或 **Excel\\頁尾** 組件。

#### <a name="option-2"></a>選項 2

修改 **頁首/頁尾外觀** 屬性的值，供其中一個不一致的 **Excel\\頁首** 或 **Excel\\頁尾** 組件使用。

## <a name="inconsistent-setting-of-page-component"></a><a id="i17"></a>Page 組件設定不一致

當您 [設定](er-fillable-excel.md) ER 格式組件以使用 Excel 範本產生輸出文件時，您可以新增 **Excel\\頁面** 組件，透過使用 ER 公式對產生的文件進行分頁。 對於每個您新增的 **Excel\\頁面** 組件，您可以新增許多巢狀[範圍](er-fillable-excel.md#range-component)組件，並且仍然符合以下[結構](er-fillable-excel.md#page-component-structure)要求：

- 您可以設定第一個巢狀 **範圍** 組件，好將 **複寫方向** 屬性設定為 **無複寫**。 此範圍可用來製作產生文件中的頁面標題。
- 您可以新增許多其他巢狀 **範圍** 組件，其中 **複寫方向** 屬性可設定為 **垂直**。 這些範圍可用來填入產生的文件。
- 您可以設定最後一個巢狀 **範圍** 組件，好將 **複寫方向** 屬性設定為 **無複寫**。 此範圍可用來製作產生文件中的頁尾並新增所需的頁面分隔符號。

如果您在設計時未在 ER 格式設計工具中為 ER 格式遵循此結構，則會發生驗證錯誤，並且您會收到以下錯誤訊息：「有兩個以上的範圍組件沒有複寫。 請移除不必要的組件。」

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解決方案

#### <a name="option-1"></a>選項 1

透過更改所有不一致 **Excel\\範圍** 組件的 **複寫方向** 屬性來修改已設定的格式。

## <a name="executability-of-an-expression-with-orderby-function"></a><a id="i18"></a>含 ORDERBY 函數運算式的可執行性

內建的 [ORDERBY](er-functions-list-orderby.md)ER 函數可用於排序 **[記錄清單](er-formula-supported-data-types-composite.md#record-list)** 類型的 ER 資料來源的記錄，其中該類型是指定為函數的引數。

`ORDERBY` 函數的引數可以[指定](er-functions-list-orderby.md#syntax-2)去排序應用程式資料表、視圖或資料執行個體的記錄，方法是調用單一資料庫來取得排序後的資料作為記錄清單。 **記錄清單** 類型的資料來源用作此函數的引數並指定調用的應用程式來源。

ER 可檢查資料庫直接查找是否可以建立到 `ORDERBY` 函數中所參考的資料來源。 如果無法建立直接查找，則 ER 模型對應設計工具中會出現驗證錯誤。 您收到的訊息指出包含 `ORDERBY` 函數的 ER 運算式不能在執行階段執行。

以下步驟顯示了此問題是如何發生的。

1. 開始設定 ER 模型對應組件。
2. 新增 **Dynamics 365 for Operations\\資料表記錄** 類型的資料來源。
3. 命名新資料來源 **Vendor**。 在 **資料表** 欄位中，選取 **VendTable** 以指定此資料來源將要求 **VendTable** 資料表。
4. 新增 **導出欄位** 類型的資料來源。
5. 將新資料來源命名為 **OrderedVendors**，並做設定好讓它包含運算式 `ORDERBY("Query", Vendor, Vendor.AccountNum)`。
 
    ![在模型對應設計工具頁面上設定資料來源。](./media/er-components-inspections-18-1.png)

6. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件並驗證是否可以查找 **OrderedVendors** 資料來源中的運算式。
7. 透過新增 **導出欄位** 類型的巢狀欄位來獲取調整後的廠商帳號，修改 **廠商** 資料來源。
8. 將新巢狀欄位命名為 **$AccNumber**，並做設定好讓它包含運算式 `TRIM(Vendor.AccountNum)`。
9. 選取 **驗證** 來檢查 **模型對應設計工具** 頁面上的可編輯模型對應組件並驗證是否可以查找 **廠商** 資料來源中的運算式。

    ![驗證是否可以在模型對應設計工具頁面上查找廠商資料來源中的運算式。](./media/er-components-inspections-18-2.png)

10. 請注意，驗證錯誤的發生是因為 **廠商** 資料來源包含 **導出欄位** 類型的巢狀欄位，其不允許 **OrderedVendors** 資料類型的運算式轉譯到資料庫直接查找陳述式。 如果您忽略驗證錯誤並選取 **執行** 來執行此模型對應，同樣的錯誤就會在執行階段發生。

### <a name="automatic-resolution"></a>自動化解決方案

沒有自動修復此問題的選項可使用。

### <a name="manual-resolution"></a>手動解析率

#### <a name="option-1"></a>選項 1

將 **$AccNumber** 巢狀欄位新增至 **FilteredVendors** 資料來源，並設定欄位好讓它包含運算式 `TRIM(FilteredVendor.AccountNum)`，而不是將 **導出欄位** 類型的巢狀欄位新增至 **廠商** 資料來源。 透過這種方式，`ORDERBY("Query", Vendor, Vendor.AccountNum)` 運算式可以在資料庫層級執行，並在之後完成 **$AccNumber** 巢狀欄位的計算。

#### <a name="option-2"></a>選項 2

將 **FilteredVendors** 資料來源的運算式從 `ORDERBY("Query", Vendor, Vendor.AccountNum)` 變更至 `ORDERBY("InMemory", Vendor, Vendor.AccountNum)`。 對於資料量大的資料表 (交易資料表)，我們不建議您更改運算式，因為會擷取所有記錄，並在記憶體中完成所需記錄的順序。 因此，這種方法可能會導致效能不佳。

## <a name="additional-resources"></a>其他資源

[ALLITEMS ER 函數](er-functions-list-allitems.md)

[ALLITEMSQUERY ER 函數](er-functions-list-allitemsquery.md)

[INT64VALUE ER 函數](er-functions-conversion-int64value.md)

[INTVALUE ER 函數](er-functions-conversion-intvalue.md)

[FILTER ER 函數](er-functions-list-filter.md)

[WHERE ER 函數](er-functions-list-where.md)

[使用 JOIN 資料來源從 ER 模型對應中的多個應用程式資料表中取得資料](er-join-data-sources.md)

[追蹤 ER 格式的執行以解決效能問題](trace-execution-er-troubleshoot-perf.md)

[商業文件管理概述](er-business-document-management.md)

[在產生的報告中隱藏 Word 內容控制](er-design-configuration-word-suppress-controls.md)

[管理單個模型根的多個衍生對應](er-multiple-model-mappings.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
