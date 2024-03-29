---
title: 設定電子訊息
description: 本主題提供有關如何設定電子訊息 (EM) 功能的資訊。
author: liza-golub
ms.date: 11/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-23
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: a9d623c712de34afd1b38dbc6a8738ebf9613d49
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2021
ms.locfileid: "8451197"
---
# <a name="set-up-electronic-messages"></a>設定電子訊息

[!include [banner](../includes/banner.md)]

**電子訊息** (EM) 功能可協助您為不同的文件類型維護不同的電子報告程序。 在一些支持[國家/地區特定報告功能](electronic-messaging.md#country-specific-regulatory-features-supported-by-the-em-functionality)的複雜場景中，EM 功能的設定使其具有許多訊息狀態、訊息項狀態、動作、附加欄位和可執行類的組合。 對於這些場景，可以匯入資料實體套件。 如果您使用這些資料實體套件，請使用資料管理工具將它們匯入法人實體。 關於如何使用資料管理工具的更多資訊，請參閱[資料管理](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)。

如果您不匯入資料實體套件，您可以手動設定 EM 功能。 在這種情況下，您必須設定以下元素：

- [數字序列](#sequences)
- [訊息項目類型](#types)
- [訊息項目狀態](#item)
- [訊息狀態](#statuses)
- [其他欄位](#additional)
- [可執行類別設定](#executable)
- [填充記錄動作。](#populate)
- [填入來自多家公司的記錄](#multiple-companies-populate)
- [Web 應用程式](#applications)
- [Web 服務設定](#settings)
- [訊息處理動作](#actions)
- [電子訊息處理](#processing)

以下部分提供了各元素的更多相關資訊。

## <a name="number-sequences"></a><a id="sequences"></a>數字序列

為訊息和訊息項目設定編號規則。 然後使用編號規則對訊息和訊息項目進行自動編號。 分配的編號作為系統中訊息和訊息項目的唯一識別碼。 您可以通過轉到 **總帳** \> **總帳設置** \> **總帳參數** 來設定電子訊息的編號規則。

## <a name="message-item-types"></a><a id="types"></a>訊息項目類型

訊息項目類型會標識電子訊息中使用的記錄類型。 您可以通過以下方式設定訊息項目類型前往 **稅務** \> **設置** \> **電子訊息** \> **訊息項目類型**。

## <a name="message-item-statuses"></a><a id="item"></a>訊息項目狀態

訊息項目狀態會標識在您正在設定的處理中應用於訊息項目的狀態。 您可以通過以下方式設定訊息項目狀態前往 **稅務** \> **設置** \> **電子訊息** \> **訊息項目狀態**。

訊息項目狀態的 **允許刪除** 參數定義您是否可以在 **電子訊息** 頁面或 **電子訊息項目** 頁面上刪除具有此狀態的訊息項目。

## <a name="message-statuses"></a><a id="statuses"></a>訊息狀態

設定在訊息處理中應該可用的訊息狀態。 您可以通過以下方式設定訊息狀態前往 **稅務** \> **設置** \> **電子訊息** \> **訊息狀態**。

下表描述了 **訊息狀態** 頁面上的欄位。

| 欄位名稱          | 描述 |
|---------------------|-------------|
| 訊息狀態      | 輸入應用程式的唯一的訊息狀態名稱。 訊息狀態用於表示電子訊息每時每刻的狀態。 您輸入的姓名顯示在 **電子訊息** 頁面和與電子訊息相關的紀錄中。 |
| 描述         | 輸入訊息狀態的描述。 |
| 回應類型       | 選擇訊息狀態的回應類型。 處理中的某些動作可以產生不止一種回應類型。 例如，**Web 服務** 類型的動作可以產生 **成功執行** 類型或 **技術錯誤** 類型的回應，具體取決於其執行結果。 在這種情況下，為兩種回應類型定義訊息狀態。 動作類型和與其相關的回應類型的更多資訊，請參閱本主題後面的[訊息處理動作類型](#action-types)部分。 |
| 訊息項目狀態 | 有時候，電子訊息的狀態必須影響相關訊息項目的狀態。 在此欄位中選擇訊息項目狀態以將其與訊息狀態相關聯。 |
| 允許刪除        | 如果使用者應該能夠在 **電子訊息** 頁面上刪除具有此狀態的電子訊息，請選中此核取方塊。 |

## <a name="additional-fields"></a><a id="additional"></a>其他欄位

EM 功能允許您從 Microsoft Dynamics 365 Finance 中的交易資料表中收集記錄作為訊息項目。 這樣，您就能準備報告的記錄，然後進行報告。 但是，交易資料表有時沒有足夠的資訊來以符合報告要求的方式填寫記錄。 若要填寫必須為記錄報告的所有資訊，您可以設定其他欄位。 附加欄位可以與訊息和訊息項目相關聯。 您可以通過以下方式設定額外欄位前往 **稅務** \> **設置** \> **電子訊息** \> **額外欄位**。

下表描述了 **額外欄位** 頁面上的一般欄位。

| 欄位       | 描述 |
|-------------|-------------|
| 欄位名稱  | 輸入與流程相關的電子訊息或訊息項目的附加欄位名稱。 當您使用該程序時，此名稱會顯示在使用者界面 (UI) 中。 該名稱還可用於與程序相關的電子報告 (ER) 設定。 |
| 描述 | 輸入附加欄位的描述。 |
| 使用者編輯   | 如果使用者應該能夠變更 UI 中附加欄位的值，請將此選項設定為 **Yes**。 |
| 計數器     | 如果附加欄位應在電子郵件中包含編號規則，請將此選項設定為 **Yes**。 執行 **電子報告匯出** 類型的動作時，會自動填寫附加欄位的值。 |
| 已隱藏      | 如果附加欄位應隱藏在 **電子訊息** 頁面或 **電子訊息項目** 頁面的 UI 中，則將此選項設定為 **Yes**。 |

在 **數值** FastTab 上，您可以預定義附加字段可以具有的值。 然後這些值可供使用者選擇。 因此，它們不必在處理過程中手動填寫。 下表說明這些欄位。

| 欄位                | 描述 |
|----------------------|-------------|
| 欄位值          | 輸入在報告期間用於訊息或訊息項目的欄位值。 |
| 描述          | 輸入欄位值的描述。 |
| 帳戶類型         | 某些欄位值可能僅限於特定帳戶類型。 選擇下列值之一：**All**、**Customer** 或 **Vendor**。 |
| 帳戶代碼         | 如果您在 **Account type** 欄位中選擇了 **Customer** 或 **Vendor**，則可以進一步將欄位值的使用限制為特定群組或資料表。 |
| 帳戶/群組編號 | 如果您在 **Account type** 欄位中選擇了 **Customer** 或 **Vendor**，如果您在 **Account code** 欄位中輸入了群組或資料表，您可以在此欄位中輸入特定的群組或代理。 |
| 生效            | 指定開始考慮該值的日期。 |
| 到期           | 指定停止考慮該值的日期。 |

預設情況下，由 **Account/Group number**、**Account code**、**Effective** 和 **Expiration** 欄位定義的條件組合不會影響選擇附加欄位的值。 但是，可以在可執行類中使用這些組合來實現計算附加欄位值的特定邏輯。

## <a name="executable-class-settings"></a><a id="executable"></a>可執行類別設定

可執行類別是一個 X++ 方法或類別，如果程序需要某些評估，則電子訊息處理可以叫用與動作相關。

您可以透過前往 **稅務** \> **設置** \> **電子訊息** \> **可執行類別設定**，在處理期間必須叫用的可執行類別。 在 **可執行類別設定** 頁面上、建立行並設定下列欄位。

| 欄位                 | 描述 |
|-----------------------|-------------|
| 可執行類別      | 輸入將在設定與叫用此類相關的訊息處理動作期間使用的名稱。 |
| 描述           | 輸入可執行類別的描述。 |
| 可執行類別名稱 | 選擇一個 X++ 可執行類別。 |
| 執行等級       | 該欄位是自動設定，因為該值是為所選的可執行類預定義的。 此欄位會限制執行相關評估的等級。 |
| 等級描述     | 該欄位是自動設定，因為該值是為所選的可執行類預定義的。 |
| 動作類型           | 當 **\[EM\] 可執行類操作類型** 功能在 **功能管理** 工作區中打開時，此欄位可用。 使用此欄位指定可執行類別的動作類型。 此欄位可以更精確地控制電子資訊頁面上，可用於 **電子訊息** 的下一步動作。 |

某些可執行類別可能具有必須在第一次執行可執行類別之前定義的強制參數。 若要定義這些參數，請在動作窗格上選擇 **參數**。 在出現的對話方塊中，設定欄位，然後選擇 **OK**。 選擇 **OK** 非常重要。 否則，參數將不會被保存到資料庫中，並且可執行類別將無法正確叫用。

## <a name="populate-records-actions"></a><a id="populate"></a>填充記錄動作

您使用填充記錄動作來設定將記錄新增到訊息項目資料表的動作，以便可以將它們新增到電子郵件中。 例如，如果您的電子郵件必須報告客戶發票，您必須設定一個填充記錄動作，該動作鏈接到客戶發票日記帳表中的 **資料來源** 欄位。

您可以透過前往 **稅務** \> **設置** \> **電子訊息** \> **訊息項目狀態** 設定填寫記錄動作。 為應將記錄新增到資料表中的每個動作建立一條新記錄，並設定下列欄位。

| 欄位       | 描述 |
|-------------|-------------|
| 姓名        | 為在您的流程中填寫記錄的動作輸入名稱。 |
| 描述 | 輸入填入記錄動作的描述。 |

在 **資料來源設定** FastTab 上，為流程使用的每個資料來源新增一行，並設定下列欄位。

| 欄位                  | 描述 |
|------------------------|-------------|
| 姓名                   | 請輸入資料來源的名稱。 |
| 訊息項目類型      | 選擇為資料來源建立記錄時，要使用的訊息項目類型。 |
| 帳戶類型           | 選擇要與資料來源中的記錄關聯的帳戶類型。 |
| 主資料表名稱      | 選擇將作為資料來源的資料表。 |
| 文件編號欄位  | 在所選的主資料表中選擇將從中獲取憑證編號的欄位。 該欄位的值用作訊息項目的 **文件編號** 欄位的數值。 |
| 文件日期欄位    | 在所選的主資料表中選擇將從中獲取憑證日期的欄位。 該欄位的值用作訊息項目的 **訊息項目日期** 欄位的數值。 |
| 文件帳戶欄位 | 在所選的主資料表中選擇將從中獲取憑證帳戶的欄位。 該欄位的值用作訊息項目的 **帳戶編號** 欄位的數值。 |
| 公司                | 當在 **功能管理** 工作區中打開 **跨公司查詢填入記錄動作** 功能時，此欄位可用。 使用此功能為填入記錄動作設定跨公司資料來源。 可以從多家公司取得資料。 |
| 使用者查詢             | <p>如果您透過選擇網格上方的 **編輯查詢** 來設定查詢，並且您指定了必須應用於從中填充資料的所選主資料表條件，則會自動選中此核取方塊。 否則，則會從所選的主資料表來源填寫所有記錄。</p><p>當針對 **填入記錄動作的跨公司查詢** 功能在 **功能管理** 工作區中打開，並且必須從多個公司收集記錄時，為每個必須新增的附加法人實體新增一行納入報告。 對於每個新行，請選擇 **編輯查詢**，並指定特定於在該行的 **公司** 欄位中指定的法人相關標準。 完成後，**資料來源設置** 網格將包含必須包含在報告中所有的法人實體行。</p> |

## <a name="populate-records-from-multiple-companies"></a><a id="multiple-companies-populate"></a>填入來自多家公司的記錄

如果您的公司必須從同一財務資料庫中的多個法人實體進行報告，請為必須將資料包含在報告中的所有法人實體設定[填入記錄動作](#populate)。

若要在您的財務環境中啟用此功能，請執行以下步驟。 

1. 移至 **工作區** \> **功能管理**。
2. 在列表中查找並選擇 **跨公司查詢以用於填充記錄動作** 功能。
3. 選取 **立即啟用**。 

若要為必須在報告中包含資料的多家公司設定[填入記錄動作](#populate)，請按照以下步驟操作。

1. 前往 **稅務** \> **設置** \> **電子訊息** \> **填入紀錄動作**。

    啟用 **跨公司查詢填入記錄動作** 功能時，**填入** 記錄動作頁面上的 **資料來源設置** 網格包含一個 **公司** 欄位。 對於在[填入記錄動作](#populate)的常規設置期間建立的現有記錄，此欄位會顯示目前法人的識別碼。

2. 在 **資料來源設置** 網格中，為必須包含在報告中的每個子公司法人實體新增一行，並設定以下欄位。

    | 欄位名稱             | 值 |
    |------------------------|-------|
    | 姓名                   | 輸入一個文字值，以幫助您了解此記錄的來源。 舉例來說，請輸入 **資料來源名稱 - 子公司 1**。 |
    | 訊息項目類型      | 選擇您的 EM 處理所需的訊息項目類型。 |
    | 帳戶類型           | 指定您的 EM 處理所需的帳戶類型。 如果您的 EM 處理沒有特定的帳戶類型，請選擇 **All**。 |
    | 主資料表名稱      | 指定 EM 處理所需的主資料表的名稱。 |
    | 文件編號欄位  | 在您的 EM 處理記錄中指定包含文件編號的欄位。 |
    | 文件日期欄位    | 在您的 EM 處理記錄中指定包含文件日期的欄位。 |
    | 文件帳戶欄位 | 在您的 EM 處理記錄中指定包含文件帳戶的欄位。 |
    | 公司                | 選擇子公司法人的識別碼。 |
    | 使用者查詢             | 當您透過選擇 **Edit query** 定義條件時，會自動選中此核取方塊。 |

3. 對於每個新行，請選擇 **編輯查詢**，並為該行的 **公司** 欄位中指定的法人指定相關條件。

## <a name="web-applications"></a><a id="applications"></a>Web 應用程式

使用 Web 應用程式設定來設置 Web 應用程式，使其支持開放授權 (OAuth) 2.0。 OAuth 是一種開放標準，允許使用者代表他們向應用程序授予「安全委託存取」，而無需分享他們的存取憑證。 您也可以透過取得授權碼和存取權杖來完成授權過程。 您可以前往 **稅務** \> **設置** \> **電子訊息** \> **Web 應用程式**，設定 Web 應用程式設定。

下表描述了 **Web 應用程式** 頁面上的欄位。

| 欄位                        | 描述 |
|------------------------------|-------------|
| 應用程式名稱             | 輸入 Web 應用程式的名稱。 |
| 描述                  | 輸入 Web 應用程式的描述。 |
| 基底 URL                     | 輸入 Web 應用程式的基本網際網路地址。 |
| 授權 URL 路徑       | 指定用於組成授權 URL 的路徑。 |
| 權杖 URL 路徑               | 指定用於構成權杖 URL 的路徑。 |
| 重新導向 URL                 | 輸入重新導向 URL。 |
| 用戶端識別碼                    | 輸入 Web 應用程式的客戶端識別碼。 |
| 用戶端密碼                | 輸入 Web 應用程式的用戶端密碼。 |
| 伺服器權杖                 | 輸入 Web 應用程式的伺服器權杖。 |
| 授權格式對應 | 選擇用於生成授權請求的 ER 格式。 |
| 匯入權杖模型對應   | 選擇用於存放存取權杖的 ER 匯入模型對應。 |
| 授與範圍                | 授予應用程式要求的範圍。 此欄位會自動更新。 |
| 存取權杖到期時間  | 存取權杖過期前的剩餘時間。 此欄位會自動更新。 | 
| 接受                       | 指定 Web 要求的 **接受** 屬性。 例如，輸入 **application/vnd.hmrc.1.0+json**。 |
| 內容類型                 | 指定內容類型。 例如，輸入 **application/json**。 |

此外，**Web 應用程式** 頁面的動作窗格上提供了以下按鈕以支持授權過程：

- **取得授權碼** - 初始化 Web 應用程式的授權。 函數會使用 **授權格式對應** 欄位中指定的 ER 格式來生成授權要求。
- **取得存取權杖** – 初始化取得存取權杖的過程。
- **重新整理存取權杖** – 重新整理存取權杖。 函數會使用 **匯入權杖模型對應** 欄位，以匯入有關接收到的存取權杖的資訊。

當 Web 應用程式的訪問權杖以加密格式儲存在系統的資料庫中時，它可用於對 Web 服務的請求。 出於安全目的，對權杖的存取必須限於允許處理這些請求的資訊安全角色。 如果安全性群組之外的任何人嘗試處理請求，他們會收到一條錯誤訊息，指出不允許他們使用所選的 Web 應用程式進行互操作。 要設定有權存取存取權杖的資訊安全角色，請使用 **Web 應用程式** 頁面上的 **資訊安全角色** FastTab。 如果未為 Web 應用程式定義資訊安全角色，則只有系統管理員可以使用 Web 應用程式進行互操作。

對於所選 Web 應用程式的每個動作，**動作紀錄** FastTab 會保存有關使用者的資訊以及日期和時間。

某些 Web 服務可能要求請求中包含不同的標題。 系統管理員可以在 **補充標題** FastTab 上設定其他標題及其值，然後在請求生成期間使用它們。

## <a name="web-service-settings"></a><a id="settings"></a>Web 服務設定

使用 Web 服務設定將資料直接傳輸到 Web 服務。 您可以前往 **稅務** \> **設置** \> **電子訊息** \> **Web 服務社定**，設定 Web 服務設定。

下表描述了 **Web 服務設定** 頁面上的欄位。

| 欄位                          | 描述 |
|--------------------------------|-------------|
| Web 服務                    | 輸入 Web 服務的名稱。 |
| 描述                    | 輸入 Web 服務的描述。 |
| 內部地址               | <p>輸入 Web 服務的網際網路地址。 如果為 Web 服務指定了 Web 應用程式，並且 Web 服務的 Internet 地址應與為該 Web 應用程式定義的網際網路位址相同，請選擇 **複製基本 URL**。 然後將 Web 應用程式的基本 URL 複製到此欄位。</p><p>**警告：** 您在此處設定的第三方服務或其他服務不需要認證，並且可能不符合 Microsoft 隱私標準。 您應該查看每個服務的隱私文件並與每個服務提供者合作，以了解有關其服務提供的合規性等級的更多資訊。 您有責任確保這些服務符合您的安全、隱私和法律標準。 貴用戶須自行承擔使用服務。 Microsoft 不提供任何明示的保證、保證或條件。 我們強烈建議您僅使用提供安全和授權連結的服務，例如 HTTPS。</p> |
| 憑證                    | 選擇之前設定的 Azure Key Vault 證書。 |
| Web 應用程式                | 選擇之前設定的 Web 應用程式。 |
| 回應類型 – XML        | 如果回應類型是 XML，則將此選項設定為 **Yes**。 |
| 要求方法                 | 指定要求的方法。 HTTP 定義了一組要求方法，這些方法指示應該對給定資源執行的動作。 要求方法可以是 **GET**、**POST** 或其他 HTTP 方法。 |
| 要求標頭                | 指定要求標頭。 要求標頭是可以在 HTTP 要求中使用的 HTTP 標頭。 它與訊息的內容無關。 |
| 接受                         | 指定 Web 要求的接受屬性。 |
| 接受編碼                | 指定接受編碼值。 接受編碼要求 HTTP 標頭通告客戶端可以理解的內容編碼。 這種內容編碼通常是一種壓縮演算法。 |
| 內容類型                   | 指定內容類型。 內容類型實體 HTTP 標頭指示資源的媒體類型。 |
| 成功的回應代碼       | 指定指示要求成功的 HTTP 狀態代碼。 |
| 要求標頭格式對應 | 選擇用於生成 Web 請求標頭的 ER 格式。 |

## <a name="message-processing-actions"></a><a id="actions"></a>訊息處理動作

您使用訊息處理動作為您的流程建立動作並設定它們的參數。 您可以透過前往 **稅務** \> **設置** \> **電子訊息** \> **訊息處理動作** 設定訊息處理動作。

下表描述了 **訊息處理動作** 頁面上的欄位。

### <a name="general-fasttab"></a>一般 FastTab

| 欄位                                     | 描述 |
|-------------------------------------------|-------------|
| 動作類型                               | 選取動作的類型。 關於可用選項的資訊，請參閱本主題後面的[訊息處理動作類型](#action-types)部分。 |
| 格式對應                            | 選擇應為動作叫用的 ER 格式。 此欄位僅適用於 **電子報告匯出**、**電子報告匯入** 和 **電子報告匯出訊息** 類型的動作。 |
| URL 路徑的格式對應               | 選擇應為動作叫用的 ER 格式。 此格式用於構成將新增到為所選 Web 伺服器指定的基本網際網路地址的 URL 地址的路徑。 此欄位僅適用於 **Web 服務** 類型的動作。 |
| 訊息項目類型                         | 選擇應評估動作的記錄類型。 此欄位適用於 **訊息項目執行等級**、**電子報告匯入** 和 **電子報告匯出訊息** 和 **Web 服務** 類型和其他類型。 如果將此欄位留空，則會評估為訊息處理定義的所有訊息項類型。 |
| 可執行類別                          | 選擇現有的可執行類別設定。 該欄位僅適用於 **訊息項目執行等級** 和 **訊息項目執行等級** 類型的動作。 |
| 填充記錄動作                   | 選擇現有的填入記錄動作。 此欄位僅適用於 **填入紀錄** 類型的動作。 |
| Web 服務                               | 選取現有 Web 服務。 此欄位僅適用於 **Web 服務** 類型的動作。 |
| 要發送的檔案名稱                         | 輸入必須透過此動作發送的電子郵件的附件名稱。 如果多個附件具有相同的原始檔案名稱，將發送最新的一個。 如果沒有找到具有指定原始檔案名稱的附件，則將發送不帶內容的要求。 此欄位僅適用於 **Web 服務** 類型的動作。 |
| 檔案名稱                                 | 指定將作為動作結果的檔案名稱。 該檔案可以是來自 Web 伺服器的回應或生成的報告。 此欄位僅適用於 **Web 服務** 和 **電子報告匯出訊息** 類型的動作。 |
| 將檔案附加到來源文件          | 選中此核取方塊可將生成的檔案附加到 EM 項目的引用主資料表中的記錄。 此欄位僅適用於 **電子報告匯出** 和 **Web服務** 類型的動作。 |
| 將檔案從輸出庫存附加到項目 | 選取此核取方塊可從輸出庫存檔案中擷取單獨的 XML 檔案並將它們附加到相應的電子郵件項目中。 此欄位僅適用於 **電子報告匯出** 類型。 |
| 每次匯出的訊息品項數        | 指定一個檔案 (訊息) 中必須包含的訊息項目數量限制。 此欄位僅適用於 **電子報告匯出** 類型。 |
| 使用 ER 來源                             | 選取此核取方塊以使用 ER 來源參數進行匯入。 否則，使用來自電子訊息的附件。 此欄位僅適用於 **電子報告匯入** 類型。 |
| 顯示對話方塊                               | 如果必須在生成報告之前向使用者顯示對話框，請將此選項設定為 **Yes**。 此欄位僅適用於 **電子報告匯出訊息** 類型。 |

#### <a name="message-processing-action-types"></a><a id="action-types"></a>訊息處理動作類型

**動作類型** 欄位中提供了以下選項：

- **建立訊息** – 使用此動作類型可讓使用者在 **電子訊息** 頁面上手動建立訊息。 無法為此類動作設定初始狀態。
- **填入記錄** - 此動作類型必須已設定。 將其與填入記錄動作相關聯，以使該動作包含在處理中。 假設此動作類型用於訊息處理中的第一個操作 (當沒有預先建立電子訊息時) 或用於將訊息項新增到先前由 **建立訊息** 動作建立的訊息動作類型。 因此，對於這種類型的動作，只能為訊息項目設定結果狀態。 只能為訊息設定初始狀態。
- **訊息執行等級** - 使用此動作類型設定應在訊息等級評估的可執行類別。
- **訊息項目執行等級** - 使用此動作類型設定應在訊息項目等級評估的可執行類別。
- **電子報告匯出** - 將此動作類型用於應基於訊息項目等級的匯出 ER 設定生成報告的動作。
- **電子報告匯出訊息** - 將此動作類型用於應基於訊息等級的匯出 ER 設定生成報告的動作 (例如，當一則訊息沒有任何訊息項目時)。
- **電子報告匯入** - 將此動作類型用於應基於匯入 ER 設定生成報告的動作。
- **訊息等級的使用者處理** – 將此動作類型用於假設使用者在訊息等級執行某些手動動作的動作。 例如，使用者可能會更新訊息的狀態。
- **使用者處理** – 將此動作類型用於假設使用者在訊息項目等級執行某些手動動作的動作。 例如，使用者可能會更新訊息項目的狀態。
- **Web 服務** – 將此動作類型用於應將生成的報告傳輸到 Web 服務的動作。 此動作類型不用於義大利採購和銷售發票通訊報告。 對於此動作類型，**訊息處理動作** 頁面包含一個 **惡意細節** FastTab，您可以在其中指定確認文字。 在將要求發送到所選 Web 服務之前，此確認文字會顯示給使用者。
- **要求驗證** – 使用此動作類型從伺服器請求驗證。

### <a name="initial-statuses-fasttab"></a>初始狀態 FastTab

> [!NOTE]
> **初始狀態** FastTab 不適用於初始動作類型為 **建立訊息** 的動作。

| 欄位               | 描述 |
|---------------------|-------------|
| 訊息項目狀態 | 選擇應評估所選訊息處理動作的訊息項目狀態。 |
| 描述         | 所選訊息項目狀態的描述。 |

### <a name="result-statuses-fasttab"></a>結果狀態 FastTab

| 欄位               | 描述 |
|---------------------|-------------|
| 訊息狀態      | 選擇應評估所選訊息處理動作的訊息狀態。 此欄位僅適用於在訊息等級評估的訊息處理動作。 例如，**電子報告匯出** 和 **電子報告匯入** 類型的動作可用，但不可用於 **使用者處理** 和 **訊息項目的動作執行等級** 類型。 |
| 描述         | 所選訊息狀態的描述。 |
| 回應類型       | 所選訊息狀態的回應類型。 |
| 訊息項目狀態 | 選擇在評估所選訊息處理動作後應該可用的結果狀態。 此欄位僅適用於在訊息項目等級評估的訊息處理動作。 例如，它可用於 **使用者處理** 和 **訊息項目執行等級** 類型的動作。 對於在訊息等級評估的訊息處理動作，此欄位會顯示為所選訊息狀態設定的訊息項目狀態。 |

下表顯示了必須為不同的動作類型和回應類型設定的結果狀態。

| 電子郵件動作類型/回應類型 | 已成功執行 | 商務錯誤 | 技術錯誤 | 使用者定義 | 取消 |
|----------------------------------------------|-----------------------|----------------|-----------------|--------------|--------|
| 建立訊息                               | X                     |                |                 |              |        |
| 電子報表匯出                  | X                     |                |                 |              |        |
| 電子報表匯入                  |                       |                |                 |              |        |
| Web 服務                                  | X                     |                | X               |              |        |
| 使用者處理                              |                       |                |                 |              |        |
| 訊息執行等級                      |                       |                |                 |              |        |
| 填入記錄                             |                       |                |                 |              |        |
| 訊息項目執行等級                 |                       |                |                 |              |        |
| 要求驗證                         | X                     | X              | X               |              |        |
| 電子報表匯出訊息          | X                     |                |                 |              |        |
| 訊息等級使用者處理                |                       |                |                 |              |        |

## <a name="electronic-message-processing"></a><a id="processing"></a>電子訊息處理

電子郵件處理是 EM 功能的一個基本概念。 這彙總了應該為電子訊息評估的動作。 可以透過使用初始狀態和結果狀態來連結動作。 或者，可以獨立啟動 **使用者處理** 類型的動作。 若要設定電子訊息處理，請前往 **稅務** \> **設置** \> **電子訊息** \> **電子訊息處理**，處理電子訊息。

**動作** FastTab 允許您將預定義的動作加入處理中。 您可以指定一個動作是否必須單獨執行，或者它是否可以由處理啟動。 若要指定處理中的動作只能由使用者初始化，請將該動作的 **單獨執行** 欄位設定為 **Yes**。 如果應通過處理處於定義為動作的初始狀態的狀態的訊息或訊息項目來啟動動作，請將 **單獨執行** 欄位設定為 **No**。 **使用者動作** 類型的操作必須始終單獨執行。

有時候，即使第一個動作設定為單獨執行，也必須將多個動作整合到一個序列中。 例如，使用者必須初始化報告生成。 但是，生成報告後，必須立即將其發送到 Web 服務，並且來自 Web 服務的回應必須反映在系統中。 在這種情況下，您可以為必須始終一起執行的動作建立不可分割的序列。 在 **動作** FastTab 上，選擇網格上方的 **不可分序列**，然後建立一個序列。 然後，對於必須在一個序列中一起執行的所有動作，請在 **不可分序列** 欄位中選擇序列。 對於此範例，對於序列中的第一個動作，可以將 **單獨執行** 欄位設定為 **Yes**，對於所有其他動作，可以將其設定為 **No**。

**電子報告匯出** 和 **電子報告匯出訊息** 類型的動作執行具有輸入參數的 ER 格式。 如果您的電子郵件處理包括其中任何一種類型的動作，您必須在生成報告之前指定輸入參數的值。 如此一來，系統可以使用批處理機制來生成報告。 您可以選擇網格上方的 **參數** 來設定所選動作類型的參數 (**電子報告匯出** 或 **電子報告匯出訊息**)。 為必須在批處理機制中使用指定參數執行的動作選項中 **使用參數** 核取方塊。

使用 **訊息項目附加欄位** FastTab 新增與訊息項目相關的預定義附加欄位。 您必須為與欄位相關的每種類型的訊息項目新增其他欄位。 您可以指定在處理期間將分配給附加欄位的預設值。

使用 **訊息附加欄位** FastTab 新增與訊息相關的預定義附加欄位。 您可以指定在處理期間將分配給附加欄位的預設值。

選用：在 **資訊安全角色** FastTab 上，為您的處理定義資訊安全角色，以限制對特定報告的存取。 具有特定角色的使用者將只能看到為該角色定義的處理。

使用 **批次** FastTab 將處理設置為以批處理方式工作。 當您在 **動作** 窗格上選擇執行處理以啟動處理時，我們建議您直接在 **電子訊息** 或 **電子訊息項目** 頁面上，為您的處理設定批次處理機制.
