---
title: 商業文件管理概述
description: 本主題提供有關如何使用 ER 架構的商業文件管理函數的資訊。
author: NickSelin
ms.date: 04/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERSecurityAccessEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: faea9d4d9b3fc8f3f1474b6bb2a8dc31cdc22511
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460249"
---
# <a name="business-document-management-overview"></a>商業文件管理概述

[!include [banner](../includes/banner.md)]

商務使用者根據各個國家/地區的法律要求使用[電子報表 (ER)](general-electronic-reporting.md)架構設定輸出文件格式。 使用者還可以定義資料流程以指定將哪些應用程式資料放置在產生的文件中。 ER 架構使用預定義的範本在 Microsoft Office 格式 (Excel 工作簿或 Word 文件) 中產生輸出文件。 在產生所需文件時，根據設定的資料流程在範本中填入所需的資料。 每個設定的格式都可以作為 ER 解決方案的一部分發布，以產生特定的輸出文件。 這由 ER 格式設定表示，該設定可以包含可用於產生不同輸出文件的範本。 商務使用者可以使用此架構來管理所需的商業文件。

**商業文件管理** 建立在 ER 架構上，使商務使用者能夠透過使用 Microsoft 365 服務或適當的 Microsoft Office 桌電應用程式編輯商業文件範本。 文件編輯可能包括更改商業文件設計和為其他資料新增預留位置，而無需更改原始程式碼和新部署。 更新商業文件範本不需要 ER 架構知識。

> [!NOTE]
> 請注意，商業文件管理允許您修改用於產生商業文件 (如訂單、發票等) 的範本。當範本已修改並發布新版本時，此版本用於產生所需的商業文件。 商業文件管理不能用於修改已經產生的商業文件。

## <a name="supported-deployments"></a>支援的部署

現行，商業文件管理函數僅針對雲端部署。 如果此函數對您的內部部署至關重要，請透過提供有關[構想](https://experience.dynamics.com/ideas/)網站。

## <a name="supported-microsoft-office-applications"></a>支援的 Microsoft Office 應用程式

若要透過 Microsoft Office 桌電應用程式使用商業文件管理編輯 Excel 或 Word 格式的範本，您必須安裝 Microsoft Office 2010 或更高版本。 這在雲端和內部部署中受支援。

若要透過 Microsoft 365 應用程式使用商業文件管理編輯 Excel 或 Word 格式的範本，您必須安裝 Microsoft 365 Office 以便使用網路訂閱。 這在雲端部署中受支援。

## <a name="business-document-availability"></a>商業文件可用性

如需計畫在 2019 年 10 月發布的所有報告的完整清單，請參閱[Word 和 Excel 中可克定的商業文件報告](/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details)。

如需計畫在 2020 年 10 月發布的所有報告的完整清單，請參閱[可設定的商業文件 - Word 範本](/dynamics365-release-plan/2020wave1/dynamics365-finance/configurable-business-documents-word-templates)。

更多報告將在未來版本中提供。 有關其他報告的特別通知將單獨發送。 若要了解如何查看現行可用報告的清單，請參閱下列區段[已在 Finance 中發布以支援可設定商業文件的 ER 設定清單](#list-of-configurations-cbd)。

若要進一步了解此函數，請完成本主題中的範例。

## <a name="configure-er-parameters"></a>設定 ER 參數

由於商業文件管理構建在 ER 架構上，因此您必須設定 ER 參數才能開始使用商業文件管理。 為此，您需要設定 ER 參數，如[設定電子報表 (ER) 架構](electronic-reporting-er-configure-parameters.md)所示。 您還需要新增新的設定提供者，如[建立設定提供者並將其標記為有效](tasks/er-configuration-provider-mark-it-active-2016-11.md)所示。

![ER 工作區。](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>匯入 ER 解決方案

此程序的範例中使用了樣本 ER 設定。 您必須匯入到您現行的 Dynamics 365 Finance 執行個體，包含可以使用商業文件管理編輯之商業文件範本的 ER 設定。 下載並在本地儲存以下檔案以完成此程序。

**樣本 ER 客戶開票解決方案**

| 檔案                                      | 內容 |
|-------------------------------------------|---------|
| 客戶開票模型.版本.2.xml    | [ER 資料模型設定](https://download.microsoft.com/download/b/f/a/bfa5cb52-e6e2-42bc-a4c0-77014a4c54e6/Customerinvoicingmodel.version.2.xml) |
| 客戶 FTI 報告 (GER).版本.2.3.xml | [普通發票 ER 格式設定](https://download.microsoft.com/download/3/c/2/3c2e58f2-6e56-43d9-85ea-4c97252a108d/CustomerFTIreportGER.version.2.3.xml) |

**樣本 ER 付款檢查解決方案**

| 檔案                                     | 內容 |
|------------------------------------------|---------|
| 支票.版本.10.xml 的模型         | [ER 資料模型設定](https://download.microsoft.com/download/3/7/6/376cb0f6-181a-4895-a432-390ffca64162/Modelforcheques.version.10.xml) |
| 支票列印格式.版本.10.9.xml | [付款支票 ER 格式設定](https://download.microsoft.com/download/6/d/6/6d61bfff-3d89-4377-9e34-2e3ee6d6df91/Chequesprintingformat.version.10.9.xml) |

**樣本 ER 外貿解決方案**

| 檔案                             | 內容 |
|----------------------------------|---------|
| Intrastat 模型.版本.1.xml    | [ER 資料模型設定](https://download.microsoft.com/download/2/0/0/200d6ed1-eff8-48ec-ab75-175a4acf9714/Intrastatmodel.version.1.xml) |
| Intrastat 報告.版本.1.9.xml | [Intrastat 控制報告 ER 格式設定](https://download.microsoft.com/download/7/a/2/7a2a27c3-a8a5-42a1-9d04-f0a8e1ec1707/Intrastatreport.version.1.9.xml) |

使用以下程序匯入每個檔案。 在您匯入相應的 ER *格式* 設定之前，匯入資料表中每個 ER 解決方案的 ER *資料模型* 設定。

1. 打開 **組織管理**\>**電子報表**\>**設定** 頁面。
2. 在頁面頂部，選取 **交易**。
3. 選取 **從 XML 文件載入**。
4. 選取 **瀏覽** 載入所需的 XML 檔案。
5. 選取 **確定** 以確認設定的匯入。

![ER 設定頁面確認設定匯入。](./media/BDM-Overview-ERSolutions.png)

或者，您可以從 Microsoft Dynamics 生命週期服務 (LCS) 匯入官方發布的 ER 格式設定。 例如，若要完成此程序，您可以匯入最新版本的 **普通發票 (Excel)** ER 格式設定。 相應的 ER 資料模型和 ER 模型對應設定將自動匯入。

![LCS 共用資產庫內容頁面。](./media/BDM-Overview-SharedAssetLibrary.png)

如需匯入 ER 設定的相關資訊，請參閱[管理 ER 設定生命週期](general-electronic-reporting-manage-configuration-lifecycle.md)。

## <a name="enable-business-document-management"></a>啟用商業文件管理

若要啟動商業文件管理，您需要打開 **函數管理** 工作區並啟用 **商業文件管理** 函數。

使用以下程序為所有法律實體啟用商業文件管理函數。

1. 打開 **函數管理** 工作區。
2. 在 **新增** 索引標籤上，選取 **商業文件管理** 清單中的函數。
3. 選取 **立即啟用** 開啟選定函數。
4. 重新整理頁面來存取新函數。

> [!NOTE]
> 如需在商業文件管理中使用新文件使用者介面的相關資訊，請參閱[商業文件管理中的新文件使用者介面](er-business-document-management-new-template-ui.md)。

![函數管理工作區。](./media/BDM-Overview-FMEnabling.png)

如需啟用新函數的相關資訊，請參閱[函數管理概述](../../fin-ops/get-started/feature-management/feature-management-overview.md)。

## <a name="configure-parameters"></a>設定參數

使用以下區段中的資訊來設定商業文件管理的基本參數。

### <a name="prerequisites-for-parameter-setup"></a>參數安裝的先決條件

在設定商業文件管理之前，您必須在文件管理架構中設定所需的文件類型。 此文件類型的用途是指定用作 ER 報告範本的 Office 格式 (Excel 和 Word) 文件的臨時儲存體。 可以使用 Office 桌電應用程式編輯臨時儲存體範本。

如需此文件類型，必須選取以下屬性值。

| 屬性名稱 | 屬性值 |
|----------------|-----------------|
| 類別          | 附加檔案     |
| 群組          | 檔案            |
| 位置       | SharePoint      |

如需如何設定所需文件管理參數和文件類型的相關資訊，請參閱[設定文件管理](../../fin-ops/organization-administration/configure-document-management.md)。

![設定文件管理文件類型。](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a><a name="SetupBdmParameters"></a>安裝參數

基本商業文件管理參數可以在 **商業文件參數** 頁面上設定。 只有特定使用者才能存取該頁面。 這包括：

- 將使用者指派至 **系統管理員** 角色。
- 指派給設定為執行職責的任何角色的使用者，**維護商業文件管理參數** (AOT 名稱 **ERBDMaintainParameters**)。

使用以下程序為所有法律實體設定基本參數。

1. 以具有存取權限的使用者身份登入 **商業文件參數** 頁。
2. 進入 **組織管理**\>**電子報表**\>**商業文件管理**\>**商業文件參數**。
3. 在 **商業文件參數** 頁面上，**附件** 索引標籤上，**SharePoint 文件類型** 欄位，定義在使用 Office 桌電應用程式編輯範本時套用於臨時儲存體 Office 格式的範本的文件類型。 

> [!NOTE]
> 只有使用 SharePoint 位置設定的文件類型可供此參數使用。

![設定商業文件管理參數。](./media/BDM-Overview-BDMSetting.png)

選定的文件類型為公司專用，將在使用者在為其設定了選定文件類型的公司中使用商業文件管理時使用。 當使用者在另一家公司使用商業文件管理時，如果沒有為這家公司設定相同的文件類型，則將使用相同的選定文件類型。 設定文件類型後則將會使用它，而不是在選定的 **SharePoint 文件類型** 欄位。

> [!NOTE]
> **SharePoint 文件類型** 參數定義了 SharePoint 資料夾作為範本儲存體，供使用 Microsoft Excel 或 Word 的可編輯範本使用。 如果您打算使用這些 Office 桌電應用程式來編輯範本，則需要設定此參數。 如需相關資訊，請參閱[在 Office 桌電應用程式中編輯範本](#EditInOfficeDesktopApp)。 如果您打算修改僅使用 Microsoft 365 函數的範本，您可以將此參數留空。 如需相關資訊，請參閱[在 Microsoft 365](#EditInOffice365) 中編輯範本。

## <a name="configure-access-permissions"></a>設定存取權限

在預設情況下，當未啟用商業文件管理的存取權限時，每個有權存取商業文件管理工作區的使用者都將看到所有可用的 ER 解決方案範本。 商業文件管理工作區將僅顯示那些駐留在 ER 格式設定中並由 **商業文件類型** 標籤標記的範本。

![帶有商業文件類型標籤的 ER 設定頁面。](./media/BDM-Overview-ERFormatTags.png)

可以透過設定存取權限來限制商業文件管理工作區中可用的範本清單。 當使用不同的範本為不同的商業領域 (函數區域) 產生商業文件時相當重要，並且您希望允許特定使用者存取不同的範本以便在商業文件管理工作區中編輯。

商業文件管理存取權限可在 **存取權限的設定程式** 中設定。 只有以下使用者才能存取該頁面：

- 被指派至 **系統管理員** 角色的使用者。
- 被指派到任何其他角色的使用者，被設定執行職責，**設定存取商業文件範本的存取權限以供編輯** (AOT 名稱 **ERBDTemplatesSecurity**)。

使用以下程序為所有法律實體設定商業文件管理權限。

1. 以具有存取權限的使用者身份登入 **存取權限的設定程式** 頁面。
2. 進入 **組織管理**\>**電子報表**\>**商業文件管理**\>**管理存取權限**。

    請注意通知您現行未啟用商業文件管理的存取權限使用的通知。

    ![商業文件管理存取權限頁面的設定程式。](./media/BDM-Overview-TemplatesAccess1.png)

    有了這個設定，每個被指派到任何資訊安全角色的使用者，如果被設定為執行 **管理商業文件範本** (AOT 名稱為 **ERBDManageTemplates**) 的職責，就能夠打開商業文件管理工作區，並可以編輯任何可用的範本。

    下圖顯示了商業文件管理工作區中指派給 **應收帳款記帳員** 角色。 使用現行的存取權限設定，使用者可以編輯來自不同函數區域的商業文件範本，包括開票、監管報告和付款。

    ![應收帳款記帳員的商業文件管理工作區頁面。](./media/BDM-Overview-TemplatesForAlice1.png)

3. 在 **存取權限的設定程式** 頁面上，選取 **存取權限設定**。
4. 在 **編輯範本的存取權限設定** 對話方塊中，啟用 **套用設定的存取權限** 選項。
5. 選取 **確定** 以確認已啟用商業文件管理存取權限。

    ![確認商業文件管理存取權限頁面。](./media/BDM-Overview-TemplatesAccess2.png)

6. 選取 **新增** 以輸入新的商業角色，必須為其設定存取商業文件管理範本的權限。
7. 在 **資訊安全角色** 對話方塊中，選取 **應收帳款記帳員** 角色，然後選取 **確定** 以確認角色選擇。
8. 在 **每個設定標籤的存取權限** 索引標籤上，選取 **新增**。
9. 在 **標籤類型** 欄位中，選取 **函數區域**，並且在 **ID** 欄位中，選取 **開票**。
10. 選取 **儲存** 為所選角色儲存設定的存取權限。

    現行的設定代表，對於任何被指派到 **應收帳款記帳員** 角色並執行 **管理商業文件範本** (AOT 名稱為 **ERBDManageTemplates**) 職責的使用者，在商業文件管理工作區的可編輯 **函數區** 標籤且有 **開票** 值的 ER 格式設定範本。

11. 從現行頁面右側的窗格將 **相關資訊** 切換。 **相關資訊** 窗格顯示如何套用設定好的存取權限，其中包括哪些 ER 設定範本可供指派給 **應收帳款記帳員** 角色。

    ![存取權限設定程式頁面上的相關資訊窗格。](./media/BDM-Overview-TemplatesAccess3.png)

12. 在 **每個設定的存取權限** 索引標籤上，選取 **新增** 選項。
13. 在 **選取設定** 對話方塊，標記 **Intrastat 報告** ER 格式設定。
14. 選取 **確定** 以確認所選設定的輸入資料，然後選取 **儲存** 以儲存為所選角色設定的存取權限。

現行的設定代表，對於任何被指派到 **應收障款記帳員** 角色並執行 **管理商業文件範本** (AOT 名稱為 **ERBDManageTemplates**) 職責的使用者，在商業文件管理工作區可以編輯下列範本：

- 有價值的範本，**函數區** 標記的 **開票**。
- 來自 ER 格式設定的範本，這些範本列在 **每個設定的存取權限** 索引標籤上 (本例中來自 **法定報告** 領域的 **Intrastat 報告** 格式設定的範本)。

![存取權限設定程式頁面上的存取權限 FastTabs。](./media/BDM-Overview-TemplatesAccess4.png)

下圖顯示了商業文件管理工作區為指派給 **應收帳款記帳員** 角色的使用者提供的內容。 在現行的商業文件管理存取權限設定下，使用者可以編輯 **開票** 領域的商業文件範本和 **Intrastat 報告** ER 格式設定。 **應收帳款記帳員** 角色不能存取 **付款** 領域的範本。

![在商業文件管理工作區頁面上編輯商業文件範本。](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> **每個設定的存取權限** 規則是透過使用 ER 格式設定的唯一識別 ID 來儲存的。 這代表當參考它們的 ER 設定被刪除時，這些規則不會被刪除。 當您將已刪除的設定匯入回此執行個體時，這些規則將再次參考它們。 刪除的設定重新匯入後，無需重新設定規則。

## <a name="use-business-document-management-to-edit-templates"></a>使用商業文件管理編輯範本

商務使用者可存取在商業文件管理工作區頁面上編輯商業文件範本。 只有以下使用者可以存取商業文件管理工作區：

- 被指派至 **系統管理員** 角色的使用者。
- 指派給設定為執行職責的任何角色的使用者，**管理商業文件範本** (AOT 名稱 **ERBDManageTemplates**)。

使用以下程序在商業文件管理工作區中編輯普通發票範本。 在完成此程序之前，您必須先完成上述本主題中的所有程序。

1. 以具有存取權限的使用者身份登入商業文件管理工作區。
2. 打開商業文件管理工作區。

當在 **函數管理** 工作區中關閉 **商業文件管理函數的類 Office 使用者介面體驗** 時，**商業文件管理** 工作區的主網格會顯示以下範本：

- 由您的 ER 設定提供者 (即，現行在 **電子報表** 工作區標記為有效的提供者)。 選取其中一個範本後，您可以選取 **編輯範本** 以開始或繼續編輯它。
- 其他 ER 設定提供者擁有的範本。 選取其中一個範本後，您可以選取 **新文件** 來建立歸您的 ER 設定提供者所有的副本，然後開始編輯該副本。

![商業文件管理工作區頁面上的範本清單。](./media/BDM-Overview-EditingTemplate1.png)

**範本** 索引標籤顯示所選範本的內容。 選取 **詳情** 索引標籤以查看所選範本的詳情以及此範本所在的 ER 格式設定的詳情。 請注意，所有的範本都有 **已發佈** 的狀態，並且在 **修訂** 資料欄中沒有包含任何詳情。 這代表這些範本現行未被編輯。

當在 **函數管理** 工作區中為 **商業文件管理函數打開類 Offie 的使用者介面體驗** 時，**商業文件管理** 工作區的主格線顯示由您的 ER 設定提供者 (即，現行在 **電子報表** 工作區中被標記為有效的提供者) 擁有的範本。 選取其中一個範本後，您可以選取 **編輯範本** 以開始或繼續編輯它。

若要使用其他 ER 設定提供者擁有的範本，請選取 **新文件**，建立由您的 ER 提供者擁有的範本副本。 然後您可以開始編輯副本。 如需相關資訊，請參閱[商業文件管理中的新文件使用者介面](er-business-document-management-new-template-ui.md)。

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>啟動您的設定提供者擁有的編輯範本

1. 在商業文件管理工作區中，選取 **支票列印格式** 清單中的範本。
2. 選取 **詳情** 索引標籤。

![商業文件管理工作區頁面，詳情索引標籤。](./media/BDM-Overview-EditingTemplate2.png)

**編輯範本** 選項可用於所選範本。 此選項一律可用於有效 ER 設定提供者擁有的 ER 格式設定中的範本 (在這範例中的 **Litware, Inc.**)。 當選取 **編輯範本** 時，底層 ER 格式設定的草稿版本的現有範本將可編輯。

### <a name="initiate-editing-templates-owned-by-other-providers"></a>啟動其他提供者擁有的編輯範本

1. 在商業文件管理工作區中，選取要用作範本的文件。

    ![選取商業文件管理工作區頁面上的清單。](./media/BDM-Overview-EditingTemplate3.png)

2. 選取 **新文件**，並且在 **標題** 欄位中，根據需求更改可編輯範本的標題。 該文字將用於命名自動建立的 ER 格式設定。 請注意，包含編輯過範本的設定的草稿版本 (**客戶 FTI (GER) 副本**) 將自動被標記為執行現行使用者的 ER 格式。 同時，基本 ER 格式設定中未修改的原始範本將用於為任何其他使用者執行此 ER 格式。
3. 在 **名稱** 欄位中，更改將自動建立的可編輯範本的第一個修訂版的名稱。
4. 在 **註解** 欄位中，為可編輯範本的自動建立的修訂版更改註解。
5. 選取 **確定** 以確認編輯流程的開始。

![確認開始編輯流程以建立新範本。](./media/BDM-Overview-EditingTemplate4.png)

如果沒有任何提供者，將提供以便建立。 如果沒有有效的提供者，將提供選取它進行啟用。

若要建立提供者，請更改 **名稱** 欄位中的名稱，更新 **網路地址** 欄位中新提供者的網路地址，然後選取 **確定** 以便確認。

   ![在 BDM 中建立新提供者。](./media/bdm_create_provider.png)

若要啟動現有的提供者，在 **設定提供者** 欄位中選取提供者的名稱，並選取 **確定**，將提供者設定為有效。

   ![啟動 BDM 的提供者。](./media/bdm_choose_provider.png)

> [!NOTE]
> 每個 BDM 範本都將提供者稱為設定的作者。 這就是範本需要有效提供者的原因。


對於現行提供的 ER 格式設定的範本和另一個提供者 (本例中為 Microsoft) 沒有任何修訂的範本，**新文件** 選項一直都可提供。 編輯後的範本將儲存在自動產生的新 ER 格式設定中。



### <a name="start-editing-a-template"></a>開始編輯範本

1. 從所選範本中，選取 **編輯文件**。
2. 在 **名稱** 欄位中，更改將自動建立的可編輯範本的第一個修訂版的名稱。
3. 在 **註解** 欄位中，為可編輯範本的自動建立的修訂版更改備註。

    ![在商業文件管理工作區頁面上編輯範本。](./media/BDM-Overview-EditingTemplate5.png)

4. 選取 **確定** 以確認編輯流程的開始。

**BDM 範本編輯器** 頁面將打開。 選定的範本將可透過使用 Microsoft 365 進行線上編輯。

![商業文件管理範本編輯頁面。](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-microsoft-365"></a><a name="EditInOffice365"></a>在 Microsoft 365 編輯範本

您可以使用 Microsoft 365 修改範本。 例如，在 Office Online 中，將範本標題中的欄位提示字體從 **一般** 改到 **粗體**。 這些更改會自動儲存在主範本儲存 (在預設情況下，Azure Blob 儲存體) 中的可編輯範本中。 這是為 ER 架構設定的。

![在商業文件管理範本編輯器頁面上的範本標題中將字體更改為粗體。](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a><a name="EditInOfficeDesktopApp"></a>在 Office 桌電應用程式中編輯範本

> [!NOTE]
> 此函數僅在 **SharePoint 文件類型** 參數設定正確時可用。 如需相關資訊，請參閱[設定參數](#SetupBdmParameters)。

1. 使用 Office 桌電應用程式 (本範例中的 Excel) 的函數選取 **在桌電應用程式中打開** 選項修改範本。 可編輯的範本從永久儲存體複製到商業文件管理參數中設定的臨時儲存體，作為 SharePoint 資料夾。
2. 確認您要從 Office 桌電 Excel 應用程式的臨時檔案儲存中打開範本。

    ![在桌電 Excel 應用程式中打開的範本。](./media/BDM-Overview-EditingLayout3.png)

3. 修改範本。 例如，透過從 **黑色** 更新到 **藍色** 更改範本標題中的欄位提示字體。

    ![使用桌電 Excel 應用程式修改範本標題中的字體顏色。](./media/BDM-Overview-EditingLayout4.png)

4. 選取 Excel 桌電應用程式中的 **儲存** 將範本更改儲存在臨時儲存中。

    ![使用桌電 Excel 應用程式儲存對商業文件管理範本編輯器頁面的更改。](./media/BDM-Overview-EditingLayout5.png)

5. 關閉 Excel 桌電應用程式。
6. 選取 **同步儲存的副本** 將臨時範本儲存同步到永久範本儲存。

> [!NOTE]
> 臨時檔案儲存中的可編輯範本的副本僅保留用於範本編輯的現行工作階段。 當您透過關閉 **BDM 範本編輯器** 頁面結束此工作階段，此副本將被刪除。 如果您調整了臨時檔案儲存中的範本並且沒有選取 **同步儲存的副本**，當您嘗試關閉 **BDM 範本編輯器** 頁面，訊息將詢問您是否要儲存引入的更改。 如果要將對範本的更改儲存在永久檔案位置，請選取 **是**。

### <a name="validate-a-template"></a>驗證範本

1. 在 **BDM 範本編輯器** 頁面上，選取 **檢查問題** 根據基礎 ER 格式設定驗證修改後的範本。 按照建議 (如果有) 將範本與基本 ER 格式設定中的格式結構對齊。
2. 選取 **顯示格式** 從必須與可編輯範本對齊的基本 ER 格式設定中查看該格式的現有結構。 
3. 選取 **隱藏格式** 關閉窗格。

    ![BDM BDM 範本編輯器頁面。](./media/BDM-Overview-EditingTemplate6.png)

4. 關閉 **BDM 範本編輯器** 頁面。

更新後的範本顯示在 **範本** 索引標籤上：請注意，編輯過的範本的狀態現在是 **草稿**，現行的修訂版不再是空白的。 這代表該範本的編輯流程已經開始。

![在商業文件管理工作區頁面上查看更新的範本。](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>測試修改後的範本 

1. 在申請表中，變更為公司 **USMF**。
2. 進入 **應收帳款**\>**發票**\>**所有普通發票**。
3. 選取 **FTI-00000002** 發票，然後選取 **列印管理**。
4. 選取 **模組 - 應收帳款**\>**文件**\>**普通發票**\>**原始文件** 層級指定要處理的發票範圍。
5. 在 **報告格式** 欄位中，選取 **客戶 FTI 報告 (GER) 副本** 指定文件層級的 ER 格式。

    ![列印管理設定頁面。](./media/BDM-Overview-TestRun1.png)

6. 按 **逃脫** 關閉現行頁面。
7. 選取 **列印**，然後選取 **已選取**。
8. 下載並用 Excel 桌電應用程式打開文件。

![普通發票頁面。](./media/BDM-Overview-TestRun2.png)

修改後的範本用於產生所選項目的普通發票報告。 若要分析您對範本所做的更改如何影響此報告，您可以在另一個應用程式工作階段中修改範本後直接在應用程式工作階段中執行此報告。

### <a name="create-an-alternative-template-revision"></a>建立替代範本修訂

1. 打開 **BDM 範本編輯器** 頁面並選取 **客戶 FTI 報告 (GER) 副本** 範本。
2. 在 **修訂** 索引標籤，選取 **新增**。
3. 如果需要，在 **名稱** 欄位中，更改第二個修訂的名稱，並根據現行有效的第一個修訂。
4. 如果有需要，在 **註解** 欄位中，為可編輯範本的自動建立的修訂版更改備註。

    ![在商業文件管理工作區頁面上建立對範本的修訂。](./media/BDM-Overview-AddRevision.png)

    您建立了範本的新修訂版，該修訂版已儲存在永久範本的儲存體中。 現在您可以繼續編輯現行選取為有效的第二個修訂的範本。

5. 選取第一個修訂版，然後選取 **設定有效**。 如果您隨時想返回到該範本的修訂版，您可以選取另一個修訂版為有效。
6. 選取第二個修訂，然後選取 **刪除**。
7. 選取 **確定** 以確認您要刪除選定的修訂。 當不再需要它們時，您可以刪除任何非有效的修訂。

### <a name="delete-a-modified-template"></a>刪除修改後的範本

1. 在 **BDM 範本編輯器** 頁面上，選取 **範本** 索引標籤。
2. 選取 **刪除**。
3. 如果您選取 **確定** 確認刪除，附有修改範本的 ER 格式的 **客戶 FTI 報告 (GER) 副本** 將被刪除。 選取 **取消** 探索其他選擇。

### <a name="revoke-changes-of-template"></a>撤銷對範本的更改

當您從現行有效提供者擁有的 ER 格式編輯範本時，您可以選取撤銷為範本引入的更改。

![拒絕對商業文件管理工作區頁面上的範本進行修改。](./media/BDM-Overview-RevokeChanges.png)

1. 在 **BDM 範本編輯器** 頁面上，選取 **範本** 索引標籤。
2. 選取 **撤消**。
3. 如果您選取 **確定** 要撤消為範本引入的更改，修改後的範本將被原始範本替換，並且所有更改都將被刪除。 當您撤銷對範本的更改時，您將能夠刪除該範本。 選取 **取消** 探索其他選擇。

### <a name="publish-a-modified-template"></a>發佈修改後的範本

1. 在 **BDM 範本編輯器** 頁面上，在 **範本** 索引標籤上，選取 **發佈**。
2. 如果您選取 **確定** 以確認發佈，導出的 **客戶 FTI 報告 (GER) 副本** ER 格式的草稿版本，其包含已標記完成的修改範本。 修改後的範本可供其他使用者使用。 此 ER 格式的完整版本將僅保留範本的最後一個有效版本。 其他修訂將被刪除。 選取 **取消** 探索其他選擇。

## <a name="frequently-asked-questions"></a>常用問題

### <a name="i-selected-edit-document-but-instead-of-going-to-the-bdm-template-editor-page-in-finance-i-was-sent-to-the-microsoft-365-webpage"></a>我選取了編輯文件，但我沒有進入 Finance 的 BDM 範本編輯頁面，而是被送到了 Microsoft 365 的網頁上。

這個問題是已知的問題，涉及 Microsoft 365 重新導向。 它發生在您第一次登入到 Microsoft 365 的時候。 若要解決此問題，請選取瀏覽器中的 **退回** 返回上一頁。

### <a name="i-understand-how-to-edit-a-template-by-using-microsoft-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-and-adjust-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-use-the-office-desktop-application-in-the-same-way"></a>我了解如何在第一個應用程式工作階段使用 Microsoft 365 編輯範本，以及如何在第二個應用程式工作階段中使用範本並調整範本以查看我的更改如何影響產生的商業文件。 我可以透過同樣的方式使用 Office 桌電應用程式嗎？

是，您可以。 在第一個應用程式工作階段中，選取 **在桌電應用程式中打開**。 您的範本將儲存在臨時檔案儲存中並在 Office 桌電應用程式中打開。 接下來，完成以下步驟以在產生的商業文件中預覽您的範本更改：

1. 使用 Office 桌電應用程式在範本中進行更改。
2. 選取 Office 桌電應用程式中的 **儲存**。
3. 在第一個應用程式工作階段的 **BDM 範本編輯器** 頁面上，選取 **同步儲存的副本**。
4. 在第二個應用程式工作階段中執行此範本 ER 格式。

### <a name="when-i-select-open-in-desktop-app-i-receive-the-following-error-message-value-cannot-be-null-parameter-name-externalid-how-do-i-work-around-this-issue"></a>當我選取在桌電應用程式中打開時，我收到以下錯誤訊息：「值不能為空。 參數名稱：externalId。」 我該如何解決這個問題？

很可能是您登入了 Azure AD 網域的應用程式的現有執行個體，而該網域與用於部署該執行個體的 Azure AD 網域不同。 因為 SharePoint 服務 (用於儲存範本，以便透過 Office 桌電應用程式進行編輯) 屬於同一個網域，我們沒有存取 SharePoint 服務的許可權。 同時若要解決此問題，請使用具有正確 Azure AD 網域的使用者憑證登入到現有的執行個體網域。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[ER 設計用於產生 OPENXML 格式報告的設定 (2016 年 11 月) ](tasks/er-design-reports-openxml-2016-11.md)

[設計 ER 設定以產生 Word 格式的報告](tasks/er-design-configuration-word-2016-11.md)

[在使用 ER 產生的文件中嵌入圖像和形狀](electronic-reporting-embed-images-shapes.md)

[設定電子報表 (ER) 以將資料提取到 Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)

## <a name="list-of-er-configurations-that-have-been-released-in-finance-to-support-configurable-business-documents"></a><a name="list-of-configurations-cbd"></a>已在 Finance 中發佈以支援可設定商業文件的 ER 設定清單

Finance ER 設定中的[清單](general-electronic-reporting.md#list-of-configurations)不斷更新。 打開[全域存放庫](er-download-configurations-global-repo.md)查看現行支援的 ER 設定清單。 您可以[篩選](../../../finance/localizations/enhanced-filtering-global-repo.md)全域存放庫以查看用於支援可設定商業文件的 ER 設定清單。

![在設定存放庫頁面上篩選全域存放庫的內容。](./media/bdm-overview-filterglobalrepo.gif)

下表顯示了支援可設定商業文件並且已在 Finance 中發佈到 2020 年 12 月的 ER 設定清單。

| 資料模型設定    | 格式設定                           |
|-----------------------------|-------------------------------------------------|
| 提單模型        | 提單 (Excel)                          |
|                             | 提單 (Word)                           |
| 原始模型的憑證 | 原始的憑證 (Excel)                   |
|                             | 原始的憑證 (Word)                    |
| 發票模型               | 客戶借方和貸方票據 (Excel)          |
|                             | 客戶借方和貸方票據 (Word)           |
|                             | 普通發票 (Excel)                       |
|                             | 普通發票 (Excel) (BH)                  |
|                             | 普通發票 (FR) (Excel)                  |
|                             | 普通發票 (LT) (Excel)                  |
|                             | 普通發票 (LV) (Excel)                  |
|                             | 普通發票 (PL) (Excel)                  |
|                             | 普通發票 (CZ) (Excel)                  |
|                             | 普通發票 (EE) (Excel)                  |
|                             | 普通發票 (HU) (Excel)                  |
|                             | 普通發票 (TH) (Excel)                  |
|                             | 普通發票 (Word)                        |
|                             | 專案合約項目 (Excel)             |
|                             | 專案合約項目 (CZ) (Excel)        |
|                             | 專案合約項目 (Excel) (BH)        |
|                             | 專案合約項目 (HU) (Excel)        |
|                             | 專案合約項目 (LT) (Excel)        |
|                             | 專案合約項目 (PL) (Excel)        |
|                             | 專案合約項目 (Word)              |
|                             | 專案客戶保留版本 (Excel)      |
|                             | 專案客戶保留版本 (CZ) (Excel) |
|                             | 專案客戶保留版本 (HU) (Excel) |
|                             | 專案客戶保留版本 (LT) (Excel) |
|                             | 專案客戶保留版本 (PL) (Excel) |
|                             | 專案客戶保留版本 (TH) (Excel) |
|                             | 專案客戶保留版本 (Word)       |
|                             | 專案發票 (Excel)                         |
|                             | 專案發票 (Word)                          |
|                             | 專案發票 (AE) (Excel)                    |
|                             | 專案發票 (CZ) (Excel)                    |
|                             | 專案發票 (BH) (Excel)                    |
|                             | 專案發票 (HU) (Excel)                    |
|                             | 專案發票 (JP) (Excel)                    |
|                             | 專案發票 (LT) (Excel)                    |
|                             | 專案發票 (PL) (Excel)                    |
|                             | 專案發票 (TH) (Excel)                    |
|                             | 完整專案發票 (MY) (Excel)               |
|                             | 簡單專案發票 (MY) (Excel)             |
|                             | 專案管理發票 (Excel)                  |
|                             | 專案管理發票 (CZ) (Excel)             |
|                             | 專案管理發票 (Excel) (BH)             |
|                             | 專案管理發票 (HU) (Excel)             |
|                             | 專案管理發票 (JP) (Excel)             |
|                             | 專案管理發票 (LT) (Excel)             |
|                             | 專案管理發票 (PL) (Excel)             |
|                             | 專案管理發票 (Word)                   |
|                             | 採購預付款發票 (Excel)                |
|                             | 採購預付款發票 (Word)                 |
|                             | 銷售預付款發票 (Excel)                   |
|                             | 銷售預付款發票 (Word)                    |
|                             | 銷售預付款發票 (PL) (Excel)              |
|                             | 銷售發票 (Excel)                           |
|                             | 銷售發票 (Excel) (BH)                      |
|                             | 銷售發票 (Excel) (CZ)                      |
|                             | 銷售發票 (Excel) (EE)                      |
|                             | 銷售發票 (Excel) (FR)                      |
|                             | 銷售發票 (Excel) (HU)                      |
|                             | 銷售發票 (Excel) (IN)                      |
|                             | 銷售發票 (Excel) (LT)                      |
|                             | 銷售發票 (Excel) (LV)                      |
|                             | 銷售發票 (Excel) (PL)                      |
|                             | 銷售發票 (Excel) (TH)                      |
|                             | 銷售發票 (Word)                            |
|                             | TMS 商業發票 (Excel)                  |
|                             | TMS 商業發票 (Word)                   |
|                             | 廠商發票文件 (Excel)                 |
|                             | 廠商發票文件 (CZ) (Excel)            |
|                             | 廠商發票文件 (HU) (Excel)            |
|                             | 廠商發票文件 (IN) (Excel)            |
|                             | 廠商發票文件 (LT) (Excel)            |
|                             | 廠商發票文件 (LV) (Excel)            |
|                             | 廠商發票文件 (MY) (Excel)            |
|                             | 廠商發票文件 (Word)                  |
| 訂單模型                 | 合約確認 (Excel)                  |
|                             | 合約確認 (Word)                   |
|                             | 購買合約確認 (Excel)         |
|                             | 購買合約確認 (Word)          |
|                             | 訂購單 (Excel)                          |
|                             | 訂購單 (CZ) (Excel)                     |
|                             | 訂購單查找 (CZ) (Excel)             |
|                             | 訂購單 (HU) (Excel)                     |
|                             | 訂購單查找 (HU) (Excel)             |
|                             | 訂購單 (Word)                           |
|                             | 訂購單查找 (Excel)                  |
|                             | 訂購單查找 (Word)                   |
|                             | 銷售訂單確認 (Excel)                |
|                             | 銷售訂單確認 (CZ) (Excel)           |
|                             | 銷售訂單確認 (HU) (Excel)           |
|                             | 銷售訂單確認 (Word)                 |
| 包裝清單模型          | 容器內容 (Excel)                      |
|                             | 容器內容 (Word)                       |
|                             | 載入清單 (Excel)                               |
|                             | 載入清單 (Word)                                |
|                             | 揀料單 (Excel)                            |
|                             | 揀料單 (CZ) (Excel)                       |
|                             | 揀料單 (Word)                             |
|                             | 生產揀料單 (Excel)                    |
|                             | 生產揀料單 (Word)                     |
|                             | 裝載的運送揀料單 (Excel)             |
|                             | 裝載的運送揀料單 (Word)              |
|                             | 貨件的運送揀料單 (Excel)         |
|                             | 貨件的運送揀料單 (Word)          |
|                             | 波次的運送揀料單 (Excel)             |
|                             | 波次的運送揀料單 (Word)              |
| 付款模型               | 客戶付款通知 (Excel)                 |
|                             | 客戶付款通知 (Word)                  |
|                             | 廠商付款通知 (Excel)                   |
|                             | 廠商付款通知 (Word)                    |
| 報價模型             | 專案報價 (Excel)                       |
|                             | 專案報價 (Word)                        |
|                             | 詢價 (Excel)                   |
|                             | 詢價 (接受) (Excel)          |
|                             | 詢價 (接受) (Word)           |
|                             | 詢價 (拒絕) (Excel)          |
|                             | 詢價 (拒絕) (Word)           |
|                             | 詢價 (退回) (Excel)          |
|                             | 詢價 (退回) (Word)           |
|                             | 詢價 (Word)                    |
|                             | 銷售報價單 (Excel)                         |
|                             | 銷售報價單 (CZ) (Excel)                    |
|                             | 銷售報價單 (HU) (Excel)                    |
|                             | 銷售報價單 (Word)                          |
|                             | 銷售報價單確認 (Excel)            |
|                             | 銷售報價單確認 (Word)             |
| 對帳模型        | 客戶對帳單，延伸 (Excel)             |
|                             | 客戶對帳單，延伸 (CN) (Excel)        |
|                             | 客戶對帳單，延伸 (Word)              |
|                             | 客戶對帳單，法國 (Excel)          |
| 提醒模型              | 收款通知單 (Excel)                  |
|                             | 收款通知單 (CN) (Excel)             |
|                             | 收款通知單 (Word)                   |
|                             | 客戶利息單 (Excel)                  |
|                             | 客戶利息單 (Word)                   |
| 運單模型               | 載入投標 (Excel)                             |
|                             | 載入投標 (Word)                              |
|                             | 訂購單裝箱單 (Excel)             |
|                             | 訂購單裝箱單 (CZ) (Excel)        |
|                             | 訂購單裝箱單 (Word)              |
|                             | 路線 (Excel)                                   |
|                             | 路線 (Word)                                    |
|                             | 銷售訂單裝箱單 (Excel)                |
|                             | 銷售訂單裝箱單 (CZ) (Excel)           |
|                             | 銷售訂單裝箱單 (LT) (Excel)           |
|                             | 銷售訂單裝箱單 (PL) (Excel)           |
|                             | 銷售訂單裝箱單 (Word)                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
