---
title: 調整 ER 格式以產生自訂電子文件
description: 本主題說明如何調整 Microsoft 提供的電子報表 (ER) 格式，以便產生自訂電子文件。
author: NickSelin
ms.date: 06/22/2020
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
ms.openlocfilehash: 14976aab474b6571c2a25907f04fd4d7ae053e74
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460222"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>調整 ER 格式以產生自訂電子文件

[!include[banner](../includes/banner.md)]

本主題中的過程說明了系統管理員或電子報表函數顧問角色的使用者如何執行這些工作：

- [電子報表 (ER) 架構](general-electronic-reporting.md)的設定參數。
- 匯入 Microsoft 提供的 ER 設定，用於在處理[廠商付款](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md)時產生付款檔案。
- 建立由 Microsoft 提供的標準 ER 格式設定的自訂版本。
- 修改自訂 ER 格式設定，使其產生滿足特定銀行要求的付款檔案。
- 在自訂 ER 格式設定中採用對標準 ER 格式設定所做的更改。

以下所有程序都可以在 **GBSI** 公司完成。 無需編碼。

- [設定 ER 架構](#ConfigureFramework)

    - [設定 ER 參數](#ConfigureParameters)
    - [啟用 ER 設定提供者](#ActivateProvider)

        - [查看 ER 設定提供者清單](#ReviewProvidersList)
        - [新增新的 ER 設定提供者](#ActivateProvider)
        - [啟用 ER 設定提供者](#ActivateAddedProvider)

- [匯入標準 ER 格式設定](#ImportERSolution1)

    - [匯入標準 ER 設定](#ImportERFormat1)
    - [查看匯入的 ER 設定](#ReviewImportedERSolution)

- [準備廠商付款以進行處理](#PrepareVendorPayment)

    - [為廠商帳戶新增銀行資訊](#AddBankAccount)
    - [輸入廠商付款](#EnterVendorPayment)

- [使用標準 ER 格式處理廠商付款](#ProcessVendorPayment1)

    - [設定電子付款方式](#ConfigureMethodOfPayment1)
    - [處理廠商付款](#ProcessPayment1)

- [自訂標準 ER 格式](#CustomizeProvidedFormat)

    - [建立自訂格式](#DeriveProvidedFormat)
    - [編輯自訂格式](#ConfigureDerivedFormat)
    - [將自訂格式標記為可執行](#MarkFormatRunnable)

- [使用自訂 ER 格式處理廠商付款](#ProcessVendorPayment2)

    - [設定電子付款方式](#ConfigureMethodOfPayment2)
    - [處理廠商付款](#ProcessPayment2)

- [匯入標準 ER 格式設定的新版本](#ImportERSolution2)

    - [匯入標準 ER 設定的新版本](#ImportERFormat2)
    - [查看匯入的 ER 格式設定](#ReviewImportedERFormat)

- [在自訂格式中採用匯入格式的新版本中的更改](#AdoptNewBaseVersion)

    - [完成自訂格式的現行草稿版本](#CompleteDerivedFormat)
    - [將自訂格式重新設定為新的基本版本](#RebaseDerivedFormat)
    - [使用重訂基底 ER 格式處理廠商付款](#ProcessPayment3)

- [其他資源](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>設定 ER 架構

作為電子報表函數顧問角色的使用者，您必須先設定最少的 ER 參數集，然後才能開始使用 ER 架構來設計標準 ER 格式的自訂版本。

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>設定 ER 參數

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **電子報表參數**。
3. 在 **電子報表參數** 頁的 **一般** 索引標籤上，將 **啟用設計模式** 選項設定為 **是**。
4. 在 **附件** 索引標籤上設定下列參數：

    - 在 **設定** 欄位中，選取 **檔案** 類型為 **USMF** 公司。
    - 在 **作業封存**、**臨時**、**基準** 和 **其他** 欄位中，選取 **檔案** 類型。

如需 ER 參數的相關資訊，請參閱[設定 ER 架構](electronic-reporting-er-configure-parameters.md)。

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>啟用 ER 設定提供者

新增的每個 ER 設定都被標記為歸 ER 設定提供者所有。 在 **電子報表** 工作區中啟用的 ER 設定提供者用於此目的。 因此，您必須先在 **電子報表** 工作區中啟用 ER 設定提供者，然後才能開始新增或編輯 ER 設定。

> [!NOTE]
> 只有 ER 設定的所有者可以對其進行編輯。 因此，在可以編輯 ER 設定之前，必須在 **電子報表** 工作區中啟動相應的 ER 設定提供者。

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>查看 ER 設定提供者清單

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **設定提供者**。
3. 在 **設定提供者資料表** 頁面，每個設定提供者記錄都有一個唯一的名稱和 URL。 查看此頁面的內容。 如果 **Litware, Inc.** (`https://www.litware.com`) 的記錄已存在，請跳過下一個程序[新增新的 ER 設定提供者](#ActivateProvider)。

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>新增新的 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **相關連結** 區段中，選取 **設定提供者**。
3. 在 **設定提供者** 頁面上，選取 **新建**。
4. 在 **名稱** 欄位中，輸入 **Litware, Inc.**
5. 在 **網址** 欄位，輸入 `https://www.litware.com`。
6. 選取 **儲存**。

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>啟用 ER 設定提供者

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定提供者** 部分中，選取 **Litware, Inc.** 圖格，然後選取 **設定為有效狀態**。

如需 ER 設定提供者的相關資訊，請參閱[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)。

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>匯入標準 ER 格式設定

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>匯入標準 ER 設定

若要將標準 ER 設定新增到您現行的 Microsoft Dynamics 365 Finance 執行個體，您必須從為該執行個體設定的 ER [存放庫](general-electronic-reporting.md#Repository)匯入它們。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定提供者** 區塊，選取 **Microsoft** 圖格，然後選取 **存放庫**，查看 Microsoft 提供者的存放庫清單。
3. 在 **設定存放庫** 頁面，選取 **全域** 類型的存放庫，然後選取 **開啟**。 如果提示您需要授權才能連線到 Regulatory Configuration Service，請遵循授權指示。
4. 在 **設定存放庫** 頁面上，在左側窗格的設定樹狀結構中，選取 **BACS (UK)** 格式設定。
5. 在 **版本** FastTab 上，選取所選 ER 格式設定的版本 **1.1**。
6. 選取 **匯入** 將所選版本從全域存放庫下載到現行 Finance 執行個體。

![設定存放庫頁面。](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> 如果您在存取[全域存放庫](er-download-configurations-global-repo.md)時遇到問題，可以改為從 Microsoft Dynamics Lifecycle Services (LCS) [下載設定](download-electronic-reporting-configuration-lcs.md)。

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>查看匯入的 ER 設定

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定** 區塊中，選取 **報表設定** 圖格。
3. 在 **設定** 頁面上，在左側窗格中的設定樹狀結構中，展開 **付款模型**。
4. 請注意，除了選定的 **BACS (UK)** ER 格式之外，還匯入了其他必需的 ER 設定。 確保以下 ER 設定可在設定樹狀結構中提供：

    - **付款模型** – 此設定包含資料模型 ER 組件，該組件表示付款業務領域的資料結構。
    - **付款模型對應 1611** – 此設定包含模型對應 ER 組件，該組件描述如何在執行階段用應用程式資料填入資料模型。
    - **BACS (UK)** – 此設定包含格式和格式對應 ER 組件。 格式組件指定報表配置。 格式對應組件包含模型資料來源，並指定如何在執行階段使用此資料來源填入報表配置。

![樹狀結構中可用之指定 ER 設定的設定頁面。](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>準備廠商付款以進行處理

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>為廠商帳戶新增銀行資訊

您必須為稍後將在註冊付款中參考的廠商帳戶新增銀行資訊。

1. 進入 **應付帳款**\>**廠商**\>**所有廠商**。
2. 在 **所有廠商** 頁面，選取 **GB_SI_000001** 廠商帳戶，然後在動作窗格中的 **廠商** 索引標籤上，在 **設定** 組中，選取 **銀行帳戶**。
3. 在 **廠商銀行賬戶** 頁面，選取 **新建**，然後輸入以下資訊：

    1. 在 **銀行帳戶** 欄位中，輸入 **GBP OPER**。
    2. 在 **銀行群組** 欄位，選取 **BankGBP**。
    3. 在 **銀行帳號** 欄位中，輸入 **202015**。
    4. 在 **SWIFT 代碼** 欄位中，輸入 <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**。
    5. 在 **IBAN** 欄位中，輸入 **GB33BUKB20201555555555**。
    6. 在 **路由序號** 欄位，保留預設值，<a id="DefineRoutingNumber"></a>**123456**。

    ![廠商銀行帳戶頁。](./media/er-quick-start2-bank-account.png)

4. 選取 **儲存**。
5. 關閉頁面。
6. 在 **所有廠商** 頁面，打開 **GB_SI_000001** 廠商帳戶。
7. 在廠商詳情頁面上，視需要選取 **編輯** 將頁面變成可編輯狀態。
8. 在 **付款** FastTab 上，在 **銀行賬戶** 欄位，選取 **GBP OPER**。

    ![廠商詳情頁](./media/er-quick-start2-bank-account-reference.png)

9. 選取 **儲存**。
10. 關閉頁面。

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>輸入廠商付款

您必須使用[付款建議](../../../finance/accounts-payable/create-vendor-payments-payment-proposal.md)輸入新的廠商付款。

1. 進入 **應收帳款**\>**付款**\>**廠商付款日記帳**。
2. 在 **廠商付款日記帳** 頁面，選取 **新建**。
3. 在 **名稱** 欄位，選取 **VendPay**。
4. 選取 **明細**。
5. 選取 **付款建議**\>**建立付款建議**。
6. 在 **廠商付款建** 議對話方塊中，設定條件以僅篩選 **GB_SI_000001** 廠商帳戶的記錄，然後選取 **確定**。
7. 選取 **00000007_Inv** 發票的明細，然後選取 **建立付款**。

    ![廠商付款建議對話方塊。](./media/er-quick-start2-payment-proposal.png)

8. 驗證輸入的付款是否設定為使用 **電子** 付款方式。

    ![廠商付款頁面。](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>使用標準 ER 格式處理廠商付款

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>設定電子付款方式

您必須設定電子付款方式，以便它使用匯入的 ER 格式設定。

1. 進入 **應付帳款**\>**付款安裝**\>**付款方式**。
2. 在 **付款方式 - 廠商** 頁面，選取左窗格中的 **電子** 付款方式。
3. 選取 **編輯**。
4. 在 **檔案格式** FastTab 上，將 **一般電子匯出格式** 設定選項為 **是**。
5. 在 **匯出格式設定** 欄位中，選取 **BACS (UK)** 格式設定。

    ![付款方式 - 廠商頁面設定電子付款方式以使用標準格式處理廠商付款。](./media/er-quick-start2-method-of-payment1.png)

6. 選取 **儲存**。

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>處理廠商付款

1. 進入 **應收帳款**\>**付款**\>**廠商付款日記帳**。
2. 在 **廠商付款日記帳** 頁面上，選取您之前新增的付款日記帳，然後選取 **明細**。
3. 在 **廠商付款** 頁面上，選取 **產生付款**。
4. 在 **產生付款** 對話方塊中，輸入以下資訊：

    - 在 **付款方式** 欄位中，選取 **電子**。
    - 在 **銀行帳戶** 欄位中，選取 **GBSI OPER**。

5. 選取 **確定**。
6. 在 **電子報表參數** 對話方塊，將 **列印控制報表** 選項設定為 **是**，然後選取 **確定**。

    ![電子報表參數對話頁。](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > 除了付款檔案，您現在還可以產生控制報表。

7. 下載 ZIP 檔案，然後從中擷取以下檔案：

    - Excel 格式的控制報表
    - TXT 格式的付款檔案

        請注意，根據提供的 ER 格式的[結構](#PositionRoutingNumber)，產生檔案中的付款明細以為設定的銀行帳戶[定義](#DefineRoutingNumber)的路由號碼開頭。

        ![TXT 格式的付款檔案。](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>自訂標準 ER 格式

對於本節中顯示的範例，您希望使用 Microsoft 提供的 ER 設定來產生 BACS 格式的廠商付款檔案，但您必須新增自訂項以支援特定銀行的要求。 您還希望能夠在新版本的 ER 設定可用時升級您的自訂格式。 但是，您希望能夠以最低的成本進行升級。

在這種情況下，作為 Litware, Inc. 的代表，您必須使用 **BACS (UK)** Microsoft 提供的設定作為基礎來建立 (衍生) 新的 ER 格式設定。

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>建立自訂格式

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **付款模型**，然後選取 **BACS (UK)**。 Litware, Inc. 將使用此 ER 格式設定的 1.1 版作為自訂版本的基礎。
3. 選取 **建立設定** 以打開下拉式對話方塊。 您可以使用此對話方塊為自訂付款格式建立新設定。
4. 在 **新建** 欄位組，選取 **名稱來源：BACS (UK)，Microsoft** 選項。
5. 在 **名稱** 欄位中，輸入 **BACS (UK custom)**。

    ![建立設定下拉式對話方塊。](./media/er-quick-start2-add-derived-format.png)

6. 選取 **建立設定**。

建立 **BACS (UK custom)** ER 格式設定的 1.1.1 版。 此版本的 [狀態](general-electronic-reporting.md#component-versioning)為 **草稿**，可以進行編輯。 您自訂 ER 格式的目前內容與 Microsoft 提供格式的內容相符。

![帶有 BACS (UK custom) ER 格式設定版本 1.1.1 的設定頁面。](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>編輯自訂格式

您必須設定您的自訂格式，使其滿足銀行特定的要求。 例如，銀行可能要求產生的付款檔案包括全球銀行金融電信 (SWIFT) 代碼，該銀行在已處理的廠商付款中被指定為代理角色。 SWIFT 代碼是識別全球特定銀行的國際銀行代碼。 它們也稱為銀行識別碼 (BIC)。 SWIFT 代碼的長度必須為 11 個字元，並且必須在產生的付款檔案中的每個付款明細的開頭輸入。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **付款模型**，然後選取 **BACS (UK custom)**。
3. 在 **版本** FastTab 上，選取所選設定的所需版本 **1.1.1**。
4. 選取 **設計工具**。
5. 在 **格式設計工具** 頁面，選取 **顯示詳情** 查看有關格式元素的更多資訊。
6. 展開並查看以下元素：

    - **資料夾** 類型的 **BACSReportsFolder** 元素。 此元素用於產生 ZIP 格式的輸出。
    - **檔案** 類型的 **檔案** 元素。 此元素用於產生 TXT 格式的付款檔案。
    - **序列** 類型的 **交易** 元素。 此元素用於在付款檔案中產生單個付款明細。
    - **序列** 類型的 **交易** 元素。 此元素用於產生單個付款明細的各個欄位。

7. 選取 **交易** 元素。

    ![ER Operations 設計工具中的交易元素。](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > 所提供的報表已設定為<a id="PositionRoutingNumber"></a>每條付款明細都以銀行路由號開頭。 **vendBankRouteNum** 格式元素主要用於此目的。 

8. 選取 **新增**，然後選取您要新增的格式元素的 **文字\\字串** 類型：

    1. 在 **名稱** 欄位中，輸入 **vendBankSWIFT**。
    2. 在 **最小長度** 欄位中，輸入 **11**。
    3. 在 **最大長度** 欄位中，輸入 **11**。
    4. 選取 **確定**。

    > [!NOTE]
    > **VendBankSWIFT** 元素將用於在產生的檔案中輸入廠商銀行的 SWIFT 代碼。

9. 在格式結構樹中，選取 **VendBankSWIFT**。
10. 選取 **上移** 將選定的格式元素上移一級。 重複此步驟，直到 **vendBankSWIFT** 元素成為 <a id="PositionSWIFTCode"></a>父 **交易** 元素下的第一個元素。

    ![VendBankSWIFT 作為 ER Operations 設計工具中交易的第一個元素。](./media/er-quick-start2-derived-format1.png)

11. 在格式結構樹中仍然選取 **vendBankSWIFT** 時，選取 **對應** 索引標籤，然後展開 **模型** 資料來源。
12. 展開 **model.Payment**\>**model.Payment.CreditorAgent**，並選取 **model.Payment.CreditorAgent.BICFI** 資料來源欄位。 此資料來源欄位公開在已處理的廠商付款中指派了代理角色的廠商銀行的 SWIFT 代碼。
13. 選取 **繫結**。 **vendBankSWIFT** 格式元素現在與 **model.Payment.CreditorAgent.BICFI** 資料來源欄位繫結，以便將 SWIFT 代碼輸入到產生的付款檔案中。

    ![vendBankSWIFT 格式元素與 ER Operations 設計工具中的 model.Payment.CreditorAgent.BICFI 資料來源欄位繫結。](./media/er-quick-start2-derived-format2.png)

14. 選取 **儲存**。
15. 關閉設計工具頁面。

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>將自訂格式標記為可執行

現在您的自訂格式的第一個版本已經建立並且狀態為 **草稿**，您可以執行它以進行測試。 若要執行報表，您必須使用參考您的自訂 ER 格式的付款方式處理廠商付款。 在預設情況下，當您從應用程式調用 ER 格式時，僅 [考慮](general-electronic-reporting.md#component-versioning)狀態為 **已完成** 或 **共用** 的版本。 此行為有助於防止使用具有未完成設計的 ER 格式。 但是，對於您的測試執行，您可以強制應用程式使用狀態為 **草稿** 的 ER 格式版本。 這樣，如果需要進行任何修改，您可以調整目前的格式版本。 如需相關資訊，請參閱[適用性](electronic-reporting-destinations.md#applicability)。

若要使用 ER 格式的草稿版本，您必須明確標記 ER 格式。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 在 **使用者參數** 對話方塊，將 **執行設定** 選項設定為 **是**，然後選取 **確定**。
4. 選取 **編輯** 根據需要使目前的頁面處於可編輯狀態。
5. 在左側窗格的設定樹狀結構中，選取 **BACS (UK custom)**。
6. 將 **執行草稿** 選項設定為 **是**。

    ![在設定頁面上執行草稿選項。](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>使用自訂 ER 格式處理廠商付款

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>設定電子付款方式

您必須設定電子付款方式，以便您的自訂 ER 格式用於處理廠商付款。

1. 進入 **應付帳款**\>**付款安裝**\>**付款方式**。
2. 在 **付款方式 - 廠商** 頁面，選取左窗格中的 **電子** 付款方式。
3. 選取 **編輯**。
4. 在 **檔案格式** FastTab 上，將 **一般電子匯出格式** 設定選項為 **是**。
5. 在 **匯出格式設定** 欄位中，選取 **BACS (UK custom)** 格式設定。

    ![付款方式 - 廠商頁面設定電子付款方式以使用自訂格式處理廠商付款。](./media/er-quick-start2-method-of-payment2.png)

6. 選取 **儲存**。

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>處理廠商付款

1. 進入 **應收帳款**\>**付款**\>**廠商付款日記帳**。
2. 在 **廠商付款日記帳** 頁面上，選取您之前建立的付款日記帳。
3. 選取 **明細**。
4. 在 **廠商付款** 頁面，在格線上方，選取 **付款狀態**\>**無**。
5. 選取 **產生付款**。
6. 在 **產生付款** 對話方塊中，輸入以下資訊：

    - 在 **付款方式** 欄位中，選取 **電子**。
    - 在 **銀行帳戶** 欄位中，選取 **GBSI OPER**。

7. 選取 **確定**。
8. 在 **電子報表參數** 對話方塊，將 **列印控制報表** 選項設定為 **是**，然後選取 **確定**。

    > [!NOTE]
    > 除了付款檔案，您只能產生控制報表。

9. 下載 ZIP 檔案，然後從中擷取以下檔案：

    - Excel 格式的控制報表
    - TXT 格式的付款檔案

        請注意，根據您的自訂 ER 格式的結構，產生檔案中的付款明細[現在](#PositionSWIFTCode)以為已處理付款的廠商的銀行帳戶[輸入](#DefineSWIFTCode)的 SWIFT 代碼開始。

        ![用於處理廠商付款的 TXT 格式的付款檔案。](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>匯入標準 ER 格式設定的新版本

對於本節中顯示的範例，您會收到有關知識庫文章[KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046)的通知。 此通知會告知您有關 Microsoft 已發佈的新版本 **BACS (UK)** ER 格式。 除了控制報表之外，這個新版本還允許使用者在處理廠商付款時產生付款通知報表和出席通知報表。 您想開始使用該函數。

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>匯入標準 ER 設定的新版本

若要將 ER 設定的新版本新增到目前的 Finance 執行個體，您必須從您設定的 ER [存放庫](general-electronic-reporting.md#Repository)中匯入它們。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面上，在 **設定提供者** 區塊，選取 **Microsoft** 圖格，然後選取 **存放庫**，查看 Microsoft 提供者的存放庫清單。
3. 在 **設定存放庫** 頁面，選取 **全域** 類型的存放庫，然後選取 **開啟**。 如果提示您需要授權才能連線到 Regulatory Configuration Service，請遵循授權指示。
4. 在 **設定存放庫** 頁面上，在左側窗格的設定樹狀結構中，選取 **BACS (UK)** 格式設定。
5. 在 **版本** FastTab 上，選取所選 ER 格式設定的版本 **3.3**。
6. 選取 **匯入** 將所選版本從全域存放庫下載到現行 Finance 執行個體。

![設定存放庫頁面、版本 FastTab、匯入按鈕。](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> 如果您無法存取[全域存放庫](er-download-configurations-global-repo.md)，則可以改為從 LCS [下載設定](download-electronic-reporting-configuration-lcs.md)。

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>查看匯入的 ER 格式設定

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定** 區塊中，選取 **報表設定** 圖格。
3. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **付款模型**，然後選取 **BACS (UK)**。
4. 在 **版本** FastTab 上，選取版型 **3.3**。
5. 選取 **設計工具**。
6. 在 **格式設計工具** 頁面上，展開 **BACSReportsFolder** 格式元素。
7.  請注意，版本 3.3 包含 **PaymentAdviceReport** 格式元素，用於在處理廠商付款時產生付款通知報表。

    ![ER Operations 設計工具中的 PaymentAdviceReport 格式元素。](./media/er-quick-start2-imported-solution2.png)

8. 關閉設計工具頁面。

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>在自訂格式中採用匯入格式的新版本中的更改

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>完成自訂格式的現行草稿版本

如果您想保持自訂格式的目前狀態，請將草稿版本 1.1.1 的狀態從 **草稿** 更改為 **已完成**。

1. 進入 **組織管理**\>**工作區**\>**電子報表**。
2. 在 **本地化設定** 頁面的 **設定** 區塊中，選取 **報表設定** 圖格。
3. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **付款模型**，展開 **BACS (UK)**，然後選取 **BACS (UK custom)**。
4. 在 **版本** FastTab 上，選取 **更改狀態**\>**完成**，然後選取 **好**。

1.1.1 版本的狀態由 **草稿** 變為 **已完成**，版本變為僅供讀取。 新增了一個新的可編輯版本 1.1.2，其狀態為 **草稿**。 您可以使用此版本對自訂 ER 格式進行進一步更改。

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>將自訂格式重新設定為新的基礎版本

若要開始在您的自訂中使用 **BACS (UK)** 格式 3.3 版的新函數，您必須更改自訂設定的基礎設定版本 **BACS (UK custom)**。 這個過程被稱為[重訂基底](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase)。 使用 3.3 版代替 **BACS (UK)** 的 1.1 版。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面的左側窗格的設定樹狀結構中，展開 **付款模型**，然後選取 **BACS (UK custom)**。
3. 在 **版本** FastTab 上，選取版本 **1.1.2**，然後選取 **重訂基底**。
4. 在 **重訂基底** 對話方塊的 **目標版本** 欄位中，選取基礎設定的 **3.3** 版本以將其應用為新的基礎設定並使用它來更新設定。

    ![重訂基底對話方塊。](./media/er-quick-start2-rebase1.png)

5. 選取 **確定**。
6. 請注意，草稿版本的編號已從 **1.1.2** 更改為 **3.3.2**，以反映基礎版本的更改。

    當自訂版本和新的基礎版本合併時，可能會因為無法自動合併的格式更改而發現一些衝突。

    ![設定頁面上存在衝突的重訂基底設定。](./media/er-quick-start2-rebase2.png)

    如果發現衝突，則必須在格式設計工具中手動解決。

7. 在 **版本** FastTab 上，選取版型 **3.3.2**。
8. 選取 **設計工具**。
9. 在 **格式設計工具** 頁的 **詳情** FastTab 上，選取一個重訂基底衝突記錄，然後選取 **套用基值**。

    ![ER Operations 設計工具中的重訂基底衝突記錄。](./media/er-quick-start2-rebase3.png)

10. 選取 **儲存**。

    重訂基底衝突記錄不應再出現在 **詳情** FastTab。

    ![在 ER Operations 設計工具中解決了衝突。](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > 您透過確認必須以這種 ER 格式使用基礎模型的版本 3 來解決衝突。

11. 展開 **BACSReportsFolder**\>**檔案**\>**交易**\>**交易**。
12. 在 **對應** 索引標籤上，請注意您的自訂 ER 格式的 3.3.2 版包含您的自訂 (**vendBankSWIFT** 格式元素及其繫結) 和 Microsoft 提供的基本 ER 格式 3.3 版的新函數 (**PaymentAdviceReport** 格式元素及其巢狀元素和設定的繫結)。 只需按幾下滑鼠，您就可以透過將新基礎版本的修改與您的自訂合併來採用它們。

    ![ER Operations 設計工具中的合併格式。](./media/er-quick-start2-rebase5.png)

13. 關閉設計工具頁面。

> [!NOTE]
> 重訂基底動作是可逆的。 若要取消此重訂基底，請在 **版本** FastTab 上選取版本 **1.1.1** 的 **BACS (UK custom)** 格式，然後選取 **取得此版本**。 3.3.2 版將被重新編號為 1.1.2，草稿 1.1.2 版的內容將與 1.1.1 版的內容相符。

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>使用重訂基底 ER 格式處理廠商付款

1. 進入 **應收帳款**\>**付款**\>**廠商付款日記帳**。
2. 在 **廠商付款日記帳** 頁面上，選取您之前建立的付款日記帳。
3. 選取 **明細**。
4. 在 **廠商付款** 頁面，在格線上方，選取 **付款狀態**\>**無**。
5. 選取 **產生付款**。
6. 在 **產生付款** 對話方塊中，輸入以下資訊：

    - 在 **付款方式** 欄位中，選取 **電子**。
    - 在 **銀行帳戶** 欄位中，選取 **GBSI OPER**。

7. 選取 **確定**。
8. 在 **電子報表參數** 對話方塊中，輸入以下資訊：

    - 將 **列印控制報表** 選項設為 **是**。
    - 將 **列印付款通知** 選項設為 **是**。

    ![電子報表參數對話方塊。](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > 除了付款檔案，您現在還可以產生控制報表和付款通知報表。

9. 選取 **確定**。
10. 下載 ZIP 檔案，然後從中擷取以下檔案：

    - Excel 格式的控制報表
    - Excel 格式的付款通知報表

        ![Excel 格式的付款通知報表。](./media/er-quick-start2-payment-advice-report.png)

    - TXT 格式的付款檔案

        請注意，產生檔案中的付款行以為已處理付款的廠商的銀行帳戶輸入的 SWIFT 代碼開頭。

        ![TXT 格式的付款檔案，用於使用重新設定的 ER 格式處理廠商付款。](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>其他資源

- [電子報表概觀](general-electronic-reporting.md)
- [從 Lifecycle Services 下載 ER 設定](download-electronic-reporting-configuration-lcs.md)
- [從設定服務的全域存放庫下載 ER 設定](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
