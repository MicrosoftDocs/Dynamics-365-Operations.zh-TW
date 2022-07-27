---
title: 更新業務文件範本的結構
description: 本主題介紹如何使用業務文件管理函數更新業務文件範本的結構。
author: NickSelin
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 2f57e3f3a84a6e767755c69074bc194e90793e6edd79d0e07ae7449d45ec7539
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460547"
---
# <a name="update-the-structure-of-a-business-document-template"></a>更新業務文件範本的結構 

[!include[banner](../includes/banner.md)]

在 [業務文件管理](er-business-document-management.md)範本編輯器的 **範本結構** 窗格中，您可以透過[新增新欄位](er-bdm-add-field-to-excel-template.md)到 Microsoft Excel 中的範本來修改業務文件範本。 範本的結構隨後會在 Dynamics 365 Finance 中自動更新，以便它反映您在 **範本結構** 窗格中所做的更改。

您還可以使用 Office 365 線上函數修改範本。 例如，您可以將新的命名項目 (例如圖片或形狀) 新增到可編輯工作表中。 在這種情況下，範本的結構不會在 Finance 中自動更新，並且您新增的項目不會出現在 **範本結構** 窗格中。 透過在範本編輯器頁面上選取 **更新結構** 手動更新 Finance 中的範本結構。

如需此函數的相關資訊，請完成以下範例。

## <a name="example-update-the-structure-of-a-business-document-template"></a>範例：更新業務文件範本的結構

此範例說明在 Office Online 中修改範本後，系統管理員如何更新 Finance 中的業務文件範本的結構。 以下區段解釋了所涉及的步驟。

### <a name="prepare-a-business-document-template-for-editing"></a>準備用於編輯的業務文件範本

完成以下[業務文件管理概述](er-business-document-management.md)中的程序。

1. [設定 ER 參數](er-business-document-management.md#configure-er-parameters)
2. [匯入 ER 解決方案](er-business-document-management.md#import-er-solutions)
3. [啟用商業檔案管理](er-business-document-management.md#enable-business-document-management)
4. [設定參數](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>編輯業務文件範本

1. 在 **商業文件管理** 工作區中，選取 **新文件**。
2. 在 **建立新範本** 頁面，選取 **普通發票 (ER 樣本)(Excel)** 範本。
3. 選取 **建立文件**。
4. 在 **標題** 欄位中，輸入 **FTI sample Litware**。
5. 選取 **確定** 建立新範本。

    > [!NOTE]
    > 如果您尚未登入 Office Online，您將[導向到 Office 365 登入頁面](er-business-document-management.md#frequently-asked-questions)。 若要回傳您的 Finance 環境，請在瀏覽器中選取 **回傳** 按鈕。

    在範本編輯器頁面上的 Excel Online 嵌入式控制項中打開新範本進行編輯。

[![使用業務文件管理工作區開始編輯業務文件範本。](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>查看可編輯範本的現行結構

1. 在 Excel Online 中的函數區上，在 **檢視** 索引標籤上，在 **顯示** 組中，選取 **格線**。
2. 在可編輯範本中，選取範本標題上方的矩形。 此矩形是名為 **rptHeaderCompLogo** 的圖片。
3. 如果 **範本結構** 窗格已隱藏，請選取 **顯示結構**。
4. 在 **範本結構** 窗格中，展開 **Report\>Invoice\>rptHeader\>rptHeaderPart1**。
5. 請注意，在 Finance 的範本結構中，**rptHeaderCompLogo** 項目作為 **Report\>Invoice\>rptHeader\>rptHeaderPart1** 的子項目呈現。

[![使用業務文件管理工作區查看可編輯範本的現行結構。](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>透過刪除圖片來更新業務文件範本的結構

1. 在 Excel Online 的可編輯範本中，選取 **rptHeaderCompLogo** 圖片。
2. 按照以下步驟之一從可編輯範本中刪除所選圖片：

    - 選取鍵盤上的 **Delete** 鍵。
    - 選取並按住 (或按右鍵點選) 圖片，然後選取 **剪下**。

    > [!NOTE]
    > 即使該圖片不再包含在 Excel 範本中，**rptHeaderCompLogo** 項目目前仍存在於 Finance 的範本結構中。

3. 選取 **更新結構** 在 Excel 和 Finance 中同步可編輯範本的結構。
4. 在 **範本結構** 窗格中，展開 **Report\>Invoice\>rptHeader\>rptHeaderPart1**。
5. 請注意，**rptHeaderCompLogo** 項目不再包含在 Finance 的範本結構中。

[![使用業務文件管理工作區從業務文件範本中刪除圖片。](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>透過新增圖片來更新業務文件範本的結構

1. 在 Excel Online 中的函數區上，在 **插入** 索引標籤上，在 **插圖** 組中，選取 **圖片**。
2. 選取 **選取檔案**，瀏覽到要新增的影像，選取它，然後選取 **確定**。
3. 選取 **插入**。
4. 移動新圖片，直到它在正確的位置。 在預設情況下，Excel 為圖片命名。 例如，它可能將圖片命名為 **Picture 2**。
5. 選取 **更新結構** 在 Excel 和 Finance 中同步可編輯範本的結構。
6. 在 **範本結構** 窗格中，展開 **Report\>Invoice\>rptHeader\>rptHeaderPart1**。
7. 請注意，新圖片現在作為項目包含在 Finance 的範本結構中。

[![使用業務文件管理工作區將圖片新增到業務文件範本。](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>相關連結

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[商業文件管理概述](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]