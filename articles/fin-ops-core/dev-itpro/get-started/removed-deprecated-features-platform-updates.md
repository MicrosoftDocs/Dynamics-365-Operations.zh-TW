---
title: 刪除或棄用的平台功能
description: 本主題介紹已刪除或計畫在財務和營運應用程式的平台更新中刪除的功能。
author: sericks007
ms.date: 03/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 27be0e720b7eca5883c5d73dfe312c09fcd22c65
ms.sourcegitcommit: ddcab9726e9dbcf3296cb0988b97a3ae7ccb3dfb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2022
ms.locfileid: "8460338"
---
# <a name="removed-or-deprecated-platform-features"></a>刪除或棄用的平台功能

[!include [banner](../includes/banner.md)]

本主題介紹已刪除或計畫在財務和營運應用程式的平台更新中刪除的功能。

- *已移除* 函數不再於產品中提供該函數。
- *已棄用* 函數未在有效開發中，可能會在未來的更新中刪除。

此清單旨在幫助您考慮移除和棄用這些自己的計畫。 

有關財務和營運應用程式中對象的詳細資訊，可在[技術參考報告 ](/dynamics/s-e/global/axtechrefrep_61)中找到。 您可以比較這些不同版本的報告，以了解每個版本的財務和營運應用程式中已更改或移除的對象。

## <a name="feature-removal-effective-march-14-2022"></a>功能移除於 2022 年 3 月 14 日生效

### <a name="xslt-scripting-in-data-management"></a>資料管理中的 XSLT 指令碼

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 資料管理中對 XSLT 指令碼的支援已棄用，以改進財務和營運應用程式中的安全性和資料保護。  |
| **被其他函數取代？**   | 編號 客戶和 ISV 應該考慮基於 X++ 語言重新實現他們的解決方案，而不是 XSLT 指令碼。 |
| **受影響的產品領域**         | 財務和營運應用程式 |
| **部署選項**              | 全部。 |
| **狀態**                         | 已棄用 - 計畫移除日期為 2022 年 3 月 14 日。<br><br>例外：現行使用 XLST 指令碼的客戶。 他們可以繼續使用它，直到更新到 10.0.30 或更高版本。 有此例外的客戶已在 Microsoft 365 系統管理中心提供的訊息中心收到通知。 |

## <a name="feature-removal-effective-october-2021"></a>功能移除於 2021 年 10 月生效

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Lifecycle Services (LCS) 中的 Microsoft Azure SQL 報表

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 所有活動和監控都將由平台透過自動化在內部執行。 這不需要任何人工干預。|
| **被其他函數取代？**   | 是的，現在有一個自動化系統，它使這些功能過時了。 |
| **受影響的產品領域**         | SQL 報表：現行 DTU、現行 DTU 詳情、獲取鎖定詳情、現行計畫指南清單、獲取查詢 ID 清單、獲取給定計畫 ID 的 SQL 查詢計畫、獲取查詢計畫和執行狀態、獲取節流設定、獲取等待 stats，列出最昂貴的查詢 |
| **部署選項**              | 雲端部署：影響 Microsoft 管理的實際執行環境和第 2 層到第 5 層沙箱環境。 |
| **狀態**                         | 已移除 |

### <a name="azure-sql-actions-in-lcs"></a>LCS 中的 Azure SQL 操作

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 我們正在棄用 LCS 中的一些 SQL 操作。 所有活動和監控都將由平台透過自動化在內部執行。 這不需要任何人工干預。 |
| **被其他函數取代？**   | 是的，現在有一個自動化系統，它使這些功能過時了。 |
| **受影響的產品領域**         | SQL 操作：建立計畫指南以強制計畫 ID、建立計畫指南以新增表提示、刪除計畫指南、禁用/啟用頁鎖和鎖升級、更新表的統計資訊、重建索引、建立索引 |
| **部署選項**              | 雲端部署：影響 Microsoft 管理的實際執行環境和第 2 層到第 5 層沙箱環境。 |
| **狀態**                         | 已移除 |


## <a name="feature-deprecation-effective-october-2021"></a>功能棄用於 2021 年 10 月生效

### <a name="show-related-document-attachments-feature"></a>「顯示相關文件附件」功能

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 該功能回傳了意外的結果。 |
| **被其他函數取代？**   | 編號 有關此函數的任何進一步計畫將透過我們的標準發佈波次揭露流程進行溝通。 |
| **受影響的產品領域**         | Web 使用者端 - 文件附件體驗 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用  |

## <a name="platform-updates-for-version-10023-of-finance-and-operations-apps"></a>財務和營運應用程式版本 10.0.23 的平台更新

### <a name="ondbsynchronize-event"></a>OnDBSynchronize 事件

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 無法控制執行此事件。 |
| **被其他函數取代？**   | 是的，將 **OnDBSynchronize** 事件訂閱的現有方法移動到 SysSetup 擴展類。 |
| **受影響的產品領域**         | 資料庫同步處理 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用。 計畫移除日期為 2022 年 10 月。 |


### <a name="systemnotificationsmanageraddnotification-api"></a>SystemNotificationsManager.AddNotification API

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Microsoft 在新增通知時需要其他參數。 |
| **被其他函數取代？**   | 是的，**SystemNotificationsManager.AddSystemNotification ()** API。 此 API 要求您為產生的通知顯式設定 ExpirationDateTime 和 RuleID。 |
| **受影響的產品領域**         | 網路使用者端 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用。 計畫移除日期為 2023 年 4 月。 |

## <a name="platform-updates-for-version-10021-of-finance-and-operations-apps"></a>財務和營運應用程式版本 10.0.21 的平台更新

### <a name="skype-for-business-online-support"></a>Skype for Business Online 支援

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Skype for Business Online 已停用。 如需相關資訊，請參閱[Skype for Business Online 服務已停用](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/the-skype-for-business-online-service-has-retired/ba-p/2596601)。 |
| **被其他函數取代？**   | 目前不會，但我們可能會考慮在未來新增來自 Teams。|
| **受影響的產品領域**         | 網路使用者端 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用。 **啟用 Skype** 從版本 10.0.21 開始，設定已關閉。 移除此設定的目標是 2022 年 4 月；但是，該功能將在 Skype 團隊關閉該服務後停止執行。 |
 
## <a name="feature-deprecation-effective-august-2021"></a>功能棄用於 2021 年 8 月生效

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Lifecycle Services (LCS) 中的 Microsoft Azure SQL 報表

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 所有活動和監控都將由平台透過自動化在內部執行。 這不需要任何人工干預。|
| **被其他函數取代？**   | 是的，現在有一個自動化系統，它使這些功能過時了。 |
| **受影響的產品領域**         | SQL 報表：現行 DTU、現行 DTU 詳情、獲取鎖定詳情、現行計畫指南清單、獲取查詢 ID 清單、獲取給定計畫 ID 的 SQL 查詢計畫、獲取查詢計畫和執行狀態、獲取節流設定、獲取等待 stats，列出最昂貴的查詢 |
| **部署選項**              | 雲端部署：影響 Microsoft 管理的實際執行環境和第 2 層到第 5 層沙箱環境。 |
| **狀態**                         | 已棄用：計畫移除日期為 2021 年 10 月。 |

### <a name="azure-sql-actions-in-lcs"></a>LCS 中的 Azure SQL 操作

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 我們正在棄用 LCS 中的一些 SQL 操作。 所有活動和監控都將由平台透過自動化在內部執行。 這不需要任何人工干預。 |
| **被其他函數取代？**   | 是的，現在有一個自動化系統，它使這些功能過時了。 |
| **受影響的產品領域**         | SQL 操作：建立計畫指南以強制計畫 ID、建立計畫指南以新增表提示、刪除計畫指南、禁用/啟用頁鎖和鎖升級、更新表的統計資訊、重建索引、建立索引 |
| **部署選項**              | 雲端部署：影響 Microsoft 管理的實際執行環境和第 2 層到第 5 層沙箱環境。 |
| **狀態**                         | 已棄用：計畫移除日期為 2021 年 10 月。 |

## <a name="feature-deprecation-effective-may-2021"></a>功能棄用於 2021 年 5 月生效

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>Lifecycle Services (LCS) 中的全球化入口網站

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 我們將棄用 LCS 中的全球化入口網站，因為此功能已被其他基於 LCS 的服務所取代。 |
| **被其他函數取代？**   | 是的，此功能已被 LCS [問題搜尋](../lifecycle-services/issue-search-lcs.md)和[動態監管警示送出服務](../lcs-solutions/submit-localization-alerts.md)取代。 |
| **受影響的產品領域**         | LCS 中的全球化入口網站|
| **部署選項**              | 雲端部署 |
| **狀態**                         | 已棄用 - 計畫移除日期為 2022 年 5 月。 |


## <a name="feature-removed-effective-january-28-2021"></a>功能已於 2021 年 1 月 28 日移除

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>處理 SQL 索引重組整理的批次處理作業

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 為了減少客戶操作、監控和維護索引管理的開銷，該功能已被刪除。 |
| **被其他函數取代？**   | 今後，索引維護將由 Microsoft 服務執行。 這將持續發生，而不會影響使用者的工作量。 |
| **受影響的產品領域**         | 財務和營運應用程式|
| **部署選項**              | 雲端部署 - 影響 Microsoft 管理的實際執行環境和第 2 層到第 5 層沙箱環境。 |
| **狀態**                         | 此功能已移除。 |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>財務和營運應用程式版本 10.0.17 的平台更新


### <a name="visual-studio-2015"></a>Visual Studio 2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 為了支援最新版本的 Visual Studio，必須對 Visual Studio 的 X++ 擴充函數進行一些更改。 這些更改與 Visual Studio 2015 不相容。 |
| **被其他函數取代？**   | Visual Studio 2017 將取代 Visual Studio 2015 作為部署和必備的版本。 |
| **受影響的產品領域**         | Visual Studio 開發工具 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：更新後，以前的 X++ 工具將從 Visual Studio 2015 中刪除，更新後的工具將不會安裝在 Visual Studio 2015 上。 對託管構建沒有影響。 對於構建虛擬機器，需要手動更新構建管道 (構建定義)，以將相依性從 MSBuild 14.0 (Visual Studio 2015) 更改為 MSBuild 15.0 (Visual Studio 2017)，如[更新 Azure Pipelines 中的舊管道](../dev-tools/pipeline-msbuild-update.md)中所述。 |

### <a name="user-avatar"></a>使用者頭像 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 導覽列右側顯示的使用者頭像是使用 Dynamics 365 標題控制項中的 API 檢索的，該控制項已被棄用。 |
| **被其他函數取代？**   | 使用者將在導覽列中的圓圈中看到他們的姓名縮寫。 這與目前在開發機器上使用的視覺效果相同。 |
| **受影響的產品領域**         | 網路使用者端 |
| **部署選項**              | 全部 |
| **狀態**                         | 從版本 10.0.17 移除 |

### <a name="enterprise-portal-ep-deprecation"></a>企業入口網站 (EP) 棄用  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 與 Dynamics AX 2012 企業入口網站 (EP) 相關的中繼資料構件已被棄用，因為財務和營運應用程式從未支援 EP。 |
| **被其他函數取代？**   | 否 |
| **受影響的產品領域**         | 網路使用者端 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：計畫在 2021 年 10 月版本中刪除所有 EP 代碼。 |

## <a name="deprecation-effective-december-2020"></a>2020 年 12 月起棄用

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11 已棄用對 Dynamics 365 的支援

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 自 2020 年 12 月起，Microsoft Internet Explorer11 已棄用對所有 Dynamics 365 產品和 Dynamics Lifecycle Services (LCS) 的支援，並且 2021 年 8 月之後將不再支援 Internet Explorer 11。<br><br>這將影響使用旨在透過 Internet Explorer 11 界面使用的 Dynamics 365 產品和 LCS 的客戶。 2021 年 8 月之後，此類 Dynamics 365 產品和 LCS 將不再支援 Internet Explorer 11。 |
| **被其他函數取代？**   | 我們建議客戶過渡到 Microsoft Edge。|
| **受影響的產品領域**         | 所有 Dynamics 365 產品和 LCS |
| **部署選項**              | 全部|
| **狀態**                         | 已棄用：2021 年 8 月之後將不再支援 Internet Explorer 11。|

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>財務和營運應用程式版本 10.0.15 的平台更新

### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Visual Studio 增益集套用中繼資料修補程式

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 2018 年 7 月推出的 8.1 版 [One Version](../../fin-ops/get-started/one-version.md) 服務更新不再支援中繼資料修補程式。 |
| **被其他函數取代？**   | 單個中繼資料修補程式不適用於受支援的版本。 而是套用累積品質更新。 |
| **受影響的產品領域**         | Visual Studio 增益集 |
| **部署選項**              | 開發虛擬機器 |
| **狀態**                         | 在 10.0.15 版本中，增益集不再包含在 Visual Studio 工具中。 |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>財務和營運應用程式版本 10.0.14 的平台更新

### <a name="online-users-page"></a>線上使用者頁面 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 這是為以前的使用者端/伺服器架構構建的舊版頁面。 此頁面上的資訊並不總是準確的，這可能會造成混淆和誤導。 |
| **被其他函數取代？**   | 我們將在未來的更新中提供一個新頁面。|
| **受影響的產品領域**         | 系統管理 |
| **部署選項**              | 全部 |
| **狀態**                         | 到 2021 年 10 月，此表格將被刪除。   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>財務和營運應用程式版本 10.0.13 的平台更新


### <a name="custom-code-defined-in-ssrs-report-properties"></a>SSRS 報表屬性中定義的自訂代碼 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 一般來說，自訂代碼提供的好處有限，同時需要大量資源和計算來支援。 自訂代碼主要由報表作者用於從自訂代碼程序集中調用公共方法。 但是，雲端託管服務不支援對 SSRS 報表的自訂程式組件的參考。 |
| **被其他函數取代？**   | 報表作者可以選取繼續從任何文字方塊運算式參考公共。NET API 以進行數學、轉換和格式操作。 如需相關資訊，請參閱[將代碼新增到報表 (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs)。  |
| **受影響的產品領域**         | RDL 中定義的包含自訂代碼的應用程式報表設計子集。 |
| **部署選項**              | 全部 |
| **狀態**                         | 在版本 10.0.13 中，編譯器將開始針對在 SSRS 報表定義中檢測到自訂代碼的執行個體發出警告。 若要解決此問題，請打開報表設計定義並刪除所有自訂代碼構件。 在未來的更新中，此警告將替換為編譯器錯誤。   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>三個 jQuery 組件庫的升級 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 正在更新三個 jQuery 組件庫以進行安全修復和保持即時性。   
| **被其他函數取代？**   | 以下組件庫正受到影響：jQuery (從版本 2.1.4 到版本 3.5.0)、jQuery UI (從版本 1.11.4 到版本 1.12.1)、jQuery qTip (從 2.2.1 到版本 3.0.3)。 移轉指南已由 jQuery 線上提供。  |
| **受影響的產品領域**         | 可擴展的控制項，特別是使用已棄用或刪除的 API 的自訂 JavaScript 代碼 |
| **部署選項**              | 全部 |
| **狀態**                         | 使用版本 10.0.13/Platform update 37，客戶可以透過啟用「升級三個 jQuery 組件庫」功能來選取移轉到最新的庫。 2021 年 4 月版本將強制移轉到新庫，以便有時間移轉受影響的 API。   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>現有的格線控制項/forceLegacyGrid () API

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 現有的格線控制項正在被新的格線控制項替換。 |
| **被其他函數取代？**   | [新的格線控制項](../..//fin-ops/get-started/grid-capabilities.md) |
| **受影響的產品領域**         | 網路使用者端 |
| **部署選項**              | 全部 |
| **狀態**                         | 在 10.0.13 版本中，新的格線控制項已普遍可用，客戶可以選取性地開啟此功能。 新的格線控制項將在 2021 年 10 月版本中預設啟用，目前的目標是在 2022 年 4 月強制執行。 當新的格線控制項成為強制性時，將不再受遵循 **forceLegacyGrid ()** API。 |

### <a name="personalization-without-saved-views"></a>沒有儲存檢視表的個人化 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 個人化子系統已透過儲存的檢視表功能進行了徹底檢查，因此它具有更好的效能並提供了額外的功能。 |
| **被其他函數取代？**   | 已儲存的檢視表 |
| **受影響的產品領域**         | 網路使用者端 |
| **部署選項**              | 全部 |
| **狀態**                         | 在 10.0.13/平台更新 37 版本中，儲存檢視表功能已普遍可用，客戶可以選取開啟此功能。 在 2021 年 10 月的版本中，儲存的檢視表功能將成為強制性的。 |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>財務和營運應用程式版本 10.0.12 的平台更新

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>包含無效欄位參考的格線或群組控制項表單擴充函數

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 格線或群組控制項上的資料組屬性用於自動顯示欄位組的所有欄位。 透過擴充函數新增的格線或群組控制項可能包含不再在欄位組上定義的欄位，或者可能缺少在欄位組上定義的欄位。 這可能會導致執行階段的行為不一致。 財務和營運應用程式版本 10.0.12 的平台更新現在將此問題歸類為編譯器 *警告*。 若要解決此問題，請打開表單擴充函數並儲存。
| **被其他函數取代？**   | 在未來的更新中，此編譯器警告將替換為編譯器錯誤。 |
| **受影響的產品領域**         | Visual Studio 開發工具 |
| **部署選項**              | 全部 |
| **狀態**                         | 財務和營運應用程式版本 10.0.12 的平台更新中引入了編譯器警告。 |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>財務和營運應用程式版本 10.0.11 的平台更新

### <a name="explicit-safe-lists-for-self-service-environments"></a>自助服務環境的明確安全清單

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 將 IP 移至安全清單的過程已更改。 自助服務不再支援 IP 安全清單。 |
| **被其他函數取代？**   | 如需相關資訊，請參閱[設定 Azure Active Directory 條件式存取](/appcenter/general/configuring-aad-conditional-access)。|
| **受影響的產品領域**         | 安全性 |
| **部署選項**              | 雲端 |
| **狀態**                         | 已棄用：對於自助服務部署，此功能已完全棄用。 |

### <a name="visual-studio-2015"></a>Visual Studio 2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 為了支援最新版本的 Visual Studio，必須對 Visual Studio 的 X++ 擴充函數進行一些更改。 這些更改與 Visual Studio 2015 不相容。 |
| **被其他函數取代？**   | Visual Studio 2017 將取代 Visual Studio 2015 作為部署和必備的版本。 |
| **受影響的產品領域**         | Visual Studio 開發工具 |
| **部署選項**              | 全部 |
| **狀態**                         | 在版本 10.0.13 (平台更新 37) 或更高版本上部署的虛擬機器包含 Visual Studio 2017。 版本 10.0.16 (平台更新 40) 是支援 Visual Studio 2015 的最終版本。 僅具有 Visual Studio 2015 的虛擬機器將無法更新到版本 10.0.17 (平台更新 41)。 |

### <a name="field-groups-containing-invalid-field-references"></a>包含無效欄位參考的欄位組

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 資料表中繼資料定義中的欄位組可能包含無效的欄位參考。 如果部署了這些欄位組，它們可能會導致 Financial Reporting 和 Microsoft SQL Server Reporting Services (SSRS) 中的執行階段失敗。 平台更新 23 引入了一個編譯器 *警告*，可以解決此中繼資料問題。 財務和營運應用程式版本 10.0.11 的平台更新將此問題歸類為編譯器 *錯誤*。<p>若要修復此問題，請按照以下步驟操作。</p><ol><li>從資料表欄位組定義中移除無效的欄位參考。</li><li>重新編譯。</li><li>確保任何錯誤都得到解決。</li></ol> |
| **被其他函數取代？**   | 此編譯器錯誤永久替換編譯器警告。  |
| **受影響的產品領域**         | Visual Studio 開發工具 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：編譯器警告是財務和營運應用程式版本 10.0.11 的平台更新中的編譯器錯誤。 |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>使用 SHA1 雜湊演算法建立的 ISV 授權

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 建立獨立軟體廠商 (ISV) 授權的過程已更改。 如需相關資訊，請參閱[獨立軟體廠商 (ISV) 授權](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes)。 |
| **被其他函數取代？**   | 是。 使用 Windows PowerShell 建立授權。 |
| **受影響的產品領域**         | Visual Studio 開發工具 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：使用 SHA1 雜湊演算法建立的 ISV 授權。 此演算法依賴於使用 MakeCert 實用程序建立的授權，並且此公用程式已被棄用。<br><br>已棄用：將 SHA1 用於安全或雜湊目的。 SHA1 將於 2021 年初停止執行。 因此，不應再使用它。<br><br>已移除：支援傳輸層安全性協定 (TLS) 1.0 和 TLS 1.1 傳入或傳出請求。 |

## <a name="platform-update-32"></a>平台更新 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>工作流程程請求更改對話方塊不再包括使用者選取下拉式清單

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 這是安全性問題，因為更改請求可能會發送給非預期使用者。 這也是可用性問題，因為它迫使使用者確定工作流程發起者是誰並手動選取他們。  |
| **被其他函數取代？**   | 否 |
| **受影響的產品領域**         | 工作流程 |
| **部署選項**              | 全部 |
| **狀態**                         | 使用者選取下拉式清單已從平台更新 32 中的請求更改對話方塊中刪除。 請求更改請求將按預期自動發送給發起者。 如需此函數的相關資訊，請參閱[在工作流程程核准過程的動作](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change)。 |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>雲端託管服務轉譯的分頁文件中不再支援嵌入式鑽研連結 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 嵌入在服務轉譯的文件中的導覽 URL 可能包含敏感的商業資料。 我們正在取消對文件中嵌入鑽研連結的支援，以作為進一步保護客戶資料的安全性預防措施。 由於此更改，使用者還將受益於改進的效能，同時以互動方式產生文件。  |
| **被其他函數取代？**   | 否 |
| **受影響的產品領域**         | 報告 |
| **部署選項**              | 全部 |
| **狀態**                         | 此功能正在從服務中主動刪除。<br><br>現代使用者端提供了許多用於產生檢視表的選項，其中包括自動產生的連結以幫助導覽應用程式。 由該轉譯服務的分頁文件被推薦用於透過電子郵件、存檔和為收件者列印的外部通訊。 我們改進了直接在瀏覽器中預覽文件的體驗，可以直接存取本機印表機。 如需相關資訊，請參閱[使用嵌入式檢視器預覽 PDF 文件](../analytics/preview-pdf-documents.md)。 |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>先前關於已移除或棄用功能的公告
若要進一步了解先前版本中已刪除或棄用的功能，請參閱[以前版本中刪除或棄用的功能](../migration-upgrade/deprecated-features.md)。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
