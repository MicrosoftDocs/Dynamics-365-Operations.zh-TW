---
title: 在 Microsoft Excel 中向商業檔案範本新增新欄位
description: 本主題提供有關如何使用商業檔案管理功能將新欄位新增到 Microsoft Excel 中的商業檔案範本的資訊。
author: NickSelin
ms.date: 11/15/2019
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
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 57eebdc38fb3f74690b92c03fa60e10c7610db1fe413320a6d167f05b0658bf1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460306"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>在 Microsoft Excel 中向商業檔案範本新增新欄位

[!include[banner](../includes/banner.md)]

您可以將新欄位新增到用於產生 Microsoft Excel 格式的商業檔案的範本。 這些欄位可以作為預留位置新增，用於使用應用程式所需的資訊填入產生的文件。 對於您新增的每個欄位，您還可以指定與資料來源的繫結，以指定在使用範本產生商業檔案時將在該欄位中輸入哪些應用程式資料。

若要進一步了解此函數，請完成本主題中的範例。 此範例說明如何更新範本以填入產生的普通發票表單中的欄位。

## <a name="configure-business-document-management-to-edit-templates"></a>設定商業檔案管理以編輯範本

由於商業檔案管理 (BDM) 建立在[電子報表 (ER) 概覽](general-electronic-reporting.md)架構之上，因此您必須先設定所需的 ER 和 BDM 參數，然後才能開始使用 BDM。

1.  以系統管理員身份登入 Microsoft Dynamics 365 Finance 實體。
2.  完成[商業檔案管理概述](er-business-document-management.md)主題中範例的以下步驟：

    1.  設定 ER 參數。
    2.  打開 BDM。

您現在可以開始使用 BDM 來編輯商業檔案範本。

## <a name="import-er-solutions-that-contain-a-template"></a>匯入包含範本的 ER 解決方案

此程序中的範例使用正式發布的 ER 解決方案。 您必須將此解決方案的 ER 設定匯入您現行的 Finance 實體。

本解決方案的 **普通發票 (Excel)** ER 格式設定包含 Excel 格式的商業檔案範本，可以使用 BDM 進行編輯。 從 Microsoft Dynamics Lifecycle Service (LCS) 匯入此 ER 格式設定的最新版本。 相應的 ER 資料模型和 ER 模型對應設定將自動匯入。

如需如何匯入 ER 設定的相關資訊，請參閱[管理 ER 設定生命週期](general-electronic-reporting-manage-configuration-lifecycle.md)。

![LCS 共用資產庫頁面。](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>編輯 ER 解決方案範本

1.  以有權存取 **商業檔案管理** 工作區的使用者身份登入。
2.  開啟 **商業檔案管理** 工作區。

    ![商業文件管理工作區。](./media/BDM-AddFldExcel-Workspace.png)

3.  在格線中，選取 **普通發票 (Excel)** 範本。
4.  在右側窗格中，選取 **新建範本** 以建立基於所選範本的新範本。
5.  在 **標題** 欄位，輸入 **普通發票 (Excel) Contoso** 作為新範本的標題。
6.  選取 **確定** 以確認編輯流程的開始。

出現 BDM 範本編輯器頁面。 您可以使用 Microsoft 365 在嵌入式控制項中在線編輯所選範本。

![BDM 範本編輯器頁面。](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>將新欄位的標籤新增到範本

1.  在 BDM 範本編輯器頁面的 Excel 功能區的 **檢視** 索引標籤上，選中可編輯 Excel 範本的 **標題和格線線** 核取方塊。

    ![已選取標題和格線線核取方塊。](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  選取儲存格 **E8:F8**。
3.  在 Excel 功能區的 **首頁** 索引標籤上，選取 **合併和居中** 以將選定的儲存格合併到一個新的合併 **E8:F8** 儲存格中。
4.  在合併的儲存格 **E8:F8** 中，輸入 **URL**。
5.  選取合併儲存格 **E7:F7**，選取 **複製格式**，然後選取合併儲存格 **E8:F8** 以與合併儲存格 **E7:F7** 相同的方式對其進行格式化。

    ![新增到範本的新欄位標籤。](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>格式化範本來為新欄位保留空間

1.  在 BDM 範本編輯器頁面上，選取合併儲存格 **G8:H8**。
2.  在 Excel 功能區的 **首頁** 索引標籤上，選取 **合併和居中** 以將選定的儲存格合併到一個新的合併 **G8:H8** 儲存格中。
3.  選取合併儲存格 **G7:H7**，選取 **複製格式**，然後選取合併儲存格 **G8:H8** 以與合併儲存格 **G7:H7** 相同的方式對其進行格式化。

    ![為新欄位保留的空間。](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  在 **名稱** 方塊欄位中，選取 **CompanyInfo**。

    現行 Excel 範本的 **CompanyInfo** 範圍包含用於填入產生報表的標題的所有欄位，其中包含現行公司作為賣方的詳情。

    ![已選取 CompanyInfo 範圍。](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>向範本新增新欄位

1.  在 **BDM 範本編輯器** 頁面，在動作窗格上，選取 **顯示格式**。
2.  在 **範本結構** 窗格中，選取 **新增**。

    > [!NOTE]
    > 您必須調整要用作新欄位的範本部分。 您已經透過格式化合併儲存格 **G8:H8** 進行了此調整。

    ![向範本新增新欄位。](./media/BDM-AddFldExcel-AddCell.png)

3.  選取 **Excel\Cell** 以將新欄位新增為範本中的儲存格。

    如果要向範本新增新範圍，可以選取 **Excel\Range**。 輸入的範圍可以包含多個儲存格。 您可以稍後新增這些儲存格。
    
    請注意，在 **範本結構** 窗格中自動選取了 **CompanyInfo** 範本組件，因為它是現行範本結構中最適合您要新增的欄位的父組件。
    
4.  在 **Excel 範圍** 欄位中，輸入 **CompanyURL_Value**。
5.  選取 **確定**。

    ![CompanyURL_Value 欄位新增到範本結構。](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  在 **範本結構** 窗格中，選取省略符號按鈕 (...)，然後選取 **顯示繫結**。

    ![顯示已選取的繫結。](./media/BDM-AddFldExcel-ShowBindings.png)

    **範本結構** 窗格現在顯示以基礎 ER 格式提供的資料來源。

7.  選取 **CompanyInfo_Value** 作為您計畫繫結到基礎 ER 格式的資料來源的欄位。
8.  在 **範本結構** 窗格的 **資料來源** 部分，展開 **Model\>InvoiceBase\>CompanyInfo**。
9.  在 **CompanyInfo** 下，選取 **WebsiteURI** 項目。

    ![已選取 WebsiteURI 項目。](./media/BDM-AddFldExcel-BindURL.png)

10. 選取 **繫結**。
11. 在 **範本結構** 窗格，選取 **儲存**，然後關閉 BDM 範本編輯器頁面。

在 **商業檔案管理** 工作區中，右窗格中的 **範本** 索引標籤顯示更新的範本。 在格線中，請注意已編輯範本的 **狀態** 欄位已更改為 **草稿**，並且 **修訂** 欄位不再為空白。 這些更改表明編輯此範本的過程已經開始。

![商業檔案管理工作區中的已編輯範本。](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>查看公司設定

1.  進入 **組織管理\>組織\>法律實體**。
2.  在 **聯絡資訊** FastTab 上，驗證是否輸入了公司 URL。

![在法律實體頁面上輸入的公司 URL。](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>產生商業檔案以測試更新的範本

1.  在應用程式中，將公司更改為 **USMF**，然後進入 **應收帳款\>發票\>所有普通發票**。
2.  選取發票 **FTI-00000002**，然後選取 **列印管理**。
3.  在左窗格中，展開 **模組 - 應收帳款\>檔案\>普通發票**。
4.  在 **普通發票** 下，選取 **原始文件** 級別以指定要處理的發票範圍。
5.  在右側窗格中，在 **報表格式** 欄位，選取指定文件級別的 **普通發票 (Excel) Contoso** 範本。

    ![已選取普通發票 (Excel) Contoso 範本。](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  按 **Esc** 關閉現行頁面。
7.  選取 **列印\>已選取**。
8.  下載產生的文件，並在 Excel 中打開。

    ![Excel 中的普通發票](./media/BDM-AddFldExcel-PreviewReport.png)

修改後的範本用於產生所選項目的普通發票報告。 若要分析您對範本所做的更改如何影響此報表，請在另一個應用程式會話中更改範本後立即在一個應用程式會話中執行該報表。

## <a name="related-links"></a>相關連結

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[商業文件管理概述](er-business-document-management.md)

[設計用於產生 OPENXML 格式報表的設定](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]