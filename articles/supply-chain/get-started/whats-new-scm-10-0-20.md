---
title: Dynamics 365 Supply Chain Management 10.0.20 (2021 年 8 月) 的新增功能或變更
description: 本主題說明 Dynamics 365 Supply Chain Management 10.0.20 中的新增功能或變更。
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a8f46165a89f064878d2e8af1b0b174b04eca37e
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "8449385"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10020-august-2021"></a>Dynamics 365 Supply Chain Management 10.0.20 (2021 年 8 月) 的新增功能或變更

[!include [banner](../includes/banner.md)]

本主題列出 Microsoft Dynamics 365 Supply Chain Management 版本 10.0.20 中的新增功能或變更。 此版本的版本編號為 10.0.886，可用時間如下：

- **發行預覽版**：2021 年 5 月
- **正式發行 (自行更新)：** 2021 年 7 月
- **正式發行 (自動更新)：** 2021 年 8 月

## <a name="features-included-in-this-release"></a>此版本中包含的功能

下表列出了此版本中包含的功能。 *功能* 資料行提供[發行計劃](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features)連結，您可以在其中查看每個功能的正式發行日期。 *詳細資訊* 資料行提供更多詳細資料和/或相關文件的連結。

大多數這些功能必須使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)啟用，才可以使用。

| 功能區域 | 功能 | 詳細資訊 |
|---|---|---|
| 庫存&nbsp;和&nbsp;物流 | [銷售訂單詳細資料效能增強](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | 此功能可讓使用者介面在打開銷售訂單時更快回應，尤其是包含多行的訂單。 |
| 製造 | [叫用程序自動化流程以建立品質檢驗訂單](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [叫用程序自動化流程以建立品質檢驗訂單](../production-control/process-automation-quality-orders.md ) |
| 製造 | [用於製造的增強型生產車間執行介面](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [設定生產現場執行介面](../production-control/production-floor-execution-configure.md) |
| 計劃 | [規劃最佳化的無限產能排程](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | [以無限產能進行排程](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| 產品資訊管理 | [管理配方及其成分的變更](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [管理配方及其成分的變更](../engineering-change-management/manage-formula-changes.md) |
| 產品資訊管理 | [產品整備度檢查](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [產品整備度](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>此版本中包含的功能增強

下表列出了此版本中包含的功能增強。 所有增強功能都為現有功能提供了增量改善。 由於它們只是增強功能，因此未列在[發行計劃](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features)中。 但是，為確保這些增強功能不會與您現有的自訂或喜好設定發生衝突，預設情況下它們都處於關閉狀態 (除非另有說明)。 如果您想使用這些功能中的任何一個，必須在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中啟用它們。

| 模組 | 功能&nbsp;管理中的功能&nbsp;名稱&nbsp; | 詳細資訊 |
|---|---|---|
| 主計劃 | 調整後需求預測的平行授權 | 此功能允許從 **調整的需求預測** 頁面平行授權調整的需求預測。 此功能的目的是在授權大量預測時提高效能。 授權時，使用者可以在授權對話方塊中指定 **執行緒數**。 |
| 主計劃 | (預覽版) 計劃大量和包裝批次訂單的可批次確定和合併 | 此功能可讓您使用批次作業來確定和合併計劃的大量和包裝訂單。 |
| 生產控制 | 複製通用途程 | 此功能增強了複製途程功能，可讓使用者複製非特定品項的途程。 它可讓系統在使用複製途程功能覆寫尚未指派給品項的途程，後更新所有相關資訊 (例如網站、途程群組、資源需求和各種時間)。 |
| 生產控制 | 途程工序變更時更新相關資源需求 | 此功能可讓系統在使用者變更現有途程步驟的工序後更新相關資源需求。 |
| 產品資訊管理 | 物料清單報表預處理以防止逾時 | 此功能會導致預先處理物料清單報表。 這將避免在為報表載入大量資料時出現逾時問題。 |
| 採購和資源開發 | 啟用重設採購相關工作流程 | 此預覽功能可讓您將以下工作流程重設為草稿狀態：訂購訂單、廠商變更和採購申請。 |
| 運輸管理 | 在捨棄貨運單時啟用廠商發票日記帳的建立 | 啟用此功能後，僅當您使用付款廠商選項時，才會出於對帳原因建立相應的廠商發票日記帳。 否則，將一律建立發票日記帳。 |
| 庫存管理 | 驗證為補貨作業選擇的範本 | 此功能有助於確保使用者在設定補貨作業時選擇有效的補貨範本。 它可以防止使用者在沒有範本的情況下建立補貨作業以及選擇 *波次需求* 類型的範本，這不會建立任何補貨工作，並且可能需要很長時間才能處理。 |

## <a name="new-and-updated-documentation-resources"></a>新增和更新的文件資源

我們最近新增或大幅更新了以下說明主題。 它們不一定與此版本的新增功能相關 (如上一節中所列)，但它們可能會幫助您從現有功能中獲得更多助益。

| 功能區域 | 新增或更新的主題 |
|---|---|
| 工程變更管理 | [產品生命週期狀態和交易](../engineering-change-management/product-lifecycle-state-transactions.md) |
| 庫存管理 | [庫存能見度轉移單](../inventory/inventory-visibility.md)<br><br>[品質和不合格管理概觀](../inventory/quality-management-processes.md) (和所有相關的品質管理主題) |
| 採購和資源開發 | [維護廠商認證](../../finance/public-sector/manage-vendor-certification.md) |
| 生產控制 | [設計生產現場執行介面](../production-control/production-floor-execution-styles.md) |
| 庫存管理 | [為 Warehouse Management 行動應用程式指派步驟圖示和標題](../warehousing/step-icons-titles.md)<br><br>[手動庫存移動的延遲處理](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>其他資源

### <a name="platform-updates-for-finance-and-operations-apps"></a>財務和營運應用程式的平台更新

Microsoft Dynamics 365 Supply Chain Management 10.0.20 包括平台更新。 若要深入了解，請參閱[財務和營運應用程式版本 10.0.20 (2021 年 7 月) 的平台更新](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md)。

### <a name="bug-fixes"></a>錯誤修正

有關 10.0.20 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS)，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8)。 

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365：2021 年發行第 1 波計劃

想了解商務應用程式或平台中即將推出和最近發布的功能嗎？

查看 [Dynamics 365：2021 年發行第 1 波計劃](/dynamics365-release-plan/2021wave1/)。 我們已經在文件中擷取了所有詳細資料，從頭到尾，從上到下，方便您進行規劃。

### <a name="removed-and-deprecated-supply-chain-management-features"></a>已移除和已取代的 Supply Chain Management 功能

[Dynamics 365 Supply Chain Management 中已移除或已取代的功能](removed-deprecated-features-scm-updates.md)主題說明了 Supply Chain Management 已經或計劃移除或取代的功能。

- *已移除* 功能不再於產品中提供該功能。
- *已取代* 功能未進行開發，可能會在未來的更新中移除。

在從產品中刪除任何功能之前，將在移除前 12 個月在 [Dynamics 365 Supply Chain Management 中已移除或已取代的功能](removed-deprecated-features-scm-updates.md)主題中公佈取代通知。

對於僅影響編譯時間但與沙盒和生產環境二進位相容的重大變更，取代時間將少於 12 個月。 這些通常是需要對編譯器進行的功能更新。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
