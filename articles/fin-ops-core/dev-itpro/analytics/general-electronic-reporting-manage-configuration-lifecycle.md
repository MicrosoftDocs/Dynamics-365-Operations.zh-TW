---
title: 管理電子報表 (ER) 設定生命週期
description: 本主題介紹如何管理 Dynamics 365 Finance 的電子報表 (ER) 設定的生命週期。
author: NickSelin
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8b61082cf17707c952b6e07613769a671c349bb8fa92c21e3fe8524ef62dcb2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460211"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>管理電子報表 (ER) 設定生命週期

[!include [banner](../includes/banner.md)]

本主題介紹如何管理 Dynamics 365 Finance 的電子報表 (ER) 設定的生命週期。

## <a name="overview"></a>概觀

電子報表 (ER) 是支援法定要求和特定國家/地區的電子文件的引擎。 通常，ER 假定能夠為單個電子文件執行以下工作。 如需相關詳情，請參閱[電子報表 (ER) 概述](general-electronic-reporting.md)。

- 為電子文件設計範本：

    - 確定可以在文件中呈現的所需資料來源：

        - 基礎資料，例如資料表、資料實體和分類。
        - 特定於流程的屬性，例如執行日期和時間以及時區。
        - 使用者輸入參數，由最終使用者在執行階段指定。

    - 定義所需的文件元素及其拓撲以指定最終文件格式。
    - 設定從選定資料來源到定義的文件元素的所需資料流程 (透過資料來源繫結到文件格式組件)，並指定過程控制邏輯。

- 提供範本使用，以便在其他情況下使用：

    - 將建立的文件範本轉換為 ER 設定，並將設定從目前應用程式實體匯出為 XML 套件，該套件可以儲存在本機或 Lifecycle Services (LCS) 中。
    - 將 ER 設定轉換為應用程式文件範本。
    - 將儲存在本機或 LCS 中的 XML 套件匯入目前實體。

- 自訂電子文件的範本：

    - 將 LCS 中的範本作為 ER 設定引入目前實體。
    - 設計 ER 設定的自訂版本，並保留對基礎版本的參考。

- 將範本與特定的業務流程整合，使其在應用程式中可供使用：

    - 透過在流程相關參數中參考該設定來設定設定，以便應用程式開始使用 ER 設定。 例如，參考特定應付帳款付款方式中的 ER 設定，以產生用於處理發票的電子付款訊息。

- 在特定的業務流程中使用範本：

    - 在特定業務流程中執行 ER 設定。 例如，在選取參考 ER 設定的付款方式時產生用於處理發票的電子付款訊息。

## <a name="concepts"></a>概念
以下角色和相關活動與 ER 設定生命週期相關聯。

| 角色                                       | 活動                                                      | 描述 |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| 電子報表函數 | 建立和管理 ER 組件 (模型和格式)。           | 設計 ER 領域特定資料模型、設計電子文件所需範本並相應繫結它們的業務人員。 |
| 電子報表開發人員             | 建立和管理資料模型對應。                          | 選取所需財務資料來源並將其繫結到 ER 域特定資料模型的專家。 |
| 會計主管                      | 設定參考 ER 成品的流程相關設定。 | 例如，**會計主管** 角色允許將 ER 設定的設定用於特定的應付帳款付款方式，以產生用於處理發票的電子付款訊息。 |
| 應付帳款付款記帳員            | 在特定的業務流程中使用 ER 成品。                | 例如，**應付帳款付款記帳員** 角色允許根據為特定付款方式設定的 ER 格式產生電子付款訊息以處理發票。 |

## <a name="er-configuration-development-lifecycle"></a>ER 設定開發生命週期
出於以下與 ER 相關的原因，我們建議您在開發環境中將 ER 設定設計為財務和營運應用程式的單獨實體：

- 具有 **電子報表開發人員** 角色或 **電子報表函數顧問** 角色的使用者可以編輯設定並執行它們以進行測試。 這種情況可能會導致調用分類和資料表的方法，這可能會損害業務資料和實體的效能。
- 作為 ER 設定的 ER 資料來源的類和表的方法的調用不受輸入點和記錄的公司內容的限制。 因此，無論是 **電子報表開發人員** 角色還是 **電子報表函數顧問** 角色的使用者都可以存取商業敏感資料。

在開發環境中設計的 ER 設定可以[上傳](#data-persistence-consideration)到測試環境，用於設定評估 (適當的流程整合、結果的正確性和效能) 和品質保證，例如角色驅動的存取權限的正確性和職責分離。 啟用 ER 設定交換的功能可用於此目的。 可以將經過驗證的 ER 設定上傳到 LCS 以與服務訂閱者分享，也可以將它們[匯入](#data-persistence-consideration)生產環境供內部使用。

![ER 設定生命週期。](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>資料持久性考慮

您可以將不同[版本](general-electronic-reporting.md#component-versioning)的 ER [設定](general-electronic-reporting.md#Configuration)單獨[匯入](tasks/er-import-configuration-lifecycle-services.md)到您的 Finance 實體。 匯入 ER 設定的新版本時，系統控制此設定的草稿版本的內容：

- 當匯入的版本低於目前 Finance 實體中該設定的最高版本時，該設定的草稿版本內容保持不變。
- 當匯入的版本高於目前財務實體中此設定的任何其他版本時，將匯入版本的內容複製到此設定的草稿版本，以便您繼續編輯上次完成的版本。

如果此設定歸目前啟用的設定 [提供者](general-electronic-reporting.md#Provider)擁有，那麼您可以在設定頁面的 **版本** FastTab 上看到此 **設定** 的草稿版本 (**組織管理** > **電子報表** > **設定**)。 您可以使用相關的 ER 設計工具選取設定的草稿版本並[修改](er-quick-start2-customize-report.md#ConfigureDerivedFormat)其內容。 當您編輯了 ER 設定的草稿版本後，其內容不再與目前 Finance 實體中此設定的最高版本的內容相符。 為防止您的更改遺失，系統會顯示無法繼續匯入的錯誤，因為此設定的版本高於目前 Finance 實體中此設定的最高版本。 發生這種情況時，例如使用格式設定 **X**，將顯示 **格式「X」版本未完成** 錯誤。

若要復原您在草稿版本中引入的更改，請在 **版本** FastTab 上選取 Finance 中 ER 設定的最高完成或共用版本，然後選取 **取得此版本** 選項。 所選版本的內容將複製到草稿版本。

## <a name="applicability-consideration"></a>適用性注意事項

當您設計 ER 設定的新版本時，您可以定義它對其他軟體組件的[相依性](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)。 此步驟被認為是控制從 ER 存放庫或外部 XML 檔案下載此設定版本以及進一步使用該版本的先決條件。 當您嘗試匯入 ER 設定的新版本時，系統會使用設定的先決條件來控制是否可以匯入該版本。

在某些情況下，您可能要求系統在匯入新版本的 ER 設定時忽略設定的先決條件。 若要讓系統在匯入期間忽略先決條件，請執行以下步驟。

1. 進入 **組織管理**\>**電子報表**\>**設定**。
2. 在 **設定** 頁面上，在動作窗格上，在 **設定** 索引標籤上，在 **進階設定** 組中，選取 **使用者參數**。
3. 將 **在匯入期間跳過產品更新和版本先決條件檢查** 選項設定為 **是**。

    > [!NOTE]
    > 此參數是使用者專用和公司專用。

## <a name="additional-resources"></a>其他資源

[電子報表 (ER) 概觀](general-electronic-reporting.md)

[定義 ER 設定對其他組件的相依性關係](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
