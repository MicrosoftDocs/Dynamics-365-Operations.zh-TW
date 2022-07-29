---
title: 建立重覆性資料匯出 App
description: 本主題說明在重覆性排程基礎上，建立 Microsoft Azure 邏輯應用程式從 Microsoft Dynamics 365 Human Resources 匯出資料。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 368eee6bb182f363f47467a5c5ad8208a57db7ec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452583"
---
# <a name="create-a-recurring-data-export-app"></a>建立重覆性資料匯出 App


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

本主題說明在重覆性排程基礎上，建立 Microsoft Azure 邏輯應用程式從 Microsoft Dynamics 365 Human Resources 匯出資料。 本教學課程充分運用 Human Resources 的 DMF 封包 REST 應用程式編寫程式界面 (API) 來匯出資料。 資料匯出後，邏輯應用程式將匯出的資料儲存到 Microsoft OneDrive 商業資料夾。

## <a name="business-scenario"></a>商務案例

在一個典型的 Microsoft Dynamics 365 整合商務方案中，資料務必以重覆性排程匯出到下游系統。 本教學課程顯示從 Microsoft Dynamics 365 Human Resources 匯出所有背景工作角色記錄，及將背景工作角色清單儲存在OneDrive 商務資料夾的方法。

> [!TIP]
> 在本教學課程匯出的特定資料和匯出資料目的地只是範例，僅供參考。 您可以輕鬆變更它們以符合您的業務需求。

## <a name="technologies-used"></a>使用的技術

本教學課程使用技術如下：

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – 將被匯出的背景工作角色主資料來源。
- **[Azure Logi Apps](https://azure.microsoft.com/services/logic-apps/)** – 提供協調流程的技術與重覆性匯出的排程。

    - **[連接器](/azure/connectors/apis-list)** – 用來連接邏輯應用程式到所需端點的技術。

        - [HTTP 與 Azure AD](/connectors/webcontents/) 連接器
        - [OneDrive 商業用途](/azure/connectors/connectors-create-api-onedriveforbusiness) 連接器

- **[DMF 封包 REST API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** – 用來觸發匯出與監控進度的技術。
- **[OneDrive 商業用途](https://onedrive.live.com/about/business/)** – 匯出背景工作角色的目的地。

## <a name="prerequisites"></a>先決條件

開始本教學課程的練習題之前，您必須備妥下列各項：

- 具備環境管理員級權限的 Human Resources 環境
- 託管邏輯應用程式的 [Azure 訂閱](https://azure.microsoft.com/free/)

## <a name="the-exercise"></a>練習題

本練習題結束時，您將擁有連接您的 Human Resources 環境和您的 OneDrive 商業帳戶的邏輯應用程式。 邏輯應用程式將從 Human Resources 匯出資料封包，等待匯出完成、下載匯出的資料封包後儲存在您指定的 OneDrive 商業資料夾。

完成的邏輯應用程式將仿照下圖。

![邏輯應用程式概觀。](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>第 1 步：在 Human Resources 建立資料匯出專案

請在 Human Resources 建立匯出背景工作角色的資料匯出專案 為專案命名為 **匯出背景工作角色**，並確定 **產生資料封包** 選項設定為 **是**。 新增單一實體 (**背景工作角色**) 到專案，然後選取要匯出的格式。 (本教學課程使用 Microsoft Excel 格式。)

![匯出背景工作角色資料專案。](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> 請記住資料匯出專案的名稱。 當您下一步建立邏輯應用程式時將會需要它。

### <a name="step-2-create-the-logic-app"></a>步驟 2：建立邏輯應用程式

大量練習題涉及建立邏輯應用程式。

1. 請在 Azure 入口網站建立邏輯應用程式。

    ![邏輯應用程式建立頁面。](media/integration-logic-app-creation-1.png)

2. 請從 Logic Apps Designer 的空白邏輯應用程式開始。
3. 新增[重覆性排程觸發程序](/azure/connectors/connectors-native-recurrence)每 24 小時執行一次邏輯應用程式 (或根據您選擇的時程)。

    ![重覆性對話方塊。](media/integration-logic-app-recurrence-step.png)

4. 呼叫 [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API 排程您的資料封包匯出。

    1. 請從 HTTP Azure AD 連接器使用 **叫用 HTTP 要求** 的動作。

        - **基礎資源 URL：** 您的 Human Resources 環境 URL (不封包括路徑/命名空間資訊。)
        - **Azure AD 資源 URL：** `http://hr.talent.dynamics.com`

        > [!NOTE]
        > Human Resources 服務尚未提供連接器公開構成 DMF 封包 REST API 的所有 API，例如 **ExportToPackage**。 您反而必須透過 HTTP Azure AD連接器使用原始 HTTPS 要求調用 API。 此連接器使用 Azure Active Directory (Azure AD) 進行 Human Resources 的驗證和授權。

        ![HTTP Azure AD 連接器。](media/integration-logic-app-http-aad-connector-step.png)

    2. 透過 HTTP Azure AD 連接器登入您的 Human Resources 環境。
    3. 設定 HTTP **POST** 要求呼叫 **ExportToPackage** DMF REST API。

        - **方法：** POST
        - **要求的 URL：** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **要求本文：**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![叫用 HTTP 要求動作。](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > 您可能想要重新命名每個步驟，讓它比預設名稱更有意義，**叫用 HTTP 要求**。 例如，您可以重新命名這個步驟 **ExportToPackage**。

5. [初始化變數](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable)以便儲存 **ExportToPackage** 要求的執行狀態。

    ![初始化變數動作。](media/integration-logic-app-initialize-variable-step.png)

6. 請等到資料匯出的執行狀態為 **成功**。

    1. 新增 [直到迴圈](/azure/logic-apps/logic-apps-control-flow-loops#until-loop)重複到 **執行狀態** 變數值為 **成功** 為止。
    2. 新增 **延遲** 動作，在目前匯出的執行狀態輪詢之前等待五秒鐘的動作。

        ![直到迴圈 Container 為止。](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > 將限制計數設定為 **15** 以便等待最長 75 秒 (15 次反覆運算 × 5 秒) 完成匯出。 如果您的匯出需要更長時間，請適時調整限制計數。        

    3. 新增 **叫用 HTTP 要求** 動作以便呼叫 [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API，並設定 **執行狀態** 變數為 **GetExecutionSummaryStatus** 的回覆結果。

        > 本範例並不檢查錯誤。 **GetExecutionSummaryStatus** API 可以傳回未成功的終端機狀態 (亦即，**成功** 以外的狀態)。 更多資訊，請參閱 [API 文件](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus)。

        - **方法：** POST
        - **要求的 URL：** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities..GetExecutionSummaryStatus
        - **要求本文：** body('Invoke\_an\_HTTP\_request')?['value']

            > [!NOTE]
            > 您可能需要在 Designer 的程式碼視圖或函數編輯器裡輸入 **要求本文** 值。

        ![叫用 HTTP 要求 2 動作。](media/integration-logic-app-get-execution-status-step.png)

        ![設定變數動作。](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > **設定變數** 動作值 (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) 將有別於 **叫用 HTTP 要求 2** 本文值，即使 Designer 將以相同方式顯示值。

7. 取得匯出封包的下載 URL。

    - 新增 **叫用 HTTP 要求** 動作以便呼叫 [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API。

        - **方法：** POST
        - **要求的 URL：** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **要求本文：**{ "executionId"：body('GetExportedPackageURL')?['value']}

        ![GetExportedPackageURL 動作。](media/integration-logic-app-get-exported-package-step.png)

8. 下載匯出的封包。

    - 新增 HTTP **GET** 要求 (內建的 [HTTP 連接器動作](/azure/connectors/connectors-native-http)) 以便從上一步傳回的 URL 下載封包。

        - **方法：** GET
        - **URI：** body('Invoke\_an\_HTTP\_request\_3').value

            > [!NOTE]
            > 您可能需要在 Designer 的程式碼視圖或函數編輯器裡輸入 **URL** 值。

        ![HTTP GET 動作。](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > 本項要求不需要任何額外驗證，因為 **GetExportedPackageUrl** API 傳回的 URL 包括共用存取簽章 Token，授予下載檔案的訪問權。

9. 使用 [OneDrive 商務版](/azure/connectors/connectors-create-api-onedriveforbusiness)連接器儲存下載的封包。

    - 新增 OneDrive 商務版[建立檔案](/connectors/onedriveforbusinessconnector/#create-file)動作。
    - 根據需求連接到您的 OneDrive 商務帳戶。

        - **資料夾路徑：** 您選擇的資料夾
        - **檔案名稱：** worker\_package.zip
        - **檔案內容：** 上一步的本文 (動態內容)

        ![建立檔案動作。](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>步驟 3：測試邏輯應用程式

若要測試您的邏輯應用程式，請選取 Designer 中的 **執行** 按鈕。 您將會看到邏輯應用程式開始執行的步驟。 30 到 40 秒鐘後，邏輯應用程式應該完成執行動作，而您的 OneDrive 商務版資料夾應包括內含匯出背景工作角色的新封包檔案。

如果有任何一步回報失敗，請在 Designer 選取失敗的步驟，然後檢查它的 **輸入** 和 **輸出** 欄位。 根據需求偵錯和調整步驟以便改正錯誤。

下圖顯示當所有邏輯應用程式步驟執行成功時，Logic Apps Designer 的外觀。

![成功的邏輯應用程式執行。](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>摘要

在本教學課程中，您已經學習到如何使用邏輯應用程式從 Human Resources 匯出資料，並將匯出的資料儲存到 OneDrive 商務資料夾。 您可以根據需求修改本教學課程的步驟以符合您的業務需求。




[!INCLUDE[footer-include](../includes/footer-banner.md)]
