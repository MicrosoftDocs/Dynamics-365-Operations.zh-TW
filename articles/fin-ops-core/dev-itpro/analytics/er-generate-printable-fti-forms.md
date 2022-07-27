---
title: 產生可列印的 FTI 表格
description: 本主題說明如何使用電子報表 (ER) 架構將可列印的普通發票 (FTI) 表單產生為 Microsoft Office 文件。
author: NickSelin
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: be5e3ef0f6ecb3d8f911b5be5f8bc9102d201fd299425e847a2df233d9b4edf4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460223"
---
# <a name="generate-printable-fti-forms"></a>產生可列印的 FTI 表格

[!include[banner](../includes/banner.md)]

電子報表 (ER) 架構允許您產生可列印的普通發票 (FTI) 表單作為 Microsoft Office 文件。 本主題提供有關如何構建您自己的設定的資訊以及可用設定範本的詳情。

## <a name="overview"></a>概觀

除了使用 Microsoft SQL Server Reporting Services (SSRS) 產生可列印 FTI 表單的現有功能之外，您現在還可以使用 ER 架構。 您可以在 Microsoft Office Excel 和 Word 中管理可列印的 FTI 表格。 您還可以修改配置、資料流程和格式以滿足特定要求，而無需更改代碼。

> [!NOTE]
> 如果您想首先概述此可列印 FTI 表單解決方案範例的現有 ER 設定，您可以直接前往本主題後面的 **下載樣本 ER 設定以產生可列印 FTI 表單** 章節。

## <a name="create-customized-configurations-for-fti-printable-forms"></a>為 FTI 可列印表單建立自訂設定
作為可列印 FTI 表單的定制解決方案的一部分，您必須建立一組 ER 設定。

### <a name="configure-the-er-data-model"></a>設定 ER 資料模型
您的應用程式必須包含 ER 資料模型設定，其中包含描述客戶發票業務領域的資料模型。 作為要求，資料模型的名稱必須是 **CustomersInvoicing**。 如需如何設計 ER 資料模型的相關資訊，請參閱[ER 設計領域特定的資料模型](tasks/er-design-domain-specific-data-model-2016-11.md)。

### <a name="configure-the-er-model-mapping"></a>設定 ER 模型對應
您的應用程式必須包含 CustomersInvoicing 資料模型的 ER 模型對應。 模型對應可以在 ER 資料模型設定或 ER 模型對應設定中。 但是，模型對應的根描述符的名稱必須是 **FreeTextInvoice**。

對應必須包含以下資料來源：

- 資料來源類型：**資料表記錄**

    - 此資料來源必須命名為 **CustInvoiceJour**。
    - 它必須參考 CustInvoiceJour 申請表。
    - 它在執行階段用於從應用程式傳遞到對應已選取列印的發票清單的 ER 模型。

- 資料來源類型：**物件**

    - 此資料來源必須命名為 **PrintMgmtPrintSettingDetail**。
    - 它必須參考 **PrintMgmtPrintSettingDetail** 應用程式表。
    - 它在執行階段用於從應用程式傳遞到正在執行的 ER 格式的列印管理設定的 ER 模型對應詳情。

應用程式與 ER 架構整合的詳情可以在應用程式源代碼中的 **ERPrintMgmtReportFormatSubscriber** 類 (ER 應用程式套件整合模型) 中找到。

如需 ER 模型對應設計的相關資訊，請參閱[定義 ER 模型對應並為其選取資料來源](tasks/er-define-model-mapping-select-data-sources-2016-11.md)。

### <a name="configure-the-er-format"></a>設定 ER 格式
在您的應用程式實體中，您必須具有將用於產生 FTI 表單的 ER 格式設定。 

> [!NOTE]
> 必須為 CustomersInvoicing 資料模型建立此格式設定，並且它必須使用具有 **FreeTextInvoice** 根描述項的模型對應。

如需如何設定 ER 格式的相關資訊，請參閱[ER 建立格式設定 (2016 年 11 月) ](tasks/er-format-configuration-2016-11.md)。 如需如何設計 ER 格式以產生 OpenXML 格式的報告的相關資訊，請參閱[ER 設計用於產生 OPENXML 格式報告的設定 (2016 年 11 月) ](tasks/er-design-reports-openxml-2016-11.md)。

## <a name="configure-print-management"></a>設定列印管理
若要使用 ER 架構產生 FTI 表單，您可以按照指派 SSRS 報告的相同方式指派 ER 格式。 若要將 ER 格式與所有應收帳款 FTI 相關聯，請前往 **應收帳款**\>**安裝**\>**格式**\>**表單安裝**\>**一般**\>**列印管理**\>**普通發票**\>**原始**。 若要將 ER 格式與特定客戶或發票相關，請執行以下步驟。

1. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
2. 選取要與 ER 格式相關的 FTI，然後開啟 **列印管理安裝** 頁。
3. 選取文件級別以指定要處理的發票範圍。
4. 選取指定文件級別的 ER 格式。

![列印管理安裝。](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> 只有使用 **CustomersInvoicing** 資料模型的 **FreeTextInvoice** 根描述項的 ER 格式才會出現在所選格式的 **報告格式查找** 欄位中。

## <a name="generate-fti-forms"></a>產生 FTI 表格
FTI 表單在 ER 架構中的產生方式與產生 SSRS 報告的方式相同。

若要產生 FTI 表單，您可以按範圍或按選取選取發票。 

![發票選取。](media/FTIbyGER-InvoiceSelection.png)

![發票預覽。](media/FTIbyGER-InvoiceExcelPreview.png)

當您使用 ER 格式以這種方式列印 FTI 表單時，將使用預設的 ER 檔案目的地。 您不能改變目的地。 如需如何為 ER 格式設定 ER 目的地的相關資訊，請參閱[電子報表 (ER) 目的地](electronic-reporting-destinations.md)。

您還可以在過帳 FTI 時產生 FTI 表單，方法是打開 **列印發票** 並關閉 **使用列印管理目的地**。

> [!NOTE]
> 當您使用 ER 格式以這種方式列印 FTI 表單時，將使用預設的 ER 檔案目的地。 如果目的地已設定，您可以在執行階段更改預設目的地。 若要更改目的地，您必須具有以下安全權限：
>
> - **名稱：** ERFormatDestinationRuntimeMaintain
> - **標籤：** 在執行階段維護電子報表格式目的地

![電子報表目的地。](media/FTIbyGER-ERFileDestinationSetting.png)

![電子報表格式目的地。](media/FTIbyGER-ERFileDestinationUsage.png)

ER 架構現行支援產生文件的以下目的地：

- **下載檔案** – 產生的表格以下載形式提供，您可以使用瀏覽器進行儲存。
- **畫面控制項** – Microsoft 365 Excel 用於以 Excel 格式預覽產生的 FTI 表格。
- **SharePoint 資料夾** – 產生的表格根據文件管理架構的設定進行儲存。
- **申請封存** – 產生的表單作為執行日誌記錄的附件儲存在 Microsoft Azure 儲存體中。
- **電子郵件** – 產生的表格作為電子郵件附件發送。

> [!NOTE]
> 您不能將直接產生的 FTI 表單發送到印表機，因為現行不支援使用 Dynamics Printer Routing Agent 的直接列印。

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>下載樣本 ER 設定以產生可列印的 FTI 表格
您可以下載樣本 ER 設定以用作 FTI 解決方案的範本。 設定儲存在 Microsoft Dynamics Lifecycle Services (LCS) 的共用資產庫中。 該設定包含：

- **客戶發票模型** 設定包含所需的資料模型和模型對應。
- **客戶 FTI 報告 (GER)** 設定包含樣本格式。

> [!NOTE]
> 這些設定已作為樣本建立，以幫助闡明可能的場景。 這些設定的未來取決於此評估的結果和收到的任何意見反應。

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>以樣本 ER 格式實施的函數
在樣本 ER 格式設定中，使用 Excel 檔案作為範本來產生 FTI 表單。

![格式設計工具。](media/FTIbyGER-ERFormat.png)

現行，此樣本 ER 格式支援以下函數來產生 FTI 表單：

- 為已過帳的原始發票和尚未過帳的原始發票產生 FTI 表單。 不支援已更正的發票和折讓單。
- FTI 表格以發票語言產生。 產生的表單中的值和日期的格式基於使用者的用戶端地區設定。
- 如果已處理的發票中沒有任何明細，則產生的發票會顯示資料不可用通知。
- 產生的發票抬頭基於已在 **應收帳款參數** 頁面上為 FTI 表單選取的紙本格式。 僅當紙本格式為空白時，公司詳情才會出現在產生的發票表單的抬頭中。
- 當在 **應收帳款參數** 頁面上為 FTI 表單選取了適當的選項時，產生的發票表單會顯示公司和客戶的免稅編號。
- 產生的發票明細和發票總計部分以發票登記貨幣顯示預設發票的貨幣詳情。
- 當在 **應收帳款參數** 頁面啟用 **以代表歐元的貨幣列印金額** 選項時，產生的發票總額部分可以顯示歐元貨幣和發票登記貨幣的貨幣詳情。
- 產生的發票表單根據 **應收帳款參數** 頁面上的設定顯示任何可用的處理發票文件。 整個發票和每個發票明細都包含註釋。
- 產生的發票表單包括客戶 FTI 表單的註釋和在 AR 表單註釋清單中設定的處理發票語言。
- 根據列印管理設定，產生的發票包括針對發票語言、ER 格式和 FTI 文件範圍設定的自訂頁尾文字。
- 產生的發票表格的總計部分包括任何可用的現金折扣資訊。
- 產生的發票表格的付款計畫部分包括任何可用的付款計畫詳情。
- 產生的發票表格的標記部分包括任何可用的費用交易。
- 產生的發票表單包括銷售稅詳情，基於 **應收帳款參數** 頁面上的 **銷售稅規格** 設定。 此部分可以僅以發票登記幣種顯示稅務明細，也可以同時以發票登記幣種和公司記帳幣種顯示稅務明細。
- 產生的發票表格顯示直接借記通知詳情。 例如，它們顯示何時為發票選取了具有強制性直接借記授權 ID 的付款方式，何時以歐元貨幣登記處理發票，以及何時為發票定義了直接借記授權 ID。
- 產生的發票顯示可用於已過帳發票的任何預付款明細。
- 產生的發票表格可以作為電子郵件附件發送給發票客戶。 應為正在使用的 ER 格式設定適當的 ER 檔案目的地。

### <a name="countryregion-specific-features"></a>國家/地區專用函數 
樣本 ER 格式中包含以下國家/地區專用函數，以顯示如何在 ER 設定中處理特定要求。

#### <a name="norway"></a>挪威
為按以下方式設定的法律實體處理發票時，企業登記條款將放在產生的發票表單的抬頭中：

- 使用挪威的國家/地區內容。
- **Print Foretaksregisteret** 參數在銷售文件上處於有效狀態。

#### <a name="spain"></a>西班牙
當為按以下方式設定的法律實體處理發票時，會在產生的發票表單的抬頭中放置 **現金會計方法的特殊制度** 術語：

- 使用西班牙的國家/地區內容。
- 現金會計方法的特殊制度在發票處理日期啟用。

當現金折扣詳情 (例如現金折扣金額和發票明細淨金額) 可用時，它們會在已為按以下方式設定的法律實體處理時顯示在產生的發票表單的發票總計部分中：

- 使用西班牙的國家/地區內容。
- **在發票中應用現金折扣** 在發票選項中打開 (**總帳參數**\>**銷售稅部分**)。

#### <a name="italy"></a>義大利
為使用義大利國家/地區內容設定的法律實體處理產生發票時，商品折扣標記包含在產生發票的發票明細中。

#### <a name="finland"></a>芬蘭
除了產生的發票表格外，還可以產生 Giro 匯款單，如下所示：

- 對於使用芬蘭國家/地區內容的法律實體，並且至少有一個標記為 **Giro 帳戶** 和 **銀行條碼** 的銀行帳戶。 
- 對於標記為 **芬蘭** 相關付款附件所需的發票。

![Giro 單。](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> 樣本 ER 格式已設定為可選地在單獨的工作表中產生 Giro 匯款單。

> [!NOTE]
> 您必須首先在本地機器上安裝用於產生條碼的字型，在該機器上將預覽產生的 Excel 格式的發票表格。

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>使用樣本 ER 格式設定電子郵件目的地
使用樣本 ER 格式的以下元素來設定電子郵件目標：

- 可以透過以下 ER 運算式存取客戶聯絡人的電子郵件地址：**model.InvoiceBase.Contact.ElectronicMail**。
- 可以透過以下 ER 運算式存取電子郵件主題文字：**Emailing.TxtToUse.Subject**。
- 可以透過以下 ER 運算式存取電子郵件內文文字：**Emailing.TxtToUse.Body**。

![目的地設定。](media/FTIbyGER-ERFileDestinationSettingEmail.png)

電子郵件主題和內文的預設文字在樣本 ER 格式中定義。 該語言取決於格式的標籤。 如果尚未新增具有預定義 **ERFTITMP** ID 的自訂組織電子郵件範本，則此預設文字將用於電子郵件。

> [!NOTE]
> **ERFTITMP** 電子郵件範本 ID 已在樣本 ER 格式中定義。 可以根據需要在從此樣本格式建立的新 ER 格式中更改它。

如果已為您正在為其處理發票的法律實體新增了具有預定義 **ERFTITMP** ID 的組織電子郵件範本，則電子郵件主題和內文的範本將用於產生電子郵件。 

![組織電子郵件範本](media/FTIbyGER-EmailTemplate.png)

![上傳電子郵件範本。](media/FTIbyGER-EmailTemplateBody.png)

樣本 ER 格式的 **Emailing.TxtToUse.Subject** ER 運算式被設定為將任何出現的預留位置 %1 替換為處理發票 ID。

樣本格式的 **Emailing.TxtToUse.Body** 運算式設定為以下預留位置替換：

- 「%1」替換為客戶聯絡人的姓名。
- 「%2」替換為公司名稱。
- 「%3」替換為客戶姓名。
- 「%4」替換為公司聯絡人的姓名。
- 「%5」替換為公司聯絡人的職稱。
- 「%6」替換為公司聯絡人的電子郵件地址。

![電子郵件。](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>其他資源
[電子報表 (ER) 概觀](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]