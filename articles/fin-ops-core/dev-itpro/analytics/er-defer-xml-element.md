---
title: 遞延執行 ER 格式的 XML 元素
description: 本主題說明如何遞延執行電子報表 (ER) 格式的 XML 元素。
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: b804e840b98321ee9e509ea483b360ec42d12880
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460412"
---
# <a name="defer-the-execution-of-xml-elements-in-er-formats"></a>遞延執行 ER 格式的 XML 元素

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>概觀

您可以使用[電子報表 (ER)](general-electronic-reporting.md) 架構的作業設計工具來[設定](./tasks/er-format-configuration-2016-11.md) ER 解決方案的格式組件，用於產生 XML 格式的輸出文件。 設定的格式組件的階層由各種類型的格式元素組成。 這些格式元素用於在執行階段用所需資訊填入產生的文件。 在預設情況下，當您執行 ER 格式時，格式元素的執行順序與它們在格式階層中的顯示順序相同：一個接一個，從上到下。 但是，在設計階段，您可以更改已設定格式組件的任何 XML 元素的執行順序。

透過打開設定格式的 XML 元素的 <a name="DeferredXmlElementExecution"></a>**遞延執行** 選項，您可以遞延 (遞延) 該元素的執行。 在這種情況下，該元素不會執行，直到其父元素的所有其他元素都已執行。

若要進一步了解此函數，請完成本主題中的範例。

## <a name="limitations"></a>限制

**遞延執行** 選項僅支援為 ER 格式設定的 XML 元素，該格式用於產生 XML 格式的 **輸出** 文件。

**遞延執行** 選項只支援只存在於其他 XML 元素中的 XML 元素。 因此，它不適用於駐留在其他類型格式元素中的 XML 元素 (例如，在 **XML 序列** 元素)。

當 **分割檔案** 選項被設定為 **是** 時，位於 **常用\\檔案** 格式元素中的 XML 元素不支援 **遞延執行** 選項。 如需如何拆分 XML 檔案的相關詳情，請參閱[根據檔案大小和內容數量拆分產生的 XML 檔案](er-split-files.md)。

## <a name="example-defer-the-execution-of-an-xml-element-in-an-er-format"></a><a name="Example"></a>範例：遞延執行 ER 格式的 XML 元素

以下步驟說明系統管理員或電子報表函數顧問[角色](../sysadmin/tasks/assign-users-security-roles.md)的使用者如何設定包含 XML 元素的ER格式，其中執行順序與格式階層中的順序不同。

這些步驟可以在 Microsoft Dynamics 365 Finance 的 **USMF** 公司中進行。

### <a name="prerequisites"></a>先決條件

若要完成此範例，您必須有權存取 Finance 中的 **USMF** 公司並擔任以下角色之一：

- 電子報表函數
- 系統管理員

如果您還沒有完成 [遞延執行 ER 格式的序列元素](er-defer-sequence-element.md#Example)主題中的範例，請下載以下 ER 解決方案樣本的[設定](general-electronic-reporting.md#Configuration)。

| 內容描述            | 檔案名稱 |
|--------------------------------|-----------|
| ER 資料模型設定    | [學習已遞延元素的模型.版本.1.xml](https://download.microsoft.com/download/7/6/0/760933ca-4ac3-4f50-bc0c-c35e596ee066/Modeltolearndeferredelements.version.1.xml) |
| ER 模型對應設定 | [學習已遞延元素的對應.版本.1.1.xml](https://download.microsoft.com/download/c/9/c/c9c4b9dd-b700-4385-a087-a84ce9fc1d0f/Mappingtolearndeferredelements.version.1.1.xml) |

在開始之前，您還必須下載範例 ER 解決方案的以下設定並將其儲存到本地電腦。

| 內容描述     | 檔案名稱 |
|-------------------------|-----------|
| ER 格式設定 | [學習已遞延 XML 元素的格式.版本.1.1.xml](https://download.microsoft.com/download/4/7/8/478fa846-22e9-4fa0-89b1-d3aeae660067/FormattolearndeferredXMLelements.version.1.1.xml) |

### <a name="import-the-sample-er-configurations"></a>匯入樣本 ER 設定

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 選取 **報表設定**。
3. 在 **設定** 頁面，如果設定樹狀結構中沒有 **Model to learn deferred elements** 設定，請匯入 ER 資料模型設定。

    1. 選取 **Exchange**，然後選取 **從 XML 檔案載入**。
    2. 選取 **瀏覽**，找到並選取 **學習已遞延元素的模型.1.xml**，然後選取 **確定**。

4. 如果設定樹狀結構中沒有 **學習已遞延元素的對應** 設定，請匯入 ER 模型的對應設定。

    1. 選取 **Exchange**，然後選取 **從 XML 檔案載入**。
    2. 選取 **瀏覽**，找到並選取 **學習已遞延元素的對應.1.1.xml**，然後選取 **確定**。

5. 匯入 ER 格式設定：

    1. 選取 **Exchange**，然後選取 **從 XML 檔案載入**。
    2. 選取 **瀏覽**，找到並選取 **學習已遞延 XML 元素的格式.1.1.xml**，然後選取 **確定**。

6. 在設定樹狀結構中，展開 **學習已遞延元素的模型**。
7. 查閱設定樹狀結構中匯入的 ER 設定清單。

    ![在設定頁面上匯入 ER 設定。](./media/ER-DeferredXml-Configurations.png)

### <a name="activate-a-configuration-provider"></a>啟用設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面，在 **設定提供者** 區段，確保列出 Litware, Inc. (`http://www.litware.com`) 樣本公司的[設定提供者](general-electronic-reporting.md#Provider)，並且被標記為有效。 如果此設定提供者未列出，或者未標記為有效，按照[建立設定提供者並將其標記為有效](./tasks/er-configuration-provider-mark-it-active-2016-11.md)中的步驟。

    ![本地化設定頁面上的 Litware, Inc. 樣本公司。](./media/ER-DeferredXml-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>查閱匯入的資料對應

查看 ER 模型對應組件的設定，該組件設定為存取稅務交易並根據要求公開存取的資料。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 選取 **報表設定**。
3. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，展開 **學習已遞延元素的模型**。
4. 選取 **學習已遞延元素的對應** 設定。
5. 選取 **設計工具** 開啟對應清單。
6. 選取 **設計工具** 查看對應詳情。
7. 選取 **顯示詳情**。
8. 查閱設定為存取稅務交易的資料來源：

    - *資料表記錄* 類型的 **交易** 資料來源被設定為存取 **TaxTrans** 申請表的記錄。
    - *導出欄位* 類型的 **憑證** 資料來源被設定為以記錄清單的形式返回所需的憑證代碼 (**INV-10000349** 和 **INV-10000350**)。
    - *導出欄位* 類型的 **已過濾** 資料來源被設定為從 **交易** 資料來源中只選取所需憑證的稅務交易。
    - *導出欄位* 類型的 **\$TaxAmount** 欄位是為 **已過濾** 資料來源新增的，以揭露具有相反符號的稅值。
    - *分組依據* 類型的 **已分組** 資料來源設定為對 **已過濾** 資料來源的過濾稅務交易進行分組。
    - **已分組** 資料來源的 **TotalSum** 彙總欄位設定為匯總該資料來源的所有已過濾稅務交易的 **已過濾** 資料來源的 **\$TaxAmount** 欄位的值。

        ![編輯「GroupBy」參數頁面上的 TotalSum 彙總欄位。](./media/ER-DeferredXml-GroupByParameters.png)

9. 查看設定的資料來源如何繫結到資料模型，以及它們如何公開存取的資料以使其以 ER 格式可用：

    - **已過濾** 資料來源繫結到資料模型的 **Data.List** 欄位。
    - **已過濾** 資料來源的 **\$TaxAmount** 欄位繫結到資料模型的 **Data.List.Value** 欄位。
    - **已分組** 資料來源的 **TotalSum** 欄位繫結到資料模型的 **Data.Summary.Total** 欄位。

    ![模型對應設計工具頁面。](./media/ER-DeferredXml-ModelMapping.png)

10. 關閉 **模型對應設計工具** 和 **模型對應** 頁。

### <a name="review-the-imported-format"></a>查閱已匯入的格式

1. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **學習已遞延 XML 元素的格式** 設定。
2. 選取 **設計工具** 查看格式詳情。
3. 選取 **顯示詳情**。
4. 查看 ER 格式組件的設定，這些組件設定為產生 XML 格式的輸出文件，其中包括稅務交易的詳情：

    - 將 **報告\\訊息** XML 元素設定為使用包含巢狀 XML 元素 (**標題**、**記錄** 和 **摘要**) 的單個節點填入輸出文件。
    - 將 **報告\\訊息\\標題** XML 元素設定為使用單個標題節點填入輸出文件，該標題節點顯示處理開始的日期和時間。
    - 將 **報告\\訊息\\記錄** XML 元素設定為使用單個記錄節點填入輸出文件，該記錄節點顯示單個稅務交易的詳情。
    - 將 **報告\\訊息\\摘要** XML 元素設定為使用單個匯總節點填入輸出文件，該節點包括來自已處理稅務交易的稅務值的總和。

    ![格式設計工具頁面上的訊息 XML 元素和巢狀的 XML 元素。](./media/ER-DeferredXml-Format.png)

5. 在 **對應** 索引標籤上，查看以下詳情：

    - **報告\\訊息\\標題** 元素不必繫結到來源以在輸出文件中產生單個節點。
    - **ExecutionDateTime** 屬性產生新增標題節點時的日期和時間 (包括毫秒)。
    - 將 **報告\\訊息\\記錄** 元素繫結到 **model.Data.List** 清單，以便為繫結清單中的每條記錄產生單個記錄節點。
    - 將 **TaxAmount** 屬性繫結到 **model.Data.List.Value** (在相對路徑視圖中顯示為 **\@.Value**) 以產生現行的稅務交易。
    - **RunningTotal** 屬性是稅值執行總計的預留位置。 現行，該屬性沒有輸出，因為沒有為其設定繫結或預設值。
    - **ExecutionDateTime** 屬性產生在此報告中處理現行交易的日期和時間 (包括毫秒)。
    - **報告\\訊息\\摘要** 元素不必繫結到資料來源以在輸出文件中產生單個節點。
    - 將 **TotalTaxAmount** 屬性繫結到 **model.Data.Summary.Total** 以產生已處理稅務交易的稅值總和。
    - **ExecutionDateTime** 屬性產生新增摘要節點時的日期和時間 (包括毫秒)。

    ![格式設計工具頁面上的對應索引標籤。](./media/ER-DeferredXml-Format2.png)

### <a name="run-the-imported-format"></a>執行已匯入的格式

1. 在 **格式設計工具** 頁面上，選取 **執行**。
2. 下載網路瀏覽器提供的檔案，然後打開它以供查看。

    ![匯入格式的下載檔案。](./media/ER-DeferredXml-Run.png)

請注意，匯總節點顯示已處理交易的稅值總和。 因為將格式設定為使用 **model.Data.Summary.Total** 繫結來返回這個總和，所以總和是透過調用模型對應中 *GroupBy* 類型的 **Grouped** 資料來源的 **TotalSum** 彙總來計算的。 若要計算這個彙總，模型對應在所有在 **已過濾** 資料來源中被選中的交易上進行反覆運算。 透過比較匯總節點和最後一個記錄節點的執行時間，可以確定計算總和花費了 12 毫秒 (ms)。 透過比較第一個和最後一個記錄節點的執行時間，可以確定所有記錄節點的產生耗時 9 ms。 因此，總共需要 21 毫秒。

### <a name="modify-the-format-so-that-the-calculation-is-based-on-generated-output"></a>修改格式好讓計算根據產生的輸出

如果交易量遠大於現行範例中的量，則計算時間可能會增加並導致效能問題。 透過更改格式設定，您可以幫助防止這些效能問題。 因為您存取稅值以將它們包含在產生的報告中，所以您可以重複使用此資訊來計算稅值。 如需相關資訊，請參閱[設定格式進行計數和求和](./tasks/er-format-counting-summing-1.md)。

1. 在 **格式設計工具** 頁面上，在 **格式** 索引標籤上，選取格式樹狀結構中的 **報告** 檔案元素。
2. 將 **收集輸出詳情** 選項設定 **是**。 現在您可以透過使用產生的報告內容作為資料來源來設定這種格式，可以透過使用[資料收集](er-functions-category-data-collection.md)類別中的內建 ER 函數來存取。
3. 在 **對應** 索引標籤上，選取 **報告\\訊息\\記錄** XML 元素。
4. 將 **收集的資料鍵名稱** 運算式設定為 `WsColumn`。
5. 將 **收集的資料鍵值** 運算式設定為 `WsRow`。

    ![格式設計工具頁面上的記錄 XML 元素。](./media/ER-DeferredXml-Format3.png)

6. 選取 **報告\\訊息\\記錄\\營業稅額** 屬性。
7. 將 **收集的資料鍵名稱** 運算式設定為 `SummingAmountKey`。

    ![格式設計工具頁面上的營業稅額屬性。](./media/ER-DeferredXml-Format4.png)

    您可以將此設定視為虛擬工作表的實現，其中儲存格 A1 的值附加了每個已處理稅收交易的稅額值。

8. 選取 **報告\\訊息\\記錄\\執行總計** 屬性，然後選取 **編輯公式**。
9. 透過使用內建的 [SUMIF](er-functions-datacollection-sumif.md) ER 函數設定 `SUMIF(SummingAmountKey, WsColumn, WsRow)` 運算式，然後選取 **儲存**。

    ![SUMIF 運算式。](./media/ER-DeferredXml-FormulaDesigner.png)

10. 關上 **公式設計工具** 頁面。
11. 選取 **儲存**，然後選取 **執行**。
12. 下載並查看網路瀏覽器提供的檔案。

    ![產生的帶有執行總計的稅值清單。](./media/ER-DeferredXml-Run1.png)

    最後一個記錄節點包含使用產生的輸出作為資料來源為所有已處理交易計算的稅值的執行總計。 此資料來源從報告的開頭開始，一直持續到最後一個稅務交易。 摘要節點包含所有處理過的交易的稅值之和，這些稅值是透過使用 *GroupBy* 類型的資料來源在模型對應中計算出來的。 請注意，這些值是相等的。 因此，可以用基於輸出的求和法來代替 **GroupBy**。 透過比較第一個記錄節點和摘要節點的執行時間，您可以確定所有記錄節點的產生和求和花了 11 毫秒。 因此，就記錄節點的產生和稅收值的求和而言，修改後的格式大約比原始格式快兩倍。

13. 選取 **報告\\訊息\\摘要\\營業稅額總計** 屬性，然後選取 **編輯公式**。
14. 輸入 `SUMIF(SummingAmountKey, WsColumn, WsRow)` 運算式而不是現有運算式。
15. 選取 **儲存**，然後選取 **執行**。
16. 下載並查看網路瀏覽器提供的檔案。

    ![使用編輯的公式產生的稅值清單。](./media/ER-DeferredXml-Run2.png)

    請注意，最後一個記錄節點中稅收值的執行總計現在等於匯總節點中的總和。

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>將基於輸出的求和值放在報表標題中

例如，如果您必須在報表標題中顯示稅值總和，您可以修改格式。

1. 在 **格式設計工具** 頁面上，在 **格式** 索引標籤上，選取 **報告\\訊息\\摘要** XML 元素。
2. 選取 **上移**。
3. 選取 **儲存**，然後選取 **執行**。
4. 下載並查看網路瀏覽器提供的檔案。

    ![已下載報告標題的稅值檔案。](./media/ER-DeferredXml-Run3.png)

    請注意，匯總節點中的稅值總和現在等於 0 (零)，因為該總和現在是根據產生的輸出計算的。 產生第一個記錄節點時，產生的輸出尚不包含具有交易詳情的記錄節點。 您可以設定這種格式，遞延執行 **報告\\訊息\\摘要** 元素，直到 **報告\\訊息\\記錄** 元素對所有稅務交易執行完畢。

### <a name="defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used"></a>遞延匯總 XML 元素的執行，以便使用計算的總數

1. 在 **格式設計工具** 頁面上，在 **格式** 索引標籤上，選取 **報告\\訊息\\摘要** XML 元素。
2. 將 **遞延執行** 選項設定為 **是**。

    ![格式設計工具頁面上的摘要 XML 元素的遞延執行選項。](./media/ER-DeferredXml-Format5.png)

3. 選取 **儲存**，然後選取 **執行**。
4. 下載並查看網路瀏覽器提供的檔案。

    ![下載的遞延執行檔案。](./media/ER-DeferredXml-Run4.png)

    現在，**報告\\訊息\\摘要** 元素只有在巢狀在其父元素 **報告\\訊息** 下的所有其他項目被執行後才會被執行。 因此，它是在對 **model.Data.List** 資料來源的所有稅務交易執行了 **報告\\訊息\\記錄** 元素後執行的。 第一個和最後一個記錄節點以及標題和摘要節點的執行時間揭露了這一事實。

## <a name="additional-resources"></a>其他資源

- [設定格式進行計數和求和](./tasks/er-format-counting-summing-1.md)
- [追蹤 ER 格式的執行，以解決效能問題](trace-execution-er-troubleshoot-perf.md)
- [遞延執行 ER 格式的序列元素](er-defer-sequence-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
