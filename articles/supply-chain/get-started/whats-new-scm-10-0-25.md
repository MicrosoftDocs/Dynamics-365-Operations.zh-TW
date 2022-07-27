---
title: Dynamics 365 Supply Chain Management 10.0.25 預覽版 (2022 年 4 月)
description: 本主題說明 Microsoft Dynamics 365 Supply Chain Management 10.0.25 中的新增功能或變更。
author: kamaybac
ms.date: 03/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 26f67be72948e33738cf805b541d3c7e701f8dba
ms.sourcegitcommit: a8f4d7d21d9af17d80b1213e5e1a81f42fb8b928
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/14/2022
ms.locfileid: "8450126"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10025-april-2022"></a>Dynamics 365 Supply Chain Management 10.0.25 預覽版 (2022 年 4 月)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題列出 Microsoft Dynamics 365 Supply Chain Management 預覽版 10.0.25 中的新增功能或變更。 此版本的版本編號為 10.0.1149，可用時間如下：

- **發行預覽版：** 2022 年 2 月
- **正式發行 (自行更新)：** 2022 年 3 月
- **正式發行 (自動更新)：** 2022 年 4 月

## <a name="features-included-in-this-release"></a>此版本中包含的功能

下表列出了此版本中包含的功能。 我們可能會更新此主題以包含在最初發佈此主題後將其納入組建的功能。

| 功能區域 | 功能 | 詳細資訊 | 啟用者   |
|---|---|---|---|
| 庫存&nbsp;和&nbsp;物流 | [有害物料增強](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/hazardous-materials-enhancements) | 即將推出 | 功能管理：<br>*有害物料增強* |
| 庫存&nbsp;和&nbsp;物流 | [裝箱站的裝箱工作](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/packing-work-packing-stations) | 即將推出 | 功能管理：<br>*裝箱站的裝箱工作* |
| 庫存&nbsp;和&nbsp;物流 | [使用 GS1 格式標準掃描倉庫中的條碼](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [GS1 條碼和 QR 代碼](../warehousing/gs1-barcodes.md) | 功能管理：<br>*掃描 GS1 條碼* |
| 製造 | [生產現場執行介面中的物料消耗和預留](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [工作人員該如何使用生產現場執行介面](../production-control/production-floor-execution-use.md) | 功能管理：<br>*（預覽版）在生產現場執行介面（非 WMS）上登記材料消耗*<br><br>和/或：<br><br>功能管理：<br>*（預覽版）在生產現場執行介面（啟用 WMS）上登記材料消耗* |
| 製造 | [依縮放單位登記物料消耗](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/register-material-consumption-scale-units) | [雲端和邊緣縮放單位的製造執行工作負載](../cloud-edge/cloud-edge-workload-manufacturing.md) | 功能管理：<br>*依縮放單位在行動應用程式上登記物料消耗* |
| 規劃 | [規劃最佳化集中行事曆維護](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-centralized-calendar-maintenance) | [行事曆和主計劃](../master-planning/supply-chain-calendars-master-planning.md) | 預設啟用 |
| 規劃 | [最佳化現有供應的規劃最佳化建議](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [動作訊息](../master-planning/action-messages.md) | 預設啟用 |
| 規劃 | 計劃訂單簡化 | [計劃訂單簡化](../master-planning/planning-optimization/planned-orders-simplified.md ) | 功能管理：<br>*計劃訂單簡化* |

## <a name="feature-enhancements-included-in-this-release"></a>此版本中包含的功能增強

下表列出了此版本中包含的功能增強。 所有增強功能都為現有功能提供了增量改善。 由於它們只是增強功能，因此未列在[發行計劃](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features)中。 但是，為確保這些增強功能不會與您現有的自訂或喜好設定發生衝突，預設情況下它們都處於關閉狀態 (除非另有說明)。

如果您想開啟或關閉這些功能，必須在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中進行作業。

| 模組 | 功能管理中的功能名稱 | 詳細資訊 |
|---|---|---|
| 庫存和倉庫管理 | (波蘭) 允許將多個 SAD 發票連結到一個 SAD 中的一個訂購單行 | 當這些訂購單行為多個不同的發票 (例如不同的裝運) 過帳時，此功能可讓您拆分訂購單行並將它們連結到單一管理文件 (SAD)。 |
| 採購和資源開發 | 按會計日期將多個採購申請合併到一個訂購單中 | 如果不同的採購申請具有不同的會計日期，此功能可將多個採購申請合併為一個訂購單。 可以設定訂購單建立和需求合併採購策略規則，以自動根據訂購單等級的會計日期對申請行進行分組決策。 如果啟用預算控制，則不支援按會計日期合併訂購單，因為會計日期用於預算預留和保留。 因此，在採購申請到訂購單的過渡期間應保留它。 |
| 採購和資源開發 | 顯示舊版預設 RFQ 回覆欄位設定 | 此功能重新引入了先前從使用者介面中刪除的舊版預設詢價 (RFQ) 回覆欄位設定。 這些設定不提供任何現成的功能，但可以根據需要進行自訂。 如果您的組織已經為預設 RFQ 回覆欄位設定新增了功能或計劃新增此功能，請啟用此功能。 啟用此功能後，您可以存取設定 **採購和資源開發參數** 頁面，打開 **詢價** 索引標籤，然後選擇 **預設詢價回覆欄位**。 |
| 採購和資源開發 | 將來自廠商的財務維度與訂購單上的使用中維度連結財務維度合併 | 如果您在財務維度和站點庫存維度之間設定連結，則此功能可讓您在採購申請核准後，將來自廠商的財務維度與使用中維度連結財務維度合併。 可以設定訂購單建立和需求合併採購策略規則，以推動在採購訂單標題等級將廠商的財務維度與有效維度連結財務維度合併的決定。 |
| 生產控制 | (俄羅斯) 為生產配方/BOM 和生產中的自動 GTD 預留/消耗啟用預設位置設定 | 此功能為根據匯入的原物料進行生產提供了更多選項 (僅限俄文當地語系化)<ul><li>用於為資源組和倉庫上的生產公式和物料清單設定自動預設位置的選項。</li><li>根據非 WMS 預留演算法在啟動 WMS 的倉庫中按 *GTD 編號* 維度自動預留原物料。 當存在 *原物料揀料* 的工作原則且 **工作建立方法** 設為 *永不*，且倉庫、位置和物料編號設定與生產 (批次) 訂單的庫存交易相符時，適用此功能。</li><li>根據之前所述而獲取的預留，在進行領料單過帳時按 *GTD 編號* 維度自動消耗原物料。</li></ul> |
| 倉庫管裡 | (預覽版) 縮放單位支援的入庫和出庫訂單 | 此功能將導致系統在下達到倉庫流程中建立出庫倉庫訂單，以及將轉移單過帳為已裝運訂單時建立入庫倉庫訂單。 然後，系統將每個入庫或出庫倉庫訂單同步到負責裝運或接收訂單的縮放單位。 請注意，啟用此功能後，必須升級倉庫執行工作負載。 更多資訊，請參閱[雲端和邊緣縮放單位的倉庫管理工作負載](../cloud-edge/cloud-edge-workload-warehousing.md)。<br><br>此功能需要 *將存放工作與 ASN 分離* 功能，並將啟用使用 Warehouse Management 行動應用程式上的牌照接收流程接收轉移單的功能。 |

## <a name="feature-state-changes-in-this-release"></a>此版本中的功能狀態變更

下表列出了從 10.0.25 開始強製或默認啟用的功能。 更新到 10.0.25 後，系統會自動啟用所有這些功能。 強制功能無法關閉，但仍可以使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)關閉預設開啟的功能。

該表還列出了處於公開預覽版狀態，但在 10.0.25 中已變為正式發行的功能，這代表現在建議在生產環境中使用它們。 除非另有說明，否則這些功能預設為關閉，因此如果您想使用它們，必須使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)來進行啟用。

| 模組 | 功能名稱 | 功能狀態 |
| --- | --- | --- |
| 資產管理 | [在執行維護計畫時，套用對工單進行分組的規則](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | 正式發行 |
| 資產管理 | [以計數器為基準的維護增強功能](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | 正式發行 |
| 成本管理 | [成本計算等級](../cost-management/cost-calculation-level.md) | 正式發行 |
| 成本管理 | 為庫存結轉沖銷啟用使用者定義的批次編號設定 | 正式發行 |
| 成本管理 | [庫存結轉進度詳細資料](whats-new-scm-10-0-21.md) | 正式發行 |
| 成本管理 | [用於庫存標準成本重估的預設財務維度的選項](../cost-management/manage-standard-cost-updates.md) | 正式發行 |
| 成本管理 | 庫存值報表資料清除 | 預設開啟 |
| 成本管理 | [庫存值報表儲存](../cost-management/inventory-value-report-storage.md) | 預設開啟 |
| 成本管理 | 在格線中顯示庫存結轉記錄 | 預設開啟 |
| 工程變更管理 | [對現有產品啟用變更管理](../engineering-change-management/change-management-existing-products.md) | 預設開啟 |
| 工程變更管理 | [工程變更管理](../engineering-change-management/product-engineering-overview.md) | 預設開啟 |
| 工程變更管理 | [生產工程通知](../engineering-change-management/engineering-change-management.md) | 預設開啟 |
| 工程變更管理 | [工程變更管理的已改進屬性繼承](../engineering-change-management/engineering-attributes-and-search.md) | 預設開啟 |
| 工程變更管理 | [管理對配方及其成分的變更](../engineering-change-management/manage-formula-changes.md) | 預設開啟 |
| 工程變更管理 | [產品整備度檢查](../engineering-change-management/product-readiness.md) | 預設開啟 |
| 工程變更管理 | [產生工程產品的變型](../engineering-change-management/engineering-variants.md) | 預設開啟 |
| 庫存和倉庫管理 | 從 BOM 行導覽到 BOM 版本 | 強制 |
| 主計劃 | [計劃散裝批次訂單和裝箱批次訂單的可批次確認和合併](whats-new-scm-10-0-20.md) | 正式發行 |
| 主計劃 | 資源規劃維護 | 正式發行 |
| 主計劃 | 啟用主計劃設定精靈功能 | 強制 |
| 主計劃 | [需求預測詳細資料上的預測模型選擇](../master-planning/manual-adjustments-baseline-forecast.md) | 強制 |
| 主計劃 | [主計劃進度視覺效果](../master-planning/tasks/monitor-master-planning-run.md) | 強制 |
| 主計劃 | [計劃訂單的平行確認](../master-planning/planning-optimization/planned-order-firming.md) | 強制 |
| 主計劃 | [使用篩選確認計劃訂單](../master-planning/planning-optimization/planned-order-firming.md) | 預設開啟 |
| 主計劃 | [計劃訂單的已儲存檢視表](saved-views-scm.md) | 預設開啟 |
| 採購 | 停用採購申請分配重設按鈕 | 正式發行 |
| 採購 | [啟用重設採購相關工作流程](whats-new-scm-10-0-20.md) | 正式發行 |
| 採購 | 能夠批次確認來自廠商共同作業的已接受訂購單 | 強制 |
| 採購 | 採購合約「已結束」狀態 | 強制 |
| 採購和資源開發 | 將行新增到與採購合約相關聯的 PO 發票 | 預設開啟 |
| 採購和資源開發 | 將 [訂購數量] 欄位新增到 [過帳產品收貨] 頁面 | 預設開啟 |
| 採購和資源開發 | [允許廠商透過廠商共同作業套用採購類別](../procurement/category-requests-from-vendors.md) | 預設開啟 |
| 採購和資源開發 | 訂購單的起始金額和終止金額 | 預設開啟 |
| 採購 | 站點和倉庫的費用設定 | 預設開啟 |
| 採購 | 啟用基於年度關稅的採購關稅計算 | 預設開啟 |
| 採購和資源開發 | [採購合約責任方](../procurement/purchase-agreements.md) | 預設開啟 |
| 採購和資源開發 | [訂購單的已儲存檢視表](saved-views-scm.md) | 預設開啟 |
| 產品資訊管理 | [嚴格驗證預設訂單數量](../production-control/default-order-settings.md) | 強制 |
| 產品資訊管理 | 物料清單報表預處理以避免逾時 | 預設開啟 |
| 產品資訊管理 | 使用品項範本時分別對應的預設財務維度 | 預設開啟 |
| 產品資訊管理 | 啟用品項範本的產品維度群組 | 預設開啟 |
| 產品資訊管理 | 根據命名法重新產生產品變型名稱 | 預設開啟 |
| 產品資訊管理 | [變型建議頁面改善](../pim/tasks/create-predefined-product-variants.md) | 預設開啟 |
| 生產控制 | 改進的生產實秤重量數量揀料 | 正式發行 |
| 生產控制 | 工作卡終端頁面新增了停止休息的新按鈕 | 強制 |
| 生產控制 | [在工作卡裝置中報告為完成時，啟用自動產生牌照號碼](../production-control/production-floor-execution-configure.md) | 強制 |
| 生產控制 | 啟用分包品項的部分收貨並解決廠商類型的物料清單行的報廢計算問題 | 強制 |
| 生產控制 | [用於鎖定工作卡裝置和工作卡終端以便對其進行處理的功能](../production-control/production-floor-execution-configure.md) | 強制 |
| 生產控制 | 核准和傳輸作業對話方塊的改進 | 強制 |
| 生產控制 | [報告為已完成的牌照新增到工作卡裝置](../production-control/production-floor-execution-configure.md) | 強制 |
| 生產控制 | [從工作卡裝置列印標籤](../production-control/production-floor-execution-configure.md) | 強制 |
| 生產控制 | [生產現場執行](../production-control/production-floor-execution-configure.md) | 強制 |
| 生產控制 | [生產現場執行介面的資產管理功能](../production-control/production-floor-execution-configure.md) | 預設開啟 |
| 生產控制 | [生產現場執行介面的作業搜尋](../production-control/production-floor-execution-configure.md) | 預設開啟 |
| 生產控制 | [覆寫預設生產預留](../production-control/override-default-reservation-principle.md) | 預設開啟 |
| 生產控制 | [在生產現場執行介面中顯示完整的序號、批次編號和牌照編號](whats-new-scm-10-0-21.md) | 預設開啟 |
| 銷售和行銷 | [銷售訂單詳細資料效能增強](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | 正式發行 |
| 銷售和行銷 | 銷售報價詳細資料效能增強 | 正式發行 |
| 銷售和行銷 | 銷售訂單參考資料匯出原則 | 強制 |
| 銷售和行銷 | [銷售訂單到訂購單行刪除原則](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | 強制 |
| 銷售和行銷 | [銷售報價參考資料匯出原則](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| 強制 |
| 銷售和行銷 | [連絡人資料實體匯出最佳化](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | 預設開啟 |
| 銷售和行銷 | 啟用對銷售報價單文件介紹和文件結論欄位的查詢 | 預設開啟 |
| 銷售和行銷 | [提高「前 100 名」客戶報表績效](whats-new-scm-10-0-23.md) | 預設開啟 |
| 銷售和行銷 | 重新計算估計的客戶餘額 | 預設開啟 |
| 銷售和行銷 | [具有或不具實秤重量的小數精確度銷售退貨單行登記](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | 預設開啟 |
| 銷售和行銷 | [銷售和行銷的已儲存檢視表](saved-views-scm.md) | 預設開啟 |
| 銷售和行銷 | 按一下銷售訂單確認 | 預設開啟 |
| 倉庫管裡 | [具有位置指令的直接轉運範本](../warehousing/planned-cross-docking.md) | 正式發行 |
| 倉庫管裡 | [停用從鎖定庫存取樣的品質檢驗訂單的預期收貨](../inventory/inventory-blocking.md) | 正式發行 |
| 倉庫管裡 | 牌照接收歷程記錄 | 正式發行 |
| 倉庫管裡 | [物料處理設備介面](../warehousing/mhax.md) | 正式發行 |
| 倉庫管裡 | [下達倉庫時將數量向下四捨五入到最接近的銷售單位](whats-new-scm-10-0-19.md) | 正式發行 |
| 倉庫管裡 | 支援倉庫應用程式工作清單的縮放單位 | 正式發行 |
| 倉庫管裡 | 裝運波次標籤詳細資料 | 正式發行 |
| 倉庫管裡 | [對裝箱站關閉/重新打開集裝箱的集裝箱使用更快的 API](whats-new-scm-10-0-21.md) | 正式發行 |
| 倉庫管裡 | [驗證為補貨作業選擇的範本](whats-new-scm-10-0-20.md) | 正式發行 |
| 倉庫管裡 | 允許補貨範本使用現有的即時補貨工作 (跨單位) | 強制 |
| 倉庫管裡 | 建立 WHS 使用者時自動指派 GUID | 強制 |
| 倉庫管裡 | 在負載品項接收期間在倉庫應用程式中擷取產品變型和追蹤維度 | 強制 |
| 倉庫管裡 | [變更由追蹤維度控制的品項的庫存狀態](../inventory/inventory-statuses.md) | 強制 |
| 倉庫管裡 | [變更工作的工作池](../warehousing/change-work-pool-on-work.md) | 強制 |
| 倉庫管裡 | [叢集位置已滿](../warehousing/cluster-position-full.md) | 強制 |
| 倉庫管裡 | [集群存放功能](../warehousing/putaway-clusters.md) | 強制 |
| 倉庫管裡 | [確認並轉移](../warehousing/confirm-and-transfer.md) | 強制 |
| 倉庫管裡 | [從批次作業確認出庫貨物](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | 強制 |
| 倉庫管裡 | [控制是否在行動裝置上顯示接收摘要頁面](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | 強制 |
| 倉庫管裡 | [手動庫存移動作業的延遲處理](../warehousing/deferred-processing-manual-inventory-movement.md) | 強制 |
| 倉庫管裡 | 不允許建立不符合波次負載組建範本要求的負載 | 強制 |
| 倉庫管裡 | [增強的牌照標籤配置](../warehousing/document-routing-layout-for-license-plates.md) | 強制 |
| 倉庫管裡 | [評估多 SKU 位置指令的所有動作](../troubleshooting/warehousing/evaluate-multiple-location-directive-actions.md) | 強制 |
| 倉庫管裡 | 隱藏 [所有負載] 和 [負載詳細資料] 頁面上的 [總值] 欄位 | 強制 |
| 倉庫管裡 | 牌照標籤組建設定 | 強制 |
| 倉庫管裡 | 針對管理員或類似受信任使用者的負載行手動更正 | 強制 |
| 倉庫管裡 | [場所牌照定位](../warehousing/location-license-plate-positioning.md) | 強制 |
| 倉庫管裡 | [位置產品維度混合](../warehousing/location-product-dimension-mixing.md) | 強制 |
| 倉庫管裡 | 使行動裝置庫存移動庫存狀態欄位可編輯 | 強制 |
| 倉庫管裡 | 針對管理員或類似受信任使用者的銷售行手動揀料服務 | 強制 |
| 倉庫管裡 | [防止在目的地倉庫以外的倉庫使用轉移單已裝運牌照](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | 強制 |
| 倉庫管裡 | 提示解析不明確的「位置/牌照」名稱 | 強制 |
| 倉庫管裡 | [品質檢查](../warehousing/quality-check.md) | 強制 |
| 倉庫管裡 | [新倉庫應用程式的使用者設定、圖示和步驟標題](../warehousing/install-configure-warehouse-management-app.md) | 強制 |
| 倉庫管裡 | [其他位置區域](../warehousing/additional-location-zones.md) | 預設開啟 |
| 倉庫管裡 | [從倉庫應用程式建立及處理轉移單](../warehousing/create-transfer-order-from-warehouse-app.md) | 預設開啟 |
| 倉庫管裡 | 啟用倉庫行動裝置的快速驗證 | 預設開啟 |
| 倉庫管裡 | [倉庫管理現有項目清理作業的最長執行時間](../warehousing/onhand-cleanup.md) | 預設開啟 |
| 倉庫管裡 | [出庫工作負載視覺效果](../warehousing/outbound-workload-visualization.md) | 預設開啟 |
| 倉庫管裡 | [處理倉庫應用程式事件](../warehousing/warehouse-app-events.md) | 預設開啟 |
| 倉庫管裡 | [負載規劃工作台的已儲存檢視表](saved-views-scm.md) | 預設開啟 |
| 倉庫管裡 | [工作詳細資料頁面的已儲存檢視表](saved-views-scm.md) | 預設開啟 |
| 倉庫管裡 | [波次處理的已儲存檢視表](saved-views-scm.md) | 預設開啟 |
| 倉庫管裡 | [負載處理的已儲存檢視表](saved-views-scm.md) | 預設開啟 |
| 倉庫管裡 | [裝運處理的已儲存檢視表](saved-views-scm.md) | 預設開啟 |
| 倉庫管裡 | [波次批次作業詳細資料](../warehousing/wave-processing.md) | 預設開啟 |
| 倉庫管裡 | [波次執行通知](../warehousing/wave-execution-notifications.md) | 預設開啟 |

## <a name="additional-resources"></a>其他資源

### <a name="platform-updates-for-finance-and-operations-apps"></a>財務和營運應用程式的平台更新

Microsoft Dynamics 365 Supply Chain Management 10.0.25 包括平台更新。 若要深入了解，請參閱[財務和營運應用程式版本 10.0.25 (2022 年 4 月) 的平台更新](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md)。

### <a name="bug-fixes"></a>錯誤修正

有關 10.0.25 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS)，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868)。

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 和產業雲端：2022 年發布第 1 波計劃

想了解商務應用程式或平台中即將推出和最近發布的功能嗎？

查看 [Dynamics 365 和產業雲端：2022 年發布第 1 波計劃](/dynamics365-release-plan/2022wave1/) 我們已經在文件中擷取了所有詳細資料，從頭到尾，從上到下，方便您進行規劃。

### <a name="removed-and-deprecated-supply-chain-management-features"></a>已移除和已取代的 Supply Chain Management 功能

[Dynamics 365 Supply Chain Management 中已移除或已取代的功能](removed-deprecated-features-scm-updates.md)主題說明了 Supply Chain Management 已經或計劃移除或取代的功能。

- *已移除* 功能不再於產品中提供該功能。
- *已取代* 功能未進行開發，可能會在未來的更新中移除。

在從產品中刪除任何功能之前，將在移除前 12 個月在 [Dynamics 365 Supply Chain Management 中已移除或已取代的功能](removed-deprecated-features-scm-updates.md)主題中公佈取代通知。

對於僅影響編譯時間但與沙盒和生產環境二進位相容的重大變更，取代時間將少於 12 個月。 這些通常是需要對編譯器進行的功能更新。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
