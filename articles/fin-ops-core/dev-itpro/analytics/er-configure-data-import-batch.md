---
title: 以批次處理模式從手動選取的檔案中匯入資料
description: 本主題介紹如何以批次處理模式從手動選取的檔案中匯入資料。
author: NickSelin
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.openlocfilehash: 8615b5a0623fd696c64f4ec03e481a2bcb16c0ac
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460592"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>以批次處理模式從手動選取的檔案中匯入資料

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

若要使用[電子報表 (ER)](general-electronic-reporting.md) 架構以批次處理模式從手動選取的輸入檔案中匯入資料，請設定支援匯入的 ER [格式](er-overview-components.md#format-component)。 然後執行使用該格式作為資料來源的 **前往目的地** 類型的[模型對應](er-overview-components.md#model-mapping-component)。 若要匯入資料，請瀏覽到要匯入的檔案，然後手動選取它。 

支援以批次處理模式匯入資料的新 ER 函數使此過程可以設定為無人值守。 您可以使用 ER 設定透過從 ER 使用者界面 (UI) 安排新的批次處理作業來執行資料匯入。

本主題介紹如何以批次處理方式從手動選取的檔案中完成資料匯入。 這些範例使用廠商交易作為業務資料。 這些範例的步驟可以在 **USMF** 公司中完成。 無需編碼。

## <a name="prerequisites"></a>先決條件

若要完成本主題中的範例，您必須具有以下存取權限：

- 以下角色之一：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

- 1099 付款的 ER 格式和模型設定

### <a name="create-the-required-er-configurations"></a>創建所需的 ER 設定

若要建立所需的 ER 配置並獲得其他先決條件，請執行以下其中一個步驟：

- 播放 **ER 從 Microsoft Excel 檔案匯入資料** 工作指南，這是 **7.5.4.3 獲取/開發 IT 服務/解決方案組件 (10677)** 業務流程的一區段。 這些工作指南將引導您完成設計和使用從 Microsoft Excel 檔案中互動式匯入廠商交易的 ER 設定的過程。 如需相關資訊，請參閱[以 Excel 格式解析傳入的文件](parse-incoming-documents-excel.md)。
- 完成[設定從 SharePoint 匯入資料](er-configure-data-import-sharepoint.md)中的範例。 這些範例將引導您完成設計和使用 ER 設定的過程，這些設定以互動方式從儲存在 SharePoint 資料夾中的 Excel 檔案中匯入廠商交易。

### <a name="download-the-required-er-configurations"></a>下載所需的 ER 設定

1. 下載以下 ER 設定，並將其儲存在本地。

    | 內容描述 | 檔案 |
    |---------------------|------|
    | **1099 付款模型** ER 資料模型設定 | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | **用於匯入廠商交易 (Excel)** ER 格式設定 | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. 使用[從 XML 檔案載入](er-defer-sequence-element.md#import-the-sample-er-configurations) ER 選項按以下順序將下載的 ER 設定匯入您的 Dynamics 365 Finance 實體：

    1. ER 資料模型設定
    2. ER 格式設定

### <a name="download-the-required-excel-files"></a>下載所需的 Excel 檔案

- 下載以下範例資料集，並儲存在本地。

    | 內容描述 | 檔案 |
    |---------------------|------|
    | 包含用於匯入的樣本資料的輸入 **1099import-data.xlsx** 檔案 | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>查看先決條件

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面，查看準備好的 ER 解決方案以批次模式匯入資料。
3. 查看 **用於匯入廠商交易 (Excel)** 格式設定。

    - 此設定的格式組件旨在解析輸入 Excel 檔案。
    - 此設定的模型對應組件用於使用解析後的 Excel 檔案中的資料填入基礎資料模型。

    ![用於從 ER UI 批次匯入資料的 ER 格式設定。](./media/er-configure-data-import-batch-configurations-1.png)

4. 查看 **1099 付款模型** 資料模型設定。

    - 此設定的模型組件表示用於在執行的 ER 組件之間傳遞資料的資料模型的結構。
    - 此設定的模型對應組件用於從執行的格式組件中提取資料，然後更新應用程式表。

    ![用於從 ER UI 批次匯入資料的 ER 資料模型。](./media/er-configure-data-import-batch-configurations-2.png)

5. 開啟 Excel 中的 **1099import-data.xlsx** 檔案。

    ![帶有資料的樣本 Excel 檔案，用於以批次處理模式匯入。](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>從 UI 為 ER 啟用批次資料匯入

1. 進入 **系統管理**\>**工作區**\>**函數管理**。
2. 在 **函數管理** 工作區，選取 **批次執行手動上傳文件的 ER 匯入** 函數，然後選取 **立即啟用**。

## <a name="import-data-from-manually-selected-excel-files"></a>從手動選取的 Excel 檔案中匯入資料

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面，選取　**1099 付款模式** 資料模型設定。
3. 在 **設定組件** FastTab，選取 **用於 1099 手動交易匯入** 連結。
4. 在 **模型到資料來源的對應** 頁，預先選取 **用於 1099 手動交易匯入** 模型對應。 選取 **執行**。
5. 在 **參數** 索引標籤上，選取 **瀏覽**。 尋找並選取 **1099import-data.xlsx** 檔案，然後選取 **確定**。
6. 在 **輸入憑證編號** 欄位，輸入 **V-00001**。
7. 在 **在背景執行** 索引標籤上，將 **批次處理** 選項設為 **是**。

    請注意，**工作描述** 欄位設定為 **執行模型對應「對於 1099 手動交易匯入」，設定「1099 付款模型」**。 此值表示所選模型對應的執行將被安排為新的批次處理作業。

    ![在電子報表參數對話方塊中以批次處理模式指定資料匯入的詳情。](./media/er-configure-data-import-batch-execution-parameters.png)

8. 選取 **確定**。 會有一條訊息通知您已安排新的批次處理作業。

    ![有關模型到資料來源對應頁面上的新安排批次處理作業的訊息。](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>查看批次處理作業頁面上的資料匯入結果

1. 進入 **常用**\>**查詢**\>**批次作業**\>**我的批次處理作業**。
2. 在 **批次處理作業** 頁面，篩選批次處理作業清單以查找計劃的批次處理，然後選取它。
3. 選取 **作業編號** 連結以查看作業詳情。
4. 在 **批次處理工作** FastTab，選取 **記錄**。

    ![批次處理作業頁面上的記錄按鈕。](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. 查看執行詳情。

    ![批次處理作業頁面上計劃批次處理作業的執行記錄。](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>更改資料匯入參數

在您的批次被安排之後並且尚未執行階段，您可以更改安排的資料匯入的參數。

1. 進入 **常用**\>**查詢**\>**批次作業**\>**我的批次處理作業**。
2. 在 **批次處理作業** 頁面，篩選批次處理作業清單以查找計劃的批次處理，然後選取它。
3. 選取 **更改狀態**。
4. 在 **選取新狀態** 對話方塊中，選取 **等待**，然後選取 **確定**。
5. 選取 **作業編號** 連結以存取作業詳情。
6. 在 **批次處理工作** FastTab，選取 **參數**。
7. 在 **電子報表參數** 對話方塊中，請按照下列步驟操作：

    1. 選取 **瀏覽** 即可選取用於資料匯入的替代檔案。
    2. 選取 **輸入憑證編號** 可更改用於匯入廠商交易的憑證編號。

        ![在電子報表參數對話方塊中更改批次處理作業安排的資料匯入參數。](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. 選取 **確定**。

8. 確保該批次仍處於選取狀態，然後再次選取 **更改狀態**。
9. 在 **選取新狀態** 對話方塊中，選取 **等待**，然後選取 **確定**。

## <a name="review-the-data-import-results-on-the-er-source-page"></a>查看 ER 來源頁面上的資料匯入結果

1. 進入 **組織管理**\>**電子報表**\>**電子報表來源**。
2. 選取 **用於匯入廠商交易 (Excel)** 在資料匯入期間自動創建的記錄。

    ![電子報表來源頁面上用於匯入廠商交易 (Excel) 設定的記錄。](./media/er-configure-data-import-batch-files-source-1.png)

3. 選取 **來源的檔案狀態**。
4. 在 **檔案** 和 **匯入格式的來源記錄** FastTabs，查看匯入詳情。
5. 在 **檔案** FastTab，選取記錄。 請注意，匯入的檔案已附加到此記錄。

    ![匯入的檔案附加到源頁面的檔案狀態上的記錄。](./media/er-configure-data-import-batch-files-source-2.png)

6. 選取 **附件** 查看匯入的檔案。

    ![文件視圖頁面上的匯入檔案。](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > 為了保留這些附件，ER 架構使用在 ER 參數的 **其他** 欄位中為現行公司[設定](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)的文件類型。

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>在廠商結算 1099 頁面查看資料匯入結果

1. 進入 **應付帳款**\>**定期工作**\>**稅 1099**\>**1099 的廠商結算**。
2. 在 **起始日期** 欄位中，輸入 **12/31/2017** (2017 年 12 月 31 日)。
3. 選取 **手動 1099 筆交易**。

    ![稅務 1099 交易頁面上的匯入廠商交易。](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>其他資源

[電子報表概述](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
