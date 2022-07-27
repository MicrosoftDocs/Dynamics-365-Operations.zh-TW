---
title: 追蹤 ER 格式的執行以解決效能問題
description: 本主題提供有關如何使用電子報表 (ER) 中的績效追蹤功能來解決績效問題的資訊。
author: NickSelin
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 10eddf2f60db914e6451840d4d7aedb9dce7108874ea3ff45f375b85a55a694f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460297"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>追蹤 ER 格式的執行以解決效能問題

[!include[banner](../includes/banner.md)]

作為設計電子報表 (ER) 設定以產生電子檔過程的一部分，您要定義用於從應用程式中取得資料並將其輸入產生之輸出中的方法。 ER 效能追蹤功能有助於顯著減少收集 ER 格式執行的詳情並使用它們來解決效能問題所涉及的時間和成本。 本教程提供了有關如何對已執行的 ER 格式進行效能追蹤以及如何使用來自這些追蹤的資訊來幫助提高效能的指南。

## <a name="prerequisites"></a>先決條件

若要完成本教學課程中的範例，您必須具有以下存取權限：

- 存取以下角色之一：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

- 存取已為和該應用程式相同之租使用者提供的以下其中一個角色的 Regulatory Configuration Services (RCS) 執行個體：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

您還必須下載並在本地儲存以下檔案。

| 檔案                                  | 內容                               |
|---------------------------------------|---------------------------------------|
| 效能追蹤模型.版本.1     | [樣本 ER 資料模型設定](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| 效能追蹤中繼資料.版本.1  | [樣本 ER 中繼資料設定](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| 效能追蹤對應.版本.1.1 | [樣本 ER 模型對應設定](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| 效能追蹤格式.版本.1.1  | [樣本 ER 格式設定](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a>設定 ER 參數

在應用程式中產生的每個 ER 效能追蹤都作為執行記錄的附件被儲存。 文件管理 (DM) 架構用於管理這些附件。 您必須提前設定 ER 參數，以指定應用於附加效能追蹤的 DM 文件類型。 在 **電子報表** 工作區，選取 **電子報表參數**。 然後，在 **電子報表參數** 頁，在 **附件** 索引標籤，在 **其他** 欄位，選取用於效能追蹤的 DM 文件類型。

![電子報表參數頁面。](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

若要在 **其他** 查詢欄位中提供，DM 文件類型必須在 **文件類型** 頁面 (**組織管理\>文件管理\>文件類型**) 以下列方式設定：

- **類別：** 附加檔案
- **群組：** 檔案

![檔案類型頁面。](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> 所選文件類型必須在目前執行個體的每個公司中都可供使用，因為 DM 附件是公司特定的。

### <a name="configure-rcs-parameters"></a>設定 RCS 參數

透過使用 ER 格式設計工具和 ER 對應設計工具將產生的 ER 效能追蹤匯入 RCS 進行分析。 由於 ER 效能追蹤儲存為與 ER 格式相關的執行記錄的附件，因此您必須提前設定 RCS 參數，以指定應用於附加效能追蹤的 DM 文件類型。 在為您公司提供的 RCS 執行個體中，在 **電子報表** 工作區，選取 **電子報表參數**。 然後，在 **電子報表參數** 頁，在 **附件** 索引標籤，在 **其他** 欄位，選取用於效能追蹤的 DM 文件類型。

![RCS 中的電子報表參數頁面。](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

若要在 **其他** 查詢欄位中提供，DM 文件類型必須在 **文件類型** 頁面 (**組織管理\>文件管理\>文件類型**) 以下列方式設定：

- **類別：** 附加檔案
- **群組：** 檔案

## <a name="design-an-er-solution"></a>設計 ER 解決方案

假設您已經開始設計新的 ER 解決方案來產生顯示廠商交易的新報表。 目前，您可以在 **廠商交易** 頁面上找到所選廠商的交易 (進入 **應付帳款\>廠商\>所有廠商**，選取廠商，然後，在動作窗格上，在 **廠商** 索引標籤上，在 **交易** 組中，選取 **交易**)。 但是，您希望在一份 XML 格式的電子文件中同時包含所有廠商交易。 該解決方案將包含多個 ER 設定，其中包含所需的資料模型、中繼資料、模型對應和格式組件。

1. 登入到已為您的公司設定的 RCS 執行個體。
2. 在本教學課程中，您將為 **Litware, Inc.** 樣本公司建立和修改設定。 因此，請確保此設定提供者已新增到 RCS 並選取為作用中。 如需說明，請參閱[建立設定提供者並標示為作用中](tasks/er-configuration-provider-mark-it-active-2016-11.md)程序。
3. 在 **電子報表** 工作區中，選取 **報告設定** 圖格。
4. 在 **設定** 頁面，將您作為前提條件下載的 ER 設定匯入 RCS，順序如下：資料模型、中繼資料、模型對應、格式。 對於每個設定，請執行以下步驟：

    1. 在動作窗格上，選取 **交換\>從 XML 檔案載入**。
    2. 選取 **瀏覽** 為所需 XML 格式的 ER 設定選取適當的檔案。
    3. 選取 **確定**。

    ![RCS 中的設定頁面。](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>執行 ER 解決方案以追蹤執行

假設您已經完成了 ER 解決方案的第一個版本的設計。 您現在想在您的執行個體中測試它並分析執行效能。

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>將 ER 設定從 RCS 匯入財務和營運應用程式

1. 登入到您的應用程式執行個體。
2. 在本教程中，您將從您的 RCS 執行個體 (您設計 ER 組件的地方) 匯入設定到您的執行個體 (您測試並最終使用它們的地方)。 因此，您必須確保已準備好所有必需的構件。 如需說明，請參閱[從 Regulatory Configuration Services (RCS) 匯入電子報表 (ER) 設定](rcs-download-configurations.md)程序。
3. 按照以下步驟將設定從 RCS 匯入應用程式：

    1. 在 **電子報表** 工作區的 **Litware, Inc.** 設定提供者圖格上，選取 **存放庫**。
    2. 在 **設定存放庫** 頁面，選取 **RCS** 類型的存放庫，然後選取 **開啟**。
    3. 在 **設定** FastTab 上，選取 **效能追蹤格式** 設定。
    4. 在 **版本** FastTab 上，選取所選設定的 **1.1** 版，然後選取 **匯入**。

    ![設定存放庫頁面。](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

資料模型和模型對應設定的相應版本將作為匯入的 ER 格式設定的先決條件自動匯入。

### <a name="turn-on-the-er-performance-trace"></a>打開 ER 效能追蹤

1. 進入 **組織管理\>電子報表\>設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊，在 **執行追踪** 區塊，請按照下列步驟動作：

    1. 在 **執行追蹤格式** 欄位，指定產生的效能追蹤的格式，執行詳情應儲存在 ER 格式和對應元素中：

        - **偵錯追蹤格式** – 如果您計劃以互動方式執行執行時間較短的 ER 格式，請選取此值。 然後開始收集有關 ER 格式執行的詳情。 選取此值後，效能追蹤將收集有關在以下動作上所用時間的資訊：

            - 執行模型對應中被調用以獲取資料的每個資料來源
            - 處理每個格式項目以在產生的輸出中輸入資料

            如果您選取 **偵錯追蹤格式** 值，您可以在 ER 動作設計工具中分析追蹤的內容。 在那裡，您可以查看追蹤中提到的 ER 格式或對應元素。

        - **彙總追蹤格式** - 如果您計劃在批次處理模式下執行具有較長執行時間的 ER 格式，請選取此值。 然後開始收集 ER 格式執行的彙總相關詳情。 選取此值後，效能追蹤將收集有關在以下動作上所用時間的資訊：

            - 執行模型對應中被調用以獲取資料的每個資料來源
            - 執行格式對應中被調用以獲取資料的每個資料來源
            - 處理每個格式項目以在產生的輸出中輸入資料

            **彙總追蹤格式** 值在 Microsoft Dynamics 365 Finance 10.0.20 及更高版本中可供使用。

            在 ER 格式設計工具和 ER 模型對應設計工具中，您可以查看單個組件的總執行時間。 此外，追蹤包含有關執行的詳情，例如執行次數以及單次執行的最短和最長時間。

            > [!NOTE]
            > 此追蹤是根據追蹤的組件路徑收集的。 因此，當單個父組件包含多個未命名的子組件或多個子組件具有相同名稱時，統計資訊可能不正確。

    2. 將以下選項設定為 **是** 以收集執行 ER 模型對應和 ER 格式組件的特定詳情：

        - **收集查詢統計資訊** – 打開此選項時，效能追蹤將收集以下資訊：

            - 資料來源進行的資料庫調用次數
            - 重複調用資料庫的次數
            - 用於進行資料庫調用的 SQL 陳述式的詳情

        - **追蹤快取的存取** – 打開此選項時，效能追蹤將收集有關 ER 模型對應的快取使用情況的資訊。
        - **追蹤資料存取** – 打開此選項時，效能追蹤將收集有關記錄清單類型的已執行資料來源的資料庫調用次數的資訊。
        - **追蹤清單列舉** – 啟用此選項時，效能追蹤將收集有關從記錄清單類型的資料來源請求的記錄數的資訊。

    > [!NOTE]
    > **使用者參數** 對話方塊中的參數特定於使用者和目前的公司。

    ![使用者參數對話方塊。](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>執行 ER 格式

1. 選取 **DEMF** 公司。
2. 進入 **組織管理\>電子報表\>設定**。
3. 在 **設定** 頁面，在設定樹狀結構中，選取 **效能追蹤格式** 項目。
4. 在動作窗格中，選取 **執行**。

請注意，產生的檔案提供了有關 6 個廠商的 265 筆交易的資訊。

## <a name="review-the-execution-trace"></a>查看執行追蹤

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>從應用程式匯出產生的追蹤

效能追蹤與源 ER 格式分離，可以序列化為外部 ZIP 檔案。

1. 進入 **組織管理\>電子報表\>設定偵錯記錄**。
2. 在 **電子報表執行記錄** 頁面，在左窗格中，在 **設定名稱** 欄位，選取 **效能追蹤格式** 查詢已由 **效能追蹤格式** 設定執行產生的記錄。
3. 選取頁面右上角的 **附件** 按鈕 (迴紋針符號)，或按 **Ctrl+Shift+A**。

    ![電子報表執行記錄頁面上的附件按鈕。](./media/GER-PerfTrace-GER-DebugLog.png)

4. 在 **電子報表執行記錄的附件** 頁面的動作窗格上，選取 **開啟** 以將效能追蹤作為 ZIP 檔案獲取並儲存在本地。

    ![電子報表執行記錄的附件。](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> 產生的追蹤僅透過 **GUID** 格式的唯一報表標識符參考來源 ER 報表。 不考慮格式的版本編號。

請注意，為執行的 ER 格式產生的效能追蹤與 ER 模型對應之間的關聯基於所使用的根描述符和 Common Data Model。 不考慮格式和模型對應的版本編號。 也不考慮模型對應的 **模型對應的預設值** 標幟的設定。

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>將產生的追蹤匯入 RCS

1. 在 RCS，在 **電子報表** 工作區中，選取 **報表設定** 圖格。
2. 在 **設定** 頁面的設定樹狀結構中，展開 **效能追蹤模型** 項目，然後選取 **效能追蹤格式** 項目。
3. 在動作窗格上，選取 **設計工具**。
4. 在 **格式設計工具** 頁面上，在動作窗格上，選取 **效能追蹤**。
5. 在 **效能追蹤結果設定** 對話方塊，選取 **匯入效能追蹤**。
6. 選取 **瀏覽** 以選取您之前匯出的 ZIP 檔案。
7. 選取 **確定**。

    ![在 RCS 中的效能追蹤結果設定對話方塊。](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>在 RCS 中使用效能追蹤進行分析 – 格式執行

1. 在 RCS 中，在 **格式設計工具** 頁面，選取 **展開/摺疊** 展開所有格式項目的內容。

    請注意，目前格式的某些項目顯示了附加資訊：

    - 使用格式項目在產生的輸出中輸入資料所花費的實際時間
    - 相同的時間表示為產生整個輸出所花費的總時間的百分比

    ![RCS 中的格式設計工具頁面。](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. 關閉 **格式設計工具** 頁面。

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>在 RCS 中使用效能追蹤進行分析 – 模型對應

1. 在 RCS 中，在 **設定** 頁面的設定樹狀結構中，選取 **效能追蹤對應** 項目。
2. 在動作窗格上，選取 **設計工具**。
3. 選取 **設計工具**。
4. 在 **模型對應設計工具** 頁面上，在動作窗格上，選取 **效能追蹤**。
5. 選取您之前匯入的追蹤。
6. 選取 **確定**。

請注意，新資訊可用於目前模型對應的某些資料來源項目：

- 使用資料來源取得資料所花費的實際時間
- 相同的時間表示為執行整個模型對應所花費的總時間的百分比

請注意，ER 通知您目前模型對應重複資料庫請求，而 VendTable/\<Relations/VendTrans.VendTable\_ AccountNum 資料來源已執行。 之所以會出現這種重複，是因為對於每個迭代的廠商記錄，廠商交易清單被調用了兩次：

- 根據設定的繫結，進行一次調用以在資料模型中輸入每個交易的詳情。
- 進行一次調用以在資料模型中輸入每個廠商的計算交易數量。

![RCS 中模型對應設計工具頁面上有關重複資料庫請求的訊息。](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

值 **\[Q:530\]** 表示調用 VendTrans 表 530 次以將該表中的記錄回傳到 VendTable/\<Relations/VendTrans.VendTable\_AccountNum 資料來源。 值 **\[530\]** 表示 VendTable/\<Relations/VendTrans.VendTable\_AccountNum 資料來源被調用了 530 次，以從該資料來源回傳一條記錄並將其詳情輸入資料模型中。

我們建議您對 VendTable/\<Relations/VendTrans.VendTable\_AccountNum 資料來源使用快取，以減少為獲取 265 個交易的詳情而進行的調用次數，並有助於提高模型對應的效能。

減少對 LedgerTransTypeList 資料來源的調用次數也很有用。 此資料來源用於將 **LedgerTransType** 列舉的每個值與其標籤相關聯。 透過使用此資料來源，您可以找到適當的標籤並將其輸入到每個廠商交易的資料模型中。 目前對該資料來源的調用次數 (9,027) 對於 265 個交易來說非常高。

![RCS 中的模型對應設計工具頁面，顯示對資料來源的 9,027 次調用。](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>根據來自執行追蹤的資訊改善模型對應

### <a name="modify-the-logic-of-the-model-mapping"></a>修改模型對應的邏輯

1. 請按照以下步驟使用快取，以幫助防止對資料庫的重複調用：

    1. 在 RCS 中，在 **模型對應設計工具** 頁面的 **資料來源** 窗格中，選取 **VendTable** 項目。
    2. 選取 **快取**。
    3. 展開 **VendTable** 項目，展開 VendTable 資料來源的一對多關係清單 (**\<Relations** 項目)，然後選取 **VendTrans.VendTable\_AccountNum** 項目。
    4. 選取 **快取**。

    ![快取設定以幫助防止重複調用。](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. 按照以下步驟將 LedgerTransTypeList 資料來源納入 VendTable 資料來源的範圍：

    1. 在 **資料來源類型** 窗格，展開 **函數** 項目，然後選取 **導出欄位** 項目。
    2. 在 **資料來源** 窗格中，選取 **VendTable** 項目。
    3. 選取 **新增**。
    4. 在 **名稱** 欄位中，輸入 **\$TransType**。
    5. 選取 **編輯公式**。
    6. 在 **公式** 欄位中，輸入 **LedgerTransTypeList**。
    7. 選取 **儲存**。
    8. 關上 **公式編輯器** 頁面。
    9. 點選 **確定**。

3. 按照以下步驟快取 **\$TransType** 欄位：

    1. 選取 **LedgerTransTypeList** 項目。
    2. 選取 **快取**。
    3. 選取 **VendTable.\$TransType** 項目。
    4. 選取 **快取**。

    ![$TransType 欄位的快取設定。](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. 按照以下步驟更改 **\$TransTypeRecord** 欄位，使其開始使用快取的 **\$TransType** 欄位：

    1. 在 **資料來源** 窗格中，展開 **VendTable** 項目，展開 **\<Relations** 項目，展開 **VendTrans.VendTable\_AccountNum** 項目，然後選取 **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord** 項目。
    2. 選取 **編輯**。
    3. 選取 **編輯公式**。
    4. 在 **公式** 欄位中，尋找以下運算式：

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. 在 **公式** 欄位中，輸入以下運算式：

        FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType))。

    6. 選取 **儲存**。
    7. 關上 **公式編輯器** 頁面。
    8. 選取 **確定**。

5. 選取 **儲存**。
6. 關上 **模型對應設計工具** 頁面。
7. 關上 **模型對應** 頁面。

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>完成 ER 模型對應設定的修改版本

1. 在 RCS 中，在 **設定** 頁，在 **版本** FastTab，選取版本 **1.2** 的 **效能追蹤對應** 設定。
2. 選取 **更改狀態**。
3. 選取 **完成**。

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>將修改後的 ER 模型對應設定從 RCS 匯入應用程式

重複本主題前面的 [將 ER 設定從 RCS 匯入財務和營運應用程式](#import-configuration)章節中的步驟，以匯入 **效能追蹤對應** 設定的 1.2 版。

## <a name="run-the-modified-er-solution-to-trace-execution"></a>執行修改好的 ER 解決方案以追蹤執行

### <a name="run-the-er-format"></a>執行 ER 格式

重複本主題前面[執行 ER 格式](#run-format)區段中的步驟以產生新的效能追蹤。

## <a name="work-with-the-execution-trace"></a>使用執行追蹤

### <a name="export-the-generated-trace-from-the-application"></a>從應用程式匯出產生的追蹤

重複本主題前面的[從應用程式匯出產生的追蹤](#export-trace)章節中的步驟，以在本地儲存新的效能追蹤。

### <a name="import-the-generated-trace-into-rcs"></a>將產生的追蹤匯入 RCS

重複本主題前面的[將產生的追蹤匯入 RCS](#import-trace)章節中的步驟，將新的效能追蹤匯入 RCS。

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>在 RCS 中使用效能追蹤進行分析 – 模型對應

重複本主題前面的[在 RCS 中使用效能追蹤進行分析 - 模型對應](#use-trace)章節中的步驟來分析最新的效能追蹤。

請注意，您對模型對應所做的調整已經消除了對資料庫的重複查找。 此模型對應對資料庫表和資料來源的調用次數也減少了。 因此，整個 ER 解決方案的效能得到了提高。

![在 RCS 的模型對應設計工具頁面上追蹤 VendTable 資料來源的資訊。](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

在追蹤資訊中，VendTable 資料來源的值 **\[12\]** 表示該資料來源被調用了 12 次。 值 **\[Q:6\]** 表示將六個調用轉換為對 VendTable 表的資料庫調用。 值 **\[C:6\]** 表示快取了從資料庫中獲取的記錄，並且使用快取處理了其他六個調用。

請注意，對 LedgerTransTypeList 資料來源的調用次數已從 9,027 減少到 240。

![在 RCS 的模型對應設計工具頁面上追蹤 LedgerTransTypeList 資料來源的資訊。](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>查看應用程式中的執行追蹤

除了 RCS，某些版本可能會提供 ER 架構設計者體驗的功能。 這些版本具有可以打開的 **啟用設計模式** 選項。 您可以在 **電子報表參數** 頁面的 **一般** 索引標籤上找到此選項，您可以從 **電子報表** 工作區打開該索引標籤。

![在電子報表參數頁面上啟用設計模式選項。](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

如果您使用這些版本之一，您可以直接在應用程式中分析產生的效能追蹤的詳情。 您不必從應用程式中匯出它們並將它們匯入 RCS。

## <a name="review-the-execution-trace-by-using-external-tools"></a>使用外部工具查看執行追蹤

### <a name="configure-user-parameters"></a>設定使用者參數

1. 進入 **組織管理\>電子報表\>設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊，在 **執行追踪** 區塊，在 **執行追蹤格式** 欄位，選取 **PerfView XML**。

### <a name="run-the-er-format"></a>執行 ER 格式

重複本主題前面[執行 ER 格式](#run-format)區段中的步驟以產生新的效能追蹤。

請注意，網路瀏覽器提供了一個 ZIP 檔案供下載。 此檔案包含 PerfView 格式的效能追蹤。 然後您可以使用 PerfView 效能分析工具來分析 ER 格式執行的詳情。

![PerfView 格式的效能追蹤資訊。](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>使用外部工具查看包含資料庫查詢的執行追蹤

由於對 ER 架構進行了改進，以 PerfView 格式產生的效能追蹤現在提供了有關 ER 格式執行的更多詳情。 在 Microsoft Dynamics 365 for Finance and Operations 版本 10.0.4 (2019 年 7 月)，此追蹤還可以包括對應用程式資料庫執行的 SQL 查詢的詳情。

### <a name="configure-user-parameters"></a>設定使用者參數

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊的 **執行追蹤** 區塊中，設定以下參數：

    - 在 **執行追蹤格式** 欄位，選取 **PerfView XML**。
    - 將 **收集查詢統計資訊** 選項設定為 **是**。
    - 將 **追蹤查詢** 選項設定為 **是**。

    ![執行追蹤區塊，使用者參數對話方塊。](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>執行 ER 格式

重複本主題前面[執行 ER 格式](#run-format)區段中的步驟以產生新的效能追蹤。

請注意，網路瀏覽器提供了一個 ZIP 檔案供下載。 此檔案包含 PerfView 格式的效能追蹤。 然後您可以使用 PerfView 效能分析工具來分析 ER 格式執行的詳情。 此追蹤現在包括執行 ER 格式期間 SQL 資料庫存取的詳情。

![PerfView 中執行的 ER 格式的追蹤資訊。](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>其他資源

- [電子報表概觀](general-electronic-reporting.md)
- [透過新增參數化的導出欄位資料來源來提高 ER 解決方案的效能](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
