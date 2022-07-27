---
title: 電子報告 (ER) 概觀
description: 本主題概述了電子報表工具。 它描述了作為解決方案一部分的關鍵概念、支援的案例和格式。
author: NickSelin
ms.date: 11/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "58941"
- intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 976a02f51e22c513b988e1ecfcb792d5f93a4b54
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460212"
---
# <a name="electronic-reporting-er-overview"></a>電子報告 (ER) 概觀

[!include [banner](../includes/banner.md)]

本主題概述了電子報表 (ER) 工具。 它包括關鍵概念、ER 支援的案例以及作為解決方案一部分設計和發佈的格式清單相關資訊。

ER 是可設定的工具，可幫助您建立和維護監管電子報告和支付。 它基於以下三個概念：

- 設定而不是編碼：

    - 設定可以由商務使用者完成，不需要開發人員。
    - 資料模型是用商業術語定義的。
    - 視覺效果編輯器用於建立 ER 設定的所有組件。
    - 用於資料轉換的語言類似於 Microsoft Excel 中使用的語言。

- 多個 Dynamics 365 Finance 版本的一種設定：

    - 管理以商業術語定義的一種特定於領域的資料模型。
    - 在依賴於發佈的資料模型對應中隔離應用程式發佈細節。
    - 根據資料模型，為目前版本的多個版本維護一種格式設定。

- 輕鬆或自動升級：

    - 支援 ER 設定的版本設定。
    - Microsoft Dynamics Lifecycle Services (LCS) 資產庫可用作 ER 設定的存放庫，用於版本交換。
    - 基於原始 ER 設定的本地化可以作為子版本引入。
    - 提供 ER 設定樹狀結構作為幫助控制版本相依性的工具。
    - 記錄本地化或增量設定的差異，以便自動升級到原始 ER 設定的新版本。
    - 您可以輕鬆手動解決本地化版本自動升級過程中發現的衝突。

ER 允許您定義電子格式結構，然後描述應如何使用資料和演算法填入這些結構。 您可以使用類似於 Excel 語言的公式語言進行資料轉換。 為了使資料庫到格式的對應更易於管理、可重用和獨立於格式更改，引入了中間資料模型概念。 這個概念使實現細節能夠從格式對應中隱藏起來，並使單個資料模型能夠重複用於多種格式對應。

您可以根據各個國家和地區的法律要求，使用 ER 設定傳入和傳出電子文件的格式。 ER 允許您在其生命週期內管理這些格式。 例如，您可以採用新的監管要求並產生所需格式的業務文件，以便與政府機構、銀行和其他各方進行電子資訊交換。

ER 引擎針對的是商務使用者而不是開發人員。 因為您設定的是格式而不是代碼，建立和調整電子檔案格式的過程更快、更容易。

ER 目前支援 TEXT、XML、JSON、PDF、Microsoft Word、Microsoft Excel，和 OPENXML 工作表格式。

## <a name="capabilities"></a>功能

ER 引擎具有以下功能：

- 它代表了用於不同領域電子報告的單一共用工具，並取代了 20 多個不同的引擎，這些引擎為財務和營運應用程式執行某種類型的電子報告。
- 它使報告的格式與目前的實作隔離開來。 換句話說，該格式適用於不同的版本。
- 它支援建立基於原始格式的自訂格式。 它還包括在原始格式因本地化/自訂要求而更改時自動升級自訂格式的功能。
- 它成為支援 Microsoft 和 Microsoft 合作夥伴在電子報告中的本地化要求的主要標準工具。
- 它支援透過 Microsoft Dynamics Lifecycle Services (LCS) 向合作夥伴和客戶分發格式的能力。

## <a name="key-concepts"></a>關鍵概念

### <a name="main-data-flow"></a>主要資料流程

[![ER 主要資料流程。](./media/ger-main-data-flow.jpg)](./media/ger-main-data-flow.jpg)

### <a name="components"></a>元件

ER 支援以下類型的組件：

- 資料模型
- 模型對應
- 格式
- 中繼資料

如需相關資訊，請參閱[電子報表組件](er-overview-components.md)。


#### <a name="component-versioning"></a>組件版本設定

ER 組件支援版本設定。 提供以下工作流程來管理 ER 組件中的更改：

1. 最初建立的版本被標記為 **草稿** 版本。 此版本可以編輯並可用於測試執行。
2. **草稿** 版本可以轉換為 **已完成** 版本。 此版本可用於本地報表流程。
3. **已完成** 版本可以轉換為 **共用** 版本。 此版本在 LCS 上發佈，可用於全球報告流程。
4. **共用** 版本可以轉換為 **中止** 版本。 然後可以刪除此版本。

具有 **已完成** 或 **共用** 狀態的版本可用於其他資料交換。 可以對具有這些狀態的組件執行以下動作：

- 該組件可以以 XML 格式序列化並以 XML 格式匯出為檔案。
- 該組件可以從 XML 檔案重新序列化，並作為 ER 組件的新版本匯入應用程式。

#### <a name="component-date-effectivity"></a>組件日期有效性

ER 組件版本是有效日期的。 您可以為 ER 組件設定 **生效日期**，以指定該組件對報告流程生效的日期。 應用程式工作階段日期用於定義組件是否有效執行。 如果多個版本在特定日期有效，則最新版本用於報告流程。

#### <a name="component-access"></a>組件存取

對 ER 格式組件的存取取決於 ISO 國家/地區代碼的設定。 如果對於格式設定的選定版本，此設定為空白，則可以在執行階段從任何公司存取格式組件。 當此設定包含 ISO 國家/地區代碼時，格式組件僅適用於具有為格式組件的 ISO 國家/地區代碼之一定義的主要地址的公司。

不同版本的資料格式組件可以有不同的 ISO 國家/地區代碼設定。

#### <a name="configuration"></a><a name="Configuration"></a>組態

ER 設定是特定 ER 組件的包裝函式。 該組件可以是資料模型組件或格式組件。 設定可以包括不同版本的 ER 組件。 每個設定都被標記為由特定的設定提供者擁有。 當設定的所有者在應用程式的 ER 設定中被選為有效提供者時，可以編輯設定組件的 **草稿** 版本。

每個模型設定都包含一個資料模型組件。 可以從特定的資料模型設定中衍生出新的格式設定。 在設定樹狀結構中，建立的格式設定顯示為原始資料模型設定的子項目。

建立的格式設定包含格式組件。 原始模型設定的資料模型組件作為預設資料來源自動插入到子格式設定的格式組件中。

ER 設定為應用程式公司共用。

#### <a name="provider"></a><a name="Provider"></a>提供者

ER 提供者是合作對象識別碼，用於指示每個 ER 設定的作者 (擁有者)。 ER 允許您管理設定提供者的清單。 作為財務和營運應用程式解決方案的一部分為電子文件發佈的格式設定被標記為歸 **Microsoft** 設定提供者所有。

若要了解如何註冊新的 ER 提供者，請播放工作指南 **ER 建立設定提供者並將其標記為有效** (**7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程的一部分)。

#### <a name="repository"></a><a name="Repository"></a>存放庫

ER 存放庫儲存 ER 設定。 目前支援以下類型的 ER 存放庫： 

- LCS 共用庫
- LCS 專案
- 檔案系統
- RCS
- 營運資源
- 全域存放庫

**LCS 共用庫** 存放庫提供對 Lifecycle Services (LCS) 中共用資產庫中設定清單的存取。 這種類型的 ER 存放庫只能為 Microsoft 提供者註冊。 從 LCS 共用資產庫中，您可以將最新版本的 ER 設定匯入目前的執行個體。

**LCS 專案** 存放庫可存取在註冊存放庫時已選取之特定 LCS 專案 (LCS 專案資產庫) 的設定清單。 ER 允許您將共用設定從目前的執行個體上傳到特定的 **LCS 專案** 存放庫。 您還可以將設定從 **LCS 專案** 存放庫匯入財務和營運應用程式目前的執行個體。

**檔案系統** 存放庫可以存取設定清單，這些設定清單以 xml 檔案的形式位於託管 AOS 服務的機器的本地檔案系統的特定資料夾中。 在存放庫註冊階段選取所需的資料夾。 您可以將設定從 **檔案系統** 存放庫匯入目前的執行個體。 

請注意，此存放庫類型可在以下環境中存取：

- 為開發目的而部署的雲端託管環境 (包含封閉套件的測試模型)
- 本地部署的環境 (內部)

如需相關資訊，請參閱[匯入電子報表 (ER) 設定](./electronic-reporting-import-ger-configurations.md)。

**RCS 存放庫** 提供對在存放庫註冊階段選取的特定[設定服務 (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) 執行個體的設定清單的存取。 ER 允許您將已完成或共享的設定從選定的 RCS 執行個體匯入到目前執行個體中，以便您可以將它們用於電子報告。

如需相關資訊，請參閱[從 RCS 匯入電子報表 (ER) 設定](./rcs-download-configurations.md)。

**全域存放庫** 存放庫可存取[設定服務](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration)中全域存放庫內的設定清單。 這種類型的 ER 存放庫只能為 Microsoft 提供者註冊。 從全域存放庫中，您可以將最新版本的 ER 設定匯入目前的執行個體。

如需相關資訊，請參閱[從設定服務的全域存放庫匯入電子報告 (ER) 設定](./er-download-configurations-global-repo.md)。

**Operations 資源** 存放庫可存取 Microsoft 作為 ER 設定提供者最初作為應用程式解決方案的一部分發佈的設定清單。 這些設定可以匯入到目前的執行個體中並用於電子報告或播放範例工作指南。 它們還可用於其他本地化和自訂。 請注意，Microsoft ER 設定提供的最新版本必須使用對應的 ER 存放庫從 LCS 共用資產庫中匯入。

可以為目前執行個體的每個設定提供者單獨註冊所需的 **LCS 專案**、**檔案系統** 和 **Regulatory Configuration Services (RCS)** 存放庫。 每個存放庫都可以專用於特定的設定提供者。

## <a name="supported-scenarios"></a>支援的案例

### <a name="building-a-data-model"></a>構建資料模型

ER 提供了一個模型設計工具，您可以使用它來為特定業務領域構建資料模型。 所有特定領域的業務實體，以及它們之間的關係，都可以在資料模型中呈現為階層。 

若要熟悉此案例的詳情，請播放 **ER 設計領域特定資料模型** 工作指南 (**7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程的一部分)。

### <a name="translating-data-model-content"></a>翻譯資料模型內容

資料模型內容 (標籤和描述) 可以翻譯成應用程式支援的其他語言。 出於以下原因，您可能希望翻譯資料模型內容：

- 在設計階段，使內容更易於講其他語言的格式設計者理解，並且將使用資料模型進行格式組件的資料對應。
- 在執行階段，透過以目前登入使用者喜歡的語言顯示執行階段參數的提示和幫助以及設定的驗證訊息 (錯誤和警告)，使內容更方便使用。

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>為傳出文件設定資料模型對應

ER 提供了模型對應設計工具，讓使用者可以將他們設計的資料模型對應到特定的應用程式資料來源。 基於對應的情況下，資料將在執行階段從選定的資料來源匯入資料模型。 然後，該資料模型用作產生傳出電子文件的 ER 格式的抽像資料來源。 

若要熟悉這個案例的詳情，請播放 **ER 定義模型對應和選取資料來源** 和 **ER 將資料模型對應到選定的資料來源** 工作指南 (屬於 **7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程)。

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>為傳入文件設定資料模型對應

ER 提供了模型對應設計工具，讓使用者可以將他們設計的資料模型對應到特定的目的地。 例如，資料模型可以對應到可更新的資料組件 (表、資料實體和檢視表)。 基於對應的情況下，資料將在執行階段使用來自資料模型的資料進行更新。 作為 ER 格式的抽象儲存體，資料模型填入了從傳入電子文件匯入的資料。 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>將設計的模型組件儲存為模型設定

ER 可以將設計的資料模型連同關聯的資料對應一起儲存為目前執行個體的模型設定。 下圖顯示了此類資料模型設定 (付款模型設定) 的範例。

若要熟悉此案例的詳情，請播放 **ER 將資料模型對應到選定的資料來源** 工作指南 (屬於 **7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程)。

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>構建以資料模型為基礎的格式

ER 支援格式設計工具，您可以透過選取模型組件作為基礎來為選定的業務領域構建電子文件的格式。 同一個 ER 格式設計工具允許您將建立的格式對應到選定領域的資料模型對應作為資料來源。 

若要熟悉此案例的詳情，請播放 **ER 設計領域特定格式** 工作指南 (**7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程的一部分)。

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>構建設定以產生 OPENXML 工作表格式的電子文件

ER 格式設計工具可用於構建 OPENXML 工作表格式的電子文件。 

若要熟悉此案例的詳情，請播放 **ER 為 OPENXML 格式的報告建立設定** 工作指南 (屬於 **7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程)。 根據匯入範本的工作指南步驟，使用[付款報告範本 (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) Excel 檔案作為範本。

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>構建設定以產生 Word 文件格式的電子文件

ER 格式設計工具可用於構建 Word 文件格式的電子文件。 下圖顯示了這種格式的範例。 請注意，此格式重用了現有的 ER 設定，該設定最初設計用於產生 OPENXML 格式的報告輸出。

若要熟悉此案例的詳情，請播放 ER 設計用於產生 Microsoft WORD 格式報告的設定工作指南 (屬於 7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677) 業務流程)。 根據匯入範本的工作指南步驟，使用以下 Word 檔案作為 ER 格式的範本：

- [付款報告範本 (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [付款報告的繫結範本 (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>構建設定以從傳入的電子文件中匯入資料

ER 格式設計工具可用於描述計劃以 XML 或文字格式匯入資料的電子文件。 設計的格式用於解析傳入的文件。 ER 格式對應設計工具可用於定義設計格式的元素與資料模型的繫結。 

若要熟悉此案例的詳情，請播放建立所需的 ER 設定以從外部檔案匯入資料工作指南 (屬於 7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677) 業務流程)。 使用以下檔案播放本指南：

- [ER 資料模型設定 (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [ER 格式設定 (1099format.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [XML 格式的傳入文件樣本 (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [用於管理傳入文件資料的活頁簿樣本 (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>將設計的格式組件儲存在格式設定中

ER 可以將設計的格式與設定的資料對應一起儲存為目前執行個體的格式設定。 上圖顯示了此類格式設定的範例 (**BACS (UK)**，即 **付款模型** 設定的子項目)。 若要熟悉此案例的詳情，請播放 **ER 設計領域特定格式** 工作指南 (**7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程的一部分)。

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>將 Finance 設定為開始在內部使用建立的格式

該應用程式可以設定為開始使用建立的格式來產生電子報告。 對建立的格式設定的參考應在特定域的設定中定義。 例如，要開始對 BACS 格式的電子廠商付款使用 ER 格式設定，應在特定的付款方式中參考格式設定。

若要熟悉此案例的詳情，請播放 **ER 使用格式產生付款電子文件** 工作指南 (屬於 **7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程)。

## <a name="handling-er-components"></a>處理 ER 組件

### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>在 LCS 中發佈 ER 組件以向外部提供 (本地化)

已建立的組件 (模型或格式) 的所有者可以使用 ER 將組件的完整版本發佈到 LCS。 需要目前 ER 設定提供者的 **LCS 專案** 類型的存放庫。 當組件的已完成版本的狀態從 **已完成** 更改為 **共用** 時，該版本將在 LCS 中發佈。 當組件已發佈到 LCS 時，該組件擁有者將成為支援該組件服務的提供者。 例如，如果格式元件的設計是為了產生法律要求的電子檔 (例如，根據當地語系化案例)，則假設該格式將保持與立法變更一致，只要出現新的立法要求，廠商就會發佈組件的新版本。 若要熟悉此案例的詳情，請播放 **ER 將設定上傳到 Lifecycle Services** 工作指南 (屬於 **7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程)。

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>從 LCS 匯入 ER 組件以在內部使用它

ER 允許您將 ER 組件從 LCS 匯入到目前的執行個體。 需要 **LCS 專案** 類型的存放庫。 當 ER 組件從 LCS 匯入到目前的執行個體時，該執行個體擁有者將成為匯入組件之擁有者 (作者) 提供的服務的消費者。 例如，如果格式組件旨在從應用程式以特定國家/地區的格式 (本地化案例) 產生特定電子文件，則假設服務消費者將能夠獲得對該格式所做的任何更新，以使其符合立法要求。 若要熟悉此案例的詳情，請播放 **ER 從 Lifecycle Services 匯入設定** 工作指南 (屬於 **7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程)。

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>構建選取另一種格式作為基礎的格式 (自訂)

ER 允許您從從 LCS 匯入的組件 (基礎) 的目前版本建立 (衍生) 新組件。 例如，使用者想要衍生新格式來實作對電子文件的一些特殊要求 (例如附加欄位或擴展描述) 以支援自訂案例。 若要熟悉此案例的詳情，請播放 **ER 透過採用新的基礎版本來升級格式** 工作指南 (屬於 **7.5.4.3 獲得/開發 IT 服務/解決方案組件 (10677)** 業務流程)。

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>升級格式選取新版本的基礎格式 (重訂基底)

ER 允許您在衍生組件的目前草稿版本中自動採用最新版本基礎組件的更改。 這個過程被稱為 *重訂基底*。 例如，在從 LCS 匯入的最新版本格式中引入的新法規更改可以自動合併到此電子文件格式的自訂版本中。 任何無法自動合併的更改都被視為衝突。 這些衝突將在設計工具工具中針對相應組件進行手動解決。 若要熟悉此案例的詳情，請播放 **ER 透過採用該格式的新基礎版本來升級格式** 工作指南 (屬於 **7.5.5.3 獲得/開發已更改的 IT 服務/解決方案組件 (10683)** 業務流程)。

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>Finance 中已發佈的 ER 設定清單

Finance ER 設定中的清單不斷更新。 打開[全域存放庫](er-download-configurations-global-repo.md)查看現行支援的 ER 設定清單。 在 **停產詳情** FastTab 上，您可以查看有關已停止或不再維護之設定的資訊。 

![設定存放庫頁面上全域存放庫的內容。](./media/er-overview-03.gif)

## <a name="additional-resources"></a>其他資源

- [建立電子報表 (ER) 設定](electronic-reporting-configuration.md)
- [管理電子報表 (ER) 設定生命週期](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
