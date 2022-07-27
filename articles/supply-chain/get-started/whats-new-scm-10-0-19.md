---
title: Dynamics 365 Supply Chain Management 版本 10.0.19 (2021 年 6 月) 的新增功能或變更
description: 本主題說明 Dynamics 365 Supply Chain Management 10.0.19 中的新增功能或變更。
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 03ed2d52f44bd38910b01ffbd3767f750da2cbf8
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449598"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10019-june-2021"></a>Dynamics 365 Supply Chain Management 版本 10.0.19 (2021 年 6 月) 的新增功能或變更

[!include [banner](../includes/banner.md)]

本主題列出 Microsoft Dynamics 365 Supply Chain Management 版本 10.0.19 中的新增功能或變更。 此版本的版本編號為 10.0.837，可用時間如下：

- **發行預覽版**：2021 年 4 月
- **正式發行 (自行更新)：** 2021 年 6 月
- **正式發行 (自動更新)：** 2021 年 6 月

## <a name="features-included-in-this-release"></a>此版本中包含的功能

下表列出了此版本中包含的功能。 *功能* 資料行提供[發行計劃](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features)連結，您可以在其中查看每個功能的正式發行日期。 *詳細資訊* 資料行提供更多詳細資料和/或相關文件的連結。

大多數這些功能必須使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)啟用，才可以使用。

| 功能區域 | 功能 | 詳細資訊 |
|---|---|---|
| 庫存&nbsp;和&nbsp;物流 | [核准並儲存廠商提交的銀行詳細資料](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/approve-save-vendor-submitted-bank-details) | [維護廠商銀行帳戶資訊](../../finance/accounts-payable/maintain-vendor-bank-info.md) |
| 庫存和物流 | [連絡人資料實體匯出最佳化](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | 啟用此功能後，對參考資料的變更不會導致相關連絡人包含在下一次增量匯出中。 停用此功能後，對參考資料的變更會導致相關連絡人包含在下一次增量匯出中。 |
| 庫存和物流 | [包含縮放單位的倉庫執行功能的增量增強功能](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[訊息處理器訊息](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[倉庫庫存調整](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[雲端和邊緣縮放單位的倉庫管理工作負載](../cloud-edge/cloud-edge-workload-warehousing.md) |
| 庫存和物流 | [銷售報價單頁面上的文件介紹和文件結論欄位的查詢功能](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | 此功能為 **銷售報價** 頁面上的 **文件介紹** 和 **文件結論** 欄位新增了查詢功能。<br><br>此功能為預設啟用。 |
| 庫存和物流 | [在您自訂硬體上包含邊緣縮放單位的倉庫執行](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [使用 LBD 在自訂硬體上部署邊緣縮放單位](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| 製造 | [在您自訂硬體上包含邊緣縮放單位的製造執行](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [使用 LBD 在自訂硬體上部署邊緣縮放單位](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| 計劃 | 查詢式計劃訂單確定 | [確定計劃訂單](../master-planning/planning-optimization/planned-order-firming.md) |
| 產品資訊管理 | [變體建議頁面改善](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [建立預先定義產品的變體](../pim/tasks/create-predefined-product-variants.md) |

## <a name="feature-enhancements-included-in-this-release"></a>此版本中包含的功能增強

下表列出了此版本中包含的功能增強。 所有增強功能都為現有功能提供了增量改善。 由於它們只是增強功能，因此未列在[發行計劃](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features)中。 但是，為確保這些增強功能不會與您現有的自訂或喜好設定發生衝突，預設情況下它們都處於關閉狀態 (除非另有說明)。 如果您想使用這些功能中的任何一個，必須在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中啟用它們。

| 模組 | 功能&nbsp;管理中的功能&nbsp;名稱&nbsp; | 詳細資訊 |
|---|---|---|
| 銷售和行銷 | 銷售記錄清除效能改善 | 如果不常在具有大量銷售更新的環境中執行，則銷售歷史清除可能需要很長的時間。 為了減少持續時間並提高可靠性，此功能將清除分成在有限期間內執行的多個批次。 在可能的情況下，將利用資料庫功能來把鎖定降至最低，並避免在清除期間加入交易表。 有關詳細資料，請參閱[銷售歷史清除效能改善](../sales-marketing/sales-update-history-cleanup-performance-improvements.md)。 |
| 銷售和行銷 | 使用公司間訂單的確認日期更新要求的收貨日期 | 此功能可讓您控制在使用公司間直接交貨時銷售和採購日期欄位值的變化。 您可以選擇系統是更新要求的日期還是跳過更新它們。 如果您跳過更新，要求的日期將代表客戶的要求。 如果您啟用更新，則要求日期 (使用交貨日期控制時) 最初僅代表客戶要求的日期。 交貨日期控制不是 *無* 時，將否決最初要求的內容。 您可以使用公司間廠商或客戶設定上的新 **更新要求收貨日期和確認日期** 設定來設定此選項。<br><br>如果停用該功能，系統將根據交貨日期控制規則覆寫原始銷售訂單的要求收貨日期，但要求的發貨日期將保持不變。 |
| 庫存管理 | 下達倉庫時將數量向下四捨五入到最接近的銷售單位 | 此功能新增了一個選項，可以限制下達到倉庫的訂單數量。 啟用後，訂單數量將向下四舍五入到最接近的整個銷售單位，包含少於一個銷售單位數量的訂單將被拒絕下達。 |
| 庫存管理 | 組織內的「排成工作建立」波次方法 | 如果啟用此功能，*排程工作建立* 波次方法將設定為在所有法人實體中平行執行。 一些額外的設定也會受到影響。 如需完整的詳細資料，請參閱[在波次期間排程工作建立](../warehousing/configure-wave-schedule-work-creation.md)。 |

## <a name="new-and-updated-documentation-resources"></a>新增和更新的文件資源

我們最近新增或大幅更新了以下說明主題。 它們不一定與此版本的新增功能相關 (如上一節中所列)，但它們可能會幫助您從現有功能中獲得更多助益。

| 功能區域 | 新增或更新的主題 |
|---|---|
| 工程變更管理 | [工程變更管理常見問題](../engineering-change-management/change-management-faq.md) |
| 採購和資源開發 | [來自廠商的類別要求](../procurement/category-requests-from-vendors.md) |
| 產品資訊管理 | [管理測量單位](../pim/tasks/manage-unit-measure.md)<br><br>[產品設定模型計算](../pim/config-model-calculations.md) |
| 生產控制 | [作業識別碼的統一編號序列](../production-control/unified-job-ids.md) |
| 運輸管理 | [LTL 類別](../transportation/ltl-class.md)<br><br>[NMFC 代碼](../transportation/nmfc-codes.md) |
| 倉庫管理、波次建立和處理 | [波次建立和處理](../warehousing/wave-processing.md)<br><br>[波次處理的倉庫參數](../warehousing/wave-warehouse-parameters.md)<br><br>[波次範本](../warehousing/wave-templates.md)<br><br>[波次配置](../warehousing/wave-allocation-method.md)<br><br>[排程波次期間的工作建立](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[集裝化](../warehousing/wave-containerization.md)<br><br>[波次執行通知](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>其他資源

### <a name="platform-updates-for-finance-and-operations-apps"></a>財務和營運應用程式的平台更新

Microsoft Dynamics 365 Supply Chain Management 10.0.19 包括平台更新。 若要深入了解，請參閱[財務和營運應用程式版本 10.0.19 (2021 年 6 月) 的平台更新](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md)。

### <a name="bug-fixes"></a>錯誤修正

有關 10.0.19 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS)，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415)。

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
