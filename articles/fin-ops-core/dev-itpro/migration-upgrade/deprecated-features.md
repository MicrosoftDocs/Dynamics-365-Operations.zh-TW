---
title: 在以前版本中移除或棄用的函數
description: 本主題描述了已移除或計畫從 Dynamics 365 for Finance and Operations 中移除的函數和以前的版本。
author: sericks007
ms.date: 02/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6dfe1cf9d3d67c6b65f64248d48a2e7420a47c93
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460195"
---
# <a name="removed-or-deprecated-features-in-previous-releases"></a>在以前版本中移除或棄用的函數

[!include [banner](../includes/banner.md)]



> [!IMPORTANT]
> 本主題已不再更新。 若要查看已從財務和營運應用程式中移除或棄用的函數現行的清單，請搜尋與您正在使用的應用程式相關的 **「移除或棄用的函數」** 內容。

本主題描述了已移除或計畫從 Dynamics 365 for Finance and Operations 棄用的函數和以前的版本。

- *已移除* 函數不再於產品中提供該函數。
- *已棄用* 函數未在有效開發中，可能會在未來的更新中刪除。

此清單旨在幫助您考慮移除和棄用這些自己的計畫。 

有關財務和營運應用程式中對象的詳細資訊，可在[技術參考報告 ](/dynamics/s-e/global/axtechrefrep_61)中找到。 您可以比較這些不同版本的報告，以了解每個版本的財務和營運應用程式中已更改或移除的對象。

## <a name="finance-1007-with-platform-update-31"></a>附 Platform 更新 31 的 Finance 10.0.7

### <a name="chinese-voucher-types-without-account-groups-selection"></a>沒有帳戶組選擇的中文憑證類型
|&nbsp;   | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 更改為具有帳戶組選擇的函數。 |
| **被其他函數取代？**   | 是 |
| **受影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：到 2020 年 12 月 1 日，我們計畫不再支援沒有帳戶組選擇的中文憑證類型安裝。 在 10.0.7 中的最新消息的新函數中尋找更多相關詳情 |

## <a name="finance-and-operations-1006-with-platform-update-30"></a>附 Platform 更新 30 的 Finance and Operations 10.0.6


### <a name="dimensionhashgethashstr-_message"></a>DimensionHash.getHash(str _message)

|&nbsp;   | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Windows 已棄用 SHA1，如[SHA1 憑證的 Windows 增強函數](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx)所記錄。  |
| **被其他函數取代？**   | 是 |
| **受影響的產品領域**         | 應用程式 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：到 2020 年 4 月 1 日，開發人員必須使用該 **HasFunction** 類中的平台 API。 |

### <a name="hashcomputesha1hashstring-message"></a>Hash.ComputeSHA1Hash(string message)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Windows 已棄用 SHA1，如[SHA1 憑證的 Windows 增強函數](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx)所記錄。  |
| **被其他函數取代？**   | 是 |
| **受影響的產品領域**         | 平台 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：到 2020 年 4 月 1 日，開發人員必須使用該 **HasFunction** 類中的平台 API。 |


### <a name="formdatetimecontrolsetutcstring"></a>FormDateTimeControl.setUtcString()

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 我們正在停用 **setUtcString()** 方法，因為有更好的替換方法可用。 |
| **被其他函數取代？**   | 是 |
| **受影響的產品領域**         | 平台 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：到 2020 年 10 月 1 日，我們計畫不再支援 **setUtcString()** 方法。 開發人員應該使用 **setUtcDateTime()** 代替方法。 |

### <a name="blocklist-report-it--feature-reference-it-00001"></a>封鎖清單報告 (IT) – 函數參考 IT-00001

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 沒有法律要求。 |
| **被其他函數取代？**   | 否 |
| **受影響的產品領域**         | 義大利文本地化 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：到 2020 年 10 月 1 日，我們計畫不再支援此報告。 |

### <a name="domestic-tax-report--feature-reference-it-00003"></a>國內稅務報告 – 函數參考 IT-00003

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 沒有法律要求。 |
| **被其他函數取代？**   | 否 |
| **受影響的產品領域**         | 義大利文本地化 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：到 2020 年 10 月 1 日，我們計畫不再支援 **國內稅務報告 – 函數參考 IT-00003**。 |

## <a name="october-2019-deprecation-announcement"></a>2019 年 10 月棄用公告

### <a name="flowchart-diagrams-in-business-process-modeler"></a>商業流程建模工具中的流程圖

<table>
<tbody>
<tr>
<td><strong>棄用/移除的原因</strong></td>
<td>我們正在棄用商業流程建模工具 (BPM) 中的流程圖組件，因為舊版設計導致使用率低。</td>
</tr>
<tr>
<td><strong>被其他函數取代？</strong></td>
<td>否</td>
</tr>
<tr>
<td><strong>受影響的領域</strong></td>
<td>商業流程建模工具</td>
</tr>
<tr>
<td><strong>狀態</strong></td>
<td>已棄用：BPM 中的流程圖組件預計將在 2020 年移除。 以下函數將不再提供：
<ul>
<li>所有流程圖都將是讀取專用且無法編輯。 與流程圖活動相關的形狀屬性也將無法提供。 這些流程圖包括自動產生的預設流程圖和基於這些預設流程圖修改的自訂流程圖。</li>
<li>該流程步驟都將是讀取專用且無法編輯。</li>     
<li>舊版適合度/落差分析函數將無法提供。 因此，不會自動建立落差清單或可用於匯出的落差清單。
<p><strong>注意事項：</strong>此函數之前已棄用並替換為 Microsoft Azure DevOps 整合。</p>
</li>
<li>流程圖的版本歷史記錄將無法提供。</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="finance-and-operations-1005-with-platform-update-29"></a>附 Platform 更新 29 的 Finance and Operations 10.0.5

### <a name="us-payroll-tax-updates"></a>美國薪資稅更新

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 由於使用率低且現在透過策略整合提供的增強函數，我們將停用美國薪資函數的稅務更新。  |
| **被其他函數取代？**   | 是 |
| **受影響的產品領域**         | 薪資表 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：到 2024 年 7 月 31 日，我們計畫不再向美國薪資客戶提供稅務更新。 該函數將保留在產品中，但增強函數將不再使函數保持最新狀態，並且將根據具體情況評估任何產品缺陷。 |

>[!NOTE]
> 這代表了與 2021 年 10 月 1 日原停產日期相比的變化。 如需相關資訊，請參閱[稅務更新在 Microsoft Dynamics 365 for Finance and Operations 中的美國薪資函數停用](https://aka.ms/financepayrollfaq)。


### <a name="data-management-staging-clean-up"></a>資料管理暫存清理
|&nbsp;   | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不滿足安排定期清理所需的核心要求。 |
| **被其他函數取代？**   | 是的，正在新增作業歷史記錄清理函數以從整體上滿足場景。 |
| **受影響的產品領域**         | 資料管理 |
| **部署選項**              | 全部  |
| **狀態**                         | 已棄用：要移除的函數的目標時間範圍是 2020 年 12 月。 |

## <a name="finance-and-operations-1004-with-platform-update-28"></a>附 Platform 更新 28 的 Finance and Operations 10.0.4

### <a name="france-fec-accounting-data-export-in-xml"></a>法國：以 XML 格式匯出 FEC 會計資料

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 替換為 TXT 格式，**法國 FEC 審計檔案** 可透過 **總帳**\>**週期任務**\>**資料匯出** 提供。
| **被其他函數取代？**   | 是 |
| **受影響的產品領域**         | 總帳 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用。 要移除的函數的目標時間範圍是 2020 年 7 月。 |


### <a name="legacy-navigation-bar"></a>舊版導覽列

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 與其他 Dynamics 和 Office 產品的標題對齊。 如需相關資訊，請參閱[更新了與 Office 標題對齊的導覽列](/business-applications-release-notes/April19/dynamics365-finance-operations/updatednavbar)。
| **被其他函數取代？**   | 從 Platform 更新 24 開始，引入了具有搜尋函數的重新設計導航列。 |
| **受影響的產品領域**         | 網路用戶端 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：從 2020 年 4 月開始，舊版導航列將不再提供。 在此之前，客戶可以透過 **用戶端效能選項** 頁面還原至舊版導覽列。 |


## <a name="finance-and-operations-1002-with-platform-update-26"></a>附 Platform 更新 26 的 Finance and Operations 10.0.2


### <a name="legacy-default-action-behavior"></a>舊版預設動作行為

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 格線中預設動作的舊版行為會導致在透過個人化重新排序格線資料欄之後具有預設動作連結的未預期資料欄。 新的黏性預設動作函數糾正了這一點。 如需相關資訊，請參閱[格線中的黏性預設動作](/business-applications-release-notes/October18/dynamics365-finance-operations/sticky-default-action)。 |
| **被其他函數取代？**   | 從 Platform 更新 21 開始，引入了「黏性預設動作」函數。 此函數可以在 **用戶端效能選項** 頁面上啟用。 |
| **受影響的產品領域**         | 網路用戶端中的格線 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：從 2020 年 4 月開始，黏性預設動作將成為預設行為，沒有還原到舊版行為的機制。 |

### <a name="legacy-is-one-of-filtering-experience"></a>舊版是篩選體驗的「其中之一」

|&nbsp;   | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 「其中之一」篩選體驗在 Platform 更新 22 中經過重新設計，搭配最終成為唯一「其中之一」篩選體驗的計畫。 |
| **被其他函數取代？**   | 從 Platform 更新 22 開始，改善的「其中之一」篩選體驗在 **用戶端效能選項** 頁面有提供。 如需相關資訊，請參閱[最佳化是篩選體驗之一](/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering)。 |
| **受影響的產品領域**         | 網路用戶端 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：從 2020 年 4 月開始，改善的「其中之一」體驗將成為預設行為，沒有還原到舊版行為的機制。 |

### <a name="parameter-to-enable-sales-orders-with-multiple-project-contract-funding-sources"></a>啟用具有多個專案合約資金提撥來源的銷售訂單的參數
在專案合約有多個資金提撥來源的情況下，支援建立專案型的銷售訂單，透過 **專案管理參數** 設定 **允許有多筆資金提撥來源的專案的銷售訂單** 來實現。 在預設情況下，此參數未啟用。 

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 移除參數後，該函數將一直啟用。 |
| **被其他函數取代？**   | 否。 將一直啟用支援具有多筆資金提撥來源的專案型的銷售訂單的函數。   |
| **受影響的產品領域**         |**允許具有多筆資金提撥來源的專案的銷售訂單** 參數將被移除。 移除參數時會修改以下方法：在 **ProjStatusType** 類別中的 **ctrlSalesOrderTable** 方法、**ProjId** 欄位的 **驗證** 方法，以及 **SalescreateOrder** 表單中的 **執行** 方法。 移除參數後，將棄用以下方法：在 **ProjTable** 資料表檔案中的 **IsSalesOrderAllowedForMultipleFundingSources**、在 **ProjTable** 資料表檔案中的 **IsAllowSalesOrdersForMultipleFundingSourcesParamEnabled** 方法、在 **ProjParameters** 表單和 **ProjParameterEntity** 檔案中的 **AllowSalesOrdersForMultipleFundingSources** 資料欄位，以及在 **ProjTable** 資料表檔案中的 **IsAssociatedToMultipleFundingSourcesContract** 私人方法。 |
| **部署選項**              | 全部  |
| **狀態**                         | 計畫在 2020 年 4 月的版本波次中棄用。 |

### <a name="legacy-workflow-reports-for-tracking-and-instance-status"></a>用於追蹤的舊版工作流程報告和執行個體狀態

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 已棄用用於追蹤的舊版工作流程報告和執行個體狀態，因為它們不再從導航列中參考。 報告名稱為 WorkflowWorkflowInstanceByStatusReport 和 WorkflowWorkflowTrackingReport。 |
| **被其他函數取代？**   | 可以改用工作流程歷程記錄表單。 |
| **受影響的產品領域**         | 網路用戶端 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：要移除的函數的目標時間範圍是 2020 年 4 月。 |

## <a name="finance-and-operations-1001-with-platform-update-25"></a>附 Platform 更新 25 的 Finance and Operations 10.0.1

### <a name="deprecated-apis-and-potential-breaking-changes"></a>已棄用的 API 和潛在的中斷性變更


#### <a name="deriving-from-internal-classes-is-deprecated"></a>已棄用從內部類衍生的做法

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 在 Platform 更新 25 之前，可以建立衍生自另一個套件/模組中定義的內部類/資料表的類別或資料表。 這不是一種安全的編碼做法。 自 Platform 更新 25 起，編譯器將顯示警告。 |
| **被其他函數取代？**   | 編譯器警告將替換為 Platform 更新 26 中的錯誤。 此更改在執行時向後兼容，這代表 Platform 更新 25 或更高版本可以部署在任何沙箱或實際執行環境中，而無需修改自訂代碼。 此更改僅影響開發和編譯時間。|
| **受影響的產品領域**         | Visual Studio 開發工具 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：警告將在 Platform 更新 26 中成為編譯錯誤。 |

#### <a name="overriding-internal-methods-is-deprecated"></a>棄用覆寫內部方法

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 在 Platform 更新 25 之前，可以覆寫在另一個套件/模組中定義的衍生類別的內部方法。 這不是一種安全的編碼做法。 自 Platform 更新 25 起，編譯器將顯示警告。 |
| **被其他函數取代？**   | 在 Platform 更新 26 中，這警告將被一個編譯錯誤所取代。 此更改在執行時向後兼容，這代表 Platform 更新 25 或更高版本可以部署在任何沙箱或實際執行環境中，而無需修改自訂代碼。 此更改僅影響開發和編譯時間。 |
| **受影響的產品領域**         | Visual Studio 開發工具 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：警告將在 Platform 更新 26 中成為編譯錯誤。 |

## <a name="finance-and-operations-1000-with-platform-update-24"></a>附平台更新 24 的 Finance and Operations 10.0.0

### <a name="renaming-released-products"></a>重新命名已發布的產品 
| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 當您使用 **重新命名主索引鍵** 函數更改已發布產品的 ItemId，僅更新直接的外部索引鍵。 對已發布產品的任何其他參考，例如來自生產訂單的參考，都將保留舊的 ItemId。 因此，可能存在不一致的資料，最終會封鎖業務流程。 |
| **被其他函數取代？**   | 否。 |
| **受影響的產品領域**         | 產品資訊管理 |
| **部署選項**              | 全部  |
| **狀態**                         | 從附 Platform 更新 24 的 Finance and Operations 10.0.0 中移除|


## <a name="finance-and-operations-813-with-platform-update-23"></a>附平台更新 23 的 Finance and Operations 8.1.3

### <a name="sql-server-reporting-services-reportviewer-control"></a>SQL Server Reporting Services ReportViewer 控制
客戶可以使用由嵌入式 SQL Server Reporting Services (SSRS) ReportViewer 控制提供的 **匯出** 動作，下載財務和營運應用程式產生的文件。 這種 HTML 型報告的簡報為使用者提供了文件的非分頁預覽。

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | HTML 型的預覽體驗的非分頁特性並 **不能** 提供與 Finance and Operations 最終製作的實體文件的準確度。 透過完全採用 PDF 作為業務文件的標準格式，使用者可以在產生應用程式報告時利用現代檢視體驗和改善的效能。 |
| **被其他函數取代？**   | 展望未來，PDF 文件將成為 Finance and Operations 呈現報告的預設格式。   |
| **受影響的產品領域**         | 這種變化確實 **不會** 影響以電子方式分發報告或直接傳送到印表機的客戶場景。    |
| **部署選項**              | 全部  |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 計畫在 2019 年 5 月的 Platform 更新中使用嵌入式 PDF 檢視器自動預覽應用程式報告的函數。 |

### <a name="client-kpi-controls"></a>用戶端 KPI 控制
嵌入式關鍵績效指標 (KPI) 可以在 Visual Studio 中由開發人員建模並由終端使用者進一步自訂。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 用於定義 KPI 的本機用戶端控制，其客戶接受度較低，並且依賴開發人員新增可追蹤的指標。 |
| **被其他函數取代？**   | PowerBI.com 服務提供世界一流的工具，用於根據來自外部來源的資料定義和管理 KPI。  在即將發行的版本中，我們計畫讓您能夠將託管在 PowerBI.com 上的解決方案嵌入到應用程式工作區中。   |
| **受影響的產品領域**         | 這一更新將阻止開發人員在 Visual Studio 設計工具中引入新的 KPI 控制。    |
| **部署選項**              | 全部  |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="deprecated-apis-and-future-breaking-changes"></a>已棄用的 API 和未來中斷性變更

#### <a name="field-groups-containing-invalid-field-references"></a>包含無效欄位參考的欄位組

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 資料表中繼資料定義可能具有包含無效欄位參考的欄位組。 如果已部署，這可能會導致 Financial Reporting 和 SQL Server Reporting Services (SSRS) 中的執行階段失敗。 這個問題現行被歸類為 *編譯器警告* 而不是一個 *錯誤*，這代表可部署套件的建立和部署可以在不解決問題的情況下繼續執行。 若要解決此問題：<br><br>1. 從資料表欄位組定義中移除無效的欄位參考。<br><br>2. 重新編譯。<br><br>3. 確保解決任何警告或錯誤。 |
| **被其他函數取代？**   | 這警告將在未來被一個編譯錯誤所取代。 |
| **受影響的產品領域**         | Visual Studio 開發工具 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：警告是針對財務和營運應用程式版本 10.0.11 的平台更新的編譯時間錯誤。 |

#### <a name="complete-list"></a>完整清單
若要存取已棄用的 API 的完整清單，請參閱[棄用方法和中繼資料元素](deprecation-deletion-apis.md)。

## <a name="finance-and-operations-81-with-platform-update-20"></a>附平台更新 20 的 Finance and Operations 8.1

### <a name="batch-transfer-rules-for-subledger-journal-account-entries"></a>子分類帳日記帳科目分錄的批次轉移規則
總帳參數中不推薦使用同步傳輸模式。  此模式已被非同步和安排專用批次作業所取代，後者已作為傳輸選項存在。 如需相關資訊，請參閱[總帳參數 - 批次轉移規則](https://community.dynamics.com/365/financeandoperations/b/financials/archive/2019/03/15/general-ledger-parameters-batch-transfer-rules)部落格。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 由於對系統的效能影響，我們正在移除同步選項。 |
| **被其他函數取代？**   | 非同步和已安排的批次作業是替代同步的選項。   |
| **受影響的產品領域**         | 總帳、應付帳款、應收帳款、採購、費用    |
| **部署選項**              | 全部  |
| **狀態**                         | 已棄用：要移除的函數，其目標時間範圍是 10.0 版本。|

### <a name="electronic-reporting-for-russia"></a>俄羅斯的電子報表
用於設定聲明的 .txt 和 .xml 文件格式的函數。 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 替換為電子報表。 |
| **被其他函數取代？**   | 是。 |
| **受影響的產品領域**         | 總帳 |
| **部署選項**              | 全部 |
| **狀態**                         | 從附 Platform 更新 20 的 Finance and Operations 8.1 中移除 |

### <a name="financial-reports-generator-for-russia"></a>俄羅斯的財務報表產生器
專門設定會計和稅務報告的資料收集，並將資料匯出到 XLS 和 DOC 報告範本的工具。 函數部分：將資料匯出到 XLS 和 DOC 報告範本、查找、移除固定要求。 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 移除的部分將替換為電子報表。 |
| **被其他函數取代？**   | 是。 財務報表安裝使用者介面應用於安裝 GL 帳戶或稅務登記報表的資料收集規則。 將資料匯出為各種檔案類型、固定要求，以及應在電子報表中設定的類似查找資料收集規則。 |
| **受影響的產品領域**         | 總帳。 |
| **部署選項**              | 全部 |
| **狀態**                         | 從附 Platform 更新 20 的 Finance and Operations 8.1 中移除 |

### <a name="integration-with-external-providers-for-sending-electronic-reporting-through-communication-channels-for-russia"></a>與外部提供者整合，透過俄羅斯的通訊管道傳送電子報表
將產生的聲明電子檔案匯出到資料夾的函數，以進一步傳送給電子報表的官方提供者並將狀態匯入。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 替換為電子訊息的可設定函數。 |
| **被其他函數取代？**   | 是。  |
| **受影響的產品領域**         | 總帳，稅金 |
| **部署選項**              | 全部 |
| **狀態**                         | 從附 Platform 更新 20 的 Finance and Operations 8.1 中移除 |


### <a name="profit-tax-register-wizard"></a>收益稅登記精靈
為新的收益稅登記建立範本的函數。 此函數為新登記建立 X++ 對象，然後將其建立為有新增適當計算邏輯的範本。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 函數與 Finance and Operations 擴充模型不相容。 |
| **被其他函數取代？**   | 否 |
| **受影響的產品領域**         | 稅金 |
| **部署選項**              | 全部 |
| **狀態**                         | 從附 Platform 更新 20 的 Finance and Operations 8.1 中移除 |

### <a name="payroll-and-human-resources-for-russia"></a>俄羅斯的薪資和人力資源
俄羅斯國家特定模組，用於管理員工行政資訊、員工時間表詳情、薪資核算和建立薪資單。 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 薪資單不包含在 Dynamics 365 產品組合的全球策略重點中。 合作夥伴和 ISV 最適合提供符合當地法規和稅務更新的薪資單函數。|
| **被其他函數取代？**   | 否|
| **受影響的產品領域**         | 俄羅斯的薪資和人力資源管理 |
| **部署選項**              | 全部 |
| **狀態**                         | 已棄用：要移除的函數，其目標時間範圍是 10.0 版本的其中一個未來更新。 |

## <a name="finance-and-operations-80-with-platform-update-15"></a>附平台更新 15 的 Finance and Operations 8.0
此版本未移除或棄用任何函數。 Platform 更新 15 是累積性的，包含來自 Platform 更新 13、Platform 更新 14 和 Platform 更新 15 的新函數或更改的函數。

## <a name="finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>附 Platform 更新 12 的 Finance and Operations Enterprise Edition 7.3

### <a name="personalized-product-recommendations"></a>個人化產品推薦 
從 2018 年 2 月 15 日開始，零售商將無法再在銷售點 (POS) 裝置上顯示個人化產品建議。 如需相關資訊，請參閱 [產品建議概覽](../../../commerce/product-recommendations.md)。  

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 我們正在移除現行版本的產品建議服務，因為我們使用更好的演算法和更新零售導向功能來重新設計了此函數。  |
| **被其他函數取代？**   | 否。 但是，在 2018 年春季之後，我們計畫恢復此函數以利用新的建議服務。   |
| **受影響的產品領域**         | POS 中的個人化產品推薦                                                    |
| **部署選項**              | 全部                                                                                      |
| **狀態**                         |自 2018 年 2 月 15 日起移除。 這會影響客戶執行 Dynamics 365 for Operations 1611 及更高版本。  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>電子報表 (ER) 函數清單的擴充函數
不再支援引入要在 ER 運算式建立幫手中使用的自訂函數的可能性 (如需相關資訊，請參閱[擴充電子報表 (ER) 函數的清單](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md))。 由於 ER API 的變化，從 ER 運算式建立幫手調用內建函數的 API 變為內部函數，無法再擴充。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 代碼密封方案  |
| **被其他函數取代？**   | 無。 每當需要新的內建函數時，必須向 ER 架構團隊提出新的擴充要求。<br><br>作為 ER 團隊正在開發要求函數時的臨時解決方法，可以將所需的邏輯編碼為自訂應用程式類別的方法。 可以在 ER 運算式中存取此方法，作為 **應用程式\類別** 的已新增 ER 資料來源的屬性，其參考該自訂應用程式類別的類型。  |
| **受影響的產品領域**         | 電子報表架構                                                      |
| **部署選項**              | 全部                                                                                      |
| **狀態**                         | 從 Finance and Operations，Enterprise edition 7.3 開始移除。    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>按品項組的庫存和按庫存維度帳齡報表的庫存

Finance and Operations 不再支援這兩個報表。 相反，**庫存帳齡** 報告可用於改善使用者體驗。

| &nbsp;  | &nbsp; |
|--------------|-----------------------|
| **棄用的原因**       | 重複函數  |
| **被其他函數取代？** | 是。 **庫存帳齡** 報告已取代這兩份報表。     |
| **受影響的產品領域**       | 庫存管理、成本管理        |
| **部署選項**        | 全部|
| **狀態**                       | 已棄用：兩份報表的選單項目已在 7.3 版中移除。 但是，報表的代碼仍保留在產品中。 該計畫是在未來的版本中移除代碼。 |

### <a name="power-bi-content-packs-available-on-appsource"></a>AppSource 上提供的 Power BI 內容套件
可在 [Microsoft AppSource](https://appsource.microsoft.com) 網站上下載的 **成本管理**、**財務表現** 和 **Retail Channel Performance** 內容套件，因 Microsoft Power BI 中的產品更新而被棄用。 用於將這些內容套件部署到 PowerBI.com 的系統管理表單也在 Finance and Operations 中被棄用。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Microsoft Power BI 中的產品更新 |
| **被其他函數取代？**   | 可 [AppSource](https://appsource.microsoft.com) 在網站上下載的 **成本管理**、**財務表現** 和 **Retail Channel Performance** 內容套件，正在被分析應用程式所取代，並允許在資料庫層級整合解決方案。 如需分析應用程式的相關資訊，請參閱[工作區中的嵌入式 Power BI](../../dev-itpro/analytics/embed-power-bi-workspaces.md)。    |
| **受影響的產品領域**         | 成本管理、Finance 和 Retail                                                                                               |
| **部署選項**              | 雲端專用 (內部部署不支援與 PowerBI.com 整合。)                                                                                                             |
| **狀態**                         | 已棄用：移除函數的目標時間範圍是 2018 年第 2 季。    |

### <a name="standard-ui-in-data-management-workspace"></a>資料管理工作區中的標準 UI

資料管理中的標準 UI 是舊版 UI，它是使用者存取資料管理工作區時呈現給使用者的預設 UI。

| &nbsp;  | &nbsp; |
|------------------|-------------------------|
| **棄用/移除的原因** | 我們正投資於在新 UI 中提供新的使用者體驗。             |
| **被其他函數取代？**   | 新的 UI 稱為 *增強視圖* 正在替換舊的 UI。            |
| **受影響的產品領域**         | 資料管理工作區                                                     |
| **部署選項**              | 全部                                                                           |
| **狀態**                         | 已棄用：要移除的函數的目標時間範圍是 2018 年第 2 季。 |

### <a name="excise-sales-tax-service-tax-for-india"></a>印度的特種消費稅、銷售稅、服務稅

這些稅款已納入印度 GST。

|  &nbsp;                                           |      &nbsp;                                                                   |
|---------------------------------------------|-------------------------------------------------------------------------|
| **移除或棄用的原因**       | 這些稅款已納入印度 GST。                          |
| **被其他函數取代？**            | 印度 GST                                                              |
| **受影響的產品領域**                  | 稅金                                                                     |
| **部署選項**                       | 所有模組                                                   |
| **狀態**                                  | 已棄用：尚未為此函數設定移除日期。 |    

### <a name="file-validation-utility-fvu-for-india"></a>印度的檔案驗證利用率 (FVU)

|              &nbsp;                               |      &nbsp;                                                                   |
|---------------------------------------------|-------------------------------------------------------------------------|
| **移除或棄用的原因**       | 缺乏客戶使用                                                  |
| **被其他函數取代？**            | 否                                                                      |
| **受影響的產品領域**                  | 印度扣繳稅款                                                  |
| **部署選項**                       | 所有模組                                                                    |
| **狀態**                                  | 已棄用：尚未為此函數設定移除日期。   |        

### <a name="tdstcs-certificate-for-india"></a>印度 TDS/TCS 憑證

使用者可以從政府入口網站下載。

|             &nbsp;                                |    &nbsp;                                                                     |
|---------------------------------------------|-------------------------------------------------------------------------|
| **移除或棄用的原因**       | 缺乏客戶使用                                                  |
| **被其他函數取代？**            | 否                                                                      |
| **受影響的產品領域**                  | 印度扣繳稅款                                                  |
| **部署選項**                       | 所有模組                                                                   |
| **狀態**                                  | 已棄用：尚未為此函數設定移除日期。     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>印度的進出口 (EXIM) 激勵計畫


|              &nbsp;                               |        &nbsp;                                                                 |
|---------------------------------------------|-------------------------------------------------------------------------|
| **移除或棄用的原因**       | 缺乏客戶使用                                                  |
| **被其他函數取代？**            | 否                                                                      |
| **受影響的產品領域**                  | 進出口                                                       |
| **部署選項**                       | 所有模組                                                                    |
| **狀態**                                  | 已棄用：尚未為此函數設定移除日期。  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>個人化產品推薦 
從 2018 年 2 月 15 日開始，零售商將無法再在銷售點 (POS) 裝置上顯示個人化產品建議。 如需相關資訊，請參閱 [產品建議概覽](../../../commerce/product-recommendations.md)。  

|  &nbsp; |  &nbsp;|
|------------|--------------------|
| **棄用/移除的原因** | 我們正在移除現行版本的產品建議服務，因為我們使用更好的演算法和更新零售導向功能來重新設計了此函數。  |
| **被其他函數取代？**   | 否。 但是，在 2018 年春季之後，我們計畫恢復此函數以利用新的建議服務。   |
| **受影響的產品領域**         | POS 中的個人化產品推薦                                                    |
| **部署選項**              | 全部                                                                                      |
| **狀態**                         |自 2018 年 2 月 15 日起移除。 這會影響客戶執行 Dynamics 365 for Retail 7.2 及更高版本。 |


## <a name="finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>附 Platform 更新 8 的 Finance and Operations Enterprise Edition 2017 年 7 月

### <a name="currency-conversion-for-accounting-and-reporting-currencies"></a>會計和報表貨幣的貨幣轉換

引入歐元時，引入了會計和報表貨幣的貨幣轉換。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 有限使用和新增複製法律實體函數作為替代方案。      |
| **被其他函數取代？**   | 否，但新增了複製法律實體和設定函數，以便更輕鬆地轉移到具有不斷變化核心要求的公司。 |
| **受影響的產品領域**         | 財務管理     |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。   |


### <a name="warehouse-mobile-devices-portal"></a>倉庫行動裝置入口網站

倉庫行動裝置入口網站 (WMDP) 是一個獨立組件，主要用於內部自我部署。 Finance and Operations 不再支援此組件。 一個改善使用者體驗的本機應用程式已經取代了 WMDP 的函數。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 重複函數。       |
| **被其他函數取代？**   | 是。 Finance and Operations 已取代此函數 - 倉儲。 如需安裝和先決條件的相關資訊，請參閱[安裝和安裝倉儲應用程式蓋覽 ](../../../supply-chain/warehousing/install-configure-warehousing-app.md)。 |
| **受影響的產品領域**         |  Warehouse Management、運輸管理     |
| **部署選項**              | 倉庫行動裝置入口網站 (WMDP) 是一個獨立組件，主要用於內部自我部署。               |
| **狀態**                         | 已棄用：要移除的函數的目標時間範圍是 2019 年第 4 季。   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>用於手動比對的進階銀行對帳資料比對規則

在對帳資料工作表中手動比對文件時，使用比對規則來選取和標記銀行文件。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用有限。                                                                         |
| **被其他函數取代？**   | 否。 應使用資料欄篩選功能來尋找要對帳的文件。 |
| **受影響的產品領域**         | 現金和銀行管理                                                               |
| **部署選項**              | 全部                                                                                    |
| **狀態**                         | 自 2017 年 7 月起移除。                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>附 Platform 更新 3 的 Dynamics 365 for Operations 1611

### <a name="aeb-payment-formats-for-spain"></a>西班牙的 AEB 付款格式

使用 Consejo Superior Bancario 付款格式向銀行發送客戶付款和廠商付款的匯款檔案。 這些格式的內容由 Asociación Española de Banca 確定。 它涵蓋了 Cuaderno 19、32、58、34。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                                  |
| **被其他函數取代？**   | 是的，適用於西班牙的 ISO20022 貸記轉帳和直接借記付款格式 |
| **受影響的產品領域**         | 應付帳款、應收帳款                                    |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。           |

### <a name="bank-payments-transfer-for-lithuania"></a>立陶宛銀行付款轉帳

透過使用立陶宛的付款轉帳 (LT) 匯出格式來產生和列印銀行付款轉帳。 立陶宛市場於 2005 年開始使用統一的電子銀行系統 LITAS。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                        |
| **被其他函數取代？**   | 是的，立陶宛的 ISO20022 貸記轉帳付款格式     |
| **受影響的產品領域**         | 應付帳款                                               |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>挪威的 BBS Direkte Remittering 付款格式

BBS Direkte Remittering 付款格式包括客戶收款匯出 (直接借記) 和退回訊息匯入。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。  |
| **被其他函數取代？**   | 挪威的 AvtaleGiro 客戶付款格式可用於產生直接借記訊息。 退回訊息匯入將在未來的版本中實施。 |
| **受影響的產品領域**         | 應付帳款、應收帳款   |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>西班牙會計科目表工具

當西班牙的會計科目表需要進行重大更改時，可以使用此工具。 使用者可以在 Microsoft Excel 或文字格式中匯入新會計科目表，還可以匯入財務報表。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用有限                                                  |
| **被其他函數取代？**   | 否                                                             |
| **受影響的產品領域**         | 總帳                                                 |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="dom80-payment-format-for-belgium"></a>比利時的 Dom80 付款格式

用於收款 (直接借記) 的舊版比利時付款格式。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                          |
| **被其他函數取代？**   | 是的，比利時的 ISO 20022 直接借記付款格式         |
| **受影響的產品領域**         | 應收帳款                                            |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="dtaezag-payment-formats-for-switzerland"></a>瑞士的 DTA/EZAG 付款格式

將 DTA/EZAG 格式整合到 ESR 系統中，因為它們可以執行參考編號。 由於參考編號不是強制性的，因此這些格式可用於處理任何廠商付款。 這些格式由在「Postfinance」以外位置擁有銀行帳戶的公司使用。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                        |
| **被其他函數取代？**   | 是的，瑞士的 ISO20022 貸記轉帳付款格式   |
| **受影響的產品領域**         | 應付帳款                                               |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>奧地利的 EDIFACT-DIRDEB 付款格式

用於收款 (直接借記) 的 EDIFACT-DIRDEB 付款格式。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                          |
| **被其他函數取代？**   | 是的，奧地利的 ISO 20022 直接借記付款格式         |
| **受影響的產品領域**         | 應收帳款                                            |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="edivat-for-belgium"></a>比利時的 EDIVAT

EDIVAT 是一個過時的比利時標準，透過安全郵件進行電子申報。 Dynamics AX 2012 保留讀取專用解決方案以啟用對歷史資料的存取權限。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用該函數。                           |
| **被其他函數取代？**   | 否                                                             |
| **受影響的產品領域**         | 總帳                                                 |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>挪威的 eGiro EDIFACT CREMUL 付款匯入格式

eGiro 根據用於自動過帳客戶付款的國際 UN EDIFACT CREMUL (多筆貸方通知訊息) 標準。 在 Dynamics AX，已將 eGiro 實施為客戶付款匯入格式。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                                                     |
| **被其他函數取代？**   | 是的，ISO20022 Camt.054 通知匯入。 |
| **受影響的產品領域**         | 應收帳款                                                                       |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                            |

### <a name="external-inventory-for-poland"></a>波蘭的外部庫存

從廠商處拿走貨物但未購買的證據。 在外部庫存中處理的貨物不影響標準庫存，可以自動出售然後購買。 這個流程會產生真實的庫存變動。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 被其他函數取代                                    |
| **被其他函數取代？**   | 是的，核心入庫寄售函數                |
| **受影響的產品領域**         | 應付帳款、庫存管理                         |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="financial-reports-generator-for-eastern-europe"></a>東歐財務報表產生器

用於設定會計和稅務報告的資料收集，並將資料匯出到 XLS 和 DOC 報告範本的工具。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用有限                                                                            |
| **被其他函數取代？**   | 否。 在未來的版本中，電子報告組態將取代該工具。 |
| **受影響的產品領域**         | 總帳                                                                           |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>為芬蘭匯入客戶付款交易

您可以選取芬蘭付款的匯入格式，以從銀行提供的外部檔案匯入客戶付款交易。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                                                     |
| **被其他函數取代？**   | 是的，ISO20022 Camt.054 通知匯入。 |
| **受影響的產品領域**         | 應收帳款                                                                       |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>將付款交易匯入芬蘭的總帳日記帳

芬蘭特有的格式用於將會計交易匯入總帳。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                                                     |
| **被其他函數取代？**   | 是的，使用進階銀行對帳的 ISO20022 Camt.053 匯入。 |
| **受影響的產品領域**         | 應收帳款                                                                       |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>比利時的 Isabel synchronized (CIS) 整合

Isabel 是歐洲電子銀行的架構，實際上是比利時的標準。

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 已中斷與 Isabel 用戶端的整合。   |
| **被其他函數取代？**   | 否。 比利時的 ISO20022 貸記轉帳付款格式取代不再使用的付款格式。 |
| **受影響的產品領域**         | 應付帳款     |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>西班牙會計科目表和會計規則的修改

此函數用於更改西班牙的會計科目表和會計規則。 它對應科目以幫助將舊會計科目表轉換為新會計科目表，並比較上一會計年度與新會計年度，即使它們已過帳到不同的科目編號。

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 使用有限                                                  |
| **被其他函數取代？**   | 否                                                             |
| **受影響的產品領域**         | 總帳                                                 |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Pagamento Fornittori 廠商付款格式

用於貸記轉帳的舊版義大利付款格式。

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                          |
| **被其他函數取代？**   | 是的，義大利的 ISO20022 貸記轉帳付款格式         |
| **受影響的產品領域**         | 應付帳款                                               |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="payment-export-formats-for-estonia"></a>愛沙尼亞的付款匯出格式

將 Telehansa 和 Teleservice 格式用於銀行付款匯出。

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                        |
| **被其他函數取代？**   | 是的，愛沙尼亞的 ISO20022 貸記轉帳付款格式       |
| **受影響的產品領域**         | 應付帳款                                               |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="payment-file-archive-for-norway"></a>挪威的付款檔案封存

產生付款檔案時，檔案封存會自動歸檔所有已建立的檔案，甚至是之前寫入或讀取的檔案。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 被其他函數取代                                        |
| **被其他函數取代？**   | 是的，電子報表歸檔作業                            |
| **受影響的產品領域**         | 應付帳款、應收帳款、組織管理 |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。     |

### <a name="payment-import-formats-for-estonia"></a>愛沙尼亞的付款匯入格式

將 Telehansa 和 TeleTeenus 格式用於銀行付款匯入。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                                                    |
| **被其他函數取代？**   | 是的，ISO20022 Camt.054 銀行通知匯入。 |
| **受影響的產品領域**         | 應收帳款                                                                        |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                             |

### <a name="payroll-information-in-human-resources"></a>人力資源中的薪資資訊

人力資源薪資資訊

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 核心薪資單和人力資源頁面已取代此函數。  |
| **被其他函數取代？**   | **福利**、**收益**，以及以前在美國薪資中的其他相關頁面已重新設定，現在是核心人力資源設定一部分，以幫助支援外部薪資處理。 此函數可透過使用 **人力資源 1**\>**薪資單** 設定鍵來存取。 |
| **受影響的產品領域**         | 人力資源，薪資   |
| **狀態**                         | 從 Dynamics 365 for Operations 版本 1611 移除。    |

### <a name="performance-management-goal-workflow"></a>績效管理目標工作流程

績效管理包括目標管理和與績效評估的整合。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 重新設計了績效管理，減少了目標頁面的數量以簡化流程。                 |
| **被其他函數取代？**   | 否。 管理員可以透過管理員自助服務入口網站看到目標，也可以由管理員更改和查看目標。 |
| **受影響的產品領域**         | 人力資本管理       |
| **狀態**                         | 從 Dynamics 365 for Operations 版本 1611 移除。    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>瑞典的 Postgirot 和 Postgirot Utland 付款格式

瑞典的 Postgirot 和 Postgirot Utland 付款格式。

|&nbsp;   |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                        |
| **被其他函數取代？**   | 是的，瑞典的 ISO20022 貸記轉帳付款格式        |
| **受影響的產品領域**         | 應付帳款                                               |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="radio-frequency-identifier"></a>無線頻率識別碼

無線頻率識別 (RFID) 是一種資料收集技術，可使用電子標籤來儲存識別資料，並使用非直視性要求讀取器來擷取識別資料。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 客戶使用率低且函數集有限。   |
| **被其他函數取代？**   | 否                                              |
| **受影響的產品領域**         | 庫存管理                            |
| **狀態**                         | 從 Dynamics 365 for Operations 1611 移除。 |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>關於拉脫維亞國家發票編號的報告

拉脫維亞立法提供了有關銷售發票編號的具體規則。 該函數允許您根據使用者或使用者群組為銷售發票指派特定編號。 然後，您可以產生報告或 XML 檔案。 您還可以列印有關使用的發票編號的報告。

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 不再需要維護國家發票編號。 不再需要有關已用發票編號的報告。 |
| **被其他函數取代？**   | 否       |
| **受影響的產品領域**         | 應收帳款    |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>為立陶宛設定公司經理和總會計師的姓名

可以在公司資訊中指定公司經理和總會計師的姓名，並在不同的本地報告列印輸出中使用。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 被其他函數取代                                     |
| **被其他函數取代？**   | 是的，官方安裝可用於相同的目的。   |
| **受影響的產品領域**         | 應付帳款、應收帳款、現金和銀行管理 |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。  |

### <a name="shipping-carrier-interface"></a>承運業者介面

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 重複函數   |
| **被其他函數取代？**   | 部分被運輸管理取代 |
| **受影響的產品領域**         | 銷售和行銷，庫存管理  |
| **狀態**                         | 從 Dynamics 365 for Operations 版本 1611 移除。  |

### <a name="telepay-payment-formats-for-norway"></a>挪威的 Telepay 付款格式

Telepay 付款格式包括廠商付款匯出 (貸記轉帳) 和客戶收款 (直接借記)。

|&nbsp;   |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                                                        |
| **被其他函數取代？**   | 是的，適用於挪威的 ISO20022 貸記轉帳付款格式和 AvtaleGiro 客戶付款格式，以及 pain.002 和 camt.054 銀行通知退回檔案匯入。 |
| **受影響的產品領域**         | 應付帳款、應收帳款                                                          |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>芬蘭的廠商付款匯出格式

芬蘭有兩種匯出付款的格式。 LM02 (FI) 用於國內付款，LUM2 (FI) 用於國外付款。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再使用付款格式。                        |
| **被其他函數取代？**   | 是的，芬蘭的 ISO20022 貸記轉帳付款格式       |
| **受影響的產品領域**         | 應付帳款                                               |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="warehouse-management-ii"></a> Warehouse Management II

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 在 **庫存管理** 模組中提供的 Warehouse Management II 解決方案 (WMS II) 複製了在 Dynamics AX 2012 R3 中發布的 **Warehouse Management** 模組的函數。                                                                         |
| **被其他函數取代？**   | 在 AX 2012 R3 中發布的 **Warehouse Management** 模組、Dynamics AX 2012 R3 CU8，以及 Dynamics AX 2012 R3 CU9 取代 Warehouse Management II 函數。 與 Warehouse Management II 相比，新模組具有更進階的函數和更靈活的倉庫管理。 |
| **受影響的產品領域**         | 庫存管理、銷售和行銷、採購和尋找來源   |
| **狀態**                         | 從 Dynamics 365 for Operations 版本 1611 移除。    |

### <a name="worker-reminders-in-human-resources"></a>人力資源中的內容工作角色提醒

人力資源薪資資訊

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用率低                                                           |
| **被其他函數取代？**   | 否                                                                  |
| **受影響的產品領域**         | 人力資源                                                     |
| **狀態**                         | 從 Dynamics 365 for Operations 版本 1611 移除 |

### <a name="workflow-for-creating-goals"></a>建立目標的工作流程

用於管理建立員工目標的工作流程是可用於幫助協調績效管理流程的多個工作流程之一。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Finance and Operations 中的績效管理已完全重新設計。     |
| **被其他函數取代？**   | 重新設計的績效管理函數可以更好控制目標的內容、用於追蹤進度的測量以及支援文件的附件。 目標可以儲存為範本，然後重複使用。 此函數可以幫助您更快地為員工設定其他目標。 |
| **受影響的產品領域**         | 人力資本管理                 |
| **狀態**                         | 從 Dynamics 365 for Operations 版本 1611 移除。 |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>能夠取消對廠商發票的更改

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 效能增強        |
| **被其他函數取代？**   | 否                             |
| **受影響的產品領域**         | 應付帳款               |
| **狀態**                         | 從 Dynamics AX 7.0 移除。 |

### <a name="aif-axd-and-axbc-integrations"></a>AIF、AxD 和 AxBC 整合

在應用程式整合框架 (AIF) 中，可以透過作為服務公開的業務邏輯與外部系統交換資料。 Dynamics AX 包括以文件為主的服務和 .NET Business Connector (AxBC)。 使用 XML 建立文件。 XML 包括已新增的標題資訊以建立一個可以轉入或轉出 Dynamics AX 的 *訊息*。 文件的範例包括銷售訂單和訂購單。 但是，幾乎任何實體 (例如客戶) 都可以由文件表示。 基於文件的服務使用 **Axd\<Document\>** 類別。

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | AIF 和 AxDs 的架構無法擴展到雲端服務。 批量匯入有效能問題。                                        |
| **被其他函數取代？**   | 此函數由支援定期批量匯入/匯出的資料匯入/匯出架構取代。 對於 AxBC，我們建議您使用實際表格。 |
| **受影響的產品領域**         | AxD、AxBC 和 AIF   |
| **狀態**                         | 從 Dynamics AX 7.0 移除。   |

### <a name="billing-code-rate-scripts"></a>計費代碼費率腳本

計費腳本用於計算計費代碼的計費率。 此腳本需要在 C Sharp 或 Visual Basic 程式設計語言中自訂開發。 在現行版本的 Dynamics AX，不支援 **計費代碼費率腳本**。

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **棄用/移除的原因** | 支援自訂 C Sharp 或 Visual Basic 腳本未在 Dynamics AX 7.0 中新增。 |
| **被其他函數取代？**   | 否                                                                                      |
| **受影響的產品領域**         | 公共部門，應收帳款                                    |
| **狀態**                         | 從 Dynamics AX 7.0 移除。                                                          |

### <a name="boms-without-bom-versions"></a>沒有 BOM 版本的 BOM

當 **BOM 版本** 設定鍵被禁用，物料清單 (BOM) 版本被隱藏在所有表格中，系統強制發布的產品和 BOM 之間的關係為 1:1。 在現行版本的 Dynamics AX，**BOM 版本** 設定鍵不能被禁用。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用設定鍵控制 BOM 版本無法在雲端環境中擴展。 |
| **被其他函數取代？**   | 否                                                                                      |
| **受影響的產品領域**         | 產品資訊管理、庫存管理                                    |
| **狀態**                         | 從 Dynamics AX 7.0 移除。                                                          |

### <a name="brazilian-bordero"></a>巴西 Bordero

巴西公司的具體付款方式

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 巴西本地化已停止支援巴西 Bordero 付款方式 |
| **被其他函數取代？**   | 否   |
| **受影響的產品領域**         | 應付帳款   |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="brazilian-sintegra-statement"></a>巴西 Sintegra 證明

ICMS 稅的聯邦稅籍證明

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 此證明不再適用於巴西的某些州。 |
| **被其他函數取代？**   | 否。 如果在特定情況下有需要，使用者可以使用透用電子報表工具來設定報表。 |
| **受影響的產品領域**         | 財政帳冊    |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>用於 NF-e 的巴西 SCAN 應急模式

(SCAN) 應急環境用於在 Secretaria da Fazenda (SEFAZ) 環境不可用時產生、匯出和匯入 Nota Fiscal eletrônica (NF-e) 的狀態。

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 這種應急方法不再適用於巴西所有州 |
| **被其他函數取代？**   | 否                                                                          |
| **受影響的產品領域**         | 應收帳款                                                         |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。              |

### <a name="business-analyzer"></a>商務分析工具

此行動應用程式可讓使用者查看關鍵業務指標。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 此函數已被另一個函數取代。   |
| **被其他函數取代？**   | Microsoft Power BI Monitor 財務績效內容套件將包括以前在商務分析工具中可用的關鍵財務指標。 |
| **受影響的產品領域**         | 總帳      |
| **狀態**                         | 已棄用：已棄用商務分析工具。    |

### <a name="business-statistics"></a>業務統計

業務統計查找的安裝，可以幫助您分析組織的績效

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 商業智慧 (BI) 的舊版方法、低客戶使用率和有限的函數集 |
| **被其他函數取代？**   | 適用於現行版本 Dynamics AX 的新 BI 解決方案                                      |
| **受影響的產品領域**         | 採購和尋找來源、應付帳款、銷售和行銷、應收帳款         |
| **狀態**                         | 從 Dynamics AX 7.0 移除。                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>發票審核日記帳中的更改文件日期函數

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用率低                                                               |
| **被其他函數取代？**   | 是。 可以更改已過帳廠商交易的文件日期。 |
| **受影響的產品領域**         | 應付帳款                                                        |
| **狀態**                         | 從 Dynamics AX 7.0 移除。                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>荷蘭的 ClieOp03 付款格式

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 該格式不再適用於荷蘭，因為它已被 SEPA 函數取代。 |
| **被其他函數取代？**   | SEPA 付款匯出  |
| **受影響的產品領域**         | 所有模組     |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。   |

### <a name="compliance-center"></a>合規性中心

合規中心是企業版入口網站，用於管理與沙賓法案相關的合規性方案的文件要求。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 缺乏客戶使用。 Microsoft SharePoint 包括合規性中心提供的相同功能。 |
| **被其他函數取代？**   | 否   |
| **受影響的產品領域**         | 合規性和內部控制  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。    |

### <a name="connector-for-microsoft-dynamics"></a>Microsoft Dynamics 連接器

此工具用於整合 Microsoft Dynamics CRM 到 Dynamics ERP 應用程式的關鍵資料。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 此函數已被另一個函數取代。 |
| **被其他函數取代？**   | Dataverse                                      |
| **受影響的產品領域**         | Dynamics 連接器                         |
| **狀態**                         | 從 Dynamics AX 7.0 移除。                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>現有容器單元和多維度

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 重複函數 |
| **被其他函數取代？**   | 是。 自從 AX 2012 年，此函數已被合併的批次訂單函數集取代。 此函數集包括合併的現有視圖。 |
| **受影響的產品領域**         | 產品資訊管理、生產控制、庫存管理、銷售和行銷  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。 |

### <a name="cue-group-metadata"></a>提示群組中繼資料

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 提示群組用於在 FactBox 區域中顯示一個或多個提示。 由於父系表單中的記錄更改導致在提示組中對每個提示進行一次查找，因此接受度有限，並且還存在效能問題。 |
| **被其他函數取代？**   | 否      |
| **受影響的產品領域**         | 所有模組    |
| **狀態**                         | 從 Dynamics AX 7.0 移除。  |

### <a name="cue-metadata"></a>提示中繼資料

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 提示中繼資料僅限於計數或總和資訊。    |
| **被其他函數取代？**   | 引入了圖標中繼資料以提供更大的建模靈活性。 例如，您可以對現行計數、導航和關鍵績效指標 (KPI) 進行建模。 計數圖標中繼資料是提示中繼資料的直接替換方案。 |
| **受影響的產品領域**         | 所有模組           |
| **狀態**                         | 從 Dynamics AX 7.0 移除      |

### <a name="danish-check-format"></a>丹麥支票格式

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 對丹麥支票格式配置的支援已中斷，該報告已從 DK 本地化中刪除。 |
| **被其他函數取代？**   | 否    |
| **受影響的產品領域**         | 所有模組    |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。  |

### <a name="data-partitions"></a>資料分割

資料分割在 Dynamics AX 中提供資料的邏輯分離資料庫。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 在 Dynamics AX 中引入了資料分割 2012 R2 啟用資料隔離。 在常用的場景中，一家公司有子公司，即使這兩個子公司都由同一個 IT 部門管理，一家子公司的資料不應該對另一家子公司公開。 但是，整個過程需要額外的腳本和管理開銷，以便建立新分割並填入資料上去，並備份分割資料。 在雲端中，我們可以存取平台即服務 (PaaS) 資料庫服務 (Microsoft Azure SQL 資料庫)，使用資料庫作為隔離容器比在過程中做隔離高效許多。 無論是子公司需要資料分割，還是多個租用戶需要資料分割，還是僅僅為了規模，我們認為透過多個 Finance and Operations 執行個體可以更高效地處理這些情況。 |
| **被其他函數取代？**   | 如果資料庫層級分離是危急問題，使用資料分割的客戶必須使用多個 Finance and Operations 執行個體。    |
| **受影響的產品領域**         | 所有模組  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。  |


### <a name="database-and-file-share-storage-for-attachments"></a>附件的資料庫和檔案共用儲存

Dynamics AX 2012 允許在資料庫和檔案共用中儲存附件。 不再支援這兩個選項。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再支援檔案共用儲存，因為雲端託管環境無法與本地檔案共用通訊。 已棄用資料庫儲存，取而代之的是 Azure Blob 儲存體。 Azure Blob 儲存體相當於資料庫中的儲存體，因為只能透過 Finance and Operations 用戶端表單存取文件。 這提供了額外的好處，即提供不會對資料庫效能產生負面影響的儲存體。 Blob 儲存體是文件管理的預設儲存體機制，可立即執行。 |
| **被其他函數取代？**   | 已棄用資料庫儲存，取而代之的是 Azure Blob 儲存體。   |
| **受影響的產品領域**         | 所有模組  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。   |

### <a name="delimitation"></a>分隔

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 未發現使用該函數。 |
| **被其他函數取代？**   | 否                                     |
| **受影響的產品領域**         | 時間及出勤                    |
| **狀態**                         | 從 Dynamics AX 7.0 移除。         |

### <a name="desktop-client"></a>桌面用戶端

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Dynamics AX 用戶端體驗已經過重新設計，以提高跨多個平台和裝置的易用性。                      |
| **被其他函數取代？**   | 新的網路用戶端根據已修改的桌面表單中繼資料和程式設計語言模型，以提供豐富的網路平台。 |
| **受影響的產品領域**         | 所有模組  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。   |

### <a name="direct-database-connection"></a>資料庫直接連線

在 Dynamics AX 2012 R3，Retail Modern POS 可以透過與 Enterprise POS 類似的方式直接連線到 Channel DB。 這是對透過零售伺服器通訊的 Retail Modern POS 標準通訊方法的補充。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 資料庫直接連線能力需要較低的安全通訊協定，主要用於實現最高層級的效能。 由於 Finance and Operations 中的效能和安全性增強函數，此函數現在導致的問題多於它解決的問題。 |
| **被其他函數取代？**   | 否。 現在僅支援標準零售伺服器通訊。  |
| **受影響的產品領域**         | Channel DB/Retail Modern POS   |
| **狀態**                         | 從 Dynamics AX 7.0 移除。  |

### <a name="dutch-swift-mt940"></a>荷蘭 SWIFT MT940

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 現在使用常用函數而不是本地化函數。                    |
| **被其他函數取代？**   | 是的，此函數已被進階銀行對帳函數取代。 |
| **受影響的產品領域**         | 所有模組                                                                              |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (德國的 XBRL)

此函數提供了專門用於德國 eBilanz 分類的可擴展業務報告語言 (XBRL) 輸出。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 缺乏客戶使用  |
| **被其他函數取代？**   | 此函數並未被其他函數所取代，但提供豐富 XBRL 函數的多個專用 XBRL 套件可用於德國市場。 |
| **受影響的產品領域**         | Management Reporter      |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。  |

### <a name="enterprise-portal-client"></a>企業入口網站用戶端

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 提供了一個單一用戶端平台。  |
| **被其他函數取代？**   | 新的網路用戶端根據已修改的桌面表單中繼資料和程式設計語言模型，以提供豐富的網路平台。 |
| **受影響的產品領域**         | 所有模組  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。   |

### <a name="environmental-sustainability"></a>環境永續性

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 客戶使用率低且函數集有限  |
| **被其他函數取代？**   | 否              |
| **受影響的產品領域**         | 合規性和內部控制，應付帳款  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。 |

### <a name="form-activex-and-managed-host-controls"></a>表單 ActiveX 和受控託管主機控制

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | ActiveX 和受控託管主機控制根據已棄用的桌面用戶端。 |
| **被其他函數取代？**   | 可擴展的控制架構支援建構基於 HTML、CSS 和 JavaScript 的新控制，並且是 Microsoft Visual Studio 工具環境中的一流控制。 |
| **受影響的產品領域**         | 所有模組     |
| **狀態**                         | 從 Dynamics AX 7.0 移除。       |

### <a name="generate-prenotes-by-using-a-batch"></a>使用批次處理產生轉帳測試

轉帳測試產生不能透過使用批次處理來完成，但它仍然可以由使用者完成。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用批次處理產生的轉帳測試檔案不存在持久儲存和顯示結果的表單。 |
| **被其他函數取代？**   | 仍然可以產生轉帳測試，並且使用者可以控制檔案的儲存位置。   |
| **受影響的產品領域**         | 應付帳款、應收帳款、現金和銀行管理  |
| **狀態**                         | 從 AX 7.0 移除。    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>德國 DTAUS 付款匯出和對帳單匯入 (總計和交易)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 該格式不再適用於德國，因為它已被單一歐元支付區 (SEPA) 函數取代。                    |
| **被其他函數取代？**   | 是的，此函數已被 SEPA 付款匯出和用於匯入帳戶對帳單的進階銀行對帳函數所取代。 |
| **受影響的產品領域**         | 所有模組  |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="german-dtazv-payment-format-in-domestic-currency"></a>德國 DTAZV 以本國貨幣付款的格式

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 該格式不再適用於德國，因為它已被 SEPA 函數取代。 |
| **被其他函數取代？**   | SEPA 付款匯出    |
| **受影響的產品領域**         | 應付帳款   |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。    |

### <a name="german-mt940-import"></a>德國 MT940 匯入

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 現在使用常用函數而不是本地化函數。                    |
| **被其他函數取代？**   | 是的，此函數已被進階銀行對帳函數取代。 |
| **受影響的產品領域**         | 所有模組                                                                              |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。                           |

### <a name="german-xml-eu-sales-list"></a>德國 XML 歐盟銷售清單

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 不再支援德國歐盟銷售清單報表的 XML 格式。 只能使用 ELMA5 文字檔案格式向德國稅務局提交歐盟銷售清單報告。 |
| **被其他函數取代？**   | 否         |
| **受影響的產品領域**         | 稅金        |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。   |

### <a name="gl-ssrs-reports"></a>GL SSRS 報告

包含以下選單項目的報告已被移除：**摘要試算表**、**詳細試算表**、**會計科目表**、**稽核線索**、**餘額** 和 **餘額清單**。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 金融 Microsoft SQL Server Reporting Services (SSRS) 報告已被 Management Reporter 功能和預設報告取代。 |
| **被其他函數取代？**   | Management Reporter (將 **Financial Reporting** 標記在現行版本的 Dynamics AX 中)    |
| **受影響的產品領域**         | 總帳   |
| **狀態**                         | 從 Dynamics AX 7.0 移除。   |

### <a name="infopart-and-formpart-metadata"></a>InfoPart 和 FormPart 中繼資料

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | InfoPart 和 FormPart 中繼資料支援為兩個不同的用戶端建立 FactBox。 |
| **被其他函數取代？**   | InfoPart 中繼資料是一種簡化的表單定義，透過升級工具轉換為表單。 參考表單的 FormPart 中繼資料被升級工具建立的更直接參考所取代。 |
| **受影響的產品領域**         | 所有模組    |
| **狀態**                         | 從 Dynamics AX 7.0 移除。        |

### <a name="main-account-list-page"></a>主科目清單頁面

法律實體科目清單和相關餘額資訊

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 餘額資訊可按科目和維度在 **試算表** 清單頁面上提供。  |
| **被其他函數取代？**   | **主科目** 包含與 **主科目** 清單頁面相同的科目清單。 **主科目** 中的格線視圖顯示了一個更小的格線類視圖。 |
| **受影響的產品領域**         | 總帳      |
| **狀態**                         | 從 Dynamics AX 7.0 移除。    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>馬來西亞和新加坡銀行現金流量報表

此函數允許使用者列印現金流量報表，該報表顯示選定銀行帳戶特定日期範圍內的現金流入和流出的交易和詳情。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 可以從查找銀行交易中獲得相同的資訊。 |
| **被其他函數取代？**   | 詢價銀行交易                                            |
| **受影響的產品領域**         | 現金和銀行管理                                                |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。          |

### <a name="mexican-cfd-electronic-invoice"></a>墨西哥 CFD 電子發票

此函數支援使用 Comprobante Fiscal Digital (CFD) 方法產生墨西哥電子發票，公司透過要求政府的相關授權來簽署發票。 此函數還提供月度報告，其中包括該期間開具的所有電子發票。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 該方法不再適用。 稅務機關已棄用使用 CFD 方法產生電子發票，取而代之的是 Comprobante Fiscal Digital a través de Internet (CFDI) 方法，其中簽名委託給第三方提供者 (PAC)。 月度報告已被刪除，查找選項可讓使用者查找歷史交易。 |
| **被其他函數取代？**   | 否    |
| **受影響的產品領域**         | 應收帳款，項目   |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="mexico-realized-and-unrealized-vat"></a>墨西哥已實現和未實現增值稅

Dynamics AX 2012 透過使用墨西哥特有的未實現稅金函數管理未實現增值稅 (VAT)。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 重複函數  |
| **被其他函數取代？**   | 是的，此函數已被 Core 提供的標準條件銷售稅函數所取代。 |
| **受影響的產品領域**         | 稅金   |
| **狀態**                         | 已棄用：尚未為此函數設定移除日期。 |

### <a name="microsoft-outlook-integration"></a>Microsoft Outlook 整合


| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 此函數已被 Microsoft Exchange Server 整合函數取代。 |
| **被其他函數取代？**   | 是                                                                            |
| **受影響的產品領域**         | 銷售和行銷                                                            |
| **狀態**                         | 從 Dynamics AX 7.0 移除。                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>私人封鎖詳細目錄和倉庫管理日記帳

庫存和倉庫日記帳不再支援將日記帳標記為所選使用者的私人日記帳的函數。 僅支援將日記帳封鎖為使用者群組的隱私，以及在編輯過程中封鎖的流程。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 未發現使用該函數。 |
| **被其他函數取代？**   | 否                                     |
| **受影響的產品領域**         | 庫存管理                   |
| **狀態**                         | 從 Dynamics AX 7.0 移除。         |

### <a name="product-builder"></a>產品建立者

產品建立者用於從銷售訂單、訂購單、生產訂單、銷售報價單、項目報價單或品項需求動態設定項目。 基於具有建模變量的產品模型，使用者可以選擇滿足客戶要求的值並獲得具有 BOM 和路線的獨特產品變型。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 產品建立者向終端使用者公開了 X++ 代碼，並且在現行版本的 Dynamics AX 中不提供支援。 它已被移除，以避免對重疊且大規模的代碼庫進行重複的維護工作。  |
| **被其他函數取代？**   | 是。 在 Dynamics AX 2012 中引入了條件式設定，並已宣布未來版本中產品建立者的折舊。 在基準產品上選擇條件式設定技術來啟用設定。 若要進一步了解，請參閱[產品設定概覽 ](../../../supply-chain/pim/build-product-configuration-model.md)。 |
| **受影響的產品領域**         | 產品資訊管理、銷售和行銷  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。      |

### <a name="production-floor-app"></a>生產車間應用程式
這是適用於採用 Windows 8.1 RT 和 Windows 8.1 Pro 的平板裝置的應用程式。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 隨著對網路式用戶端的更改，可以透過本機 Dynamics AX 7.0 用戶端提供類似的函數。 作業卡裝置提供了一個生產車間使用者介面，該介面針對觸控和平板板型規格進行了最佳化。 |
| **被其他函數取代？**   | 是。 作業卡裝置是 Dynamics AX 7.0 的本機部分。                                                                           |
| **受影響的產品領域**         | 產品控制                                                |
| **狀態**                         | 已棄用：Microsoft Store 中的移除日期尚未為此函數做設定。                                                |


### <a name="rename-product-dimension"></a>重新命名產品尺寸

此函數允許您將三個標準產品尺寸 (尺寸、顏色或樣式) 之一的名稱更改為更適合您業務需求的名稱。 重命名包括使用產品尺寸名稱的所有標籤。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 現行版本的 Dynamics AX 無法在執行時更改標籤。 |
| **被其他函數取代？**   | 否                                                                            |
| **受影響的產品領域**         | 產品資訊管理                                                |
| **狀態**                         | 從 Dynamics AX 7.0 移除。                                                |

### <a name="retail-server-connectivity-using-http"></a>使用 HTTP 的零售伺服器連線能力

在 Dynamics AX 2012 R3，零售伺服器可以使用 HTTP 通訊 (非安全) 來運作。 這是對使用 HTTPS 的標準通訊的補充。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 由於新的安全要求，現在僅支援使用 TLS 1.2 (或更高版本，如果可用) 的安全通訊。 自助服務安裝程式將自動為此通訊設定好電腦。 |
| **被其他函數取代？**   | 否。 現在僅支援標準 HTTPS 通訊。 |
| **受影響的產品領域**         | 零售伺服器  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。 |

### <a name="role-center-pages"></a>角色中心頁面

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 角色中心頁面是在已棄用的企業入口網站平台上構建的，該平台已被現行版本的 Dynamics AX 中的新網路用戶端平台取代。 |
| **被其他函數取代？**   | 新的工作區表單模式為使用者提供了以流程為中心的設計，可以輕鬆存取該流程中的常用任務。                       |
| **受影響的產品領域**         | 所有模組    |
| **狀態**                         | 從 Dynamics AX 7.0 移除   |

### <a name="sales-tax-jurisdictions"></a>銷售稅管轄區

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 客戶使用率低且函數集有限 |
| **被其他函數取代？**   | 否                                           |
| **受影響的產品領域**         | 美國銷售稅                                 |
| **狀態**                         | 從 Dynamics AX 7.0 移除。               |

### <a name="sites-services"></a>網站服務

網站服務允許您建立網站，將您的業務流程擴展到網路，而無需 IT 技術支援。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Dynamics AX 使用的 Microsoft Azure 基礎結構具有可以替代使用的新功能 (例如，Azure 網站)。 |
| **被其他函數取代？**   | 否   |
| **受影響的產品領域**         | 人力資源招募、案例管理、報價要求、廠商註冊、機會和活動的協作工作區  |
| **狀態**                         | 從 Dynamics AX 7.0 移除。    |

### <a name="ssas-demand-forecasting-strategy"></a>SSAS 需求預測策略

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 新的雲端架構無法支援該函數的設計。 |
| **被其他函數取代？**   | Azure Machine Learning 需求預測策略                           |
| **受影響的產品領域**         | 主計畫                                                              |
| **狀態**                         | 從 Dynamics AX 7.0 移除。                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>不包括過帳明細的廠商發票集區

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用率低。 此函數已被具有工作流程函數的發票日記帳取代。 |
| **被其他函數取代？**   | 發票日記帳的工作流程功能。     |
| **受影響的產品領域**         | 應付帳款 |
| **狀態**                         | 從 Dynamics AX 7.0 移除。    |


### <a name="virtual-company-accounts"></a>虛擬公司帳戶

Dynamics AX 不再支援虛擬公司函數。 虛擬公司函數允許使用者設定可由一組公司共用的表格。 如需該函數的說明，請參閱[公司帳戶和虛擬公司帳戶 ](../../fin-ops/get-started/ax4-content-retired.md)。 該函數透過將表格分組到指派給虛擬公司的集合物件中來運作，這些虛擬公司是現有「真實」公司的群組。 建立查找以便虛擬公司中的所有公司都可以存取相關表格集合物件之表格中的資料。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | - 必須先設定虛擬公司，然後才能將資料儲存在表格中。 將虛擬公司改造到現有實施中非常困難。<br><br>- 因為在現行版本的 Dynamics AX 中有太多的資料規範化，很難知道要向表格集合物件中新增什麼。 例如，很難知道要共用哪些表格。 還必須新增從虛擬公司表格參考的所有表格。 由於表格規範化，即使是分佈在多個表格中的簡單主資料也必須是虛擬公司的一部分。 在這裡犯的任何錯誤都會導致函數問題。<br><br>- 當表格是虛擬公司的一部分時，它會遺失有關資料來源的資訊，並且只記錄虛擬公司。   |
| **被其他函數取代？** | 全域表格可用於使所有公司都可以存取表格。 現行沒有替代方案。 |   
| **受影響的產品領域**       | 所有模組 |   
| **狀態**                       | 從 Dynamics AX 7.0 移除。   |   

### <a name="windows-8-tablet-app"></a>Windows 8 平板電腦應用程式

Windows 8 平板電腦應用程式提供了費用輸入和核准函數。

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | Finance and Operations 與平板電腦相容。 不再需要平板電腦應用程式。    |
| **被其他函數取代？**   | 否。          |
| **受影響的產品領域**         | 費用管理   |
| **狀態**                         | 已移除：此函數僅適用於 Dynamics AX 2012 R3。 |

### <a name="workplanner"></a>工作規劃員

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 使用率低 |
| **被其他函數取代？**   | 不，但是 **設定檔關係** 頁面，從 **設定檔組** 頁面打開，支援與棄用 **工作規劃員** 頁面相同的業務場景。 |
| **受影響的產品領域**         | 時間及出勤     |
| **狀態**                         | 該代碼尚未移除。 但是，沒有遷移表單 JmgWorkPlanner。    |

### <a name="x-financial-statements"></a>X++ 財務報表

| &nbsp;  | &nbsp; |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>棄用/移除的原因</strong> |                         此函數已被另一個函數取代。                         |
|  <strong>被其他函數取代？</strong>  | Management Reporter (將 <strong>Financial Reporting</strong> 標記在現行版本的 Dynamics AX 中) |
|     <strong>受影響的產品領域</strong>     |                                              總帳                                              |
|             <strong>狀態</strong>             |                                      從 Dynamics AX 2012 移除                                      |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
