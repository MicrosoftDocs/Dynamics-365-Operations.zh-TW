---
title: ER 設定中的效能問題故障排除
description: 本主題說明如何在電子報表 (ER) 設定中尋找和修復效能問題。
author: NickSelin
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b5f5308f171b6cd4224debec897dbde133e6d8424673aabfab51e6b83b9014e2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460575"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>ER 設定中的效能問題故障排除

本主題說明如何在[電子報表](general-electronic-reporting.md) (ER) [設定](general-electronic-reporting.md#Configuration)中尋找和解決效能問題。

通常，效能調查包括幾個步驟。

1. [收集](#collecting-data)資料。
2. 分析收集的資料。
3. 根據分析結果，使用 ER 設定[做出改變](#making-changes)，或決定收集更多資料。

## <a name="troubleshooting"></a>疑難排解

### <a name="analyze-execution-time"></a>分析執行時間

執行時間可能取決於不可預測的因素，例如在同一環境中執行的其他工作以及第一次調用時使用資料的快取。 因此，您應該多次重複執行和測量。

有時，效能問題不是由用於報表的 ER 格式設定引起的。 相反，它們是由用於打開該 ER 格式設定的 X++ 代碼引起的。

1. 在[動作中心](#infolog-time)或[事件記錄檔](#event-log-time)中，查看報表的執行時間。
2. 將報表的執行時間與場景中的總執行時間進行比較。
3. 如果報表的執行時間遠小於總執行時間，請考慮報表處理的資料量：

    - 如果報表處理少量資料，則問題可能涉及設定的載入時間。
    - 如果報表處理大量資料，則問題可能涉及預處理 X++。 採用[Trace Parser](#analyze-trace-parser-trace)來分析這個案例。

    對於其他情況，請參閱下一節。

4. 執行涉及不同資料量的多個測試，以確定執行時間如何取決於資料量。

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>分析 Trace Parser 追蹤

準備一個小範例，或者在報表產生的隨機部分收集幾個追蹤。

那麼，在[Trace Parser](#trace-parser)，做一個標準的自下而上的分析，並回答以下問題：

- 就時間消耗而言，最重要的方法是什麼？
- 這些方法使用了總時間的哪一部分？

對查詢回答相同的問題。

如果您看到方法以「ER」為前綴，請轉到下一節。

如果您發現方法或查詢源自應用程式套件，請考慮進行通用最佳化 (例如，建立索引)。

分析調用次數。 如果數量明顯高於預期，請考慮快取設定的相應節點。

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>分析資料庫調用

準備一個具有少量資料的範例，以便您可以收集 [ER 追蹤](#electronic-reporting-traces)。

然後在 ER 模型對應設計工具中打開追蹤，並查看頁面底部。 回答下列問題：

- 是否有任何重複查詢？ 如果有，請考慮以下修復之一：

    - 如果您認為一個父記錄中有多個調用，請[使用快取](#use-caching)。
    - 如果您認為不同記錄中存在對同一記錄的調用，請[使用快取的參數化計算欄位](#cached-parameterized)。
    - 如果您必須從資料庫中讀取大量不同的記錄，請 [使用 **JOIN** 資料來源](#use-join-datasource)。

- 查詢和提取記錄的數量是否與資料總量相對應？ 例如，如果一個文件有 10 行，那麼統計資料是否顯示報表提取了 10 行或 1,000 行？ 如果您有大量提取的記錄，請考慮以下修復之一：

    - [使用 **FILTER** 函數而不是 **WHERE** 函數](#filter)來處理 SQL Server 端的資料。
    - 使用快取來避免獲取相同的資料。
    - [使用收集的資料函數](#collected-data)以避免獲取相同的資料進行匯總。

### <a name="analyze-perfview-traces"></a>分析 PerfView 追蹤

[PerfView](#perfview)是資深開發人員的工具。 如需以下步驟的相關詳情，請參閱[掛鐘時間調查基礎](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics)。

1. 使用線程時間收集追蹤。
2. 僅包括使用 **runUnattended** 的堆疊，以僅篩選具有設定執行的線程。 (將 **runUnattended** 新增到 **IncPats** 輸入方塊。)
3. 摺疊所有 CPU、網路和封鎖時間。
4. 載入[PerfView 的 ER 預設](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml)。
5. 選取 **ER**\>**其他預設**。
6. 查看名稱：

    - 您可能會看到消耗時間最多的平台代碼。
    - 您可以點兩下 (或按兩下點選) 並向上瀏覽 **被調用者**。

        如果您找到前綴為「ERExpression」的類，並且它們是與公式相關的函數，您可以根據類名猜測函數名，您可以查看 ER repo 來查看屬性。

### <a name="fixes"></a>修復

- 如果您看到大部分 CPU 時間都被查詢所消耗，請嘗試減少查詢次數：

    - 為重複的查詢[查看 ER 追蹤](#analyze-database-calls)。
    - 查看獲取了多少記錄，並評估理論上應該獲取多少資料。

- 如果您看到大部分 CPU 時間都被所使用的函數所消耗，請嘗試在設定中找到消耗資源最多的位置。
- 如果您發現大部分 CPU 時間都被資料收集函數佔用，請考慮在模型對應方面將它們替換為 *SQL 分組依據*。

### <a name="collecting-data"></a><a name="collecting-data"></a>收集資料

根據您的環境，有幾種方法可以收集可用資料：

- 獲取總執行階段間：

    - 從動作中心
    - 從事件記錄檔

- 分析執行：

    - 透過使用 ER 工具
    - 透過使用 Trace Parser
    - 透過使用 PerfView

#### <a name="collecting-data-in-a-production-environment"></a>在生產環境中收集資料

有時，只有在生產環境中才能重現問題。 可以透過以下方式收集資料：

- 透過使用[Trace Parser](../perf-test/trace-trace-tutorial.md)追蹤
- 透過使用[ER 執行](trace-execution-er-troubleshoot-perf.md)追蹤
- 透過使用總執行時間

#### <a name="collecting-data-in-a-development-environment"></a>在開發環境中收集資料

除了可以在生產環境中使用的工具之外，還有一些工具可以在開發環境中使用：

- 事件記錄檔 (Microsoft-Dynamics-ElectronicReporting)。 該記錄可以為您提供總執行時間。
- 通用 .NET 工具，例如 PerfView。

此外，開發環境為您提供了更大的實驗靈活性。 例如，您可以關閉部分報表以查看執行時間如何受到影響。

### <a name="tools"></a><a name="tools"></a>工具

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>動作中心的執行時間

ER 可以在動作中心顯示設定的執行時間。 此選項僅適用於特定使用者和特定公司，並且僅適用於互動式工作階段。 若要提供此功能，請按照以下步驟動作。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊中，將 **顯示檔案產生時間** 選項設定為 **是**。

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>事件記錄檔中的執行時間

1. 開啟視窗事件檢視器。
2. 在 **應用程式和服務記錄** 下面，開啟 **Microsoft-Dynamics-ElectronicReporting/Operational**。
3. 查詢 **FormatMapingRun** 事件，其中 **EventID=2**，因為這些事件包含有關經過時間的資訊。

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>Trace Parser 追蹤 

因為 ER 是在 X++ 中實作，所以您可以使用常用的 X++ 工具來分析效能。 如需相關資訊，請參閱[使用 Trace Parser 進行追蹤](../perf-test/trace-trace-tutorial.md)。

這種方法有一些限制。 由於部分 ER 是用 C# 實作的，因此並非所有細節都可用。 但是，您可以查看資料使用詳情。 此外，長時間執行的報表可能會超出追蹤儲存空間限制。

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>ER 追蹤

ER 可以收集自己的追蹤，並為這些追蹤提供視覺效果和分析工具。 如需相關資訊，請參閱[跟踪 ER 格式的執行以解決效能問題](trace-execution-er-troubleshoot-perf.md)。

#### <a name="perfview"></a><a name="perfview"></a>PerfView

因為 X++ 和 ER 都是在 .NET 平台之上實作，所以您可以使用常用的 .NET 工具。 例如，您可以使用免費的[PerfView](https://github.com/Microsoft/perfview)工具。

您還可以從命令列收集資料。 例如，以下 Windows PowerShell 指令碼收集執行時間，直到電腦上停止任何格式執行。

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

這種方法有一些限制。 您必須具有對電腦的管理存取權限。 此外，您必須是經驗豐富的開發人員，因為學習曲線陡峭。

### <a name="making-changes"></a><a name="making-changes"></a>做出改變

#### <a name="use-caching"></a><a name="use-caching"></a>使用快取

儘管快取減少了再次獲取資料所需的時間，但它會消耗記憶體。 在獲取的資料量不是很大的情況下使用快取。 如需相關資訊和說明如何使用快取的範例，請參閱[根據來自執行追蹤的資訊改進模型對應](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace)。

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>使用快取的參數化導出欄位

有時，必須反複查詢值。 範例包括帳戶名稱和帳號。 為了幫助節省時間，您可以建立一個在頂層具有參數的導出欄位，然後將該欄位新增到快取中。

我們建議您僅在快取資料較小的情況下使用此方法。 如需相關資訊，請參閱[透過新增參數化的導出欄位資料來源來提高 ER 解決方案的效能](er-calculated-field-ds-performance.md)。

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>使用 JOIN 資料來源

**JOIN** 資料來源使一個查詢可以獲取多個連線的記錄。 不必使用單獨的查詢來獲取每個連線的記錄。 例如，如果您有 1,000 行，並且您按關係獲取每行的項目資料，那麼您將有 1,001 個查詢 (= 1,000 + 1)。 如果您使用 **JOIN** 資料來源，您將只使用一個查詢來獲取相同的資料。 如需相關資訊，請參閱[在 ER 模型對應中使用 JOIN 資料來源從多個應用程式表中獲取資料](er-join-data-sources.md)。

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>使用 FILTER 函數而不是 WHERE 函數

**[FILTER](er-functions-list-filter.md)** 函數在 SQL Server 上執行條件，而 **WHERE** 函數從清單中獲取所有資料，一次一條記錄，並為每條記錄套用條件。 例如，您想從 1,000 條記錄中選取一條記錄。 如果您使用 **WHERE**，將獲取所有 1,000 條記錄。 但是，如果您使用 **FILTER**，只會獲取一條記錄。 **FILTER** 也可以在資料庫端使用索引。

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>使用收集的資料函數或累積的資料資料來源

如果您的設定有一個 *分組依據* 組件，該組件按報表匯總先前獲取的資料，則該組件將再次獲取所有資料。 透過使用收集的資料函數，您可以使 ER 在第一次擷取期間累積資料。 如需相關資訊，請參閱[ER 設定格式以進行計數和求和](tasks/er-format-counting-summing-2.md)。

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>在 X++ 中重寫部分設定

ER 支援調用資料表和分類的方法，包括擴充功能。 考慮在 X++ 中重寫部分模型對應以幫助提高效能。

ER 可以使用來自以下來源的資料：

- 分類 (**物件** 和 **分類** 資料來源)
- 資料表 (**資料表** 和 **資料表記錄** 資料來源)

[ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory)還提供了一種從調用代碼發送預先計算的資料的方法。 應用程式套件包含許多這種方法的範例。
