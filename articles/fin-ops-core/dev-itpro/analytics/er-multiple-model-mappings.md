---
title: 管理單個模型根的多個衍生對應
description: 本主題說明如何管理為單個模型根設定的多個衍生對應。
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d71b05b3f2eda93a93f728926e675c040371781e
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460556"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>管理單個模型根的多個衍生對應

[!include [banner](../includes/banner.md)]

每個設定的 ER 格式組件都使用[電子報表 (ER)](general-electronic-reporting.md) 資料模型組件作為資料來源來產生輸出文件。 若要描述單個業務域，請設定具有許多根定義的資料模型組件。 

每個根定義都允許您以最適合特定報告目的的方式表示該領域的資料。 對於每個根定義，您可以將 ER 模型對應組件設定為您的資料模型的 Microsoft Dynamics 365 Finance 專用實施。 透過這種方式，您可以描述如何在執行階段填入資料模型。

ER 模型對應組件可以駐留在 ER 資料模型[設定](general-electronic-reporting.md#Configuration)和 ER 模型對應設定中。 單個 ER 設定可以包含許多對應組件，每個對應組件都針對單個根定義進行設定。 或者，單個 ER 設定可以只包含一個為單個根定義設定的對應組件。

許多設定提供程式可能會為相同的 ER 資料模型提供 ER 模型對應設定。 這些模型對應設定可能包含不同根定義的對應組件。 您可以為一個[提供者](general-electronic-reporting.md#Provider)提供的一個根定義使用模型對應，並為另一個提供者提供的另一個根定義使用模型對應。

本主題中的程序說明當 ER 資料模型的多個 ER 模型對應設定包含為同一根定義設定的不同模型對應組件時，如何管理它們。 

若要完成本主題中的程序，您必須被指派到系統管理員或電子報表開發人員角色。

以下所有程序都可以在 USMF 公司完成。 無需編碼。

## <a name="configure-the-er-framework"></a>設定 ER 架構

作為電子報表開發人員角色的使用者，請在使用 ER 架構產生業務文件之前[設定最少](er-quick-start2-customize-report.md#ConfigureFramework)的 ER 參數集。

## <a name="import-the-standard-er-format-configurations"></a>匯入標準 ER 格式設定

要將標準 ER 設定新增到 Finance 的現行執行個體中，您必須從為該執行個體設定的 ER 存放庫中匯入這些設定。 按照[從設定服務的全域存放庫下載 ER 設定](er-download-configurations-global-repo.md)中的步驟匯入以下 ER 格式設定：

- **普通發票 (Excel)**，220.106 版
- **專案發票 (Excel)**，226.27 版

## <a name="review-the-imported-er-configurations"></a>查看匯入的 ER 設定

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定** 區塊中，選取 **報表設定** 圖格。
3. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，展開 **發票模型**。

    ![在設定頁面查看匯入的設定。](./media/er-multiple-model-mappings-image1.png)

4. 審查 **普通發票 (Excel)** 格式：

    1. 在左側窗格的設定樹狀結構中，選取 **普通發票 (Excel)**。
    2. 在動作窗格上，選取 **設計工具**。
    3. 在 **格式設計工具** 頁面的 **對應** 索引標籤上，在資料來源清單中，選取 **模型**。
    4. 選取 **檢視**。
    
       現行 ER 格式設定為使用 **發票模型** 的 **InvoiceCustomer** 根定義。 執行此格式並調用 **模型** 資料來源時，為 **InvoiceCustomer** 根定義設定的模型對應用於存取應用程式資料並填入資料模型。

        ![在格式設計工具頁面上查看模型資料來源。](./media/er-multiple-model-mappings-image2.png)

    6. 關上 **格式設計工具** 頁面。

5. 查看 **發票模型對應** 設定的內容：

    1. 在左側窗格的設定樹中，選取 **發票模型對應**。
    2. 在動作窗格上，選取 **設計工具**。
    3. 在 **要用於資料來源對應的模型** 頁面，請注意現行的 ER 模型對應設定包含幾個模型對應組件：

        + **客戶發票** 模型對應是為 **發票模型** 的 **InvoiceCustomer** 根定義設定的。 因此，在執行 **普通發票 (Excel)** ER 格式時，可以選取此 ER 設定的 **客戶發票** 模型對應來存取應用程式資料並填入資料模型。
        + **專案發票** 模型對應是為 **發票模型** 的 **InvoiceProject** 根定義設定的。 因此，在執行 **專案發票 (Excel)** ER 格式時，可以選取此 ER 設定的 **專案發票** 模型對應來存取應用程式資料並填入資料模型。

        ![模型到資料來源對應頁面上的發票模型對應。](./media/er-multiple-model-mappings-image3.png)

    4. 關閉 **資料來源對應的模型** 頁面。
    5. 在 **版本** FastTab 卡，選取 **刪除** 來刪除此 ER 設定的所有晚於 240.175 的版本。

6. 查看 **專案發票模型對應 (RDP)** 設定的內容：

    1. 在左側窗格的設定樹狀結構中，選取 **專案發票模型對應 (RDP)**。
    2. 在動作窗格上，選取 **設計工具**。
    3. 在 **要用於資料來源對應的模型** 頁面，請注意現行的 ER 模型對應設定包含 **InvoiceProject** 模型對應，並且此模型對應設定為 **發票模型** 的 **InvoiceProject** 根定義。 當 **專案發票 (Excel)** ER 格式執行階段，選取此 ER 設定的 **InvoiceProject** 模型對應以存取應用程式資料並填入資料模型。

        ![模型到資料來源對應頁面上的項目發票模型對應。](./media/er-multiple-model-mappings-image4.png)

    4. 關閉 **資料來源對應的模型** 頁面。
    5. 在 **版本** FastTab 卡，選取 **刪除** 來刪除此 ER 設定的所有晚於 226.35 的版本。

## <a name="customize-the-imported-er-configurations"></a>自訂匯入的 ER 設定

本節說明如何[自訂](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration) Microsoft 提供的模型對應。 例如，可能需要自訂來實現您的自訂邏輯或新增缺少的繫結。

### <a name="customize-the-invoice-model-mapping-configuration"></a>自訂發票模型對應設定

1. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **發票模型對應**。
2. 在動作窗格上，選取 **建立設定**。
3. 在 **建立設定** 下拉式對話方塊中，在 **新建** 欄位，選取 **來源名稱：發票模型對應，Microsoft**。
4. 在 **名稱** 欄位中，輸入 **Invoice model mapping Litware**。
5. 選取 **建立設定**。
6. 將衍生對應的[草稿](general-electronic-reporting.md#component-versioning)版本[標記](er-quick-start2-customize-report.md#MarkFormatRunnable)為可在執行階段使用：

    1. 在動作窗格上，在 **設定** 索引標籤，在 **進階設定** 組，選取 **使用者參數**。
    2. 在 **使用者參數** 對話方塊，將 **執行設定** 選項設定為 **是**，然後選取 **確定**。
    3. 選取 **編輯** 根據需要使頁面處於可編輯狀態。
    4. 對於現行在設定樹狀結構中選取的 **發票模型對應 Litware** 設定，將 **執行草稿** 選項設定為 **是**。

7. 在動作窗格上，選取 **設計工具** 查看此設定的模型對應。

    ![查看要用於資料來源對應的模型頁面上的發票模型對應。](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > 您現在可以在設計工具中打開此 ER 設定的任何 ER 模型對應組件來設定您的自訂邏輯。 如需相關資訊，請參閱[自訂模型對應設定 ](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration)。

8. 關閉 **資料來源對應的模型** 頁面。

您現在有 **發票模型對應** 和 **發票模型對應 Litware** 設定，每個設定都有設定為 **發票客戶** 根定義的模型對應。 將模型對應之一明確指派為任何 ER 格式使用的預設模型對應，例如包含具有 **InvoiceCustomer** 根定義的模型資料來源的 **普通發票 (Excel)** 格式。 否則，當您執行、編輯或驗證其中一種 ER 格式時，將引發以下異常以通知您未顯式指派預設模型對應：
 
> 設定\<configuration names separated by commas\>中的「\<model name\> (\<root descriptor\>)」資料模型存在多個模型對應。 將其中一項組態設定為預設值。

![在設定頁面上打開格式進行編輯。](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>自訂專案發票模型對應 (RDP) 設定

1. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **專案發票模型對應 (RDP)**。
2. 在動作窗格上，選取 **建立設定**。
3. 在 **建立設定** 對話方塊中，在 **新建** 欄位，選取 **來源名稱：專案發票模型對應 (RDP)，Microsoft**。
4. 在 **名稱** 欄位中，輸入 **Project invoice model mapping Litware**。
5. 選取 **建立設定**。
6. 對於現行在設定樹狀結構中選取的 **專案發票模型對應 Litware** 設定，將 **執行草稿** 選項設定為 **是**。
7. 在動作窗格上，選取 **設計工具** 查看此設定的模型對應。

    ![查看要用於資料來源對應的模型頁面上的自訂專案發票模型對應。](./media/er-multiple-model-mappings-image7.png)

8. 關閉 **資料來源對應的模型** 頁面。

您現在擁有 **發票模型對應**、**專案發票模型對應 (RDP)** 和 **專案發票模型對應 Litware** 設定。 這些設定中的每一個都具有為 **InvoiceProject** 根定義設定的模型對應。 將模型對應之一明確指派為任何 ER 格式使用的預設模型對應。 例如，使用包含具有 **InvoiceProject** 根定義的模型資料來源的 **專案發票 (Excel)** 格式。 否則，當您執行或編輯其中一種 ER 格式時，將引發異常以通知您未明確指派預設模型對應。

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>選取衍生的發票模型對應 Litware 設定作為包含預設模型對應的設定

1. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **發票模型對應 Litware**。
2. 將 **模型對應的預設值** 選項設定為 **是**。

    ![在設定頁面上將模型對應設定為預設模型對應。](./media/er-multiple-model-mappings-image8.png)

    由於此設定，當您執行 **普通發票 (Excel)** 或編輯或驗證它時，將使用 **客戶發票副本** 模型對應。 來自 **發票模型對應** 設定的 **客戶發票** 模型對應會被忽略。

    您現在可以在格式設計工具中打開 **普通發票 (Excel)** 格式以供審閱。

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>選取衍生的專案發票模型對應 Litware 設定作為包含預設模型對應的設定

1. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **專案發票模型對應 Litware**。
2. 將 **模型對應的預設值** 選項設定為 **是**。

    在這種情況下，與上一節中為 **發票模型對應 Litware** 設定描述的情況不同，您不能從 **專案發票模型對應 Litware** 設定開始使用 **InvoiceProject Copy** 模型對應。 包含 **InvoiceProject** 根定義的模型對應的兩個設定現行被標記為預設設定。 因此，它們具有相同的使用優先順序。 若要解決此問題，請完成此程序的剩餘步驟。

3. 在左側窗格的設定樹狀結構中，選取 **發票模型對應 Litware**。
4. 在動作窗格上，選取 **設計工具**。
5. 在 **要用於資料來源對應的模型** 頁面，選取 **編輯** 根據需要使頁面可編輯。
6. 選取 **專案發票副本** 模型對應，然後選取 **被刪除** 核取方塊。

    ![在模型到資料來源對應頁面上將模型對應設定為虛擬刪除。](./media/er-multiple-model-mappings-image9.png)

    由於此設定，**發票模型對應 Litware** 設定被視為沒有針對 **InvoiceProject** 根定義的模型對應。 **InvoiceProject Copy** 模型對應預設下發佈。 包含此模型對應的設定 **專案發票模型對應 Litware** 被標記為預設設定。 因為它被標記為預設值，所以它比來自 **專案發票模型對應 (RDP)** 設定的 **InvoiceProject** 模型對應具有更高的優先順序。

## <a name="other-considerations"></a>其他注意事項

**專案發票模型對應 Litware** 設定的 **InvoiceProject Copy** 模型對應旨在使用 **ReportDataProvider** 資料來源。 資料來源是參考 **PsaProjInvoiceDP** 應用程式類的 *物件* 類型的一部分。 此類被實現為列印管理架構的項目發票 SQL Server Reporting Services (SSRS) 報告的資料提供者。 選取此資料來源作為 ER[整合點 ](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents)。 列印管理報告的現行 ER 實施考慮了此設定。 如需相關資訊，請查看 **ERPrintMgmtDataProviderReport** 應用程式類的原始程式碼。 在執行階段，將 **ReportDataProvider** 資料來源指派為模型對應整合點會強制 Finance 將此對應組件的優先順序高於 **專案發票模型對應 (RDP)** 設定中的 **InvoiceProject** 對應組件。

## <a name="see-also"></a>另請參閱

- [在單獨的 ER 設定中管理 ER 模型對應](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [設定依賴於 ER 模型對應的國家背景](er-country-dependent-model-mapping.md)
- [電子報表架構 API 更改](er-apis-app10-0-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
