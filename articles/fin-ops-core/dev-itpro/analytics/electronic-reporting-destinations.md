---
title: 電子報表 (ER) 目的地
description: 本主題提供有關電子報表目的地管理、支援的目的地類型和安全注意事項的資訊。
author: nselin
ms.date: 09/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: e8e176b8d4e14eee2050b3c66f7547ff878b5174
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "8460311"
---
# <a name="electronic-reporting-er-destinations"></a>電子報表 (ER) 目的地

[!include [banner](../includes/banner.md)]

您可以為每個電子報表 (ER) 格式設定及其輸出組件 (檔案夾或檔案) 設定目的地。 具有適當存取權限的使用者還可以在執行階段修改目的地設定。 本主題介紹 ER 目的地管理、受支援的目的地類型以及安全注意事項。

ER 格式設定通常包含至少一個輸出組件：檔案。 通常，設定包含多個不同類型的檔案輸出組件 (例如，XML、TXT、XLSX、DOCX 或 PDF)，它們被分組到單個檔案夾或多個檔案夾中。 ER 目的地管理允許您預先設定每個組件執行階段發生的情況。 在預設情況下，執行設定時，會出現一個對話方塊，讓您儲存或打開檔案。 當您匯入 ER 設定並且不為其設定任何特定目的地時，也會發生相同的行為。 為主要輸出組件建立目的地後，該目的地將覆蓋預設行為，並根據目的地的設定寄送檔案夾或檔案。

## <a name="availability-and-general-prerequisites"></a>可用性和一般先決條件

ER 目的地的函數在 Microsoft Dynamics AX 7.0 (2016 年 2 月) 中不提供。 因此，您必須安裝 Microsoft Dynamics 365 for Operations 1611 版 (2016 年 11 月) 或更高版本以使用以下目的地類型：

- [電子郵件](er-destination-type-email.md)
- [封存](er-destination-type-archive.md)
- [檔案](er-destination-type-file.md)
- [篩選](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

或者，您可以安裝以下其中一個先決條件。 但是，請注意，這些替代方案提供的 ER 目的地體驗更加有限。

- Microsoft Dynamics AX 應用程式 7.0.1 版 (2016 年 5 月)
- [電子報表目的地管理應用程式 Hotfix](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

還有[列印](er-destination-type-print.md)目的地類型。 若要使用它，您必須安裝 Microsoft Dynamics 365 Finance 10.0.9 版 (2020 年 4 月)。

## <a name="overview"></a>概觀

您只能為 [已匯入](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally)現行 Finance 執行個體的 ER 設定，以及 **電子報表設定** 頁面上的可用格式設定目的地。 ER 目的地管理函數可在 **組織管理**\>**電子報表**\>**電子報表目的地** 中使用。

### <a name="default-behavior"></a>預設行為

ER 格式設定的預設行為取決於您在 ER 格式啟動時指定的執行類型。

在 **Intrastat 報告** 對話方塊中，在 **在背景執行** FastTab 上，如果您將 **批次處理** 選項設定為 **否**，ER 格式立即以互動式模式執行。 成功完成此執行後，產生的輸出文件可供下載。

如果您把 **批次處理** 選項設定為 **是**，ER 格式將以[批次](../sysadmin/batch-processing-overview.md)模式執行。 根據您在 **ER 參數** 對話方塊的 **在背景執行** 索引標籤上指定的參數，建立適當的批次作業。

> [!NOTE]
> 工作說明書通知您有關 ER 格式對應的執行。 它還包含正在執行的 ER 組件的名稱。

[![執行 ER 格式。](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

您可以在多個地方找到有關此工作的資訊：

- 進入 **常用**\>**查找**\>**批此作業**\>**我的批次作業** 即可檢查已安排作業的狀態。
- 進入 **組織管理**\>**電子報表**\>**電子報表作業** 即可檢查已安排作業的狀態和已完成作業的執行結果。 作業執行成功完成後，選取 **電子報表職位** 頁面上的 **顯示檔案** 以取得產生的輸出文件。

    > [!NOTE]
    > 此文件儲存為現行工作記錄的附件，並由[文件管理](../../fin-ops/organization-administration/configure-document-management.md)架構控制。 用於儲存這種類型的 ER 製造物的[文件類型](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types)在 [ER 參數](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)中設定。

- 在 **電子報表作業** 頁面上，選取 **顯示檔案** 查看作業執行期間產生的任何錯誤和警告的清單。

    [![查看 ER 作業清單。](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>使用者設定的行為

在 **電子報表目的地** 頁面上，您可以覆寫設定的預設行為。 匯入的設定不會顯示在這個頁面上，直到您選取 **新建**，然後在 **參考** 欄位中，選取設定來建立目的地設定。

[![在參考欄位中選取設定。](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

建立參考後，您可以為所參考 ER 格式的每個 **資料夾** 或 **檔案** 輸出組件建立檔案目的地。

[![建立檔案目的地。](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

接下來，在 **目的地設定** 對話方塊中，您可以啟用和禁用檔案目的地的各個目的地。 **設定** 按鈕用於控制選定檔案目的地的所有目的地。 在 **目的地設定** 對話方塊中，您可以透過設定每個目的地的 **啟用** 選項來單獨控制它。

在 **10.0.9 版之前** 的 Finance 版本中，您可以為每個相同格式的輸出組件建立 **一個檔案目的地**，如資料夾或在 **檔案名稱** 欄位中選取的檔案。 然而，在 **10.0.9 及之後的版本** 中，您可以為同一格式的每個輸出組件建立 **多個檔案目的地**。

例如，您可以使用此功能為用於產生 Excel 格式的輸出文件的檔案組件設定檔案目的地。 一個目的地 ([封存](er-destination-type-archive.md)) 可以設定為將原始 Excel 檔案儲存在 ER 作業封存中，以及另一個目的地 ([電子郵件](er-destination-type-email.md)) 可以設定為同時將 Excel 檔案[轉換](#OutputConversionToPDF)為 PDF 格式並透過電子郵件寄送 PDF 檔案。

[![為單個格式元素設定多個目的地。](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

執行 ER 格式時，一律執行為該格式的組件設定的所有目的地。 此外，在 Finance **10.0.17 及之後的版本** 中，改進了 ER 目的地的函數，現在可以讓您為 ER 格式設定不同的目的地集。 此設定將每個集合標記為針對特定使用者動作設定。 ER API 已[擴展](er-apis-app10-0-17.md)以便可以提供使用者透過執行 ER 格式執行的動作。 提供的動作代碼將傳遞到 ER 目的地。 您可以執行 ER 格式的不同目標，具體取決於提供的動作代碼。 如需相關資訊，請參閱[設定依賴於動作的 ER 目的地](er-action-dependent-destinations.md)。

## <a name="destination-types"></a>目的地類型

ER 格式現行支援以下目的地。 您可以同時禁用或啟用所有類型。 透過這種方式，您可以什麼都不做，也可以將組件寄送到所有設定的目的地。

- [電子郵件](er-destination-type-email.md)
- [封存](er-destination-type-archive.md)
- [檔案](er-destination-type-file.md)
- [篩選](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [列印](er-destination-type-print.md)

## <a name="applicability"></a>適用性

您只能為已匯入的 ER 設定，以及 **電子報表設定** 頁面上的可用格式設定目的地。

> [!NOTE]
> 設定的目的地是公司特定的。 如果您計畫在現行 Finance 執行個體的不同公司中使用 ER 格式，則必須為每個公司設定該 ER 格式的目的地。

當您為選定格式設定檔案目的地時，您為整個格式設定它們。

[![設定連結。](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

同時，您可能有多個[版本](general-electronic-reporting.md#component-versioning)的格式被匯入到現行的 Finance 執行個體中。 如果您選取 **設定** 連結，您可以查看它們，該連結在您選取 **參考** 欄位時提供。

[![設定版本。](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

預設情況下，只有當您執行狀態為 **已完成** 或 **共用的** ER 格式版本時，才會應用設定的目的地。 但是，在執行 ER 格式的草稿版本時，您有時必須使用已設定的目的地。 例如，您修改格式的草稿版本，並希望使用設定的目的地來測試產生的輸出將如何傳遞。 執行草稿版本時，請按照以下步驟為 ER 格式應用目的地。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 將 **使用目的地作為草稿狀態** 選項設定為 **是**。

[![使用目的地作為草稿狀態選項。](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

若要使用 ER 格式的草稿版本，您必須相應地標記 ER 格式。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 將 **執行設定** 選項設定為 **是**。

[![執行設定選項。](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

完成此安裝後，可對您修改的 ER 格式使用 **執行草稿** 選項。 將此選項設定為 **是**，在格式執行階段開始使用格式的草稿版本。

[![執行草稿選項。](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>目的地失敗處理

通常，ER 格式在特定業務流程的範圍內執行。 但是，在執行 ER 格式期間產生的輸出文件的交付有時必須被視為該業務流程的一部分。 在這種情況下，如果將產生的輸出文件傳送到設定的目的地不成功，則必須取消業務流程的執行。 若要設定適當的 ER 目的地，請選取 **失敗時停止處理** 選項。

例如，您設定廠商付款處理，以便執行 **ISO20022 貸記轉帳** ER 格式以產生付款檔案和補充檔案 (例如，隨函和控制報告)。 如果只有在隨函透過電子郵件成功送達的情況下才應視為付款已成功處理，則您必須在相應的檔案目的地中為 **CoveringLetter** 組件選取 **失敗時停止處理** 核取方塊，如以下圖所示。 在這種情況下，只有當產生的隨函被 Finance 執行個體中設定的電子郵件廠商成功接受寄送時，被選中處理的付款狀態才會從 **無** 變為 **已寄送**。

[![為檔案目標失敗設定進程處理。](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

如果您清除了目的地中 **CoveringLetter** 組件的 **失敗時停止處理** 核取方塊，即使隨函沒有透過電子郵件成功寄送，付款也將被視為成功處理。 即使因為收件者或寄件者的電子郵寄地址遺失或不正確等原因而無法寄送隨函，付款狀態也將從 **無** 變為 **已寄送**。

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>輸出轉換為 PDF

您可以使用 PDF 轉換選項將 Microsoft Office (Excel 或 Word) 格式的輸出轉換為 PDF 格式。

### <a name="make-pdf-conversion-available"></a>提供 PDF 轉換

若要使 PDF 轉換選項在現行的 Finance 執行個體中可使用，打開 **函數管理** 工作區，並打開 **將電子報表輸出文件從 Microsoft Office 格式轉換為 PDF** 函數。

[![在函數管理中打開輸出文件的 PDF 轉換函數。](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>適用性

在 **10.0.18 版之前** 的 Finance 版本中，只有用於產生 Office (Excel 或 Word) 格式輸出的 **Excel\\檔案** 組件可以打開 PDF 轉換選項。 打開此選項後，以 Office 格式產生的輸出會自動轉換為 PDF 格式。 然而，在 **10.0.18 及之後** 的版本中，您也可以為 **常用\\檔案** 類型的組件打開這個選項。

> [!NOTE]
> 注意，當您為 **常用\\檔案** 類型的 ER 組件打開 PDF 轉換選項時，您會收到警告資訊。 此訊息通知您，在設計時無法保證所選檔案組件將在執行階段以 PDF 格式顯示內容或可轉換為 PDF 的內容。 因此，僅當您確定所選檔案組件已設定為在執行階段以 PDF 格式或可轉換為 PDF 的內容顯示內容時，才應打開該選項。
> 
> 如果您為格式組件打開 PDF 轉換選項，如果該組件以 PDF 以外的格式公開內容，並且如果公開的內容無法轉換為 PDF 格式，則會在執行階段發生異常。 您收到的訊息通知您產生的內容無法轉換為 PDF 格式。

### <a name="limitations"></a>限制

PDF 轉換選項僅適用於雲端部署。

產生的 PDF 文件的最大長度限制為 300 頁。

在 Finance **10.0.9 版本** 中，從 Excel 輸出的 PDF 文件中只支援橫向頁面方向。 在 Finance **10.0.10 (2020 年 5 月) 及之後的版本** 中，您可以在設定 ER 目的地的同時[指定由 Excel 輸出的 PDF 文件的頁面方向](#SelectPdfPageOrientation)。

僅使用 Window 作業系統的常用系統字型來轉換不包含嵌入字型的輸出。

### <a name="use-the-pdf-conversion-option"></a>使用 PDF 轉換選項

若要為檔案目的地打開 PDF 轉換，請選取 **轉換至 PDF** 核取方塊。

[![為檔案目的地打開 PDF 轉換。](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">選取 PDF 轉換的頁面方向</a>

如果您產生 Excel 格式的 ER 設定並希望將其轉換為 PDF 格式，您可以明確指定 PDF 文件的頁面方向。 當您選取 **轉換為 PDF** 核取方塊為產生 Excel 格式輸出檔案的檔案目的地打開 PDF 轉換，**頁面方向** 欄位就可在 **PDF 轉換設定** FastTab 上提供。 在 **頁面方向** 欄位中，選取偏好方向。

[![選取 PDF 轉換的頁面方向](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

若要選取 PDF 頁面方向，請安裝 Finance 10.0.10 或更高版本。 在 **10.0.23 版之前** 的 Finance 版本中，該選項提供了以下頁面方向選項。

- 直向
- 橫向

選定的頁面方向將應用於以 Excel 格式產生然後轉換為 PDF 格式的輸出文件的所有頁面。

然而，在 **10.0.23 及之後** 的版本中，頁面方向選項的清單已被擴展如下：

- 直向
- 橫向
- 特定於工作表

當您選取 **特定的工作表** 選項時，產生的 Excel 活頁簿的每個工作表都會透過使用在所使用的 Excel 範本中為該工作表設定的頁面方向轉換為 PDF。 因此，您可能有一個包含縱向和橫向頁面的最終 PDF 文件。 

如果 Word 格式的 ER 設定轉換為 PDF 格式，則 PDF 文件的頁面方向始終取自 Word 文件。

## <a name="output-unfolding"></a>輸出展開

當您為 ER 格式的 **資料夾** 組件設定目的地時，您可以指定該組件的輸出如何交付給設定的目的地。

### <a name="make-output-unfolding-available"></a>提供輸出展開

若要使輸出展開選項在現行 Finance 執行個體中可使用，請打開 **函數管理** 工作區，並打開 **允許設定 ER 目的地將資料夾內容作為獨立檔寄送**。

### <a name="applicability"></a>適用性

輸出展開選項只能為 **資料夾** 類型的格式組件進行設定。 當您開始設定 **資料夾** 組件時，在 **電子報表目的地** 頁上，**一般** FastTab 變得可供使用。 

### <a name="use-the-output-unfolding-option"></a>使用輸出展開選項

在 **一般** FastTab 上，在 **寄送資料夾為** 欄位中，選取以下數值之一：

- **ZIP 壓縮檔案** – 將產生的檔案作為 ZIP 檔案提供。
- **單獨的檔案** – 將產生的 ZIP 檔案的每個檔案作為單獨的檔案交付。

    > [!NOTE]
    > 當您選取 **單獨的檔案**，產生的輸出以壓縮狀態收集在記憶體中。 因此，當實際檔案大小可能超過這個限制時，最大的[檔案大小限制](er-compress-outbound-files.md)適用於壓縮輸出。 當您預計產生的輸出的大小太大時，我們建議您選取此值。

[![為資料夾格式組件設定目的地。](./media/er_destinations-set-unfolding-option.png)](./media/er_destinations-set-unfolding-option.png)

### <a name="limitations"></a>限制

如果您將包含其他巢狀 **資料夾** 組件的 **資料夾** 組件的 **寄送資料夾為** 欄位設定為 **單獨的檔案**，該設定不會遞迴應用於巢狀 **資料夾** 組件。

## <a name="security-considerations"></a>安全性注意事項

將兩種類型的權限和職責用於 ER 目的地。 一種類型控制使用者維護為法律實體設定的目的地的總體能力 (即，它控制對 **電子報表目的地** 頁的存取)。 另一種類型控制應用程式使用者在執行階段覆寫 ER 開發人員或 ER 函數顧問已設定的目的地設定的能力。

| 角色 (AOT 名稱)                     | 角色名稱                                  | 責任 (AOT 名稱)                     | 責任名稱                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | 電子報表開發人員             | ERFormatDestinationConfigure        | 設定電子報表格式目的地                |
| ERFunctionalConsultant              | 電子報表函數 | ERFormatDestinationConfigure        | 設定電子報表格式目的地                |
| PaymAccountsPayablePaymentsClerk    | 應付帳款付款記帳員            | ERFormatDestinationRuntimeConfigure | 在執行階段設定電子報表格式的目的地 |
| PaymAccountsReceivablePaymentsClerk | 應收帳款付款記帳員         | ERFormatDestinationRuntimeConfigure | 在執行階段設定電子報表格式的目的地 |

> [!NOTE]
> 在前面的職責中使用了兩個權限。 這些權限與相應的職責具有相同的名稱：**ERFormatDestinationConfigure** 和 **ERFormatDestinationRuntimeConfigure**。

## <a name="frequently-asked-questions"></a>常用問題

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>我已匯入電子設定，並在電子報表設定頁面上看到它們。 但為什麼我在電子報表目的地頁面上看不到它們？

確保您選取 **新建** 然後在 **參考** 欄位中選取設定。 **電子報表目的地** 頁面僅顯示已設定目的地的設定。

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>是否有辦法定義使用哪個 Microsoft Azure 儲存體帳戶和 Azure Blob 儲存體？

編號 使用為文件管理系統定義和使用的預設 Microsoft Azure Blob 儲存體。

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>目的地設定中檔案目的地的用途是什麼？ 這個設定有什麼作用？

當您在互動式模式下執行 ER 格式時，**檔案** 目的地用於控制網路瀏覽器的對話方塊。 如果啟用此目的地，或者沒有為設定定義目的地，則在建立輸出檔案後，網路瀏覽器中會出現一個開啟或儲存對話方塊。

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>您能否舉例說明我可以向其寄送電子郵件的廠商帳戶的公式？

該公式特定於 ER 設定。 例如，如果您使用 ISO 20022 貸記轉帳設定，您可以使用 **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** 或 **model.Payments.Creditor.Identification.SourceID** 來獲取相關的廠商帳戶。

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>我的格式設定之一包含多個檔案，這些檔案被分組到一個資料夾中 (例如，Folder1 包含 File1、File2 和 File3)。 如何設定目的地，以便根本不建立 Folder1.zip，透過電子郵件寄送 File1，將 File2 寄送到 SharePoint，我可以在設定執行後立即打開 File3 嗎？

您的格式必須首先在 ER 設定中提供。 如果滿足此先決條件，請開啟 **電子報表目的地** 頁面，並建立對設定的新參考。 然後，您必須有四個檔案目的地，每個輸出組件一個。 建立第一個檔案目的地，給它一個名稱，例如 **檔案夾**，然後選取代表設定中檔案夾的檔案名稱。 然後選取 **設定**，並確保所有目的地都被禁用。 對於此檔案目的地，不會建立檔案夾。 預設情況下，由於檔案和父檔案夾之間的分層依賴關係，檔案將以相同的方式執行。 換句話說，它們不會被寄送到任何地方。 若要覆蓋該預設行為，您必須再建立三個檔案目的地，每個檔案一個。 在每個目的地設定中，您必須啟用檔案應寄送到的目的地。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[設定依賴於動作的 ER 目的地](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
