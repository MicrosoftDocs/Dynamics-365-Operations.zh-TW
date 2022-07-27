---
title: 在 ER 模型對應中使用 JOIN 資料來源，從多個申請表中獲取資料
description: 本主題說明如何在電子報表 (ER) 中使用 JOIN 類型資料來源。
author: NickSelin
ms.date: 04/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: c9a06c048e98676e30a6652cad6634c2e13531d4ebc6d35f325f4c7153cd82ae
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460523"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>使用 JOIN 資料來源從電子報表 (ER) 模型對應中的多個應用表中獲取資料

[!include[banner](../includes/banner.md)]

在設定電子報表 (ER) 模型對應或格式時，您可以 [新增](#review)所需的 **聯結** 類型的資料來源。 在設計階段，將 **聯結** 資料來源設定為一組多個資料來源，每個資料來源返回記錄清單。 如需除第一個資料來源之外的每個資料來源，您都需要定義必要條件來連接現行和先前資料來源的記錄。 在執行階段，設定的 **聯結** 類型的資料來源會[返回](#executeERformat)單一的聯結記錄清單，其中包含來自巢狀資料來源記錄的欄位。

現行支援以下類型的聯結：

- 外 (左) 聯結：
    - 聯結第一個 (最左邊) 資料來源的所有記錄，然後按照設定的條件比對第二個 (最右邊) 資料來源的任何記錄。
- 內 (右) 聯結：
    - 根據設定的條件，只聯結第一 (最左邊) 資料來源的記錄和第二 (最右邊) 資料來源的記錄，彼此比對。

在設定的 **聯結** 資料來源中，當所有的資料來源都是 **資料表記錄** 類型時，聯結資料來源的執行可以[在資料庫層面上進行](#analyze)，使用單一 SQL 陳述式。 此陳述式減少了資料庫調用的次數，從而提高了模型對應效能。 否則，**聯結資料** 來源的執行將在記憶體中進行。

> [!NOTE]
> 現行尚不支援在 ER 運算式中使用 **VALUEIN** 函數，該運算式指定了在聯結類型的資料來源中連接記錄的條件。 造訪[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)頁面了解有關此函數的更多詳情。

若要進一步了解此函數，請完成本主題中的範例。

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>範例：在 ER 模型對應中使用 JOIN 資料來源

下面的步驟解釋了系統管理員或電子報表開發人員如何設定電子報表 (ER) 模型對應，透過使用 **聯合** 類型的資料來源，一次從多個應用程式表中獲取資料，以提高資料存取效能。 這些步驟可以為 Dynamics 365 Finance 或 Regulatory Configuration Services (RCS) 的任何公司執行。

### <a name="prerequisites"></a>先決條件

若要完成本主題中的範例，您必須有權存取以下內容之一，具體取決於用於完成這些步驟的服務：

**以下其中一個角色的 Finance 存取權限：**

- 電子報表開發人員
- 電子報表函數
- 系統管理員

**以下其中一個角色存取 RCS：**

- 電子報表開發人員
- 電子報表函數
- 系統管理員

您還必須首先完成[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)程序中的步驟。

您還必須提前下載並儲存以下範例 ER 設定檔：

| **內容描述**  | **檔案名稱**   |
|--------------------------|-----------------|
| 樣本 **ER 資料模型** 設定檔，用作範例的資料來源。| [學習 JOIN 資料來源的模型.版本.1.1.xml](https://download.microsoft.com/download/5/c/1/5c1d8a57-6ebd-425b-bc5d-c71dde92c6af/ModeltolearnJOINdatasources.version.1.xml) |
| 樣本 **ER 模型對應** 設定檔，它實現了該範例的 ER 資料模型。 | [學習 JOIN 資料來源的對應.版本.1.1.xml](https://download.microsoft.com/download/9/2/f/92f339ca-41fc-4f5e-b458-6983c957d3dd/MappingtolearnJOINdatasources.version.1.1.xml)|
| 樣本 **ER 格式** 設定檔 此檔案描述了用於填入範例的 ER 格式組件的資料。 | [學習 JOIN 資料來源的格式.版本.1.1.xml](https://download.microsoft.com/download/f/f/8/ff8f1b48-14d0-4c73-9145-bcdf8b5265bc/FormattolearnJOINdatasources.version.1.1.xml) |

### <a name="activate-a-configurations-provider"></a>啟用設定提供者

1. 在網路瀏覽器的第一個工作階段中存取 Finance 或 RCS。
2. 進入 **組織管理\>工作區\>電子報表**。
3. 在 **本地化設定** 頁面上，在 **設定提供者** 區段，確保列出 [Litware, Inc.](http://www.litware.com) 樣本公司的設定提供者，並且將它標記為 **有效**。 如果您沒有看到這個設定提供者，請按照[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)程序的步驟進行。

    ![電子報表工作區](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>匯入樣本 ER 設定檔

1. 選取 **報表設定**。
2. 匯入 ER 資料模型設定檔。
    1. 選取 **Exchange**。
    2. 選取 **從 XML 文件載入**。
    3. 選取 **瀏覽** 找到 **學習 JOIN 資料來源的模型.版本.1.1.xml** 檔案。
    4. 選取 **確定**。
3. 匯入 ER 模型對應設定檔。
    1. 選取 **Exchange**。
    2. 選取 **從 XML 文件載入**。
    3. 選取 **瀏覽** 找到 **學習 JOIN 資料來源的對應.版本.1.1.xml** 檔案。
    4. 選取 **確定**。
4. 匯入 ER 格式設定檔：
    1. 選取 **Exchange**。
    2. 選取 **從 XML 文件載入**。
    3. 選取 **瀏覽** 找到 **學習 JOIN 資料來源的格式.版本.1.1.xml** 檔案。
    4. 選取 **確定**。
5. 在設定樹狀結構中，展開 **學習 JOIN 資料來源的模型** 項目以及其他模型項目 (如果有的話)。
6. 觀察樹狀結構中的 ER 設定清單，以及 **版本** FastTab 上的版本細節 - 將它們用作樣本報告的資料來源。

    ![電子報表設定頁面。](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>打開執行追蹤選項

1. 選取 **設定**。
2. 選取 **使用者參數**。
3. 設定執行諄宗參數，如下面的螢幕擷取畫面所示。

    ![電子報表使用者參數頁面。](./media/GER-JoinDS-Parameters.PNG)

    開啟這些參數後，每次執行匯入的 ER 格式檔案，都會產生執行追蹤。 使用產生的執行追蹤的詳情，您可以分析 ER 格式和 ER 模型對應組件的執行。 造訪[追蹤 ER 格式的執行對效能問題進行疑難排解](trace-execution-er-troubleshoot-perf.md)頁面以獲取有關 ER 執行追蹤函數的更多詳情。

### <a name="review-er-model-mapping-part-1"></a>查閱 ER 模型對應 (第 1 節)

查看 ER 模型對應組件的設定。 該組件被設定為存取有關 ER 設定版本、設定詳情和設定提供程式的資訊，而無需使用 **聯結** 類型。

1. 選取 **學習 JOIN 資料來源的對應** 設定。
2. 選取 **設計工具** 開啟對應清單。
3. 選取 **設計工具** 查看對應詳情。
4. 選取 **顯示詳情**。
5. 在設定樹狀結構中，展開 **Set1** 和 **Set1.Details** 資料模型項目：

    1. 繫結 **詳細資訊：記錄清單 = 版本** 表示 **Set1.Details** 項目已繫結到 **版本** 資料來源，返回 **ERSolutionVersionTable** 資料表的記錄。 此表的每條記錄代表 ER 設定的單個版本。 該表的內容在 **設定** 頁面上的 **版本** FastTab 中顯示。
    2. 繫結 **ConfigurationVersion: String = @.PublicVersionNumber** 代表每個 ER 設定的公開版本的值取自 **ERSolutionVersionTable** 表的 **PublicVersionNumber** 欄位，並放置到 **ConfigurationVersion** 項目。
    3. 繫結 **ConfigurationTitle: String = @.'>Relations'.Solution.Name** 表示 ER 設定的名稱取自 **ERSolutionTable** 表的 **名稱** 欄位，透過使用 **ERSolutionVersionTable** 和 **ERSolutionTable** 表之間的多對一關係 (**'>Relations'**) 評估。 現行應用程式執行個體的 ER 設定的名稱在 **設定** 頁面的設定樹狀結構中顯示。
    4. 繫結 **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** 代表擁有現行設定的設定提供者的名稱取自 **ERVendorTable** 表的 **名稱** 欄位，透過使用 **ERSolutionTable** 和 **ERVendorTable** 表之間的多對一關係評估。 ER 設定提供者的名稱在 **設定** 頁面的設定樹狀結構中，在每個設定的頁面標題上呈現。 ER 設定提供者的整個清單可以在 **組織管理\>電子報表\>設定提供者** 資料表頁找到。

    ![ER 模型對應設計工具頁面，繫結的資料模型項目清單。](./media/GER-JoinDS-Set1Review.PNG)

6. 在設定樹狀結構中，展開 **Set1.Summary** 資料模型項目：

    1. 繫結 **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** 表示將 **Set1.Summary.VersionsNumber** 項目繫結到 **GroupBy** 類型的 **VersionsSummary** 資料來源的 **VersionsNumber** 彙總欄位，該資料來源被設定為透過 **版本** 資料來源返回 **ERSolutionVersionTable** 表的記錄數量。

    ![編輯「分組依據」參數頁面。](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. 關閉頁面。

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a>查閱 ER 模型對應 (第 2 節)

查看 ER 模型對應組件的設定。 將該組件設定為使用 **聯結** 類型的資料來源來存取關於ER設定的版本、設定的細節和設定提供者的資訊。

1. 在設定樹狀結構中，展開 **Set2** 和 **Set2.Details** 資料模型項目。 繫結 **Details: Record list = Details** 表示 **Set2.Details** 項目被繫結到 **詳情** 資料來源，被設定為 **聯結** 類型的資料來源。

    ![ER 模型對應設計工具頁面顯示擴展的 Set2:Record 資料模型項目。](./media/GER-JoinDS-Set2Review.PNG)

    可以透過選取 **函數/聯結** 資料來源來新增 **聯結** 資料來源。

    ![ER 模型對應設計工具頁面，聯結資料來源類型。](./media/GER-JoinDS-AddJoinDS.PNG)

2. 選取 **詳情** 資料來源。
3. 在 **資料來源** 窗格中選取 **編輯**。
4. 選取 **編輯聯結**。
5. 選取 **顯示詳情**。

    ![JOIN 資料來源參數頁面。](./media/GER-JoinDS-JoinDSEditor.PNG)

    本頁用於設計所需的 **聯結類型** 的資料來源。 在執行階段，這個資料來源將從 **已聯結清單** 格線中的資料來源建立單一的聯結清單記錄。 記錄的聯結將從格線中作為第一個的 **ConfigurationProviders** 資料來源開始 (**類型** 資料欄是空白的)。 因此，每個其他資料來源的記錄將根據其在此格線中的順序聯結到父資料來源的記錄。 每個聯結的資料來源都必須設定為巢狀在目標資料來源下的資料來源 (`1Versions` 資料來源巢狀在 `1Configurations` 下；`1Configurations` 資料來源巢狀在 **ConfigurationProviders** 下)。 每個設定的資料來源都必須包含聯結條件。 在這個特定 **聯結** 的資料來源中，定義了以下的聯結：

    - **ConfigurationProviders** 資料來源 (指 **ERVendorTable** 表) 的每條記錄只與 **1Configurations** 中 (指 **ERSolutionTable** 表) 在 **SolutionVendor** 和 **RecId** 欄位中具有相同值的記錄聯結。 將 **內部聯結** 類型用於這個聯結，以及以下條件的比對記錄：

    FILTER (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - **1Configurations** 資料來源 (指 **ERSolutionTable** 表) 的每條記錄都與 **1Versions** 的唯一記錄 (指 **ERSolutionVersionTable** 表) 聯結，這些記錄在 **解決方案** 和 **RecId** 欄位中有相同的值。 將 **內部聯結** 類型用於這個聯結，以及以下條件的比對記錄：

    FILTER (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - 將 **執行** 選項設定為 **查找**，這代表該聯結資料來源將在執行階段作為直接 SQL 調用在資料庫層面上執行。

    對於表示申請表的資料來源的聯結記錄，您可以透過使用欄位對來指定聯結條件，而不是描述這些表之間存在的 AOT 關係的欄位。 這種類型的聯結也可以設定為在資料庫級別執行。

6. 關閉頁面。
7. 選取 **取消**。
8. 在設定樹狀結構中，展開 **Set2.Summary** 資料模型項目：

    - 繫結 **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** 表示 **Set2.Summary.VersionsNumber** 項目被繫結到 **GroupBy** 類型的 **DetailsSummary** 資料來源的 **VersionsNumber** 彙總欄位，該資料來源被設定為返回 **聯結** 類型的 **詳情** 資料來源的加入記錄數。
    - 將 **執行** 位置選項設定為 **查找**，代表這個 **GroupBy** 資料來源將在執行階段作為資料庫級別的直接 SQL 調用執行。 這種行為是可能的，因為 **聯結** 類型的基礎資料來源 **詳情** 被設定為在資料庫級別執行。

    ![GROUPBY 資料來源參數頁面。](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. 關閉頁面。
10. 選取 **取消**。

### <a name="execute-er-format"></a><a name="executeERformat"></a>執行 ER 格式

1. 在網路瀏覽器的第二個工作階段中使用與第一個工作階段中相同的認證和公司存取 Finance 或 RCS。
2. 進入 **組織管理\>電子報表\>設定**。
3. 展開 **學習 JOIN 資料來源的模型** 設定。
4. 選取 **學習 JOIN 資料來源的格式** 設定。
5. 選取 **設計工具**。
6. 選取 **顯示詳情**。
7. 選取 **對應**。
8. 選取 **展開/折疊**。

    此格式旨在為產生的文字檔案填入每個版本的 ER 設定 (**版本** 序列)。 每個產生的行列將包含擁有現行設定的設定提供者的名稱、設定名稱和設定版本，以分號分隔。 產生檔案的最後一行將包含已發現的 ER 設定版本的數量 (**摘要** 序列)。

    ![ER 格式設計工具頁面，格式索引標籤。](./media/GER-JoinDS-FormatReview.PNG)

    **資料** 和 **摘要** 資料來源用於向產生的檔填入設定版本細節。

    - 當您在執行 ER 格式時，在使用者對話頁上為 **選取器** 資料來源選取 **否** 時，會使用來自 **Set1** 資料模型的資訊。
    - 當您在使用者對話方塊頁面上執行階段為 **選取器** 資料來源選取 **是** 時，會使用來自 **Set2** 資料模型的資訊。

    ![ER 格式設計工具頁面，對應索引標籤。](./media/GER-JoinDS-FormatMappingReview.PNG)

9. 選取 **執行**。
10. 在對話方塊頁面上，在 **使用 JOIN 資料來源** 欄位中選取 **否**。
11. 選取 **確定**。
12. 查看產生的檔案。

    ![電子報表參數產生檔案未使用 JOIN 資料來源。](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>分析 ER 格式執行追蹤

1. 在 Finance 或 RCS 的第一個工作階段中，選取 **設計工具**。
2. 選取 **效能追蹤**。
3. 在 **效能追蹤** 格線，選取使用現行模型對應組件的 ER 格式的最新執行追蹤的最頂部記錄。
4. 選取 **確定**。

    執行統計資料會通知您對申請表的重複調用：

    - 調用 **ERSolutionTable** 的次數與您在 **ERSolutionVersionTable** 表中的設定版本記錄一樣多，而這種調用的次數可以減少，以提高效能。
    - 對於在 **ERSolutionVersionTable** 表中發現的每一條設定版本記錄，都調用 **ERVendorTable** 了兩次，而這種調用的數量也可以減少。

    ![ER 模型對應設計工具頁面上的執行統計資料。](./media/GER-JoinDS-Set1Run2.PNG)

5. 關閉頁面。

### <a name="execute-er-format"></a>執行 ER 格式

1. 使用 Finance 或 RCS 的第二個工作階段切換到您的網路瀏覽器索引標籤。
2. 選取 **執行**。
3. 在對話方塊頁面上，在 **使用 JOIN 資料來源** 欄位中選取 **是**。
4. 選取 **確定**。
5. 查看產生的檔案。

    ![使用 JOIN 資料來源產生的電子報表參數檔案。](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a>分析 ER 格式執行追蹤

1. 在 Finance 或 RCS 的第一個工作階段中，選取 **設計工具**。
2. 選取 **效能追蹤**。
3. 在 **效能追蹤** 格線中，選取最上面的記錄，代表使用現行模型對應組件的 ER 格式的最新執行追蹤。
4. 選取 **確定**。

    統計資料會告知您以下資訊：

    - 應用資料庫已經被調用一次，從 **ERVendorTable**、**ERSolutionTable** 和 **ERSolutionVersionTable** 表中獲取記錄，以存取所需的欄位。

    ![ER 模型對應設計工具頁面效能統計細節。](./media/GER-JoinDS-Set2Run2.PNG)

    - 應用程式資料庫已經被調用過一次，透過使用 **詳情** 資料來源中設定的聯結來計算設定版本的數量。

    ![顯示應用程式資料庫調用的 ER 模型對應設計工具頁面。](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>限制

從本主題的範例中可以看出，**JOIN** 資料來源可以由幾個資料來源建立，這些資料來源描述了最終必須連接的記錄的各個資料集。 您可以透過使用內建的 ER [FILTER](er-functions-list-filter.md)函數設定這些資料來源。 當您設定資料來源，使其在 **JOIN** 資料來源之外被調用時，您可以使用公司範圍作為資料選取的條件的一部分。 **JOIN** 資料來源的初始實現並不支援這種類型的資料來源。 例如，當您在 **JOIN** 資料來源的執行範圍內調用一個基於[FILTER](er-functions-list-filter.md)的資料來源時，如果被調用的資料來源包含公司範圍作為資料選取條件的一部分，就會出現異常。

在 Microsoft Dynamics 365 Finance 10.0.12版 (2020 年 8 月) 中，您可以在基於 [FILTER](er-functions-list-filter.md)的資料來源中使用公司範圍作為資料選取條件的一部分，這些資料來源在 **JOIN** 資料來源的執行範圍中被調用。 由於應用程式 [查找](../dev-ref/xpp-library-objects.md#query-object-model)產生器的限制，公司範圍只支援 **JOIN** 資料來源的第一個資料來源。

### <a name="example"></a>範例

例如，您必須對應用程式資料庫進行一次調用，以獲取多家公司的外貿交易清單以及這些交易中參考的庫存項目的詳情。

在這種情況下，您在 ER 模型對應中設定以下工件：

- 代表 **Intrastat** 表的 **Intrastat** 根資料來源。
- 代表 **InventTable** 表的 **項目** 根資料來源。
- **公司** 根資料來源，返回必須存取交易的公司清單 (本例中為 **DEMF** 和 **GBSI**)。 公司代碼可從 **Companies.Code** 欄位中獲得。
- 含有運算式 `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))` 的 **X1** 根資料來源。 作為資料選取條件的一部分，此運算式包含公司範圍的定義 `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`。
- **X2** 資料來源作為 **X1** 資料來源的巢狀項目。 它包括運算式 `FILTER (Items, Items.ItemId = X1.ItemId)`。

最後，您可以設定一個 **JOIN** 資料來源，**X1** 是第一個資料來源，**X2** 是第二個資料來源。 您可以指定 **查找** 作為 **執行** 選項，強制 ER 在資料庫層面上以直接 SQL 調用的方式執行該資料來源。

當設定的資料來源執行時，同時 ER 執行被[追蹤](trace-execution-er-troubleshoot-perf.md)，以下陳述式作為 ER 效能追蹤的一部分顯示在 ER 模型對應設計工具中。

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> 如果您執行已經設定好的 **JOIN** 資料來源，使其包含的資料選取條件對所執行的 **JOIN** 資料來源的其他資料來源有公司範圍，那麼就會發生錯誤。

## <a name="additional-resources"></a>其他資源

[電子報表中的公式設計工具](general-electronic-reporting-formula-designer.md)

[追蹤 ER 格式的執行，以解決效能問題](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
