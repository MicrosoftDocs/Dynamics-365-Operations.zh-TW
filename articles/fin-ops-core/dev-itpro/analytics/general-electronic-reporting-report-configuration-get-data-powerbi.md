---
title: 設定電子報表 (ER) 以將資料提取到 Power BI
description: 本主題說明如何使用電子報表 (ER) 設定來安排將資料從執行個體傳輸到 Power BI 服務。
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: aa9a47c9ee7c76322fd2d9bfcf5fc61a50bf421321891b3c78a782be6a9f8e6a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460210"
---
# <a name="configure-electronic-reporting-er-to-pull-data-into-power-bi"></a>設定電子報表 (ER) 以將資料提取到 Power BI

[!include [banner](../includes/banner.md)]

本主題說明如何使用電子報表 (ER) 設定來安排將資料從執行個體傳輸到 Power BI 服務。 例如，本主題使用 Intrastat 交易作為必須傳輸的業務資料。 Power BI 地圖視覺效果使用此 Intrastat 交易資料來呈現用於分析 Power BI 報表上的公司匯入/匯出活動的檢視表。

## <a name="overview"></a>概觀

Microsoft Power BI 是軟體服務、應用程式和連接器的集合，它們相互合作，將外部資料來源轉化為連貫的、視覺上身臨其境和互動式的見解。 電子報表 (ER) 讓使用者可以輕鬆設定資料來源並安排將資料從應用程式傳輸到 Power BI。 資料作為檔案傳輸到 OpenXML 工作表 (Microsoft Excel 活頁簿檔案) 格式。 傳輸的檔案儲存在為此目的而設定的 Microsoft SharePoint 伺服器上。 儲存的檔案在 Power BI 中用於製作包含視覺效果 (表格、圖表、地圖等) 的報表。 Power BI 報表與 Power BI 使用者共用，並可在 Power BI 儀表板和應用程式頁面上存取。 本主題介紹以下工作：

- 設定 Microsoft  Dynamics 365 Finance。
- 準備 ER 格式設定以從 Finance 應用程式取得資料。
- 設定 ER 環境以將資料傳輸到 Power BI。
- 使用傳輸的資料建立 Power BI 報表。
- 使 Power BI 報表可在 Finance 中存取。

## <a name="prerequisites"></a>先決條件
若要完成本主題中的範例，您必須具有以下存取權限：

- 存取以下角色之一：

    - 電子報表開發人員
    - 電子報表函數
    - 系統管理員

- 存取設定為與應用程式一起使用的 SharePoint 伺服器
- 存取 Power BI 架構

## <a name="configure-document-management-parameters"></a>設定檔案管理參數
1. 在 **文件管理參數** 頁面上，設定對將在您登入的公司 (本範例中為 DEMF 公司) 中使用的 SharePoint 伺服器的存取權限。
2. 測試與 SharePoint 伺服器的連線以確保您已被授予存取權限。

    [![檔案管理參數頁面。](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)

3. 打開設定的 SharePoint 網站。 建立一個新資料夾，ER 將在其中儲存 Excel 檔案，其中包含 Power BI 報表所需的業務資料作為 Power BI 資料集的來源。
4. 在 **檔案類型** 頁面，建立一個新的文件類型，用於存取您剛剛建立的 SharePoint 資料夾。 在 **群組** 欄位中輸入 **File**，在 **位置** 欄位中輸入 **SharePoint**，然後輸入 SharePoint 資料夾的位置。

    [![檔案類型頁面。](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>設定 ER 參數
1. 在 **電子報表** 工作區，點選 **電子報表參數** 連結。
2. 在 **附件** 索引標籤上，為所有欄位選取 **檔案** 文件類型。
3. 在 **電子報表** 工作區中，透過點選 **設定啟用** 所需的提供者。 如需相關資訊，請播放 **ER 選取服務提供者** 工作指南。

## <a name="use-an-er-data-model-as-the-source-of-data"></a>使用 ER 資料模型作為資料來源
您必須有一個 ER 資料模型作為將用於 Power BI 報表的業務資料來源。 此資料模型是從 ER 設定存放庫上傳的。 如需相關資訊，請參閱 [從 Lifecycle Services 下載電子報表設定](download-electronic-reporting-configuration-lcs.md)，或播放 **ER 從 Lifecycle Services 匯入設定** 工作指南。 選取 **Intrastat** 作為將從所選 ER 設定存放庫上傳的資料模型。 (在此範例中，使用模型的版本 1。) 然後您可以在 **設定** 頁面上存取 **Intrastat** ER 模型設定。

[![設定頁面上的 Intrastat ER 模型設定。](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>設計 ER 格式設定
您必須建立一個新的 ER 格式設定，該設定使用 **Intrastat** 資料模型作為業務資料的來源。 此格式設定必須將輸出結果產生為 OpenXML (Excel 檔案) 格式的電子文件。 如需相關資訊，請播放 **ER 為 OPENXML 格式的報表建立設定** 工作指南。 將新設定命名為 **匯入/匯出活動**，如下圖所示。 設計 ER 格式時，請使用[ER 資料 - 匯入和匯出詳情](https://download.microsoft.com/download/f/7/5/f755c0fd-025c-4aa9-920b-909abb8302ad/ER-data-import-and-export-details.xlsx) Excel 檔案作為範本。 (如需如何匯入格式範本的相關資訊，請播放工作指南。)

[![匯入/匯出活動設定。](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png)

若要修改 **匯入/匯出活動** 格式設定，請按照下列步驟操作。

1. 點選 **設計工具**。
2. 在 **格式** 索引標籤上，為此格式的 **Excel 輸出檔案** 命名檔案元素。

    [![Excel 輸出檔案元素。](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)

3. 在 **對應** 索引標籤，指定執行此格式時將產生的 Excel 檔案的名稱。 設定相關運算式回傳值 **匯入和匯出詳情** (會自動新增 .xlsx 檔案副檔名)。

    [![格式設計工具。](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)

4. 為此格式新增一個新的資料來源項目。 (進一步的資料繫結需要此列舉。)

    1. 將資料來源命名為 **direction\_enum**。
    2. 選取 **資料模型列舉** 作為資料來源類型。
    3. 請參閱 **方向** 資料模型列舉。

    [![direction_enum.](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)

5. 完成 **Intrastat** 資料模型元素與設計格式元素的繫結，如下圖所示。

    [![完成繫結。](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

執行後，ER 格式產生 Excel 格式的輸出結果。 它將 Intrastat 交易的詳情發送到輸出結果，並將它們分離為描述匯入活動或匯出活動的交易。 點選 **執行** 以測試 **Intrastat** 頁面 (**稅金**&gt;**申報**&gt;**外貿**&gt;**Intrastat**) 上 Intrastat 交易清單的新 ER 格式。

[![Intrastat 頁面。](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png)

產生以下輸出結果。 該檔案名為 **Import and export details.xlsx**，正如您在格式設定中指定的那樣。

[![Import and export details.xlsx.](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>設定 ER 目的地
您必須設定 ER 架構以特殊方式發送新 ER 格式設定的輸出結果。

- 輸出結果必須發送到所選 SharePoint 伺服器的資料夾。
- 每次執行格式設定都必須建立相同 Excel 檔案的新版本。

在 **電子報表** 頁 (**組織管理**&gt;**電子報表**)，點選 **電子報表目的地** 項目，並新增一個新的目的地。 在 **參考** 欄位，選取您之前建立的 **匯入/匯出活動** 格式設定。 按照以下步驟新增新的檔案目的地記錄以供參考。

1. 在 **名稱** 欄位中，輸入檔案目的地的圖格。
2. 在 **檔案名稱** 欄位，選取 Excel 檔案格式組件的名稱 **Excel 輸出檔案**。

點選新目的地記錄的 **設定** 按鈕。 然後，在 **目的地設定** 對話方塊中，按照以下步驟操作。

1. 在 **Power BI** 索引標籤上，將 **已啟用** 選項設定 **是**。
2. 在 **SharePoint** 欄位，選取您之前建立的 **共用** 文件類型。

## <a name="schedule-execution-of-the-configured-er-format"></a>安排執行設定的 ER 格式
1. 在 **設定** 頁 (**組織管理**&gt;**電子報表**&gt;**設定**)，在設定樹狀結構中，選取您之前建立的 **匯入/匯出活動** 設定。
2. 將版本 1.1 的狀態從 **草稿** 更改為 **已完成**，以使此格式可供使用。

    [![在設定頁面上匯入/匯出活動設定。](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png)

3. 選取 **匯入/匯出活動** 設定的完成版本，然後點選 **執行**。 請注意，設定的目標將應用於以 Excel 格式產生的輸出結果。
4. 將 **批次處理** 選項設定 **是** 以無人值守模式執行此報表。
5. 點選 **週期** 安排此批次處理執行所需的週期。 該週期定義更新資料傳輸到 Power BI 的頻率。

    [![電子報表參數對話方塊。](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png)

6. 設定完成後，您可以在 **批次處理作業** 頁面 (**系統管理&gt;查詢&gt;批次處理作業**) 上找到 ER 報表執行作業。

    [![批次處理作業頁面。](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png)

7. 首次執行此作業時，該目標會在選定的 SharePoint 資料夾中建立一個具有設定名稱的新 Excel 檔案。 以後每次執行作業時，該目標都會建立此 Excel 檔案的新版本。

    [![新版本的 Excel 檔案。](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>使用 ER 格式的輸出結果建立 Power BI 資料集
1. 登入到 Power BI，然後打開現有的 Power BI 組 (工作區) 或建立一個新組。 點選 **匯入或連線到資料** 區塊的 **檔案** 下的 **新增**，或點選左窗格中 **資料集** 旁邊的加號 (**+**)。

    [![建立資料集。](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png)

2. 選取 **SharePoint – 團隊網站** 選項，然後輸入您正在使用的 SharePoint 伺服器路徑 (在我們的範例中為`https://ax7partner.litware.com`)。
3. 瀏覽至 **/Shared Documents/GER data/PowerBI** 資料夾，選取您建立的 Excel 檔案作為新 Power BI 資料集的資料來源。

    [![選取 Excel 檔案。](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png)

4. 點選 **連線**，然後點選 **匯入**。 將建立一個基於所選 Excel 檔案的新資料集。 資料集也可以自動新增到新建立的儀表板中。

    [![儀表板上的資料集。](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png)

5. 設定此資料集的重新整理調度以強制定期更新。 定期更新允許使用透過在 SharePoint 伺服器上建立的 Excel 檔案的新版本定期執行 ER 報表而獲得的新業務資料。

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>使用新資料集建立 Power BI 報表
1. 點選您建立的 **匯入和匯出詳情** Power BI 資料集。
2. 設定視覺效果 例如，選取 **區域分布圖** 視覺效果，而設定如下：

    - 將 **CountryOrigin** 資料集欄位指派給地圖視覺效果的 **位置** 欄位。
    - 將 **Amount** 資料集欄位指派給地圖視覺效果的 **顏色彩度** 欄位。
    - 將 **活動** 和 **年份** 資料集欄位新增到地圖視覺效果的 **篩選器** 欄位集合中。

3. 將 Power BI 報表另存為 **匯入和匯出詳情報表**。

    [![Import and export details report.](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png)

    請注意，地圖顯示了 Excel 檔案中提到的國家/地區 (本例中為奧地利和瑞士)。 這些國家/地區以顏色顯示每個國家/地區的發票金額比例。

4. 更新 Intrastat 交易清單。 新增了源自義大利的出口交易。

    [![Intrastat 交易清單。](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png)

5. 等待 ER 報表的下一次調度執行和 Power BI 資料集的下一次調度更新。 然後查看 Power BI 報表 (選取僅顯示匯入交易)。 更新後的地圖現在顯示義大利。

    [![更新後的地圖。](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance"></a>在 Finance 中存取 Power BI 報表
設定與 Power BI 的整合。 如需相關資訊，請參閱[為工作區設定 Power BI 整合](configure-power-bi-integration.md)。

1. 在支援 Power BI 整合的 **電子報表** 工作區頁面 (**組織管理**&gt;**工作區**&gt;**電子報表工作區**)，點選 **選項**&gt;**開啟報表目錄**。
2. 選取您建立的 **匯入和匯出詳情** Power BI 報表，以將該報表顯示為所選頁面上的動作項目。
3. 點選動作項目以打開顯示您在 Power BI 中設計的報表的頁面。

    [![在 Power BI 中設計的匯入和匯出詳情報表。](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 目的地](electronic-reporting-destinations.md)

[電子報表 (ER) 概觀](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
