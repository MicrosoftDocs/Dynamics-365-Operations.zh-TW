---
title: Dynamics 365 Supply Chain Management 10.0.23 (2022 年 1 月) 的新增功能或變更
description: 本主題說明 Microsoft Dynamics 365 Supply Chain Management 10.0.23 中的新增功能或變更。
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 83d19f92984c9f67242946aa8faf445d9d2bd881
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449571"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10023-january-2022"></a>Dynamics 365 Supply Chain Management 10.0.23 (2022 年 1 月) 的新增功能或變更

[!include [banner](../includes/banner.md)]

本主題列出 Microsoft Dynamics 365 Supply Chain Management 版本 10.0.23 中的新增功能或變更。 此版本的版本編號為 10.0.1037，可用時間如下：

- **發行預覽版：** 2021 年 10 月
- **正式發行 (自行更新)：** 2021 年 12 月
- **正式發行 (自動更新)：** 2022 年 1 月

## <a name="features-included-in-this-release"></a>此版本中包含的功能

下表列出了此版本中包含的功能。 *功能* 資料行提供[發行計劃](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)連結，您可以在其中查看每個功能的正式發行日期。 *詳細資訊* 資料行提供更多詳細資料和/或相關文件的連結。 若要決定如何打開功能，請參閱 *啟用者* 資料行。 更多有關如何使用功能管理的資訊，請參閱[功能管理概觀](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。 我們可能會更新此主題以包含在最初發佈此主題後將其納入組建的功能。

| 功能區域 | 功能 | 詳細資訊 | 啟用者   |
|---|---|---|---|
| 全球通訊錄 | 在地址設定中為每個國家/地區定義預設縣/市 | 您現在可以在全球通訊錄的地址設定中為每個國家/地區定義預設縣/市。 設定預設縣/市後，當您為該國家/地區建立新的縣或市記錄時，它將是在縣/市欄位中輸入的預設值。 另請參閱[地址設定](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json) | 預設啟用。 |
| 庫存&nbsp;和&nbsp;物流 | [在 Warehouse Management 行動應用程式中暫停工作](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [為行動裝置功能表項目中的步驟設定繞道](../warehousing/warehouse-app-detours.md) | 功能管理 (*Warehouse Management 應用程式繞道*) |
| 庫存&nbsp;和&nbsp;物流 | [倉庫應用程式升階欄位](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [為行動裝置應用程式中的步驟設定升階欄位](../warehousing/warehouse-app-promoted-fields.md)| 功能管理 (*倉庫應用程式升階欄位*) |
| 製造 | [製造執行系統整合](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [與第三方製造執行系統整合](../production-control/mes-integration.md) | 功能管理 (*製造執行系統整合*) |
| 製造 | [從生產現場執行介面報告副產物和副產品](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [工作人員該如何使用生產現場執行介面](../production-control/production-floor-execution-use.md) | 管理功能 (*從生產現場執行介面報告聯產品和副產品*) |
| 規劃 | [規劃最佳化支援具有優先順序的規劃](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [具有優先順序的規劃](../master-planning/planning-optimization/priority-based-planning.md) | 功能管理 (*規劃最佳化的優先順序導向的MRP 支援*) |

## <a name="feature-enhancements-included-in-this-release"></a>此版本中包含的功能增強

下表列出了此版本的新功能增強。 所有增強功能都為現有功能提供了增量改善。 由於它們只是增強功能，因此未列在[發行計劃](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)中。 但是，為確保這些增強功能不會與您現有的自訂或喜好設定發生衝突，預設情況下它們都處於關閉狀態 (除非另有說明)。

如果您想打開或關閉這些功能，您必須在 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中進行，其中所列的功能使用下表 *功能管理中的功能名稱* 資料行中顯示的名稱。

| 模組 | 功能管理中的功能名稱 | 詳細資訊 |
|---|---|---|
| 資產管理 | 用於工單日記帳中費用的沖銷帳戶 | 此功能可讓您為工單日記帳中列出的每項費用指定沖銷帳戶。 您通常可以將廠商帳戶與每項費用相關聯，但也支援其他帳戶類型。 它將兩個新資料行 (**沖銷帳戶類型** 和 **沖銷帳戶**) 新增到 **工單日記帳** 頁面的 **費用** FastTab。|
| 成本管理 | 為標準成本四捨五入重估建立相關憑證 | <p>進行庫存財務過帳 (例如銷售訂單發票或庫存交易) 時，此功能會導致系統為任何相關的標準成本四捨五入重估建立單獨的憑證，並將其作為相關憑證附加到財務過帳憑證。</p><p>如果沒有此功能，系統會在同一個憑證過帳上記錄標準成本四捨五入重估。 這種行為有時會導致日期資訊發生衝突，因為重估使用工作階段或系統日期，而財務過帳使用過帳日期。</p> |
| 庫存和倉庫管理 | \[俄羅斯\]根據銷售訂單財務憑證中的更正旗標過帳 Storno 財務庫存交易 | 此功能會影響俄羅斯的貸方票據更正功能。 它可讓根據總帳中的更正選項過帳銷售發票的庫存交易記錄。 啟用此功能後，庫存交易的財務憑證上的 **更正** 旗標和庫存交易的 **Storno** 旗標之間不再存在差異。 |
| 庫存和倉庫管理 | (俄羅斯) 批次執行庫存餘額周轉報表計算 | 對於 Supply Chain Management 的俄羅斯當地語系化，此功能提供了執行 *存貨餘額周轉率* 批量報告，存儲它，並查看之前產生的報告。 |
| 庫存和倉庫管理 |  (俄羅斯) 在庫存管理中使用國家或地區特定主要形式的當地語言翻譯 | 對於 Supply Chain Management 的俄文當地語系化，此功能可讓在以下俄文特定庫存列印輸出中對產品/項目名稱和計量單位使用俄文翻譯：盤點清單 (INV-3)、盤點清單 (INV-5)、和盤點清單 (INV-6)。 |
| 主計劃 | 用於需求預測的 Azure Machine Learning 服務 | 此功能可讓 Azure Machine Learning Service 根據歷史資料產生需求預測。 如需詳細資訊，請參閱[需求預測步驟](../master-planning/demand-forecasting-setup.md)。 |
| 採購和資源開發 | 清理訂購單更新歷程記錄 | 此功能可讓您清理與訂購單更新相關的臨時歷史記錄。 它將名為 **清理購買更新歷史** 的新按鈕新增到 **所有訂購單** 頁面的動作窗格。 此功能為預設啟用。 |
| 生產控制 | (預覽版) 為自動過帳的揀料單啟用倉庫自動揀料 | 此功能可讓您為自動過帳、衍生和倒沖的揀料單日記帳自動揀料和解決庫存維度。 |
| 生產控制 | 根據計劃消耗日期驗證原物料的到期日 | 此功能改變了在保留要在生產期間使用的一批原物料時驗證批次到期日的方式。 啟用此功能後，將根據生產物料清單行或批次訂單公式行中建立的計劃消耗日期 (原物料日期) 驗證批次到期日期。 停用此功能時，將根據生產或批次訂單的計劃交貨日期 (如前所述) 驗證批次到期日期。 |
| 銷售和行銷 | 根據存留期清理銷售更新歷史 | 此功能可讓您設定在執行 **銷售更新歷史清理** 週期性工作時要保留的最長記錄期限。 舊記錄將刪除。 當您將工作設定為定期執行時，此功能會很實用，因為存留期都是相對於工作執行日期計算的。 如果沒有此功能，您只能為要保留的最舊記錄設定特定日期。 |
| 銷售和行銷 | 提高「前 100 名」客戶報表績效 | 此功能透過跨所有客戶執行報表 (其為預定用途) 而不是允許自訂查詢來提高 **前 100 名** 客戶報表的效能。 啟用此功能後，在 **前 100 名** 報告對話方塊中將停用所有 **要包括的記錄** 設定。 |
| 庫存管理 | 縮放單位支援下達到倉庫的出庫訂單 | 啟用此功能後，出庫訂單可以從中樞直接下達到訂單將在其中完成的縮放單位。 |

## <a name="new-and-updated-documentation-resources"></a>新增和更新的文件資源

我們最近新增或大幅更新了以下說明主題。 這些主題不一定與為此版本新增的新功能相關，如上一節中所列。 但是，它們可能會幫助您充分利用現有功能。

| 功能區域 | 新增或更新的主題 |
|---|---|
| 工程變更管理 | [工程屬性與工程屬性搜尋](../engineering-change-management/engineering-attributes-and-search.md)中說明工程屬性繼承的運作原理。 |
| 主計劃 | [具有需求預測的主計劃](../master-planning/planning-optimization/demand-forecast.md)和[預測縮減參數](../master-planning/reduction-keys.md)現在提供有關如何使用縮減參數的更多資訊。 |
| 主計劃 | [品項的安全庫存履行](../master-planning/safety-stock-replenishment.md)現在提供有關使用最小/最大參數的更多資訊。 |
| 主計劃 | [庫存預測](../master-planning/inventory-forecast.md)現在提供有關配置預測的更多資訊。 |
| 主計劃 | [供應排程](../master-planning/supply-schedule.md) |
| 庫存管理 | [全球行動裝置參數](../warehousing/mobile-device-parameters.md) |
| 庫存管理 | [錨定](../warehousing/anchoring.md) |
| 銷售和行銷 | 從[建立公司間貿易](../sales-marketing/intercompany-trade-set-up.md)及其相關主題開始，詳細描述公司間貿易。 |
| 庫存管理 | 從[庫存能見度增益集概觀](../inventory/inventory-visibility.md)及其相關主題開始，庫存能見度文件內容已擴充和更新。 |

## <a name="additional-resources"></a>其他資源

### <a name="platform-updates-for-finance-and-operations-apps"></a>財務和營運應用程式的平台更新

Microsoft Dynamics 365 Supply Chain Management 10.0.23 包括平台更新。 若要深入了解，請參閱[財務和營運應用程式版本 10.0.23 (2021 年 11 月) 的平台更新](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md)。

### <a name="bug-fixes"></a>錯誤修正

有關 10.0.23 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS)，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910)。

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
