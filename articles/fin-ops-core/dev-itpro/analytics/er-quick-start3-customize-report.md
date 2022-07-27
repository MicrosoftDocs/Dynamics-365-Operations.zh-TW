---
title: 自訂電子報表設定以產生電子文件
description: 本主題說明如何自訂 Microsoft 提供的用於產生自訂電子文件的電子報表 (ER) 設定。
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c8cf4866b6a8c239359d726d8cd4f03a9eb4137
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460545"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>自訂電子報表設定以產生電子文件

[!include[banner](../includes/banner.md)]

[電子報表 (ER) 架構](general-electronic-reporting.md)允許您將 Microsoft 提供的 ER [設定](general-electronic-reporting.md#Configuration)上傳到您的 Microsoft Dynamics 365 Finance 執行個體中。 透過這種方式，Microsoft 提供的設定可以作為用於產生電子客戶發票 (電子發票) 的 ER 解決方案。 您可以使用此 ER 解決方案來設定您的自訂 ER 解決方案以存取您的自訂資料庫欄位並產生符合您的特定要求的電子發票，而無需編輯原始程式碼。

## <a name="overview"></a>概觀

對於本主題中的範例，您必須將聯邦稅識別碼指定為您以電子方式開票的每個客戶的新自訂屬性。 因此，您必須透過在產生的每張電子發票中新增一個必須填入稅碼的新項目來自訂現行使用的發票結構。

本主題中的過程說明了系統管理員、電子報表開發人員或電子報表功能顧問角色的使用者如何在您的 Finance 執行個體中執行以下工作：

- [設定開始使用 ER 架構所需的最小 ER 參數集](#ConfigureER)。
- [匯入為產生電子發票而提供的標準 ER 設定的初始版本](#ImportERConfigurations1)。
- [設定應收帳款參數以開始使用標準 ER 設定](#ConfigureAR1)。
- [設定法律實體參數以向客戶開具發票](#ConfigureLE)。
- [準備電子發票的客戶記錄](#ConfigureCustomer1)。
- [使用標準 ER 設定新增、過帳和發送客戶發票](#ProcessInvoice1)。
- [新增自訂資料庫欄位以管理客戶的聯邦稅識別碼](#AddCustomField)。
- [重新整理 ER 中繼資料以啟用 ER 模型對應設計工具的資料庫更改](#RefreshERMetadata)。
- [設計自訂 ER 設定以產生包含新稅碼的電子發票](#DesignCustomERConfigurations)。
- [設定應收帳款參數以開始使用自訂 ER 設定](#ConfigureAR2)。
- [更新電子發票的客戶記錄](#ConfigureCustomer2)。
- [使用自訂 ER 設定新增、過帳和發送客戶發票](#ProcessInvoice2)。
- [匯入為產生電子發票而提供的標準 ER 設定的新版本](#ImportERConfigurations2)。
- [在您的自訂 ER 設定中採用對標準 ER 設定新版本的更改](#RebaseCustomERConfigurations)。
- [使用新版本自訂 ER 設定新增、過帳和發送客戶發票](#ProcessInvoice3)。

所有這些程序都可以在 **DEMF** 公司完成。

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>設定 ER 架構

作為電子報表功能顧問或電子報表開發人員角色的使用者，您必須設定最小的 ER 參數集。 然後，您可以開始使用 ER 架構來設計用於產生電子發票的 ER 解決方案標準設定的自訂版本。

### <a name="configure-er-parameters"></a>設定 ER 參數

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **電子報表參數**。
3. 在 **電子報表參數** 頁的 **一般** 索引標籤上，將 **啟用設計模式** 選項設定為 **是**。
4. 在 **附件** 索引標籤，在 **設定** 欄位，選取 **檔案**。
5. 在 **作業封存**、**臨時**、**基準** 和 **其他** 欄位中，選取 **檔案** 類型。

如需 ER 參數的相關資訊，請參閱[設定 ER 架構](electronic-reporting-er-configure-parameters.md)。

### <a name="activate-an-er-configuration-provider"></a>啟用 ER 設定提供者

新增的每個 ER 設定都被標記為歸 ER 設定提供者所有。 在 **電子報表** 工作區中啟用的 ER 設定提供者用於此目的。 因此，您必須先在 **電子報表** 工作區中啟用 ER 設定提供者，然後才能開始新增或編輯 ER 設定。

> [!NOTE]
> 只有 ER 設定的所有者可以對其進行編輯。 因此，在可以編輯 ER 設定之前，必須在 **電子報表** 工作區中啟動相應的 ER 設定提供者。

#### <a name="review-the-list-of-er-configuration-providers"></a>查看 ER 設定提供者清單

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **設定提供者**。
3. 在 **設定提供者資料表** 頁面，每個設定提供者記錄都有一個唯一的名稱和 URL。 查看此頁面的內容。 如果 **Litware, Inc.** (`https://www.litware.com`) 的記錄已存在，請跳過下一個程序[新增新的 ER 設定提供者](#AddProvider)。

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>新增新的 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **設定提供者**。
3. 在 **設定提供者** 頁面上，選取 **新建**。
4. 在 **名稱** 欄位中，輸入 **Litware, Inc.**
5. 在 **網址** 欄位，輸入 `https://www.litware.com`。
6. 選取 **儲存**。

#### <a name="activate-an-er-configuration-provider"></a>啟用 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定提供者** 部分中，選取 **Litware, Inc.** 圖格，然後選取 **設定為有效狀態**。

如需 ER 設定提供者的相關資訊，請參閱[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)。

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>匯入標準 ER 設定的初始版本

要將標準 ER 設定新增到現行 Finance 執行個體中，您必須從為該執行個體設定的 ER [存放庫](general-electronic-reporting.md#Repository)中匯入這些設定。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定提供者** 區塊，選取 **Microsoft** 圖格，然後選取 **存放庫**，查看 Microsoft 提供者的存放庫清單。
3. 在 **設定存放庫** 頁面，選取 **全域** 類型的存放庫，然後選取 **開啟**。 如果提示您需要授權才能連線到 Regulatory Configuration Service，請遵循授權指示。
4. 在 **設定存放庫** 頁面上，在左側窗格的設定樹狀結構中，選取 **Peppol 銷售發票** 格式設定。
5. 在 **版本** FastTab 上，選取版型 **11.2.2**。
6. 選取 **匯入** 以從全域存放庫下載選定的版本。

![設定存放庫頁面。](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> 如果您在存取[全域存放庫](er-download-configurations-global-repo.md)時遇到問題，可以改為從 Microsoft Dynamics Lifecycle Services (LCS) [下載設定](download-electronic-reporting-configuration-lcs.md)。

### <a name="review-the-imported-er-configurations"></a>查看匯入的 ER 設定

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定** 區塊中，選取 **報表設定** 圖格。
3. 在 **設定** 頁，展開 **設定組件** FastTab。
4. 在左窗格的設定樹狀結構中，展開 **發票模型**，然後展開 **UBL 銷售發票**。

請注意，除了選定的 **Peppol 銷售發票** ER 格式之外，還匯入了其他必需的 ER 設定。 由於 ER 設定的新版本不斷發佈到全局存放庫和 LCS 以使相應的解決方案符合新的要求，因此匯入了所需資料模型設定及其模型對應設定的最新版本。

![設定頁面。](./media/er-quick-start3-imported-solution1a.png)

如果您在過去 (例如，2019 年 8 月 7 日) 匯入了 **Peppol 銷售發票** ER 格式的版本 **11.2.2**，為了模擬現行 Finance 執行個體中的 ER 設定將處於的狀態，請執行以下步驟。

- 在動作窗格上，選取 **刪除** 刪除 2019 年 8 月 7 日之後發佈的所有 ER 設定。 必須保留唯一的 **發票模型**、**發票模型對應** (最初命名為 **客戶發票模型對應**)、**UBL 銷售發票** 和 **Peppol 銷售發票** 設定。
- 對於剩餘的 ER 設定，在 **版本** FastTab 上，選取 **刪除** 以刪除 2019 年 8 月 7 日之後發佈的所有 ER 設定版本。

然後驗證設定樹狀結構中是否存在以下設定：

- **發票模型** ER 資料模型設定 (最初命名為 **客戶發票模型**)：

    - 版本 11 包含版本 10 的資料模型 ER 組件，它表示開票業務領域的資料結構。 此 ER 設定已作為選取匯入的 **Peppol 銷售發票** ER 格式的上階匯入。
    - 版本 50 包含資料模型 ER 組件的版本 31。 此 ER 設定已作為 2019 年 8 月 7 日版本 **發票模型對應** ER 模型對應設定的上階匯入。

    ![設定頁面上的發票模型 ER 資料模型設定。](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > 如果您沒有看到此資料模型的版本 50，請打開全域存放庫，然後匯入版本 50.19 的 **發票模型對應** ER 設定。

- **發票模型對應** ER 模型對應設定 (最初命名為 **客戶發票模型對應**)：

    - 版本 50.19 已作為 **發票模型** ER 資料模型設定的版本 50 的最新實作匯入。 它包含兩個模型對應 ER 組件，用於描述如何在執行階段用應用程式資料填入資料模型。

    ![設定頁面上的發票模型對應 ER 模型對應設定。](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > 如果您沒有看到此模型對應的版本 50.19，請打開全域存放庫，然後匯入版本 50.19 的 **發票模型對應** ER 設定。

- **UBL 銷售發票** ER 格式設定：

    - 版本 11.2 包含格式和格式對應 ER 組件。 格式組件指定報表配置。 格式對應組件包含模型資料來源，並指定如何使用此資料來源在執行階段填入報表配置。 此 ER 格式設定為以通用商務語言 (UBL) 格式產生電子發票。 它已作為選取匯入的 **Peppol 銷售發票** ER 格式的父系匯入。

- **Peppol 銷售發票** ER 格式設定：

    - 版本 11.2.2 包含格式和格式對應 ER 組件，這些組件被設定為以 Pan-European Public Procurement OnLine (PEPPOL) 格式產生電子發票。

    ![設定頁面上的 Peppol 銷售發票 ER 格式設定。](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>設定應收帳款參數

1. 進入 **應收帳款**\>**設定**\>**應收帳款參數**。
2. 在 **電子檔案** 索引標籤，在 **電子報表** FastTab，在 **銷售和普通發票** 欄位，選取 **Peppol 銷售發票**。
3. 選取 **儲存**。

![應收帳款參數頁面上的電子文件索引標籤。](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>設定法律實體參數

1. 進入 **組織管理**\>**組織**\>**法律實體**。
2. 對於選定的 **DEMF** 公司，在 **銀行帳戶資訊** FastTab 上的 **路由編號** 欄位中，輸入 **1234**。
3. 選取 **儲存**。
4. 關上 **法律實體** 頁。

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>準備客戶記錄

1. 進入 **應收帳款**\>**客戶**\>**所有客戶**。
2. 在 **所有客戶** 頁面，選取 **DE-014** 客戶帳戶連結。

### <a name="add-a-customer-contact"></a>新增客戶聯絡人

1. 進入 **應收帳款**\>**客戶**\>**所有客戶**。
2. 在動作窗格的 **客戶** 索引標籤上，於 **帳戶** 群組中選取 **聯絡人**。
3. 選取 **新增聯絡人**。
4. 在 **聯絡人** 頁，在 **名字** 欄位，打開查詢，選取 **Adam Carter**，然後選取 **選取** 關閉查詢。
5. 選取 **儲存**。
6. 關閉 **聯絡人** 頁面。

### <a name="define-a-primary-contact"></a>定義主要聯絡人

1. 進入 **應收帳款**\>**客戶**\>**所有客戶**。
2. 在 **銷售人口統計** FastTab，在 **主要聯絡人** 欄位，選取 **Adam Carter**。

### <a name="set-the-e-invoicing-option"></a>設定電子發票選項

1. 進入 **應收帳款**\>**客戶**\>**所有客戶**。
2. 在 **發票和交貨** FastTab，將 **電子發票** 選項設定 **是**。
3. 選取 **儲存**。
4. 關閉 **所有客戶** 頁。

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>使用標準 ER 設定處理客戶發票

您現在可以使用您匯入的標準 ER 設定以電子方式向客戶發送普通發票。

### <a name="add-a-new-invoice"></a>新增新發票

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 在 **普通發票** 頁面，選取 **新建**。
3. 在 **普通發票抬頭** FastTab，在 **客戶帳戶** 欄位，選取 **DE-014**。
4. 在 **發票明細** FastTab，自動新增發票明細。 在此行中設定以下欄位：

    - 在 **描述** 欄位中輸入 **Notebook**。
    - 在 **主科目** 欄位中選取 **401100**。
    - 在 **單價** 欄位中，輸入 **1000**。

5. 選取 **儲存**。

![普通發票頁面。](./media/er-quick-start3-add-invoice.png)

如需相關資訊，請參閱[建立普通發票](../../../finance/accounts-receivable/create-free-text-invoice-new.md)。

### <a name="post-a-new-invoice"></a>過帳新發票

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 在 **普通發票** 頁面，在動作窗格上，選取 **過帳**。
3. 在 **過帳普通發票** 對話方塊，選取 **確定**。

![普通發票詳情頁面。](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>發送已過帳發票

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 在 **普通發票** 頁面，在動作窗格上，在 **文件** 組，選取 **發送**\>**原始**。

    ![原始發票的預覽。](./media/er-quick-start3-send-invoice.png)

3. 關閉 **普通發票** 頁。

### <a name="analyze-a-generated-e-invoice"></a>分析產生的電子發票

1. 進入 **組織管理**\>**電子報表**\>**電子報表作業**。
2. 在 **電子報表作業** 頁面上，選取具有工作描述 **發送電子發票 XML** 的初始記錄。
3. 選取 **顯示檔案** 存取產生的檔案清單。

    ![電子報表作業頁面。](./media/er-quick-start3-jobs-list.png)

4. 選取 **開啟** 下載產生的電子發票 XML 檔案。
5. 分析電子發票 XML 檔案。 請注意，客戶稅務模式現行由 **schemeID** 和 **schemeAgencyID** XML 屬性表示。 另請注意，**cbc:CustomizationID** XML 元素現行包含以下文字：`urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`。

    ![產生的電子發票 XML 檔案的預覽。](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>新增自訂資料庫欄位

您可以使用[自訂欄位](../../fin-ops/get-started/user-defined-fields.md)功能在現行 Finance 執行個體中進行以下自訂：

- 透過新增一個新的自訂資料庫欄位來自訂資料庫結構，該欄位儲存每個客戶的聯邦稅識別碼。
- 透過新增可用於在新的自訂資料庫欄位中輸入稅碼值的新資料輸入欄位來自訂 **客戶** 頁面。

請按照以下步驟進行自訂。

1. 進入 **應收帳款**\>**客戶**\>**所有客戶**。
2. 在 **所有客戶** 頁面，選取 **DE-014** 客戶帳戶連結。
3. 在 **一般** FastTab 上，按右鍵點選 **語言** 欄位下的任何空白區域，然後選取 **個人化：UpperGroup**。

    強調顯示 **一般** FastTab 的內容，並出現 **個人化** 選單。

4. 在 **個人化** 選單，選取 **新增欄位**。
5. 在 **新增資料欄** 對話方塊，選取 **建立新欄位**。
6. 在 **建立新欄位** 對話方塊，在 **資料表名稱** 欄位，選取 **客戶**。
7. 在 **名稱首碼** 欄位中，輸入 **FederalTaxID**。

    > [!NOTE]
    > 整個欄位名稱已自動定義為 **FederalTaxID\_Custom**。

8. 在 **標籤** 欄位，輸入 **Federal Tax ID**。
9. 在 **類型** 欄位中，選取 **文字**。
10. 在 **長度** 欄位中，輸入 **20**。
11. 選取 **儲存**。
12. 在出現的訊息方塊中，選取 **是** 以確認您要為 **客戶** 表建立新的 **FederalTaxID** 欄位分錄。
13. 選取 **插入** 將 <a name="insert_custom_field"></a>**FederalTaxID\_Custom** 欄位新增到現行頁面。

    ![所有客戶頁面。](./media/er-quick-start3-create-new-field.gif)

14. 關閉 **所有客戶** 頁。

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>重新整理 ER 中繼資料

您必須重新整理 ER 中繼資料以使您新增的自訂欄位在 ER 模型對應設計工具中[顯示](electronic-reporting-er-configure-parameters.md#frequently-asked-questions)。

1. 進入 **組織管理**\>**電子報表**\>**重建資料表參考**。
2. 在 **更新資料模型** 對話方塊，選取 **好**。

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>設計自訂 ER 設定

您可以使用 Microsoft 提供的 ER 設定來設計您的自訂 ER 設定，以便它們產生包含新稅碼的電子發票。

### <a name="customize-the-data-model-configuration"></a>自訂資料模型設定

作為電子報表功能顧問角色的使用者，您可以設計您的自訂 ER 資料模型。

#### <a name="add-a-custom-data-model-configuration"></a>新增自訂資料模型設定

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **客戶發票模型**。
3. 在動作窗格上，選取 **建立設定**。
4. 在下拉式對話方塊中，在 **新建** 欄位，選取 **名稱來源：客戶發票模型，Microsoft** 指示您的新自訂 ER 資料模型設定應基於 ER 資料模型設定。
5. 在 **名稱** 欄位中，輸入 **Invoice model (Litware)**。
6. 選取 **建立設定** 以新增新的 ER 設定。

您現在可以使用 ER 資料模型設計工具來編輯處於 **草稿**[狀態](general-electronic-reporting.md#component-versioning)的 **發票模型 (Litware)** ER 設定的 50.1 版本。

![設定頁面上的 ER 設定版本 50.1。](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>設定自訂資料模型

您必須透過新增一個新欄位來修改您的自訂資料模型以提供聯邦稅識別碼的值。 此代碼是將使用此資料模型作為資料來源的每種 ER 格式的客戶資料的一部分。

1. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，選取 **發票模型 (Litware)**。
2. 在 **版本** FastTab 上，選取處於 **草稿** 狀態的所選 ER 資料模型設定的版本 **50.1**。
3. 在動作窗格上，為選定的設定版本選取 **設計師**。
4. 在 **資料模型設計師** 頁面，在資料模型樹狀結構中，選取 **客戶資訊 (客戶)**。
5. 選取 **新增**。
6. 在下拉式對話方塊中，在 **新節點作為** 欄位，接受預設值，**有效節點的子節點**。
7. 在 **名稱** 欄位中，輸入 **FederalTaxID\_Litware**。
8. 在 **項目類型** 欄位，接受預設值，**字串**。
9. 選取 **新增**，然後選取 **儲存**。

    ![資料模型設計工具頁面。](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > **標籤** 和 **描述** 欄位描述了新欄位的用途。 您可以用多種語言填入這些欄位。 如需相關資訊，請參閱[在電子報表中設計多語言報表](er-design-multilingual-reports.md)。

10. 關上 **資料模型設計工具** 頁面。

#### <a name="complete-a-custom-data-model-configuration"></a>完成自訂資料模型設定

您必須使用自訂 ER 資料模型設定的 50.1 版[完成](general-electronic-reporting.md#component-versioning)您的工作，以使其可用，以便可以新增其他自訂 ER 設定。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **發票模型**，然後選取 **發票模型 (Litware)**。
3. 在 **版本** FastTab 上，選取 **更改狀態**\>**完成**，然後選取 **好**。

50.1 版本的狀態由 **草稿** 變為 **已完成**，版本變為僅供讀取。 新增了一個新的可編輯版本 50.2，其狀態為 **草稿**。 您可以使用此版本對自訂 ER 資料模型設定進行進一步更改。

![版本 50.1 在設定頁面上完成。](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>自訂模型對應設定

作為電子報表開發人員角色的使用者，您可以設計您的自訂 ER 模型對應。

#### <a name="add-a-custom-model-mapping-configuration"></a>新增自訂模型對應設定

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **客戶發票模型**，然後選取 **客戶發票模型對應**。
3. 在動作窗格上，選取 **建立設定**。
4. 在下拉式對話方塊中，在 **新建** 欄位，選取 **名稱來源：客戶發票模型對應** 指示您的新自訂 ER 模型對應設定應基於 ER 模型對應設定。
5. 在 **名稱** 欄位中，輸入 **Invoice model mapping (Litware)**。
6. 在 **目標模型** 欄位，選取 **發票模型 (Litware)**。

    > [!IMPORTANT]
    > 這一步非常重要。 如果您省略它，您將無法在設定的模型對應中使用您的自訂資料模型。

7. 選取 **建立設定** 以新增新的 ER 設定。

![在設定頁面上新增自訂模型對應設定。](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>設定自訂模型對應

您必須修改自訂模型對應並指定自訂資料模型的自訂 **FederalTaxID\_Litware** 欄位應如何在執行階段使用應用程式資料填入。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **客戶發票模型**\>**客戶發票模型對應**，然後選取 **發票模型對應 (Litware)**。
3. 在動作窗格上，選取 **設計工具**。
4. 在 **對資料來源對應建模** 頁面上，選取 **客戶發票** 對應。

    ![模型到資料來源的對應頁面。](./media/er-quick-start3-select-customer-mapping.png)

5. 選取 **設計工具**。
6. 在 **模型對應設計工具** 頁，在 **資料來源** 窗格，展開 **CustInvoiceJour** 資料來源代表 **CustInvoiceJour** 申請表。
7. 在 **CustInvoiceJour** 下，展開 **關係** 以查看 **CustInvoiceJour** 表的多對一 (N:1) 類型的關係清單。
8. 在 **CustInvoiceJour**\>**關係** 下，展開 **客戶 (CustTable)** 以存取 **客戶 (CustTable)** 表的欄位和關係。
9. 選取您 [之前](#insert_custom_field)實作的 **FederalTaxID\_Custom** 資料來源欄位。
10. 在 **資料模型** 窗格，展開 **客戶資訊 (客戶)**，並選取 **FederalTaxID\_Litware** 資料模型欄位。
11. 選取 **繫結**。

    ![模型對應設計工具頁面。](./media/er-quick-start3-customize-model-mapping.gif)

12. 選取 **儲存**。
13. 關上 **模型對應設計工具** 頁面。
14. 關閉 **資料來源對應的模型** 頁面。

#### <a name="complete-a-custom-model-mapping-configuration"></a>完成自訂模型對應設定

您必須使用自訂 ER 模型對應設定的 50.19.1 版本[完成](general-electronic-reporting.md#component-versioning)您的工作，以使其可供使用。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **客戶發票模型**\>**客戶發票模型對應**，然後選取 **發票模型對應 (Litware)**。
3. 在 **版本** FastTab 上，選取 **更改狀態**\>**完成**，然後選取 **好**。

50.19.1 版本的狀態由 **草稿** 變為 **已完成**，版本變為僅供讀取。 新增了一個新的可編輯版本 50.19.2，其狀態為 **草稿**。 您可以使用此版本對自訂 ER 模型對應設定進行進一步更改。

![版本 50.19.1 在設定頁面上完成。](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> 支援的設定[生命週期](general-electronic-reporting-manage-configuration-lifecycle.md)不包括資料庫更改的生命週期。 如果您從現行 Finance 執行個體匯出 **發票模型對應 (Litware)** 設定的 50.19.1 版本，並嘗試將其匯入另一個執行個體，該執行個體不包含 **CustTable** 表中的自訂 **FederalTaxID\_Custom** 欄位 ，就會發生異常。 異常將聲明匯入的 ER 設定與目標 Finance 執行個體的中繼資料不相容。

### <a name="customize-the-format-configuration"></a>自訂格式設定

作為電子報表功能顧問角色的使用者，您可以設計您的自訂 ER 格式。

#### <a name="add-a-custom-format-configuration"></a>新增自訂格式設定

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在左側窗格的設定樹狀結構中，展開 **客戶發票模型**\>**UBL 銷售發票**，然後選取 **Peppol 銷售發票**。
3. 在動作窗格上，選取 **建立設定**。
4. 在下拉式對話方塊中，在 **新建** 欄位，選取 **名稱來源：Peppol 銷售發票，Microsoft** 指示您的自訂 ER 格式設定應基於 ER 格式設定。
5. 在 **名稱** 欄位中，輸入 **Peppol Sales Invoice (Litware)**。
6. 在 **資料模型** 欄位，選取 **發票模型 (Litware)** 使用您的自訂資料模型和模型對應組件。

    > [!NOTE]
    > 這一步非常重要。 如果您省略它，您將無法在設定的格式中使用您的自訂資料模型。

7. 在 **資料模型** 欄位，選取 **InvoiceCustomer** 根定義。
8. 選取 **建立設定** 以新增新的 ER 設定。

![在設定頁面上新增自訂格式設定。](./media/er-quick-start3-adding-custom-format.png)

您現在可以使用 ER Operations 設計工具來編輯處於 **草稿**[狀態](general-electronic-reporting.md#component-versioning)的 **Peppol 銷售發票 (Litware)** ER 設定的 11.2.2.1 版本。

![設定頁面上的 ER 設定版本 11.2.2.1。](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>設定自訂格式

您必須透過新增新格式元素來修改您的自訂格式，以填入已開票客戶的聯邦稅務識別碼的值。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在左側窗格的設定樹狀結構中，展開 **客戶發票模型**\>**UBL 銷售發票**\>**Peppol 銷售發票**，然後選取 **Peppol 銷售發票 (Litware)**。
3. 在動作窗格上，選取 **設計工具**。
4. 在格式樹狀結構中，展開 **XMLHeader** \> **Invoice** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme**，然後選取 **cbc:ID**。
5. 選取 **新增**，然後選取 **XML**\>**屬性**。
6. 在下拉式 **組件屬性** 對話方塊中，在 **名稱** 欄位中，輸入 **FederalTaxID**。
7. 選取 **確定** 以新增新格式元素以在產生的 XML 檔案中建立新的 **FederalTaxID** XML 屬性。
8. 在格式樹狀結構，在 **XMLHeader** \> **Invoice** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID** 下，選取 **FederalTaxID**。
9. 選取 **上移**。

![格式設計工具頁面上的新格式元素。](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>設定自訂格式對應

1. 在 **格式設計工具** 頁面上，在 **對應** 索引標籤上，展開 **模型** 類型的 **發票** 資料來源。
2. 在 **發票** 下，展開 **客戶資訊 (客戶)**，並選取 **FederalTaxID\_Litware**。
3. 選取 **繫結**。

    ![格式設計工具頁面。](./media/er-quick-start3-customized-format-mapping.png)

4. 選取 **模型** 類型的 **發票** 資料來源，然後選取 **編輯**。
5. 在 **版本** 欄位中，選取您的自訂資料模型的版本 **1**，然後選取 **確定**。
6. 選取 **儲存**。
7. 關上 **格式設計工具** 頁面。

#### <a name="complete-a-custom-format-configuration"></a>完成自訂格式設定

您必須使用自訂 ER 格式設定的 11.2.2.1 版本[完成](general-electronic-reporting.md#component-versioning)您的工作，以使其可供使用。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在左側窗格的設定樹狀結構中，展開 **客戶發票模型**\>**UBL 銷售發票**\>**Peppol 銷售發票**，然後選取 **Peppol 銷售發票 (Litware)**。
3. 在 **版本** FastTab 上，選取 **更改狀態**\>**完成**，然後選取 **好**。

11.2.2.1 版本的狀態由 **草稿** 變為 **已完成**，版本變為僅供讀取。 新增了一個新的可編輯版本 11.2.2.2，其狀態為 **草稿**。 您可以使用此版本對自訂 ER 格式設定進行進一步更改。

![版本 11.2.2.1 在設定頁面上完成。](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>設定應收帳款參數以開始使用自訂 ER 設定

1. 進入 **應收帳款**\>**設定**\>**應收帳款參數**。
2. 在 **電子檔案** 索引標籤，在 **電子報表** FastTab，在 **銷售和普通發票** 欄位，選取 **Peppol 銷售發票 (Litware)**。
3. 選取 **儲存**。

![應收帳款參數頁面、電子文件索引標籤、電子報表 FastTab。](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>透過新增聯邦稅務識別碼來更新客戶記錄

1. 進入 **應收帳款**\>**客戶**\>**所有客戶**。
2. 在 **所有客戶** 頁面，選取 **DE-014** 客戶帳戶連結。
3. 在 **一般** FastTab，在 **聯邦稅號** 欄位，輸入 **LITWARE-6789**。
4. 選取 **儲存**。

    ![DE-014 客戶詳情頁面。](./media/er-quick-start3-added-tax-id-value.png)

5. 關閉 **所有客戶** 頁。

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>使用自訂 ER 設定處理客戶發票

### <a name="select-and-send-a-posted-invoice"></a>選取並發送已過帳的發票

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 在 **普通發票** 頁面，選取您之前新增和過帳的發票。
3. 在動作窗格上，在 **文件** 分組，選取 **發送**\>**原始**。
4. 關閉 **普通發票** 頁。

### <a name="analyze-a-generated-e-invoice"></a>分析產生的電子發票

1. 進入 **組織管理**\>**電子報表**\>**電子報表作業**。
2. 在 **電子報表作業** 頁面上，選取具有工作描述 **發送電子發票 XML** 的最新記錄。
3. 選取 **顯示檔案** 存取產生的檔案清單。
4. 選取 **開啟** 下載產生的電子發票 XML 檔案。
5. 分析電子發票 XML 檔案。 請注意，根據您的自訂，除了 **schemeID** 和 **schemeAgencyID** XML 屬性之外，客戶稅務架構還包括自訂 **FederalTaxID** XML 屬性。 這個新 XML 屬性的值由為開票客戶輸入的 **LITWARE-6789** 聯邦稅號指定。

    ![使用您的自訂預覽產生的電子發票 XML 檔案。](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>匯入標準 ER 設定的最新版本

若要使 Finance 執行個體中的一組標準 ER 設定保持[最新](general-electronic-reporting-manage-configuration-lifecycle.md)，您必須在為該執行個體設定的 ER [存放庫](general-electronic-reporting.md#Repository)中可用時匯入它們的新版本。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定提供者** 區塊，選取 **Microsoft** 圖格，然後選取 **存放庫**，查看 Microsoft 提供者的存放庫清單。
3. 在 **設定存放庫** 頁面，選取 **全域** 類型的存放庫，然後選取 **開啟**。 如果提示您需要授權才能連線到 Regulatory Configuration Service，請遵循授權指示。
4. 在 **設定存放庫** 頁面上，在左側窗格的設定樹狀結構中，選取 **Peppol 銷售發票** 格式設定。
5. 在 **版本** FastTab 上，選取已發佈以支援 PEPPOL BIS 3 格式的客戶電子發票的所選 ER 格式設定的版本 **32.6.7**。 如需相關資訊，請參閱[KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic)。
6. 選取 **匯入** 將所選版本從全域存放庫下載到現行 Finance 執行個體。

![在設定存放庫頁面上選取了版本 32.6.7。](./media/er-quick-start3-import-solution2.png)

如需如何自動化此過程的相關資訊，請參閱[匯入 ER 設定的更新版本](er-download-updated-versions-global-repo.md)。

### <a name="review-the-imported-er-configurations"></a>查看匯入的 ER 設定

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定** 區塊中，選取 **報表設定** 圖格。
3. 展開 **設定組件** FastTab。
4. 在左側窗格的設定樹狀結構中，展開 **發票模型**。 請注意，在匯入的 ER 資料模型設定之一中，**客戶發票模型** 的名稱已更改為 **發票模型**。
5. 在左側窗格的設定樹狀結構中，展開 **發票模型對應**。 請注意，在匯入的 ER 模型對應設定之一中，**客戶發票模型對應** 的名稱已更改為 **發票模型對應**。
6. 展開 **UBL 銷售發票**\>**Peppol 銷售發票**。

請注意，除了選定的 **Peppol 銷售發票** ER 格式之外，匯入了其他所需 ER 設定的最新版本。 由於 ER 設定的新版本不斷發佈到全局存放庫和 LCS 以使相應的 ER 解決方案符合新的要求，因此匯入了所需資料模型設定及其模型對應設定的最新版本。

確保以下 ER 設定最終在設定樹狀結構中可用：

- **發票模型** ER 資料模型設定：

    - 版本 206 (或更新) 包含版本 24 (或更新) 的資料模型 ER 組件，它表示開票業務領域的資料結構。 此 ER 設定已作為最新可用 **發票模型對應** ER 模型對應設定的祖先匯入。

    ![在設定頁面上的版本 206。](./media/er-quick-start3-imported-solution2b1.png)

- **發票模型對應** ER 模型對應設定：

    - 版本 206.132 (或更新) 已作為 **發票模型** ER 資料模型設定的版本 206 的最新實作匯入。 它包含幾個模型對應 ER 組件，用於描述如何在執行階段用應用程式資料填入資料模型。

    ![在設定頁面上的版本 206.132。](./media/er-quick-start3-imported-solution2b2.png)

- **UBL 銷售發票** ER 格式設定：

    - 版本 32.6 包含格式和格式對應 ER 組件。 格式組件指定報表配置。 格式對應組件包含模型資料來源，並指定如何使用此資料來源在執行階段填入報表配置。 此 ER 格式設定為產生 UBL 格式的電子發票。 它已作為選取匯入的 **Peppol 銷售發票** ER 格式的父系匯入。

- **Peppol 銷售發票** ER 格式設定：

    - 版本 32.6.7 包含格式和格式對應 ER 組件，這些組件被設定為產生 PEPPOL 格式的電子發票。

    ![在設定頁面上的版本 32.6.7。](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>在您的自訂 ER 設定中採用對新標準 ER 設定的更改

### <a name="adopt-your-custom-er-data-model"></a>採用您的自訂 ER 資料模型

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **發票模型**，然後選取 **發票模型 (Litware)**。
3. 在 **版本** FastTab 上，對於所選資料模型設定的草稿版本 **50.2**，選取 **重訂基底**。
4. 在 **目標版本** 欄位中，確認選取基本 ER 資料模型設定的版本 **206**，然後選取 **確定**。

    您的自訂 ER 資料模型設定的草稿版本從 **50.2** 重新編號為 **206.2**，以表明它現在包含與基本 ER 資料模型設定的最新版本 (206) 中的更改合併的自訂。

    > [!NOTE]
    > 重訂基底動作是可逆的。 若要取消此重訂基底，請在 **版本** FastTab 上選取版本 **50.1** 的 **發票模型 (Litware)** 模型，然後選取 **取得此版本**。 206.2 版本將重新編號回 **50.2**，50.2 版本草稿內容與 50.1 版本內容一致。

5. 在 **版本** FastTab 上，選取 **更改狀態**\>**完成**，然後選取 **好**。

206.2 版本的狀態由 **草稿** 變為 **已完成**，版本變為僅供讀取。 新增了一個新的可編輯版本 206.3，其狀態為 **草稿**。 您可以使用此版本對自訂 ER 資料模型設定進行進一步更改。

![版本 206.2 在設定頁面上完成。](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>採用您的自訂 ER 模型對應

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **發票模型**\>**發票模型對應**，然後選取 **發票模型對應 (Litware)**。
3. 在 **版本** FastTab 上，對於所選模型對應設定的草稿版本 **50.19.2**，選取 **重訂基底**。
4. 在 **目標版本** 欄位中，確認選取基本 ER 模型對應設定的版本 **206.132**，然後選取 **確定**。

    您的自訂 ER 模型對應設定的草稿版本從 **50.19.2** 重新編號為 **206.132.2**，以表明它現在包含與基本 ER 模型對應設定的最新版本 (206.132) 中的更改合併的自訂。

    請注意，發現了一些重訂基底衝突。 您現在必須手動解決這些衝突。

    ![設定頁面上的重訂基底衝突訊息。](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. 在動作窗格上，選取 **設計工具**，然後在對應清單中選取 **客戶發票**。
6. 對於每個變基衝突，請選取 **保留自己的值**，因為您必須為已提及的每個組件保留自訂資料模型的版本編號。

    ![模型對應設計工具頁面上的重訂基底衝突。](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. 選取 **儲存**，然後關閉 **模型對應設計工具** 頁面。
8. 在對應清單中，選取 **專案發票**。
9. 對於每個變基衝突，請選取 **保留自己的值**，因為您必須為已提及的每個組件保留自訂資料模型的版本編號。
10. 選取 **儲存**，然後關閉 **模型對應** 頁面。

    > [!NOTE]
    > 重訂基底動作是可逆的。 若要取消此重訂基底，請在 **版本** FastTab 上選取版本 **50.19.1** 的 **發票模型對應 (Litware)** 模型對應，然後選取 **取得此版本**。 版本 206.132.2 將重新編號回 50.19.2，草稿版本 **50.19.2** 的內容將匹配版本 50.19.1 的內容。

11. 在 **版本** FastTab 上，選取 **更改狀態**\>**完成**，然後選取 **好**。

206.132.2 版本的狀態由 **草稿** 變為 **已完成**，版本變為僅供讀取。 新增了一個新的可編輯版本 206.132.3，其狀態為 **草稿**。 您可以使用此版本對自訂 ER 模型對應設定進行進一步更改。

![版本 206.132.2 在設定頁面上完成。](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>採用您的自訂 ER 格式

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在左側窗格的設定樹狀結構中，展開 **發票模型**\>**UBL 銷售發票**\>**Peppol 銷售發票**，然後選取 **Peppol 銷售發票 (Litware)**。
3. 在 **版本** FastTab 上，對於所選格式設定的草稿版本 **11.2.2.2**，選取 **重訂基底**。
4. 在 **目標** 版本欄位中，確認選取基本 ER 格式設定的版本 **32.6.7**，然後選取 **確定**。

    您的自訂 ER 格式設定的草稿版本從 **11.2.2.2** 重新編號為 **32.6.7.2**，以表明它現在包含與基本 ER 格式設定的最新版本 (32.6.7) 中的更改合併的自訂。

    請注意，發現了一些重訂基底衝突。 您現在必須手動解決這些衝突。

5. 在動作窗格上，選取 **設計工具**。
6. 對於每個變基衝突，請選取 **保留自己的值**，因為您必須為已提及的每個組件保留自訂資料模型的版本編號。
7. 選取 **儲存**。
8. 在 **對應** 索引標籤上，選取 **模型** 類型的 **發票** 資料來源，然後選取 **編輯**。
9. 在 **版本** 欄位中，選取您的自訂資料模型的版本 **2**，然後選取 **確定**。
10. 選取 **儲存**。

    > [!NOTE]
    > 重訂基底動作是可逆的。 若要取消此重訂基底，請在 **版本** FastTab 上選取版本 **11.2.2.1** 的 **Peppol 銷售發票 (Litware)** 格式，然後選取 **取得此版本**。 版本 32.6.7.2 將重新編號回 11.2.2.2，草稿版本 **11.2.2.2** 的內容將匹配版本 11.2.2.1 的內容。

11. 關上 **格式設計工具** 頁面。
12. 在 **版本** FastTab 上，選取 **更改狀態**\>**完成**，然後選取 **好**。

32.6.7.2 版本的狀態由 **草稿** 變為 **已完成**，版本變為僅供讀取。 新增了一個新的可編輯版本 32.6.7.3，其狀態為 **草稿**。 您可以使用此版本對自訂 ER 格式設定進行進一步更改。

![版本 32.6.7.2 在設定頁面上完成。](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>使用新版本的自訂 ER 設定處理客戶發票

### <a name="select-and-send-a-posted-invoice"></a>選取並發送已過帳的發票

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 在 **普通發票** 頁面，選取您之前新增和過帳的發票。
3. 在動作窗格上，在 **文件** 分組，選取 **發送**\>**原始**。

    > [!NOTE] 
    > 因為您現在有兩個版本的 **Peppol 銷售發票 (Litware)** ER 格式設定，並且兩個版本都沒有[有效日期](general-electronic-reporting.md#component-date-effectivity)值，所以最新版本用於產生電子發票。

4. 關閉 **普通發票** 頁。

### <a name="analyze-a-generated-e-invoice"></a>分析產生的電子發票

1. 進入 **組織管理**\>**電子報表**\>**電子報表作業**。
2. 在 **電子報表作業** 頁面上，選取具有工作描述 **發送電子發票 XML** 的最近記錄。
3. 選取 **顯示檔案** 存取產生的檔案清單。
4. 選取 **開啟** 下載產生的電子發票 XML 檔案。
5. 分析電子發票 XML 檔案。 請注意，根據您的自訂，除了 **schemeID** 和 **schemeAgencyID** XML 屬性之外，客戶稅務架構還包括自訂 **FederalTaxID** XML 屬性。 此外，由於新版本的基本 **UBL 銷售發票** 格式的更改已與您的自訂合併，因此 **cbc:CustomizationID** XML 元素的文字已從 `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0` 到 `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0`。

    ![使用自訂預覽產生的電子發票 XML 檔案。](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>其他資源

- [電子報表概觀](general-electronic-reporting.md)
- [從 Lifecycle Services 下載 ER 設定](download-electronic-reporting-configuration-lcs.md)
- [從設定服務的全域存放庫下載 ER 設定](er-download-configurations-global-repo.md)
- [建立普通發票](../../../finance/accounts-receivable/create-free-text-invoice-new.md)
- [建立和搭配自訂欄位](../../fin-ops/get-started/user-defined-fields.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
