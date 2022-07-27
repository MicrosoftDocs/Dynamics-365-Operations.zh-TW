---
title: 'Microsoft Office - 商業文件管理中的樣式使用者介面 (包含影片) '
description: 本主題說明如何使用電子報表 (ER) 架構的商業文件管理函數中的新使用者介面。
author: v-anamir
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e33830e2147d92ad5ee53ad11da55a50613b8ef9
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460292"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Microsoft Office - 商業文件管理中的樣式使用者介面

[!include [banner](../includes/banner.md)]

商業文件管理允許業務使用者使用 Microsoft Office 365 服務或適當的 Microsoft Office 桌面應用程式編輯商業文件範本。 編輯可能包括設計更改或新部署，或者使用者可能會新增預留位置以包含其他資料，而無需更改原始程式碼。 如需如何使用商業文件管理的相關資訊，請參閱[商業文件管理概述](er-business-document-management.md)。

新的使用者介面 (UI) 更清晰，使用更舒適。 **商業文件** 區域僅顯示現行[作用中](tasks/er-configuration-provider-mark-it-active-2016-11.md)[提供者](general-electronic-reporting.md#Provider)擁有並位於 Dynamics 365 Finance 的現行實體中的範本。 在之前的 UI 中，**範本** 索引標籤列出了可用於任何提供者的所有範本。 它還顯示了由具有相同角色的任何使用者建立和編輯的所有範本。

您可以使用 **商業文件管理** 工作區中的 **新文件** 按鈕來建立和編輯由另一個提供者提供並位於現行 Finance 實體中的[電子報表 (ER)](general-electronic-reporting.md) 格式[設定](general-electronic-reporting.md#Configuration)的範本，或者從Excel 活頁簿。 此外，在版本 10.0.25 及更高版本中，您可以使用 **新文件** 按鈕以儲存在[全域存放庫](general-electronic-reporting.md#Repository)中的 ER 格式設定建立和編輯範本。

在本主題的範例中，作用中提供者是 Contoso，您可以使用它來建立基於 Microsoft 提供的範本的範本。 或者，您可以透過上傳您自己的 Excel 格式範本來建立範本。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

[使用商業文件管理建立新的商業文件](https://youtu.be/gAIYl-mM_pw) 影片 (如上所示) 包含在 YouTube 上的 [Finance and Operations 播放清單](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) 中。

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>使商業文件管理中的新文件 UI 可供使用

若要開始在商業文件管理中使用新的文件 UI，您必須在 **函數管理** 工作區中打開 **商業文件管理的類似 Office 的 UI 體驗** 函數。

按照以下步驟為所有法律實體啟用此函數。

1. 在 **函數管理** 工作區的 **全部** 索引標籤上，選取清單中的 **用於商業文件管理的類似 Office 的 UI 體驗** 函數。
2. 選取 **立即啟用** 開啟選定函數。
3. 重新整理頁面來存取新函數。

## <a name="add-or-activate-a-provider"></a>新增或啟用提供者

商業文件的每個範本都儲存在標記為由特定設定提供者擁有的 ER 格式設定中。 建立新範本時，會建立一個新的 ER 格式設定來儲存它。 因此，必須為該設定確定提供者。 ER 架構的作用中提供者用於此目的。 如果 ER 中沒有提供者，您可以建立一個。 如果沒有 *作用中* 提供者，您可以啟用現有提供者之一。 當您開始新增新範本時，需要時會打開一個用於新增或啟用提供程式的對話方塊。

### <a name="add-a-new-provider"></a>新增供應商

若要建立新的提供者，請按照 **設定提供者** 對話方塊的步驟操作：

1.  在 **選取設定提供者** 索引標籤，在 **名稱** 欄位，輸入新提供者的名稱。
2.  在 **網址** 欄位中，輸入新提供者的網址 (URL)。 
3.  選取 **確定**。

    ![在商業文件管理中建立新的提供者。](./media/bdm_create_provider.png)

已新增的提供者將被自動啟用。

### <a name="activate-a-provider"></a>啟用提供者

若要啟用提供者，請按照 **設定提供者** 對話方塊的步驟操作：

1.  在 **選取設定提供者** 索引標籤，在 **設定提供者** 欄位，輸入提供者。
2.  選取 **確定**。

    ![在商業文件管理中啟用提供者。](./media/bdm_choose_provider.png)

選定的提供者將被啟用。

> [!NOTE]
> 每個商業文件管理範本都位於將提供者稱為設定作者的 ER 格式設定中。 因此，每個範本都需要一個作用中的提供者。

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>編輯由其他提供者擁有的範本

此範例說明如何使用 **商業文件管理** 工作區中的 **新文件** 按鈕來建立和編輯 ER 格式設定的範本，該範本由另一個提供者提供並位於現行 Finance 實體中。 在此範例中，作用中的提供者是 Contoso，它使用 Microsoft 提供的 ER 格式設定。 選取 **新文件** 後，**建立新範本** 頁面上的 **選取** 索引標籤會顯示現行提供者和其他提供者擁有的現行 Finance 實體的所有範本。 選取一個範本將其開啟。 然後，您可以建立範本的新可編輯副本。 編輯後的範本儲存在自動產生的新 ER 格式設定中。

1. 在 **商業文件管理** 工作區中，選取 **新文件**。

    ![商業文件管理工作區。](./media/BDM_overview_new_template1.png)

2. 在 **建立新範本** 頁面的 **選取** 索引標籤上，選取要用作範本的文件，然後選取 **建立文件**。

    ![商業文件對話方塊。](./media/BDM_overview_new_template2.png)

3. 在新對話方塊中，在 **抬頭** 欄位，根據需要更改抬頭。 抬頭文字用於命名自動建立的新 ER 格式設定。 此設定的草稿版本 (**客戶 FTI 報告 (GER) 副本**) 將包含已編輯的範本，並將用於為現行使用者執行此 ER 格式。 來自基本 ER 格式設定的原始範本將用於為每個其他使用者執行此 ER 格式。
4. 在 **名稱** 欄位中，更改將自動建立的可編輯範本的第一個修訂版的名稱。
5. 在 **註解** 欄位中，更新將自動建立的可編輯範本的修訂註釋。
6. 選取 **確定** 以確認編輯流程的開始。

    ![文件建立對話方塊。](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>上傳使用現有 Excel 活頁簿的範本

此範例說明如何根據可用的 Excel 活頁簿，使用 **商業文件管理** 工作區中的 **新文件** 按鈕以 ER 格式設定建立和編輯範本。 在此範例中，作用中的提供者是 Contoso，您使用 Microsoft 提供的 ER [資料模型](er-overview-components.md#data-model-component)和 ER [模型對應](er-overview-components.md#model-mapping-component)設定。 選取 **新文件** 後，選取 **建立新範本** 頁面上的 **上傳** 索引標籤。 在那裡，您可以指定 Excel 活頁簿上傳的詳情。 上傳 Excel 活頁簿後，它會轉換為可以打開進行編輯的商業文件範本。 編輯後的範本將儲存在自動產生的新 ER 格式設定中。

在上傳範本之前，請按照以下步驟提供所需資訊。

1. 在 **商業文件管理** 工作區中，選取 **新文件**。
2. 在 **建立新範本** 頁面的 **上傳** 索引標籤上的 **範本** 索引標籤上，選取 **瀏覽** 以查找並選取要用作範本的 Excel 檔案。 在 **範本** 區段，**抬頭** 和 **描述** 欄位會自動填入。 它們指定自動建立的新 ER 格式設定的名稱和描述。 您可以根據需要編輯這些欄位。
3. 在 **文件類型** 區段的 **名稱** 欄位中，指定商業文件的類型。 此值將用於搜尋正確的資料來源 (即 ER 模型設定)。

    ![建立新範本頁面的上傳索引標籤上的範本索引標籤。](./media/BDM_overview_new_UI_import_21.jpg)

4. 在 **資料來源** 索引標籤上的 **過濾器** FastTab 上，選取 **套用過濾器**。 在 **資料來源** 區段，**名稱** 欄位會自動填入，或者您可以手動選取一個值。 您可以使用過濾器按名稱、描述、國家/地區代碼和商業文件類型搜尋適當的資料來源名稱。

    ![建立新範本頁面的上傳索引標籤上的資料來源索引標籤。](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > **過濾器** FastTab 用於搜尋正確的資料來源 (即 ER 模型設定)。 您可以編輯所有過濾器欄位，為您上傳的文件找到最合適的資料來源。
    > 
    > **過濾器** FastTab 上的條件用作 **OR** 條件。

5. 在 **對應** 索引標籤上，選取 **自動偵測**。 **根定義** 欄位會自動填入，或者您可以手動選取一個值。 此索引標籤顯示來自範本和模型的元素的最終對應。

    ![建立新範本頁面的上傳索引標籤上的對應索引標籤。](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > **範本結構** 區段中的對應使用使用者語言的資料來源中的標籤或描述以及範本中的儲存格名稱的完全相符。

6. 選取 **建立文件** 以確認您要建立範本並開始編輯流程。

如需相關資訊，請參閱[商業文件管理概述](er-business-document-management.md)。

## <a name="upload-a-template-from-the-global-repository"></a>從全域存放庫上傳範本

此範例說明如何使用 **商業文件管理** 工作區中的 **新文件** 按鈕來建立和編輯由 Microsoft 提供並位於全域存放庫中的 ER 格式設定的範本。 在此範例中，作用中的提供者是 Contoso，它使用 Microsoft 提供的 ER 格式設定。 選取 **新文件** 後，**建立新範本** 頁面上的 **從全域存放庫匯入** 索引標籤顯示儲存在全域存放庫中但在現行 Finance 實體中遺失的所有商業文件範本。 選取範本後，它會從全域存放庫匯入到現行 Finance 實體中，以建立新的可編輯副本。 編輯後的範本儲存在自動產生的新 ER 格式設定中。

1. 在 **商業文件管理** 工作區中，選取 **新文件**。
2. 在 **建立新範本** 頁面的 **從全域存放庫匯入** 索引標籤上，選取要用作範本的文件，然後選取 **建立文件**。

    ![從建立新範本頁面上的全域存放庫索引標籤匯入。](./media/BDM_overview_new_template22.png)

3. 在訊息方塊中，選取 **是** 以確認您要將選定文件從全域存放庫匯入到現行 Finance 實體中。 如果系統提示您進行授權，請按照螢幕上的說明進行操作。
4. 在新對話方塊中，在 **抬頭** 欄位，根據需要更改抬頭。 抬頭文字用於命名自動建立的新 ER 格式設定。 此設定的草稿版本 (**催款單 (Excel) 副本**) 將包含已編輯的範本，並將用於為現行使用者執行此 ER 格式。 來自基本 ER 格式設定的原始範本將用於為每個其他使用者執行此 ER 格式。
5. 在 **名稱** 欄位中，更改將自動建立的可編輯範本的第一個修訂版的名稱。
6. 在 **註解** 欄位中，更新將自動建立的可編輯範本的修訂註釋。
7. 選取 **確定** 以確認編輯流程的開始。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
