---
title: Dynamics 365 Supply Chain Management 10.0.21 (2021 年 10 月) 的新增功能或變更
description: 本主題說明 Dynamics 365 Supply Chain Management 10.0.21 中的新增功能或變更。
author: kamaybac
ms.date: 10/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ec7fcb97bd46551846ccee13b369a1b02a589688
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449892"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10021-october-2021"></a>Dynamics 365 Supply Chain Management 10.0.21 (2021 年 10 月) 的新增功能或變更

[!include [banner](../includes/banner.md)]

本主題列出 Microsoft Dynamics 365 Supply Chain Management 版本 10.0.21 中的新增功能或變更。 此版本的版本編號為 10.0.960，可用時間如下：

- **發行預覽版**：2021 年 8 月
- **正式發行 (自行更新)：** 2021 年 9 月
- **正式發行 (自動更新)：** 2021 年 10 月

## <a name="features-included-in-this-release"></a>此版本中包含的功能

下表列出了此版本中包含的功能。 *功能* 資料行提供[發行計劃](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)連結，您可以在其中查看每個功能的正式發行日期。 *詳細資訊* 資料行提供更多詳細資料和/或相關文件的連結。

大多數這些功能必須使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)啟用，才可以使用。

| 功能區域 | 功能 | 詳細資訊 |
|---|---|---|
| 庫存&nbsp;和&nbsp;物流 | [Dynamics 365 Supply Chain Management 的全球庫存會計增益集。](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [全球庫存會計首頁](../global-inventory-accounting/global-inventory-accounting-home.md) |
| 庫存&nbsp;和&nbsp;物流 | [使用連接到沖銷帳戶的代碼過帳現有調整](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [庫存盤點的原因代碼](../warehousing/reason-codes-for-counting-journals.md) |
| 庫存&nbsp;和&nbsp;物流 | [銷售報價參考資料匯出原則](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | 選擇對報價參考資料的變更是否會導致這些報價 (或行) 包含在下一次增量匯出中。 如果您選擇不包含此類報價或行，您的增量匯出將執行得更快。<br><br>此功能將名為 **在變更追蹤期間跳過銷售報價參考資料** 的設定新增到 **應收帳款參數** 頁面。 |
| 庫存&nbsp;和&nbsp;物流 | [密封投標](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sealed-bidding) | [詢價的密封投標](../procurement/sealed-bidding.md) |
| 庫存&nbsp;和&nbsp;物流 | [庫存能見度增益集的軟預留](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [庫存能見度預留](../inventory/inventory-visibility-reservations.md) |
| 庫存&nbsp;和&nbsp;物流 | [回扣管理的扣除和實秤重量增強](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [使用扣除 Workbench 管理扣除額](../rebate-management/deduction-workbench.md )<br><br>[處理、審查和過帳回扣](../rebate-management/process-review-post.md)<br><br>[回扣管理交易](../rebate-management/rebate-management-deals.md) |
| 庫存&nbsp;和&nbsp;物流 | [Warehouse 應用程式步驟說明](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [為 Warehouse Management 行動應用程式自訂步驟標題和指示](../warehousing/mobile-app-titles-instructions.md) |
| 庫存&nbsp;和&nbsp;物流 | [到岸成本的工間休息和追蹤更新](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [更新存放追蹤](../landed-cost/update-tracking-putaway.md )<br><br>[在運品處理程序](../landed-cost/in-transit-processing.md) |
| 主計劃 | [規劃最佳化的負天數](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [延遲容忍期 (負天數)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>此版本中包含的功能增強

下表列出了此版本中包含的功能增強。 所有增強功能都為現有功能提供了增量改善。 由於它們只是增強功能，因此未列在[發行計劃](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)中。 但是，為確保這些增強功能不會與您現有的自訂或喜好設定發生衝突，預設情況下它們都處於關閉狀態 (除非另有說明)。 如果您想使用這些功能中的任何一個，必須在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中啟用它們。

| 模組 | 功能&nbsp;管理中的功能&nbsp;名稱&nbsp; | 詳細資訊 |
|---|---|---|
| 成本管理 | 庫存結轉進度詳細資料 | 此預覽功能可以詳細查看庫存結算進度。 |
| 採購和資源開發 | 當工作流程中有多個採購申請時，防止過度消耗一般預算預留 | 當使用者提交和核准超出一般預算預留行剩餘餘額的採購申請時，此預覽功能改進了錯誤檢查。 這有助於防止在工作流程中有多個採購申請時，過度消耗一般預算預留。 |
| 生產控制 | 在生產車間執行介面中顯示完整的序號、批次編號和牌照編號 | 此功能為在生產車間執行介面中查看序號、批次編號和牌照編號清單提供了更佳的體驗。 顯示從具有有限數字字元的卡片檢視表變為提供足夠空間來顯示完整值的清單檢視表。 該清單還提供了搜尋特定數字的功能。 |
| 銷售和行銷 | 限制可以選擇過帳的銷售訂單數量 | 此功能可讓您定義在從銷售訂單清單頁面過帳確認、揀料單、裝箱單和發票時可以選擇的最大銷售訂單數。 它是自動啟用的。 該功能將名為 **過帳的最大銷售訂單數** 的設定新增到 **應收帳款參數** 頁面。 新設定預設值為 *100*。 當選擇大量銷售訂單時，該功能有助於提高銷售訂單清單頁面的效能。 它對週期性工作可以處理的銷售訂單數量沒有影響。 |
| 庫存管理 | 將存放工作與 ASN 分離 | 當您在縮放單位 (作為分佈式混合拓撲的一部分) 上執行倉庫管理工作負載時，需要此功能來發送和接收提前裝運通知 (ASN)。 它新增了一個新的資料庫表，專門用於儲存有關存放工作的資訊。 以前，此資訊也儲存在用於 ASN 的資料表中。 |
| 庫存管理 | 貨位混合單位 | 可讓系統將品項放入包含混合單位 (例如盒子和箱子) 的位置。 對於每個貨位範本行，此功能可讓您選擇該行是否應將品項放入混合單位或單一單位位置。 |
| 庫存管理 | 在裝箱站關閉/重新打開集裝箱時使用更快的 API | 啟用此預覽功能後，將使用新的輕量級流程建立與集裝箱相關的庫存交易，該流程可提高手動裝箱站處理期間關閉或重新打開集裝箱的效能。 |

## <a name="features-turned-on-by-default-in-this-release"></a>此版本中預設啟用的功能

下表列出了 10.0.21 中預設開啟的功能。 大多數已自動開啟的功能都可以在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中關閉。

| 功能名稱 | 啟用日期 | 新增的功能 | 功能狀態 | 模組 |
| :--- | :--- | :--- | :--- | :--- |
| 現有庫存報表儲存 | 9/1/2021 | 4/1/2020 | 預設開啟 | 庫存和倉庫管理 |
| 轉移單取消 | 9/1/2021 | 7/13/2020 | 預設開啟 | 庫存和倉庫管理 |
| 解鎖庫存日記帳 | 9/1/2021 | 8/17/2020 | 預設開啟 | 庫存和倉庫管理 |
| 庫存管理的已儲存檢視表 | 9/1/2021 | 9/30/2020 | 預設開啟 | 庫存和倉庫管理 |
| 從 BOM 行導覽到 BOM 版本 | 9/1/2021 | 11/11/2019 | 預設開啟 | 庫存和倉庫管理 |
| 在庫存日記帳中使用測量單位和單位數量 | 9/1/2021 | 11/11/2019 | 預設開啟 | 庫存和倉庫管理 |
| 允許空的批次屬性值 | 9/1/2021 | 11/11/2019 | 預設開啟 | 庫存和倉庫管理 |
| 庫存轉移單行的自動遞增行號 | 9/1/2021 | 10/11/2019 | 預設開啟 | 庫存和倉庫管理 |
| 庫存日記帳核准工作流程 | 9/1/2021 | 1/6/2020 | 預設開啟 | 庫存和倉庫管理 |
| 啟用庫存品質管理參數警告功能 | 9/1/2021 | 10/7/2019 | 預設開啟 | 庫存和倉庫管理 |
| 從銷售行建立轉移單 | 9/1/2021 | 8/31/2019 | 預設開啟 | 庫存和倉庫管理 |
| 需求預測詳細資料上的預測模型選擇 | 9/1/2021 | 10/11/2019 | 預設開啟 | 主計劃 |
| 主計劃進度視覺效果 | 9/1/2021 | 10/7/2019 | 預設開啟 | 主計劃 |
| 規劃最佳化的自動確定 | 9/1/2021 | 10/11/2019 | 預設開啟 | 主計劃 |
| 計劃訂單的平行確認 | 9/1/2021 | 8/31/2019 | 預設開啟 | 主計劃 |
| 投標提交成功訊息 | 9/1/2021 | 5/15/2019 | 預設開啟 | 採購和資源開發 |
| 新增至 PO 的 RFQ 參考連結 | 9/1/2021 | 8/31/2019 | 預設開啟 | 採購和資源開發 |
| 能夠批次確認來自廠商共同作業的已接受訂購單 | 9/1/2021 | 9/10/2019 | 預設開啟 | 採購和資源開發 |
| 採購 cXML 增強功能 | 9/1/2021 | 11/11/2019 | 預設開啟 | 採購和資源開發 |
| 將&quot;開啟已發佈的詢價&quot;連結顯示為圖標 | 9/1/2021 | 9/30/2020 | 預設開啟 | 採購和資源開發 |
| RFQ 問答 | 9/1/2021 | 2/19/2020 | 預設開啟 | 採購和資源開發 |
| 有害物料產品資訊和裝運文件 | 9/1/2021 | 6/14/2020 | 預設開啟 | 產品資訊管理 |
| 嚴格驗證預設訂單數量 | 9/1/2021 | 6/24/2020 | 預設開啟 | 產品資訊管理 |
| 原產地管理功能 | 9/1/2021 | 7/13/2020 | 預設開啟 | 產品資訊管理 |
| 已發佈產品的已儲存檢視表 | 9/1/2021 | 9/30/2020 | 預設開啟 | 產品資訊管理 |
| 核准和傳輸作業對話方塊的改進 | 9/1/2021 | 10/11/2019 | 預設開啟 | 生產控制 |
| 報告為已完成的牌照新增到工作卡裝置 | 9/1/2021 | 8/31/2019 | 預設開啟 | 生產控制 |
| 工作卡終端頁面新增了停止休息的新按鈕 | 9/1/2021 | 2/19/2020 | 預設開啟 | 生產控制 |
| 啟用分包品項的部分收貨並解決廠商類型的物料清單行的報廢計算問題。 | 9/1/2021 | 11/11/2019 | 預設開啟 | 生產控制 |
| 產品控制的已儲存檢視表 | 9/1/2021 | 8/17/2020 | 預設開啟 | 生產控制 |
| 製造業適用的 Dynamics 365 Guides | 9/1/2021 | 7/13/2020 | 預設開啟 | 生產控制 |
| 生產車間執行 | 9/1/2021 | 9/30/2020 | 預設開啟 | 生產控制 |
| 鎖定工作卡裝置和工作卡終端以便對其進行處理的功能 | 9/1/2021 | 5/10/2020 | 預設開啟 | 生產控制 |
| 銷售訂單的費用分配 | 9/1/2021 | 9/30/2020 | 預設開啟 | 銷售和行銷 |
| 限制可以選擇過帳的銷售訂單數量 | 9/1/2021 | 9/1/2021 | 預設開啟 | 銷售和行銷 |
| 清理銷售訂單更新歷程記錄 | 9/1/2021 | 9/1/2021 | 預設開啟 | 銷售和行銷 |
| 變更週期盤點工作的編號 | 9/1/2021 | 10/7/2019 | 預設開啟 | 庫存管理 |
| 基於工作的波次需求補貨 | 9/1/2021 | 10/7/2019 | 強制 | 庫存管理 |
| 隱藏&quot;所有負載&quot;和&quot;負載詳細資料&quot;頁面上的「總值」欄位 | 9/1/2021 | 10/7/2019 | 預設開啟 | 庫存管理 |
| 波次標籤列印 | 9/1/2021 | 2/19/2020 | 強制 | 庫存管理 |
| 將訂購單庫存交易與負載相關聯 | 9/1/2021 | 1/6/2020 | 強制 | 庫存管理 |
| 增強的牌照標籤配置 | 9/1/2021 | 2/19/2020 | 預設開啟 | 庫存管理 |
| 組織範圍內的工作中斷 | 9/1/2021 | 2/19/2020 | 強制 | 庫存管理 |
| 工作行詳細資料 | 9/1/2021 | 10/11/2019 | 預設開啟 | 庫存管理 |
| 使行動裝置庫存移動庫存狀態欄位可編輯 | 9/1/2021 | 10/16/2019 | 預設開啟 | 庫存管理 |
| 從批次作業確認出庫貨物 | 9/1/2021 | 7/13/2020 | 預設開啟 | 庫存管理 |
| 控制是否在行動裝置上顯示接收摘要頁面 | 9/1/2021 | 4/1/2020 | 預設開啟 | 庫存管理 |
| 提示解析不明確的 &#39;Loc / LP&#39; 名稱 | 9/1/2021 | 4/1/2020 | 預設開啟 | 庫存管理 |
| 在負載品項接收期間在倉庫應用程式中擷取產品變型和追蹤維度 | 9/1/2021 | 5/10/2020 | 預設開啟 | 庫存管理 |
| 不允許建立不符合波次負載組建範本要求的負載。 | 9/1/2021 | 8/17/2020 | 預設開啟 | 庫存管理 |
| 評估多 SKU 位置指令的所有動作 | 9/1/2021 | 9/30/2020 | 預設開啟 | 庫存管理 |

## <a name="new-and-updated-documentation-resources"></a>新增和更新的文件資源

我們最近新增或大幅更新了以下說明主題。 它們不一定與此版本的新增功能相關 (如上一節中所列)，但它們可能會幫助您從現有功能中獲得更多助益。

| 功能區域 | 新增或更新的主題 |
|---|---|
| 主計劃 | [庫存預測](../master-planning/inventory-forecast.md) |
| 主計劃 | [規劃最佳化未使用的參數](../master-planning/planning-optimization/not-used-parameters.md) |
| 主計劃 | [補貨方式及數量修改](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| 主計劃 | [以無限產能進行排程](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| 主計劃 | [檢視計劃歷程與規劃記錄](../master-planning/planning-optimization/plan-history-logs.md) |
| 庫存管理 | [集裝箱裝箱策略](../warehousing/container-packing-strategy-overview.md) |
| 庫存管理 | [週期盤點範例案例](../warehousing/cycle-counting-scenarios.md) |
| 庫存管理 | [透過 V2 資料實體匯入入庫 ASN](../warehousing/import-asn-v2-data-entity.md) |
| 庫存管理 | [銷售訂單和轉移單的超選](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| 庫存管理 | [在波次期間排程波次標籤列印](../warehousing/configure-task-based-wave-label-printing.md) |
| 庫存管理 | [Warehouse Management 行動應用程式中的新增功能或變更](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>其他資源

### <a name="platform-updates-for-finance-and-operations-apps"></a>財務和營運應用程式的平台更新

Microsoft Dynamics 365 Supply Chain Management 10.0.21 包括平台更新。 若要深入了解，請參閱[財務和營運應用程式版本 10.0.21 (2021 年 10 月) 的平台更新](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md)。

### <a name="bug-fixes"></a>錯誤修正

有關 10.0.21 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS)，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de)。

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
