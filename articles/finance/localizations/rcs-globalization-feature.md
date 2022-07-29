---
title: Regulatory Configuration Service (RCS) - 全球化功能
description: 本主題解釋如何使用 Microsoft Regulatory Configuration Services (RCS) 和 Global 存放庫建立和使用 Globalization 功能。
author: JaneA07
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: e8df8a56d493e58f28699a87dd9dab1f87540a4ee327450384f89e6d426ba1a7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450630"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a>Regulatory Configuration Service (RCS) - 全球化功能

[!include [banner](../includes/banner.md)]

您可以使用 Microsoft Regulatory Configuration Services (RCS) 建立可在 Globalization 服務使用的 Globalization 功能，例如電子發票服務。 RCS 可讓您執行任務如下：

- 定義相關功能組成要素。
- 透過功能狀態管理功能生命週期。
- 開放定義的環境使用功能。
- 與其他組織共用功能。

下列程序解釋 RCS 使用者如何新增 Globalization 功能和相關組成要素、更新功能狀態及開放使用功能，以便可在 Globalization 服務使用。

完成這些程序之前，您必須完成與下列任務有關的步驟：

- 存取 RCS 執行個體。
- 建立和啟動組態提供者。 更多資訊，請參閱[建立組態提供者並標示為有效](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)。

請在您的財務和營運應用程式執行個體按照下列步驟進行。

1. 前往 **組織管理**\>**工作區**\>**電子報表**。
2. 如果貴公司未佈建任何 RCS 環境，請選取 **Regulatory Services - 組態**，並按照說明佈建一個。

> [!NOTE]
> 如果貴公司已經佈建 RCS 環境，請使用頁面 URL 選取登入選項存取此環境。

## <a name="turn-on-the-globalization-features"></a>開啟 Globalization 功能

1. 在您的 RCS 執行個體中，選取 **功能管理** 圖格。
2. 請在 **功能管理** 工作區，在清單中選取 **全球功能**，然後選取 **立即啟用**。

    ![功能管理中的 Globalization 功能。](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a>全球化功能

若要使用全球化功能，您必須先從全域存放庫匯入並建立您自己的版本。 新增全域功能有兩種方法：

- 新增以發佈或共用既有功能為主的衍生功能。
- 新增您從頭開始建立的新功能。

## <a name="access-globalization-features"></a>存取全球化功能

1. 請確定功能管理已經開啟 **全球化功能** 的功能，如本主題稍早所述。
2. 打開新 **全球化功能** 工作區，並在 **功能** 下方選取 **電子發票** 圖格。

    ![全球功能工作區。](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    **電子發票功能** 頁面已打開。

    ![電子發票功能頁面。](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a>新增衍生的全球化功能

您可以藉由從已發佈或共用的既有功能衍生，進而新增新全球化功能。

1. 選取 **匯入** 以便打開 **從全域存放庫匯入功能** 頁。

    ![從全域存放庫匯入功能頁。](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. 選取 **同步** 獲得最新功能。

    同步清單包括開放您使用的功能，因為它們由 Microsoft 發佈，或者因為它們由另一個組態提供者與您共用。

    ![同步功能清單。](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. 請在清單選取要匯入的功能，並選取 **匯入**。 成功匯入選取功能時，您會收到一則訊息。

    ![成功匯入的訊息。](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. 選擇 **新增**，然後在下拉式對話方塊中選擇 **根據現有版本** 選項。
5. 輸入功能的名稱和描述。
6. 在開放使用功能清單中，選取功能的基本版本，然後選取 **建立功能**。

    ![新增衍生的功能。](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    您新增的功能已經建立，狀態是 **草稿**。

    ![狀態是草稿的衍生功能。](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. 查看功能元件以確定是否需要更新：

    - 審核組態，以防您需要客製化電子申報 (ER) 格式及綁定功能版本的格式測繪。
    - 審核設定，以防您需要客製化功能版本的 **動作** 索引標籤、**適用規則** 索引標籤或 **變數** 索引標籤。

8. 請在 **版本** 索引標籤上，選取 **生效** 日期，如果 **說明** 欄位為空白，也輸入說明。
9. 選取 **更改狀態** 完成此功能。 完成的功能可開放特定環境使用，方便用於全球化服務，或者發佈到全域存放庫。

> [!NOTE]
> **發佈** 為 **功能版本狀態** 值的力能可以與外部組織共用。

## <a name="add-a-new-globalization-feature"></a>新增全球化功能

您可以藉由從頭開始建立的方式新增全球化功能。

1. 請在 **從全域存放庫匯入功能** 頁面上，選取 **新增**，接著在下拉式對話方塊選取 **新功能** 選項。
2. 輸入功能的名稱和描述。
3. 選取 **建立功能**。

    ![新增功能。](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. 請在 **版本** 索引標籤上，選取 **生效** 日期和 **更改狀態** 完成此功能。 完成的功能可開放特定環境使用，方便用於全球化服務，或者發佈到全域存放庫。

> [!NOTE]
> **發佈** 為 **功能版本狀態** 值的力能可以與外部組織共用。

## <a name="feature-component-overview"></a>功能組成要素概觀

全球化功能有幾個組成要素：

- **版本** – 此組成要素支援功能生命週期管理，並讓使用者管理不同功能版本的狀態。
- **組態** – 此組成要素讓使用者管理、檢視和編輯有關的 ER 格式和格式測繪。
- **設置** – 此元件允許全域化服務 (例如電子發票服務) 的使用者管理相關功能版本的設定。 因此，它支持靈活建構通訊和回應規則。
- **環境** – 此組成要素讓全球化服務 (例如電子發票服務) 的使用者管理使用功能版本設定的環境，並授予將可存取的使用者權限。
- **組織** – 此組成要素讓使用者與外部組織共用此功能。

## <a name="configuring-feature-components"></a>配置功能組成要素

### <a name="version-and-status"></a>版本和狀態

此版本用來管理全球化功能生命週期。

狀態可在 **版本** 索引標籤上的 **狀態** 欄位更改。目前開放使用的狀態如下：

- **草稿** – 只能在此狀態下編輯功能。
- **完成** – 功能和所有相關組成要素已經定案 (已完成) 並且無法編輯。
- **發佈** – 此功能和所有相關組成要素已經發佈到全域存放庫。
- **已共用** – 此功能和所有相關組成要素已和外部組織共用。
- **已啟用** – 此功能和所有相關組成要素已經啟用，可用於全球化服務，例如電子發票服務。

> [!NOTE]
> 功能必須依照順序經歷其中一些狀態。 因此，並非每個狀態都可能在每個生命週期階段開放使用。

### <a name="configurations"></a>配置

下列動作可用於組態：

- **檢視** – 檢視不需要任何更新的基本功能組態。
- **編輯** – 建立選取組態的草稿版本，以便在格式設計器中編輯格式或格式測繪。
- **刪除** – 從功能刪除選取的組態。
- **重訂基底** – 重訂功能基底。 更多資訊，請參閱本主題稍候介紹的[重訂衍生全球化功能基底](#rebase)章節。

### <a name="setups"></a>設定

下列動作可用於功能設定：

- **新增** – 建立新功能設定。 此功能設定會從既有的功能設定衍生或從頭開始建立。
- **刪除** – 刪除選取的功能設定。
- **檢視** – 檢視不需要任何更改的基本功能設定。
- **編輯** – 建立、刪除或修改功能設定的三個主要組成要素的屬性：

    - 動作和它們的參數
    - 適用性規則
    - 變數

![功能版本設定頁。](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a>環境

下列動作開放環境使用：

- **啟用** – 以選取的功能版本而言，選取已發佈的環境和它應該開放使用的 **生效** 日期。 更多資訊，請參閱本主題稍候介紹的[配置啟用環境](#configureenvironment)章節。
- **取消** – 移除功能設定環境。

### <a name="organizations"></a>組織

按照以下步驟，與外部組織共用全球化功能。

1. 請在 **電子發票功能** 頁面，選取要共用的功能與功能版本。
2. 請在 **組織** 索引標籤上，選取 **共用對象**，接著在下拉式對話方塊輸入組織的網域名稱。
3. 選取 **共用**。

    ![與組織共用功能。](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

本功能與選取的組織共用，並開放 Global 存放庫的組織使用。 此功能可以從那裡匯入組織的 RCS 執行個體或 Dynamics 365 Finance 方便使用。

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a>重訂衍生的全球化功能基底

您可以將衍生的全球化功能基底重訂為全新或更新的基底功能版本。 如此一來就能自動更新基底版本已經發生的更改。 更新後的基底功能版本由原始組態提供者建立，接著發佈或共用。

![更新後的基底功能版本。](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

例如，如果您想重訂已建立的衍生功能版本基底，您必須先藉由從 Global 存放庫匯入才能取得最新的功能版本。

1. 請在 **電子發票功能** 頁，選取 **匯入**。
2. 選取 **同步** 獲得最新功能。
3. 請在功能清單，選取要匯入的功能，並選取 **匯入**。

    ![匯入最新版本的功能。](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. 在功能清單中，選擇要重訂基底的功能。
5. 請在 **版本** 索引標籤上，選取 **新增** 以建立草稿版本。

    ![已建立新草稿版本。](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. 選取 **重訂基底**。
7. 請在 **重訂基底** 對話方塊，選取要重訂基底的最新功能版本。

    ![重訂基底對話方塊。](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. 選取 **確定**。
9. 查看功能元件，並進行所需的任何變更。
10. 選取 **更改狀態** 完成重訂基底功能。 重訂基底完成後，您可以執行其他操作。 例如，您可以發佈此功能並使它在全球化服務中開放使用。

    ![功能狀態更新為已完成。](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a>為全球化功能配置環境

全球化服務使用者可管理環境，以便設定全球化功能並授予其他有權存取的使用者權限。

1. 請在 **環境** 下方的 **全球化功能** 工作區選取 **電子發票** 圖格。

    ![全球化功能工作區。](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. 選取 **Key Vault 參數**，然後選取 **新增** 建立 Azure Key Vault 密碼。
3. 輸入 Key Vault 的名稱和說明，並在 **Key Vault URI** 欄位，輸入可辨認在 Azure 中的 Key Vault 資源 URL。
4. 請在 **證書** FastTab 上，選取 **新增** 以新增證書，並輸入每張證書的名稱和說明。

    ![已新增證書。](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. 選取 **新增** 以建立新環境。
6. 輸入儲存設備所需的名稱、說明和共用的存取簽名權杖密碼。
7. 請在 **使用者** FastTab 上，選取 **新增** 以新增將有權訪問此環境的使用者。
8. 輸入使用者的使用者識別碼和電子郵件地址。
9. 重複步驟 7 到 8 新增更多使用者。
10. 選取 **發佈** 以發佈環境。

    ![已發佈的環境。](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]