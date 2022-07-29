---
title: 開始使用適用於墨西哥的電子開票功能
description: 本主題提供的資訊將幫助您開始使用適用於墨西哥的電子開票功能。
author: gionoder
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f512a6208bc85cd5796ce9515d2bc440f92ea79f
ms.sourcegitcommit: 5033d42a2aac852916d726e40bd98a164d1a837d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2022
ms.locfileid: "8451464"
---
# <a name="get-started-with-electronic-invoicing-for-mexico"></a>開始使用適用於墨西哥的電子開票功能

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> 墨西哥的電子發票目前可能不支援 Comprobante Fiscal Digital por Internet (CFDI) 文件以及內建於 Microsoft Dynamics 365 Finance 或 Dynamics 365 Supply Chain Management 的相關整合中提供的所有功能。

本主題提供的資訊將幫助您開始使用適用於墨西哥的電子開票功能。 引導您完成 Regulatory Configuration Services (RCS) 和 Finance 中與國家/地區相關的設定步驟。 還將引導您完成 Finance 中透過服務提交 CFDI 發票必須遵循的步驟，並說明如何查看處理結果和 CFDI 發票的狀態。

## <a name="prerequisites"></a>先決條件

在完成本主題中的步驟之前，您必須完成[開始使用電子開票服務管理](e-invoicing-get-started-service-administration.md)和[開始使用電子開票](e-invoicing-get-started.md)中的步驟。

## <a name="set-up-the-cadena-xslt"></a>設定 Cadena XSLT

要將 Cadena XSLT 結構描述新增到 CFDI 處理的全球化功能，請完成以下步驟。

1. 從 [SAT 網站](http://www.sat.gob.mx/sitio_internet/cfd/3/cadenaoriginal_3_3/cadenaoriginal_3_3.xslt)下載結構描述。
2. 將結構描述壓縮為 ZIP 檔案。
3. 將 xslt 檔案儲存到在服務環境中為新容器設定的 Azure 儲存體帳戶。

## <a name="rcs-setup"></a>RCS 設定

在 RCS 設定期間，您將完成以下工作：

1. 匯入電子開票功能以處理 CFDI 發票。
2. 查看產生、提交和接收有關 CFDI 發票的回應，以及提交和接收有關取消的回應所需的格式設定。
3. 設定支援 CFDI 開票提交方案的事件。
4. 發佈 CFDI 發票的電子開票功能。

> [!NOTE]
> 「電子開票功能」是設定和發佈以使用電子開票伺服器的資源的通用名稱。 在這種情況下，CFDI 發票 (MX) 是您要設定的電子開票功能。

## <a name="import-the-e-invoicing-feature"></a>匯入電子開票功能

1. 登入您的 RCS 帳戶。
2. 在 **全球化功能** 工作區的 **功能** 區段中，選擇 **電子開票** 圖格。
3. 在 **電子開票功能** 頁面，選擇 **匯入** 以從全域存放庫中匯入 **CFDI 發票 (MX)**。

    > [!NOTE]
    > 如果您沒有在清單中看到該功能，請選擇 **同步**，然後重複步驟 3。

![匯入 CFDI 發票 (MX) 功能。](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

從全域存放庫匯入 **CFDI 發票 (MX)** 功能時，還將匯入所有功能設定，包括設定和動作。

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>建立新版本的 CFDI 發票 (MX) 功能

例如，如果必須更新 URL，您可以建立新版本。 更多資訊，請參閱[電子開票 CFDI](tasks/mx-00010-e-invoicing-cfdi.md)。

- 在 **電子開票功能** 頁面的 **版本** 索引標籤，選擇 **新增**。

![新增電子開票功能版本。](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>更新設定版本

1. 在 **電子開票功能** 頁面的 **設定** 索引標籤，選擇 **新增** 或 **刪除** 以管理設定版本 (ER 檔案格式設定)。

    ![管理電子開票功能設定。](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    建立新版本時，所有設定都繼承自上次發佈的版本。 要處理 CFDI 發票，需要以下設定：

    - CFDI 發票 (BusinessDocumentService)
    - CFDI 回應訊息匯入
    - CFDI 錯誤記錄匯入
    - CFDI 取消要求 (MX) (BusinessDocumentService)
    - CFDI 發票 (BusinessDocumentService)

2. 在清單中，選擇一個設定版本，然後選擇 **編輯** 或 **查看** 以打開 **格式設計工具** 頁面，您可以在其中編輯或查看設定。

    ![打開格式設計工具頁面。](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. 使用 **格式設計工具** 頁面以編輯和查看 ER 格式檔案設定。 如需相關資訊，請參閱[建立電子文件設定](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md)。

    ![格式設計工具頁面。](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>管理電子開票功能設定

- 在 **電子開票功能** 頁面的在 **設定** 索引標籤，選擇 **新增**、**刪除** 或 **編輯** 來管理電子開票功能設定。

![管理電子開票功能設定。](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

要提交 CFDI 發票以進行授權 (產生 XML 文件、提交 XML 文件並處理回應)，需要 **銷售發票** 功能設定。

要提交 CFDI 發票取消，需要 **消除** 和 **取消** 功能設定。

### <a name="configure-the-sales-invoice-feature-setup"></a>設定銷售發票功能設定

1. 在 **電子開票功能** 頁面的 **設定** 索引標籤，在 **功能設定** 欄，選擇 **銷售發票**。
2. 選擇 **編輯** 以設定動作、適用性規則和變數。

    ![編輯電子開票功能設定。](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. 在 **功能版本設定** 頁面，選擇 **動作** 索引標籤以管理動作清單。 動作定義必須按順序執行以完成事件的完整執行的動作清單。

    ![動作索引標籤。](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | 動作識別碼 | 動作                   | 動作名稱                                  | 動作描述                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | 轉換文件       | 產生不包含數位簽章的 CFDI 電子發票 | 產生 CFDI 電子發票。                                |
    | 2         | 簽署文件            | 數位簽章                                 | 對電子發票進行數位簽章以進行提交。                |
    | 3         | 呼叫墨西哥 PAC 服務 | 提交 CFDI 電子發票                        | Windows Communication Foundation (WCF) 用戶端提交 CFDI 電子發票。 |
    | 4         | 處理回應         | 分析 Web 服務回應                 | 分析 Web 服務回應，並傳回錯誤記錄。 |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>設定墨西哥 PAC Web 服務的 URL 

1. 在 **功能版本設定** 頁面的 **動作** 索引標籤中，在 **動作** FastTab，選擇 **呼叫墨西哥 PAC 服務**。
2. 在 **參數** FastTab 的 **URL 地址** 欄位，輸入用於提交 CFDI 發票的 Web 服務的 URL。

> [!NOTE]
> 使用相同的步驟為 **取消** 和 **取消要求** 功能設定更新 **呼叫墨西哥 PAC 服務** 動作的 URL。

### <a name="set-up-the-path-for-the-cadena-xlst-schema"></a>設定 Cadena XLST 結構描述的路徑

1. 在 **功能版本設定** 頁面的 **變數** 索引標籤，選擇變數名稱 **DigitalSignatureXSLT**。
2. 在 **值** 欄位輸入：{"containerUrl":"https://&lt;AccountStorageName&gt;.blob.core.windows.net/&lt;ContainerName&gt;","path":"&lt;RelativePath&gt;"}
   
    其中：<RelativePath> = folder\\folder\\filename，使用雙反斜線，ContainerName 必須表示用於服務的容器。
   
    變數的範例是：
    
    {"path":"xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\\dev\\cadena_xslt","containerUrl":https://yyyyyyyyyy.blob.core.windows.net/containername}

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>將草稿版本指派給電子開票環境

1. 在 **電子開票功能** 頁面的 **環境** 索引標籤，選擇 **啟用**。
2. 在 **環境** 欄位中，選擇環境。
3. 在 **生效開始日期** 欄位，選擇環境應生效的日期。
3. 選取 **啟用**。

![啟用電子開票環境。](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>將版本狀態變更為 [已完成]

1. 在 **電子開票功能** 頁面的 **版本** 索引標籤，選擇狀態為 **草稿** 的電子開票功能版本。
2. 選取 **變更狀態 \> 完成**。

## <a name="change-the-version-status-to-published"></a>將版本狀態變更為 [已發佈]

- 在 **電子開票功能** 頁面的 **版本** 索引標籤，選擇 **變更狀態 \> 發佈**。

## <a name="publish-the-e-invoicing-feature"></a>發佈電子開票功能

1. 在 **電子開票功能** 頁面上，選擇 **版本** 索引標籤，管理 **CFDI 發票 (MX)** 功能的狀態。
2. 選擇 **變更狀態** 變更功能的狀態。

![變更電子開票功能的狀態。](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing--integration-in-finance"></a>在 Finance 中設定電子開票整合

要在 Finance 中設定電子開票，您將完成以下任務：

1. 匯入 ER 資料模型、ER 資料模型對應以及 CFDI 發票所需的格式。
2. 設定更新 CFDI 發票的回應類型。 這些回應類型用於來自授權憑證提供者 (PAC) 伺服器的回應。

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>匯入 CFDI 發票的 ER 資料模型、ER 資料模型對應和內容設定

1. 登入 Finance。
2. 在 **電子報表** 工作區的 **設定提供者** 區段，選擇 **Microsoft** 標題。 確保此設定提供者設定為 **使用中**。 有關如何將提供者設定為 **使用中** 的資訊，請參閱[建立設定提供者並將其標記為使用中](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)。
3. 選擇 **存放庫**。
4. 選取 **全域資源 \> 打開**。
5. 匯入 **發票模型**、**發票模型對應**、**CFDI 發票格式 (MX)**、**CFDI 發票取消要求格式 (MX)** 和 **CFDI 發票取消格式 (MX)**。

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>開啟處理 CFDI 發票的功能

1. 前往 **組織管理 \> 設定 \> 電子文件參數**。
2. 在 **功能** 索引標籤，選擇功能參考 **MX-00010** 和 **MX-00016** 列中的 **啟用** 核取方塊。

![開啟處理 CFDI 發票的功能。](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>匯入 ER 設定並設定更新 CFDI 發票的回應類型

#### <a name="import-er-configurations"></a>匯入 ER 設定

1. 在 **電子報表** 工作區的 **設定提供者** 區段，選擇 **Microsoft** 標題。
3. 選擇 **存放庫**。
4. 選取 **全域資源 \> 打開**。
5. 匯入 **回應訊息模型**、**CFDI 錯誤記錄匯入 (MX)** 和 **CFDI 回應訊息匯入 (MX)**。

#### <a name="set-up-the-response-types"></a>設定回應類型

1. 前往 **組織管理 \> 設定 \> 電子文件參數**。
2. 在 **電子文件** 索引標籤上，選擇 **新增**。
3. 輸入客戶發票日記帳，然後在 **資料表名稱** 欄位，選擇專案發票。
4. 對於每個資料表，定義相關的文件內容：

    - 如果是 **客戶發票日記帳**，輸入 **客戶發票內容**。
    - 如果是 **專案發票**，輸入 **專案發票內容**。

4. 選擇 **回應類型** 以設定可以從電子開票傳回並包含在客戶發票日記帳或專案發票中的回應類型。
5. 選擇 **新增**，然後在 **回應類型** 欄位中選擇 **回應**。
6. 請在 **提交狀態** 欄位，選取 **待處理**。
7. 在 **模型對應** 欄位，選擇 **回應訊息匯入格式 – 來自回應訊息的模型對應**。
8. 選擇 **儲存**。
9. 選擇 **新增**，然後在 **回應類型** 欄位中選擇 **ResponseData**。
10. 請在 **提交狀態** 欄位，選取 **待處理**。
11. 在 **模型對應** 欄位，選擇 **CFDI 回應資料匯入格式 (詳細資料) - 回應資料匯入**。
12. 選擇 **儲存**。

## <a name="process-electronic-invoices-in-finance"></a>在 Finance 中處理電子發票 

透過電子開票在 Finance 中處理 CFDI 發票期間，您可以執行以下工作：

- 提交 CFDI 發票。
- 檢視提交執行記錄。
- 提交取消 CFDI 發票。

### <a name="submit-cfdi-invoices"></a>提交 CFDI 發票

開啟 **可設定的電子開票整合** 功能後，將不再使用用於提交 CFDI 發票的 **匯出/匯入電子發票** 流程 (**應收帳款 \> 發票 \> 電子發票**)。 取而代之的是名為 **提交電子文件** 的新流程。

> [!NOTE]
> 使用新版的 **提交電子文件** 流程之前，請先確認是否已完成墨西哥電子發票所需的設定。 有關詳細資訊，請參閱 [CFDI 配置版本 3.3](./latam-mex-cfdi-3-3.md)。

1. 前往 **組織管理 \> 定期 \> 電子文件 \> 提交電子文件**。
2. 對於任何文件的首次提交，請一律將 **重新提交文件** 選項設定為 **否**。 如果您必須透過該服務重新提交文件，請將此選項設定為 **是**。
3. 在 **要包括的記錄** FastTab，選擇 **篩選** 以打開 **查詢** 對話方塊，您可以在其中組建查詢以選擇要提交的文件。

![提交 CFDI 文件。](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> 在您首次嘗試透過該服務提交文件時，系統將提示您確認與電子開票的連線。 選擇 **點擊此處以連接電子文件提交服務**。

### <a name="view-submission-logs"></a>檢視提交記錄

您可以查看所有提交文件的提交記錄，也可以查看一個提交文件的提交記錄。

#### <a name="view-all-submission-logs"></a>檢視全部提交記錄

開啟 **可設定的電子開票整合** 功能後，將出現一個新頁面，可讓您跟進文件提交流程。 您可以使用此頁面查看所有已提交文件的提交記錄。

1. 前往 **組織管理 \> 定期 \> 電子文件 \> 電子文件提交記錄**。
2. 在 **文件類型** 欄位，選擇 **客戶發票日記帳** 以篩選所需的電子文件。

    ![選擇文件類型以查看提交記錄。](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. 在動作窗格上，選擇 **查詢 \> 提交詳細資料** 以查看提交執行記錄的詳細資訊。

    ![查看提交記錄詳細資訊。](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

提交記錄中的資訊分為三個 FastTab：

- **處理動作** - 此 FastTab 顯示在 RCS 中設定的功能版本中設定的動作執行記錄。 **狀態** 欄顯示動作是否成功執行。
- **動作檔案** - 此 FastTab 顯示在執行動作期間產生的中間檔案。 你可以選擇 **查看** 以下載和查看檔案。
- **處理動作記錄** – 此 FastTab 顯示電子開票與目標 Web 服務之間的通訊結果。 它還顯示了從 Web 服務處理傳回的內容。 **錯誤碼** 欄顯示授權 Web 服務傳回的傳回代碼。

提交的 CFDI 發票獲得授權後，其狀態將更新為 **已核准**。

#### <a name="view-submission-logs-from-cfdi-invoices"></a>查看 CFDI 發票的提交記錄

開啟 **可設定的電子開票整合** 功能後，您還可以查看來自 CFDI 發票的提交記錄。

1. 前往 **應收帳款 \> 查詢和報告 \> CFDI (電子發票)**。
2. 選擇打開 **可設定的電子開票整合** 功能後提交的 CFDI 發票。
3. 在動作窗格上的 **歷史記錄** 索引標籤中，選擇 **電子文件記錄**。

![查看 CFDI 發票的提交記錄。](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> 對於在打開 **可設定的電子開票整合** 功能之前提交的 CFDI 發票，可使用 **歷史記錄** 按鈕。 對於在打開 **可設定的電子開票整合** 功能之後提交的 CFDI 發票，無法使用 **歷史記錄** 按鈕。

### <a name="submit-cancellation-of-cfdi-invoices"></a>提交取消 CFDI 發票

打開 **可設定的電子開票整合** 功能後，不再使用舊的取消 CFDI 發票流程。 取而代之的是嵌入在 **電子發票提交記錄** 頁面上的新取消流程。

1. 前往 **應收帳款 \> 查詢和報告 \> CFDI (電子發票)**。
2. 如果 CFDI 發票的狀態為 **已核准**，則選擇 **功能 \> 取消 CFDI**。
3. 前往 **組織管理 \> 定期 \> 電子文件 \> 電子文件提交記錄**。
4. 選擇 CFDI 發票，然後選擇 **功能\>發送相關提交**。
5. 輸入相關提交的描述，然後選擇 **確定**。

#### <a name="view-cancellation-submission-logs"></a>檢視取消提交記錄

1. 前往 **組織管理 \> 定期 \> 電子文件 \> 電子文件提交記錄**。
2. 在 **文件類型** 欄位，選擇 **客戶發票日記帳** 以僅篩選出客戶發票日記帳文件。
3. 選擇 CFDI 發票，然後在動作窗格上，選擇 **查詢 \> 相關提交**。

    **相關提交** 頁面顯示指定 CFDI 發票的所有相關提交及其提交狀態。 在下圖中，第一行表示要求核准 CFDI 發票的提交。 第二行代表取消該 CFDI 發票的提交。

    ![檢視取消提交記錄。](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. 在動作窗格上，選擇 **查詢 \> 提交詳細資料** 以查看提交執行記錄的詳細資訊。

    ![查看取消提交記錄詳細資訊。](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>隱私權注意事項
啟用 **CFDI 墨西哥電子發票 (MX)** 功能可能需要發送有限的資料，其中包括組織稅務登記識別碼。 這將傳輸到稅務機關授權的第三方機構，以便以與政府網路服務整合所需的預定義格式向該稅務機關發送電子發票。 管理員可以瀏覽至 **組織管理 \> 設定 \> 電子文件參數** 啟用和停用 **CFDI 墨西哥電子發票 (MX)** 功能。 選取 **功能** 索引標籤，選擇包含 **CFDI 墨西哥電子發票 (MX)** 功能的列，然後進行適當的選擇。 從這些外部系統匯入此 Dynamics 365 線上服務的資料受[隱私權聲明](https://go.microsoft.com/fwlink/?LinkId=512132)約束。 有關詳細資訊，請查閱特定國家/地區特定功能文件中的「隱私權聲明」區段。

## <a name="additional-resources"></a>其他資源

- [電子開票概觀](e-invoicing-service-overview.md)
- [開始使用電子開票](e-invoicing-get-started.md)
- [設定電子開票](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
