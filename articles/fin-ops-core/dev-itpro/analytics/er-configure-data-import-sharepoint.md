---
title: 從 SharePoint 設定資料匯入
description: 本主題說明如何從 Microsoft SharePoint 匯入資料。
author: NickSelin
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 9ac328e660c7a8a3b4a4f34a650062a0fa974771
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460246"
---
# <a name="configure-data-import-from-sharepoint"></a>從 SharePoint 設定資料匯入

[!include[banner](../includes/banner.md)]

若要使用電子報表 (ER) 架構從傳入檔案匯入資料，您必須設定支援匯入的 ER 格式，然後執行使用該格式作為資料來源的 **至目的地** 類型的模型對應。 若要匯入資料，您必須導航到要匯入的檔案。 傳入的檔案可以由使用者手動選取。 借助支援從 Microsoft SharePoint 匯入資料的新 ER 功能，可以將此過程設定為無人值守。 您可以使用 ER 設定從儲存在 Microsoft SharePoint 資料夾中的檔案執行資料匯入。 本主題說明如何完成從 SharePoint 的匯入。 這些範例使用廠商交易作為業務資料。

## <a name="prerequisites"></a>先決條件
若要完成本主題中的範例，您必須具有以下存取權限：

- 存取以下角色之一：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

- 存取設定為與應用程式一起使用的 Microsoft SharePoint Server 實體。
- 1099 付款的 ER 格式和模型設定。

### <a name="create-required-er-configurations"></a>建立所需的 ER 設定
播放 **ER 從 Microsoft Excel 檔案匯入資料** 工作指南，這是 **7.5.4.3 獲取/開發 IT 服務/解決方案組件 (10677)** 業務流程的一區段。 這些工作指南將引導您完成設計和使用 ER 設定以交互方式從 Microsoft Excel 檔案匯入廠商交易的過程。 如需相關資訊，請參閱[以 Excel 格式解析傳入的文件](parse-incoming-documents-excel.md)。 完成工作指南後，您將進行以下安裝。

#### <a name="er-configurations"></a>ER 設定

- ER 模型設定，**1099 付款模型**
- ER 格式設定，**從 Excel 匯入廠商交易的格式**

![用於從 SharePoint 匯入資料的 ER 設定。](./media/GERImportFromSharePoint-01-Configurations.PNG)

#### <a name="sample-of-the-incoming-file-for-data-import"></a>資料匯入的傳入檔案樣本

- Excel 檔案 **1099import-data.xlsx**，包含應匯入的廠商交易。

![用於從 SharePoint 匯入的樣本 Excel 檔案。](./media/GERImportFromSharePoint-02-Excel.PNG)
    
> [!NOTE]
> 匯入廠商交易的格式被選為預設模型對應。 因此，如果您執行 **1099 付款模型** 的模型對應，並且該模型對應屬於 **至目的地** 類型，則模型對應會執行此格式以從外部檔案匯入資料。 然後它使用該資料來更新申請表。

## <a name="configure-access-to-sharepoint-for-file-storage"></a>設定對 SharePoint 的存取以進行檔案儲存
若要將電子報表檔案儲存在 SharePoint 位置，您必須設定對現行公司將使用的 SharePoint Server 實體的存取權限。 在此範例中，公司是 USMF。 如需相關資訊，請參閱[設定 SharePoint 儲存](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage)。

1. 完成[設定 SharePoint 儲存](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage)中的步驟。
2. 打開設定的 SharePoint 網站。
3. 建立以下資料夾，其中可以儲存傳入的電子報表檔案：

     - 檔案匯入來源 (主要) (範例如以下螢幕擷取畫面所示)
     - 檔案匯入來源 (替代) 

    ![檔案匯入來源 (主要)。](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

4.  (選取性) 建立以下資料夾，匯入後可以在其中儲存檔案。 

    - 檔案封存資料夾 - 此資料夾將用於成功匯入的檔案。
    - 檔案警告資料夾 - 此資料夾用於存放帶有警告的匯入檔案。
    - 檔案錯誤資料夾 - 此資料夾用於存放無法匯入的檔案。

4. 進入 **組織管理 > 文件管理 > 文件類型**。
5. 建立以下將用於存取您建立的 SharePoint 資料夾的文件類型。 如需相關資訊，請參閱[設定文件類型](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types)。

|檔案類型       | 群組              | 位置      | SharePoint 資料夾      |
|--------------------|--------------------|---------------|------------------------|
|SP 主要             |檔案                |SharePoint     |檔案匯入來源 (主要)|
|SP 替代             |檔案                |SharePoint     |檔案匯入來源 (替代) |
|SP 封存             |檔案                |SharePoint     |檔案封存資料夾|
|SP 警告             |檔案                |SharePoint     |檔案警告資料夾|
|SP 錯誤             |檔案                |SharePoint     |檔案錯誤資料夾|

![SharePoint設定 - 新增檔案類型。](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>為 ER 格式設定 ER 來源
1. 點選 **組織管理**\>**電子報表**\>**電子報表來源**。
2. 在 **電子報表來源** 頁面上，使用設定的 ER 格式設定資料匯入的來源檔案。
3. 定義檔案名掩碼，以便僅匯入擴充名為 .xlsx 的檔案。 檔案名掩碼是選取性，僅在已定義時使用。 您只能為每種 ER 格式定義一個掩碼。
4. 將 **匯入前排序檔案** 更改為 **不排序**，如果有多個檔案要匯入並且匯入順序不重要
5. 選取您之前建立的所有 SharePoint 資料夾。

    [![ER 檔案來源設定。](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - ER *來源* 是為每個應用程式公司單獨定義的。 相比之下，ER *設定* 在公司之間共用。
> - 當您刪除 ER 格式的 ER 來源設定時，所有連線的檔案狀態 (見下文) 也會透過確認刪除。

## <a name="review-the-files-states-for-the-er-format"></a>查看 ER 格式的檔案狀態
1. 在 **電子報表來源** 頁面，選取 **來源的檔案狀態** 查看現行 ER 格式的已設定檔案來源的內容。
2. 在 **檔案** 區段中，查看檔案清單。 此清單提供以下內容：

    - 適用的來源檔案，基於檔案名掩碼 (如果定義了檔案名掩碼)，並且已準備好進行資料匯入。 對於這些檔案，**匯入格式的來源記錄** 區段為空白。
    - 以前匯入的檔案。 對於每一個檔案，在 **匯入格式的來源記錄** 區段中，您可以查看此檔案的匯入歷史記錄。

您還可以透過選取 **組織管理**\>**電子報表**\>**來源的檔案狀態** 來開啟 **來源的檔案狀態** 頁面。 在這種情況下，該頁面提供有關您現行登入的公司中已為其設定檔案來源的所有 ER 格式的檔案來源的資訊。

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>從 SharePoint 資料夾中的 Excel 檔案匯入資料
1. 在 SharePoint 中，將包含廠商交易的 Microsoft Excel 檔案 **1099import-data.xlsx** 上傳到您之前建立的 **檔案匯入來源 (主要)** SharePoint 資料夾。

    [![SharePoint 內容 - 用於匯入的 Microsoft Excel 檔案。](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. 在 **來源的檔案狀態** 頁面，選取 **重新整理** 來重新整理頁面。 上傳到 SharePoint 的 Excel 檔案顯示在此頁面上，狀態為 **準備**。 現行支援以下狀態：

    - **準備** – 為 SharePoint 資料夾中的每個新檔案自動指派。 此狀態表示檔案已準備好匯入。
    - **輸入中** – 當檔案將被匯入進程鎖定以防止其被其他進程使用 (如果其中許多進程同時執行) 時，由 ER 報告自動指派。
    - **已進口** – 檔案匯入成功完成時由 ER 報告自動指派。 此狀態表示匯入的檔案已從設定的檔案來源中刪除 (SharePoint 資料夾)。
    - **失敗** – 當檔案匯入完成但出現錯誤或異常時，由 ER 報告自動指派。
    - **等候中** – 由使用者在此頁面上手動指派。 此狀態表示暫時不會匯入該檔案。 此狀態可用於推遲某些檔案的匯入。

    [![重新整理了所選來源的 ER 檔案狀態頁面。](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>從 SharePoint 檔案匯入資料
1. 開啟 ER 設定樹狀結構，選取 **1099 付款模式**，並展開 ER 模型組件清單。
2. 選取模型對應的名稱以開啟所選 ER 模型設定的模型對應清單。

    [![設定頁面。](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. 選取 **執行** 來執行選定的模型對應。 因為您為 ER 格式設定了檔案來源，所以您可以更改 **檔案來源** 選項，如果需要。 如果您保留此選項的設定，則 .xslx 檔案將從設定的來源匯入 (SharePoint 資料夾，在本例中)。

    在此範例中，您只匯入一個檔案。 但是，如果有多個檔案，則會按照它們新增到 SharePoint 資料夾的順序選取它們進行匯入。 ER 格式的每次執行都會匯入一個選定的檔案。

    [![從 SharePoint 匯入並執行 ER 模型對應。](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. 模型對應可以在批次處理模式下[無人值守](#limitations)地執行。 在這種情況下，每次批處理執行此 ER 格式時，都會從設定的檔案來源匯入一個檔案。

    從 SharePoint 資料夾成功匯入檔案後，該檔案將從該資料夾中刪除，並移至成功匯入檔案的資料夾或匯入檔案的資料夾，並顯示警告。 否則，如果未設定失敗檔案的資料夾，它將移動到失敗檔案的資料夾或保留在此資料夾中。 

5. 輸入憑證 ID，例如 **V-00001**，然後選取 **確定**。

    [![執行 ER 模型對應。](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. 在 **來源的檔案狀態** 頁面，選取 **重新整理** 來重新整理頁面。

    [![來源頁面的 ER 檔案狀態。](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. 在 **檔案** 區段中，查看檔案清單。 **匯入格式的來源記錄** 區段提供 Excel 檔案匯入的歷史記錄。 由於此檔案已成功匯入，因此它在 SharePoint 資料夾中標記為 **已刪除**。
8. 審查 **檔案匯入來源 (主要)** SharePoint 資料夾。 成功匯入的 Excel 檔案已從此資料夾中刪除。
9. 選取 **應付帳款**\>**定期工作**\>**稅 1099**\>**1099 的廠商結算**。
10. 在 **從日期** 和 **迄今為止** 欄位，輸入適當的值。 然後選取 **手動 1099 筆交易**。

    從 SharePoint 上的 Excel 檔案匯入的憑證 **V-00001** 的廠商交易記錄顯示在頁面上。

    [![1099 廠商交易頁面。](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>準備要匯入的 Excel 檔案
1. 開啟您之前使用的 Excel 檔案。 在第 3 列第 1 欄中，新增應用程式中不存在的廠商代碼。 向該行新增額外的假廠商資訊。

    [![用於從 SharePoint 匯入的樣本 Microsoft Excel 檔案。](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. 將包含廠商交易的更新後的 Excel 檔案上傳到 **檔案匯入來源 (主要)** SharePoint 資料夾。
3. 開啟 ER 設定樹狀結構，選取 **1099 付款模式**，並展開 ER 模型組件清單。
4. 選取模型對應的名稱以更新模型對應，以便在資料匯入過程中將錯誤的廠商代碼視為錯誤。
5. 選取 **設計工具**。
6. 在 **驗證** 索引標籤，您必須更改驗證規則的驗證後操作，該規則設定為評估匯入的廠商帳戶是否存在於應用程式中。 將 **驗證後動作** 欄位的值更新為 **停止執行**、儲存更改並關閉頁面。

    [![ER 模型對應設計工具頁面。](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. 儲存您的更改，然後關閉 ER 模型對應設計工具。
8. 選取 **執行** 以執行修改後的 ER 模型對應。
9. 輸入憑證 ID，例如 **V-00002**，然後選取 **確定**。

    Infolog 包含一條通知，指出 SharePoint 資料夾中有一個檔案包含不正確的廠商帳戶並且無法匯入。

    [![已完成的執行 ER 模型對應。](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. 在 **來源的檔案狀態** 頁面上，選取 **重新整理**，然後在 **檔案** 區段，查看檔案清單。

    [![所選來源的 ER 檔案狀態頁面。](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

   **匯入格式的來源記錄** 區段表明匯入過程失敗並且檔案位於檔案錯誤 SharePoint 資料夾中 (未選定 **已刪除** 核取方塊)。 如果您透過新增正確的廠商代碼在 SharePoint 上修復此檔案，然後將其移動到檔案匯入源 (主要) SharePoint 資料夾，則可以再次匯入該檔案。

11. 選取 **應付帳款**\>**定期工作**\>**稅 1099**\>**1099 的廠商結算**，在 **從日期** 和 **迄今為止** 欄位輸相應的值，然後選取 **手動 1099 交易**。

    只有憑證 V-00001 的交易可用。 即使在 Excel 檔案中找到最後匯入交易的錯誤，也沒有可用的憑證 V-00002 交易。

## <a name=""></a><a name="limitations">限制</a>

在 10.0.25 版之前的 Dynamics 365 Finance 中，ER 架構的使用者介面 (UI) 不提供啟動新批次處理作業的功能，該批處理作業將執行模型對應以在無人值守模式下匯入資料。 相反，您必須開發新邏輯，以便可以從應用程式 UI 調用設定的 ER 模型對應以從輸入檔案匯入資料。 若要開發此邏輯，需要進行一些工程工作。 

如需 ER API 的相關資訊，請參閱[應用程式更新 7.3 的 ER 架構 API 更改](er-apis-app73.md)中的[為資料匯入執行格式對應的代碼](er-apis-app73.md#code-to-run-a-format-mapping-for-data-import)章節。 查看 `Application Suite` 模型的 `BankImport_RU` 類中的代碼，了解如何實現您的自訂邏輯。 `BankImport_RU` 類擴展了 `RunBaseBatch` 類。 特別是，查看 `runER()` 方法，其中 `ERIModelMappingDestinationRun` 物件被建立為 ER 模型對應的執行程式。

在 Finance 版本 10.0.25 及更高版本中，ER 架構 UI 確實提供了啟動新批次處理作業的功能，該作業將執行模型對應以在無人參與模式下匯入資料。 如需此過程的相關資訊，請參閱[從手動選取的檔案中以批次處理模式匯入資料](er-configure-data-import-batch.md)。

## <a name="additional-resources"></a>其他資源

[電子報表概觀](general-electronic-reporting.md)

[應用程式更新 7.3 的 ER 架構 API 更改](er-apis-app73.md)

[應用程式更新 10.0.23 的 ER 架構 API 更改](er-apis-app10-0-23.md)

[應用程式更新 10.0.25 的 ER 架構 API 更改](er-apis-app10-0-25.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
