---
title: Dynamics 365 Supply Chain Management 10.0.24 (2022 年 2 月) 的新增功能或變更
description: 本主題說明 Microsoft Dynamics 365 Supply Chain Management 10.0.24 中的新增功能或變更。
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: a254e20dd7fcc29ca520282b4bf9fcd903e4de58
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "8449898"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10024-february-2022"></a>Dynamics 365 Supply Chain Management 10.0.24 (2022 年 2 月) 的新增功能或變更

[!include [banner](../includes/banner.md)]

本主題列出 Microsoft Dynamics 365 Supply Chain Management 版本 10.0.24 中的新增功能或變更。 此版本的版本編號為 10.0.1084，可用時間如下：

- **發行預覽版：** 2021 年 12 月
- **正式發行 (自行更新)：** 2022 年 1 月
- **正式發行 (自動更新)：** 2022 年 2 月

## <a name="features-included-in-this-release"></a>此版本中包含的功能

下表列出了此版本中包含的功能。 我們可能會更新此主題以包含在最初發佈此主題後將其納入組建的功能。

| 功能區域 | 功能 | 詳細資訊 | 啟用者   |
|---|---|---|---|
| 分佈式混合拓撲 | [增強縮放單位的倉庫執行工作負載](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [雲端和邊緣縮放單位的倉庫管理工作負載](../cloud-edge/cloud-edge-workload-warehousing.md) | 預設啟用。 |
| 分佈式混合拓撲 | [針雲端和邊緣縮放單位的倉庫管理工作負載啟動生產訂單](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-manufacturing-execution-workloads-scale-units) | [雲端和邊緣縮放單位的製造執行工作負載](../cloud-edge/cloud-edge-workload-manufacturing.md) | 功能管理 (*針雲端和邊緣縮放單位的倉庫管理工作負載啟動生產訂單*)  |
| 規劃 | [規劃最佳化支援再訂購寬限期和發貨寬限期](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [安全寬限期](../master-planning/planning-optimization/safety-margins.md) | 預設啟用。 |

## <a name="feature-enhancements-included-in-this-release"></a>此版本中包含的功能增強

下表列出了此版本中包含的功能增強。 所有增強功能都為現有功能提供了增量改善。 由於它們只是增強功能，因此未列在[發行計劃](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)中。 但是，為確保這些增強功能不會與您現有的自訂或喜好設定發生衝突，預設情況下它們都處於關閉狀態 (除非另有說明)。

如果您想開啟或關閉這些功能，必須在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中進行作業。

| 模組 | 功能管理中的功能名稱 | 詳細資訊 |
|---|---|---|
| 生產控制 | 生產訂單的隨選物料可用性檢查 | 此功能可以更快地打開 **生產訂單下達** 頁面，可從 **生產現場管理** 工作區進入該頁面。 如果沒有此功能，系統會在您打開頁面後立即自動檢查所有列出的生產訂單的物料是否可用，對於大量訂單，這可能會花費大量時間。 啟用此功能後，系統會提供工具列按鈕，您可以使用該按鈕僅在選定訂單和需要時啟動物料檢查。 |
| 生產控制 | (預覽版) 在生產現場執行介面 (非 WMS) 上登記物料消耗 | 此功能可讓工人使用生產現場執行介面來登記物料消耗、批次編號和序號。 此功能僅支援未啟用使用進階倉庫流程 (WMS) 的品項。 計劃在未來的版本中支援啟用 WMS 的品項。<p>某些製造商，尤其是加工業的製造商，必須明確登記每個批次或生產訂單消耗的材料量。 例如，工人可能會使用秤來稱量他們工作時消耗的材料量。 為了確保完全的材料可追溯性，這些組織還必須登記生產每種產品所消耗的批次編號。 |
| 生產控制 | 雲端和邊緣縮放單位的倉庫管理工作負載報告為已完成 | 當應用程式針對雲或邊緣縮放單位上的倉庫管理工作負載執行時，此功能讓工作人員可以使用 Warehouse Management 行動應用程式將生產或批次訂單報告為已完成。 有關詳細資訊，請參閱[報告為已完成並依縮放單位存放](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF). |
| 庫存管理 | 新的負載規劃工作台頁面 | 啟用兩個新的負載規劃工作台頁面：**入庫負載規劃工作台** 和 **出庫負載規劃工作台**。 |

## <a name="new-and-updated-documentation-resources"></a>新增和更新的文件資源

我們最近新增或大幅更新了以下說明主題。 這些主題不一定與為此版本新增的新功能相關，如上一節中所列。 但是，它們可能會幫助您充分利用現有功能。

| 功能區域 | 新增或更新的主題 |
|---|---|
| 成本管理 | [庫存值報表](../cost-management/inventory-value-report-storage.md) |
| 成本管理 | [庫存值報表範例和邏輯](../cost-management/inventory-value-report-examples.md) |
| 主計劃 | [規劃最佳化使用的日期與時間參數](../master-planning/planning-optimization/date-time-used.md) |
| 主計劃 | [需求預測設定](../master-planning/demand-forecasting-setup.md) |
| 主計劃 | [使用安全庫存日記帳更新品項的最小涵蓋範圍](../master-planning/safety-stock-journal.md) |
| 生產控制 | [自訂生產現場執行介面](../production-control/production-floor-execution-customize.md) |
| 生產控制 | [設計生產現場執行介面](../production-control/production-floor-execution-styles.md) |
| 銷售和行銷 | [銷售記錄清除效能改善](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| 庫存管理 | [行動裝置使用者帳戶](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>其他資源

### <a name="platform-updates-for-finance-and-operations-apps"></a>財務和營運應用程式的平台更新

Microsoft Dynamics 365 Supply Chain Management 10.0.24 包括平台更新。 若要深入了解，請參閱[財務和營運應用程式版本 10.0.24 (2022 年 2 月) 的平台更新](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md)。

### <a name="bug-fixes"></a>錯誤修正

有關 10.0.24 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS)，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f)。

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 和產業雲端：2021 年發布第 2 波計劃

想了解商務應用程式或平台中即將推出和最近發布的功能嗎？

查看 [Dynamics 365 和產業雲端：2021 年發布第 2 波計劃](/dynamics365-release-plan/2021wave2/) 我們已經在文件中擷取了所有詳細資料，從頭到尾，從上到下，方便您進行規劃。

### <a name="removed-and-deprecated-supply-chain-management-features"></a>已移除和已取代的 Supply Chain Management 功能

[Dynamics 365 Supply Chain Management 中已移除或已取代的功能](removed-deprecated-features-scm-updates.md)主題說明了 Supply Chain Management 已經或計劃移除或取代的功能。

- *已移除* 功能不再於產品中提供該功能。
- *已取代* 功能未進行開發，可能會在未來的更新中移除。

在從產品中刪除任何功能之前，將在移除前 12 個月在 [Dynamics 365 Supply Chain Management 中已移除或已取代的功能](removed-deprecated-features-scm-updates.md)主題中公佈取代通知。

對於僅影響編譯時間但與沙盒和生產環境二進位相容的重大變更，取代時間將少於 12 個月。 這些通常是需要對編譯器進行的功能更新。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
