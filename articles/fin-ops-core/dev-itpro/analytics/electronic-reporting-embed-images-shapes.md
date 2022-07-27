---
title: 在使用 ER 產生的檔案中嵌入影像和形狀
description: 本主題說明如何使用電子報表工具產生具有內嵌影像和形狀的業務文件。
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 550ecca31af48e624e292b342d909abd6eb3e87af122f736eb388524b42f1e05
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460310"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>在使用 ER 產生的檔案中嵌入影像和形狀

[!include [banner](../includes/banner.md)]

您可以使用電子報表 (ER) 工具來設計可以執行以產生所需電子文件的報告。 您可以使用 Microsoft Excel 或 Microsoft Word 文件來指定報告的配置。 ER Operations 設計工具允許您附加 Excel 或 Word 文件作為報告的範本。 附加範本中的命名元素與 ER 報告的格式元素相關。 報表的格式元素繫結到資料來源。 這些元素指定將在執行階段在產生的文件中輸入的資料。

這一新函數超越了現有的 ER 函數，可用於建立 Microsoft Office 格式的文件。 如需相關資訊，請播放以下工作指南。 您可以在 7.5.4.3 獲取/開發 IT 服務/解決方案組件 (10677) 業務流程下找到這些工作指南。

- ER 設計用於產生 OPENXML 格式報告的設定
- ER 設計用於產生 Microsoft Word 格式報告的設定

## <a name="embed-an-image-in-an-excel-document"></a>在 Excel 文件中嵌入影像

### <a name="embed-an-image-in-an-excel-worksheet"></a>在 Excel 工作表中嵌入影像

首先，您必須為 Excel 文件中的影像新增預留位置。 開啟 Excel 活頁簿，然後新增一張影像作為稍後要新增的影像的預留位置。 然後使用 ER 工具新增新的 ER 格式設定以包含您正在設計的報告。 附上 Excel 活頁簿作為報表格式的範本，然後將工作簿的內容匯入 ER 格式。 格式定義將自動建立。 您新增的影像預留位置將作為 **儲存格** 元素包含在 ER 格式定義中。

> [!NOTE]
> 您可以手動指定格式定義而不是匯入它。 當您儲存更改時，將驗證格式。

接下來，將 ER 格式的 **儲存格** 元素繫結到格式資料來源中的欄位，該欄位在執行階段以二進位格式提供影像資料。 當使用 ER 資料模型作為格式的資料來源時，欄位的資料類型必須是[容器](er-formula-supported-data-types-composite.md#container)。 現行，具有[容器](er-formula-supported-data-types-composite.md#container)資料類型的 ER 資料模型欄位可以繫結到多種類型的資料來源，這些資料來源以二進位格式回傳影像。 您可以使用文件管理架構存取資料表中的欄位和附加到資料表記錄的檔案。

> [!IMPORTANT]
> - 如果要在使用 Excel 範本建立的文件中填入影像預留位置，ER 格式必須包含參考 Excel 範本中命名影像元素的 **儲存格** 元素。 否則，報告的輸出中不會出現影像預留位置。 如果 **儲存格** 元素的繫結在執行階段沒有回傳資料，則產生的文件將顯示範本中的影像預留位置。 若要在您產生的文件中隱藏影像，請定義一個 **儲存格** 元素，並指定 **啟用** 運算式應回傳 **FALSE** 值。
> - 在 Excel 範本中，為每個元素使用唯一的名稱。 這些元素包括影像和儲存格。 如果重複元素名稱，則產生的報告內容將模棱兩可且令人困惑。

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>在 Excel 工作表的抬頭和頁尾中嵌入影像

使用 Excel 活頁簿文件作為範本來指定報表的配置。 活頁簿可以包含多個工作表，每個工作表都可以設計為具有抬頭和頁尾。 Excel 在每個工作表的抬頭和頁尾中最多支援三個影像。 影像可以左對齊、右對齊或居中對齊。

在 Finance 10.0.21 版中，您可以管理由具有 Excel 範本的 ER 解決方案產生的抬頭和頁尾影像。

如果您希望預設影像出現在產生的文件的抬頭或頁尾中，您可以將影像新增到 ER 範本的工作表的抬頭或頁尾。 若要以您的 ER 格式存取此影像，您必須在格式的 [抬頭](er-fillable-excel.md#header-component)或 [頁尾](er-fillable-excel.md#footer-component)組件下新增 **影像** 組件。 根據需要設定 **影像** 組件的對齊方式。 

即使範本不包含預設影像，您也可以使用 **圖片** 組件在執行階段將影像放入產生文件的抬頭或頁尾。 若要指定應放入產生文件的抬頭或頁尾的媒體內容作為新影像或預設影像的替換，您必須將 **圖片** 組件繫結到以二進位表示影像的[容器](er-formula-supported-data-types-composite.md#container)類型的資料來源格式。

每個 **抬頭** 或 **頁尾** 組件可以為每個支援的對齊方式儲存一個 **圖片** 組件：**左**、**中** 和 **右**。

**圖片** 組件的 **縮放高度** 屬性允許您使用設定的繫結來控制影像的大小：

- 選取 **原始** 以保持影像的初始大小。
- 選取 **相對** 以與包含該影像的抬頭或頁尾的高度成比例縮放影像的高度。

    - 在這種情況下，影像的高度必須定義為父抬頭或頁尾的百分比。
    - 如果縮放值超過 100%，影像可能會與相應工作表的資料區域重疊。
    - 如果在套用縮放時更改了影像的高度，則寬度也會更改以保持影像的原始外觀比例。

- 選取 **絕對** 可根據設計階段提供的高度和寬度值 (以像素為單位) 調整影像大小。

    - 如果指定的高度超過父抬頭或頁尾的高度，則影像可能會與相應工作表的資料區域重疊。

您還可以使用 **圖片** 組件的 **啟用** 屬性來控制透過使用此組件放入產生的文件中的影像的可見性。

> [!NOTE]
> 您必須使用 ER 格式設計工具將 **圖片** 組件新增到可編輯的 ER 格式。 使用[商業文件管理](er-business-document-management.md)工作區編輯業務文件範本時，無法新增組件。

若要進一步了解此函數，請按照[設計 ER 格式以產生 Excel 格式的報告，並在抬頭或頁尾中內嵌影像](er-embed-images-header-footer-excel-reports.md)中的步驟。

## <a name="embed-a-shape-in-an-excel-document"></a>在 Excel 文件中嵌入形狀

首先，您必須為 Excel 文件中的形狀新增預留位置。 開啟 Excel 活頁簿，然後選取 **形狀**、**文字方塊** 或 **WordArt** 作為形狀的預留位置。 然後使用 ER 工具新增新的 ER 格式設定以包含您正在設計的報告。 附上 Excel 活頁簿作為報表格式的範本，然後將工作簿的內容匯入 ER 格式。 格式定義將自動建立。 您新增的形狀預留位置將作為 **儲存格** 元素包含在 ER 格式定義中，該元素參考已命名的 Excel 形狀元素。

> [!NOTE]
> 您可以手動指定格式定義而不是匯入它。 當您儲存更改時，將驗證格式。

接下來，將 ER 格式的 **儲存格** 元素繫結到格式資料來源中的欄位，該資料來源在執行階段提供資料。 此資料可以轉換為文字字串。 當 ER 格式的 **儲存格** 元素參考 Excel 範本中支援文字的形狀元素時，在執行階段透過此繫結提供的文字將在產生的文件中以形狀顯示。

> [!IMPORTANT]
> - 如果要使用包含形狀預留位置的 Excel 範本產生新文件，則 ER 格式必須包含參考 Excel 形狀元素的 **儲存格** 元素。 否則，報告的輸出中不會出現形狀預留位置。 如果參考命名 Excel 形狀元素的 **儲存格** 元素的繫結在執行階段未回傳資料，則產生的文件將顯示 Excel 範本中形狀預留位置的文字。 若要在您產生的文件中隱藏形狀，請定義一個參考命名 Excel 形狀元素的 **儲存格** 元素，並指定 **啟用** 運算式應回傳 **FALSE** 值。
> - 在 Excel 範本中，為每個元素使用唯一的名稱。 這些元素包括形狀和儲存格。 如果重複元素名稱，則產生的報告內容將模棱兩可且令人困惑。

## <a name="embed-an-image-in-a-word-document"></a>在 Word 文件中嵌入圖像
> [!IMPORTANT]
> 您可以重複使用使用 Excel 範本的 ER 格式來建立包含內嵌影像的文件。 在 ER 格式中，確保為參考 Excel 中命名圖片元素的 **儲存格** 元素指定名稱，並且該名稱繫結到在執行階段回傳圖片的資料來源。

首先，您必須設定 Word 文件的配置。 使用 **圖片內容** 控制為內嵌影像建立一個預留位置。 若要存取此控制，您必須先使 **開發人員** 索引標籤在 Word 函數區上顯示。

接下來，從 ER 格式中刪除 Excel 範本，並附加 Word 範本文件。 更新對範本的參考，並儲存您的更改。 現行 ER 格式的結構作為名為 **報表** 的新自訂 XML 組件儲存到 Word 範本中。

接下來，將現行 ER 格式的 Word 範本儲存到本地電腦。 開啟範本，然後開啟 **XML 對應** 窗格。 找到名為 **報表** 的自訂 XML 組件，然後指向繫結到以二進位格式回傳影像的資料來源的 ER 報告中的 **儲存格** 元素。 將此 XML 組件的項目對應到選定的 **圖片內容** 控制，並儲存您的更改。

[![內嵌影像。](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

最後，從 ER 格式中刪除 Word 範本，並附加包含對應的自訂 XML 組件的 Word 文件。 更新對範本的格式參考，並儲存您對此 ER 格式所做的更改。

## <a name="more-information"></a>更多資訊
若要熟悉此函數的詳情，請播放工作指南集，**ER 以 MS Office 格式製作帶有內嵌影像的報表**。 這些工作指南展示了如何在 Excel 和 Word 文件中使用 ER 工具產生的付款支票中嵌入公司標誌和授權人簽名的影像。

下表列出了完成 **ER 製作帶有內嵌影像的 MS Office 格式的報告** 工作指南所需的檔案。 下載檔案並將其儲存到本地電腦。

| 描述                                          | 檔案名稱                   |
|------------------------------------------------------|-----------------------------|
| ER 資料模型設定                          | [支票.xml 的模型](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| ER 格式設定                              | [支票列印格式.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| 公司標誌圖片                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| 簽名影像                                      | [簽名影像.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| 替代簽名影像                          | [簽名影像 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| 用於列印付款支票的 Microsoft Word 範本  | [支票範本 Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| 用於列印付款支票的 Microsoft Excel 範本 | [支票範本.xlsx](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

下圖提供了從 Excel 範本產生的付款支票的測試列印輸出範例。

[![付款支票測試列印輸出。](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
