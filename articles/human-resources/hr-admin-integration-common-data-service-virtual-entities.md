---
title: 配置 Dataverse 虛擬資料表
description: 本主題顯示如何配置、產生、更新既有虛擬資料表及分析產生且可用的 Dynamics 365 Human Resources 資料表。
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f7ffe522f0f17a21280e53728c6efc2823743733
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452526"
---
# <a name="configure-dataverse-virtual-tables"></a>配置 Dataverse 虛擬資料表


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Dynamics 365 Human Resources 是 Microsoft Dataverse 裡的虛擬資料來源。 它從 Dataverse 和 Microsoft Power Platform 提供完整的建立、讀取、更新和刪除 (CRUD) 操作。 虛擬資料表資料不儲存在 Dataverse，只儲存在應用程式資料庫。

若要啟用從 Dataverse 對人力資源實體進行 CRUD 操作，您必須使實體在 Dataverse 以虛擬資料表形式使用。 這能讓您從 Dataverse 和 Microsoft Power Platform 對人力資源的資料執行 CRUD 操作。 這些操作也支援人力資源的完整商務邏輯驗證，以確保將資料寫入實體時，資料的一致性。

> [!NOTE]
> 人力資源實體對應到 Dataverse 資料表。 更多有關 Dataverse (前身為 Common Data Service) 和術語更新的資訊，請參閱[何謂 Microsoft Dataverse？](/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>可用的人力資源虛擬資料表

Human Resources 中的所有開放性資料協議 (OData) 實體皆可在 Dataverse 當成虛擬資料表使用。 它們也可以在 Power Platform 使用。 您現在可以使用完整 CRUD 功能從人力資源直接建構含有資料的應用程式和體驗，無需將資料複製或同步到 Dataverse。 您可以使用 Power Apps 入口網站建構朝外運作的網站，為人力資源的業務流程啟用共同作業方案。

您可以檢視環境中啟用的虛擬資料表清單，並開始搭配 **Dynamics 365 HR 虛擬資料表** 解決方案中的 [Power Apps](https://make.powerapps.com) 資料表操作。

![Power Apps 中的 Dynamics 365 HR 虛擬資料表。](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>虛擬資料表與本機資料表之對照

人力資源虛擬資料表與針對人力資料建立的本機 Dataverse 資料表不同。 

人力資料本機資料表是在 Dataverse  裡的 HCM Common 解決方案分開產生與維護。 資料利用本機資料表儲存在 Dataverse 並且需要與人力資源應用程式資料庫同步。

> [!NOTE]
> 關於人力資料本機 Dataverse 資料表清單，請參閱 [Dataverse 資料表](./hr-developer-entities.md)。

## <a name="setup"></a>設定

請按照這些設定步驟在您的環境啟用虛擬表。

### <a name="enable-virtual-tables-in-human-resources"></a>在人力資源啟用虛擬資料表

首先您必須在 **功能管理** 工作區啟用虛擬資料表。

1. 請在人力資源選取 **系統管理**。

2. 請選取 **功能管理** 圖格。

3. 選取 **Dataverse 的人力資源虛擬資料表支援**，然後選取 **啟用**。

更多有關啟用和停用功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

### <a name="register-the-app-in-microsoft-azure"></a>在 Microsoft Azure 註冊應用程式

您必須在 Azure 入口網站註冊您的人力資源執行個體，Microsoft 身分識別平台才能為應用程式和用戶提供驗證和授權服務。 更多有關在 Azure 註冊應用程式的資訊，請參閱[快速入門：與 Microsoft 身分識別平台註冊應用程式](/azure/active-directory/develop/quickstart-register-app)。

1. 打開 [Microsoft Azure 入口網站](https://portal.azure.com)。

2. 請在 Azure 服務清單選取 **應用程式註冊**。

3. 選取 **新註冊**。

4. 請在 **名稱** 欄位輸入應用程式的描述性名稱。 例如，**Dynamics 365 Human Resources 虛擬資料表**。

5. 請在 **重新導向 URI** 欄位輸入您的人力資源執行個體命名空間 URL。

6. 請選取 **註冊**。

7. 註冊完成後，Azure 入口網站會顯示應用程式註冊的 **概觀** 窗格，其中包括它的 **應用程式 (用戶端) 識別碼**。 此時請記下 **應用程式 (用戶端) 識別碼**。 當您[配置虛擬資料表資料來源](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source)時，您將會輸入這項資訊。

8. 請在左側瀏覽窗格選取 **證書和密碼**。

9. 請在本頁的 **用戶端密碼** 區選取 **新用戶端密碼**。

10. 提供說明、選取持續時間和 **新增**。

11. 從資料表的 **值** 屬性記錄密碼值。 當您[配置虛擬資料表資料來源](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source)時，您將會輸入這項資訊。

    > [!IMPORTANT]
    > 此時請務必記下密碼值。 離開本頁之後，此密碼將不再顯示。

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>安裝 Dynamics 365 HR Virtual Table 應用程式

在您的 Power Apps 環境安裝 Dynamics 365 HR Virtual Table 應用程式，以便將虛擬資料表解決方案包佈署到 Dataverse。

1. 請在人力資源中打開 **Microsoft Dataverse 整合** 頁。

2. 請選取 **虛擬資料表** 索引標籤。

3. 選取 **安裝虛擬資料表應用程式**。

### <a name="configure-the-virtual-table-data-source"></a>配置虛擬資料表資料來源

下一步是在 Power Apps 環境配置虛擬資料表資料來源。

1. 打開 [Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com)。

2. 請在 **環境** 清單中選取與您的人力資源執行個體有關聯的 Power Apps 環境。

3. 請在本頁的 **細節** 部份選取 **環境 URL**。

4. 請在 **解決方案健康中心** 選取應用程式頁右上角的 **進階尋找** 圖示。

5. 請在 **進階尋找** 頁上的 **尋找** 下拉式清單選取 **財務和營運虛擬資料來源組態**。

   > [!NOTE]
   > 從上一個設定步驟安裝虛擬資料表應用程式可能需要幾分鐘。 如果 **財務和營運虛擬資料來源組態** 不在清單內，請稍候片刻，然後重新整理清單。

6. 選取 **結果**。

7. 選取 **Microsoft HR 資料來源** 記錄。

8. 輸入資料來源組態所需資料如下：

   - **確定目標 URL**：您的人力資源命名空間 URL。 確定目標 URL 格式為：
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     例如： 
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >請確定在 URL 結尾納入 "**/**" 字元避免收到錯誤訊息。

     >[!NOTE]
     >確定目標 URL 判定虛擬資料表將為資料指向的人力資源環境。 如果您藉由建立正式環境副本的方式建立沙箱環境，請將此值更新為新沙箱環境的命名空間 URL。 這可確保虛擬資料表連接到沙箱環境資料，而不是繼續指向正式環境。

   - **租用戶識別碼**：Azure Active Directory(Azure AD) 租用戶識別碼。

   - **AAD 應用程式識別碼**：為 Microsoft Azure 入口網站中註冊的應用程式建立的應用程式 (用戶端) 識別碼。 您已在[註冊 Microsoft Azure 裡的應用程式](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) 步驟前收到這項資訊。

   - **AAD 應用程式密碼**：在 Microsoft Azure 入口網站針對註冊的應用程式建立的用戶端密碼。 您已在[註冊 Microsoft Azure 裡的應用程式](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) 步驟前收到這項資訊。

   ![Microsoft 人力資源資料來源。](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. 請選取 **儲存和關閉**。

### <a name="grant-app-permissions-in-human-resources"></a>在人力資源授予應用程式權限

授予人力資源裡的兩個 Azure AD 人力資源應用程式權限：

- 在 Microsoft Azure 入口網站為您的租用戶建立的應用程式
- 在 Power Apps 環境安裝的 Dynamics 365 人力資源虛擬資料表應用程式 

1. 請在人力資源中打開 **Azure Active Directory 應用程式** 頁。

2. 請選取 **新建** 建立新應用程式記錄：

    - 請在 **用戶端識別碼** 欄位輸入您在 Microsoft Azure 入口網站註冊的應用程式用戶端識別碼。
    - 請在 **名稱** 欄位輸入您在 Microsoft Azure 入口網站註冊的應用程式名稱。
    - 請在 **使用者識別碼** 欄位選取具備人力資源管理員權限的用戶的用戶識別碼和 Power Apps 環境。

3. 請選取 **新建** 建立第二筆應用程式記錄：

    - **用戶端識別碼** f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **名稱**：Dynamics 365 HR 虛擬資料表
    - 請在 **使用者識別碼** 欄位選取具備人力資源管理員權限的用戶的用戶識別碼和 Power Apps 環境。

## <a name="generate-virtual-tables"></a>產生虛擬資料表

設定完成時，您可以選取希望在您的 Dataverse 執行個體中產生和啟用的虛擬資料表。

1. 請在人力資源中打開 **Microsoft Dataverse 整合** 頁。

2. 請選取 **虛擬資料表** 索引標籤。

> [!NOTE]
> **啟用虛擬資料表** 切換將設定為 **是**，當所有必要設定完成後自動執行。 如果切換設定為 **否**，請回顧本文件前面部分的步驟，確保所有前提條件設定已完成。

3. 請選取希望在 Dataverse 中產生的一個或多個資料表。

4. 請選取 **產生/重新整理**。

![Dataverse 整合。](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>檢查資料表產生狀態

虛擬資料生在 Dataverse 透過非同步背景流程產生。 在操作中心顯示流程的更新。 此段流程的詳細資訊，包括錯誤記錄，會顯示在 **流程自動化** 頁。

1. 請在人力資源中打開 **流程自動化** 頁。

2. 請選取 **背景流程** 索引標籤。

3. 請選取 **虛擬資料表輪詢非同步操作背景流程**。

4. 請選取 **檢視最近結果**。

滑出窗格會顯示流程的最近執行結果。 您可以檢視流程記錄，包括從 Dataverse 傳回的任何錯誤。

## <a name="see-also"></a>也請參閱

[何謂 Dataverse？](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Dataverse 中的資料表](/powerapps/maker/common-data-service/entity-overview)<br>
[資料表關係概觀](/powerapps/maker/common-data-service/relationships-overview)<br>
[建立和編輯包含外部資料來源的資料的虛擬資料表](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[何謂 Power Apps 入口網站？](/powerapps/maker/portals/overview)<br>
[在 Power Apps 中建立應用程式概觀](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
