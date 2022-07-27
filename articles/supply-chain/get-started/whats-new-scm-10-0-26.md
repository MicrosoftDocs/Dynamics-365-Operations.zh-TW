---
title: Dynamics 365 Supply Chain Management 10.0.26 預覽版 (2022 年 5 月)
description: 本主題說明 Microsoft Dynamics 365 Supply Chain Management 10.0.26 中的新增功能或變更。
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: fae25eb1cb9dd4059b9d49e47cbb0060e717c9bc
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2022
ms.locfileid: "8450087"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10026-may-2022"></a>Dynamics 365 Supply Chain Management 10.0.26 預覽版 (2022 年 5 月)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

本主題列出 Microsoft Dynamics 365 Supply Chain Management 預覽版 10.0.26 中的新增功能或變更。 此版本的版本編號為 10.0.1192，可用時間如下：

- **發行預覽版**：2022 年 3 月
- **正式發行 (自行更新) ：** 2022 年 4 月
- **正式發行 (自動更新) ：** 2022 年 5 月

## <a name="features-included-in-this-release"></a>此版本中包含的功能

下表列出了此版本中包含的功能。 我們可能會更新此主題以包含在最初發佈此主題後將其納入組建的功能。

| 功能區域 | 功能 | 詳細資訊 | 啟用者   |
|---|---|---|---|
| 庫存和物流 | [庫存能見度現有查詢，支援進階倉庫管理品項](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | 即將推出 | 功能管理：<br>*在庫存能見度中啟用倉庫品項* |
| 庫存和物流 | [庫存能見度增益集的可承諾量](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | 即將推出 | 由服務設定啟用 |
| 製造 | [生產現場執行介面的實秤重量品項](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [工作人員該如何使用生產現場執行介面](../production-control/production-floor-execution-use.md) | 功能管理：<br>*（預覽版）從生產現場執行介面報告實秤重量品項* |
| 製造 | 生產現場執行介面的 [我的作業索引標籤] <!-- KFM: Add link to release plan when available --> | [工作人員該如何使用生產現場執行介面](../production-control/production-floor-execution-use.md) | 功能管理：<br>*生產現場執行介面的 [我的作業索引標籤]* |

## <a name="feature-enhancements-included-in-this-release"></a>此版本中包含的功能增強

下表列出了此版本中包含的功能增強。 所有增強功能都為現有功能提供了增量改善。 由於它們只是增強功能，因此未列在[發行計劃](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features)中。 但是，為確保這些增強功能不會與您現有的自訂或喜好設定發生衝突，預設情況下它們都處於關閉狀態 (除非另有說明)。

如果您想開啟或關閉這些功能，必須在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中進行作業。

| 模組 | 功能管理中的功能名稱 | 詳細資訊 |
|---|---|---|
| 採購和資源開發 | 為收據和廠商發票過帳已登記的庫存產品和無庫存產品的剩餘數量 | 此功能改變了在處理廠商發票和針對訂購單的入庫裝運時過帳無庫存產品 (例如服務) 數量的方式。 該功能修改了用於過帳收據和廠商發票的 *已登記數量和服務* 數量選項的行為，方法是將其變更為與過帳銷售裝箱單數量時已提供的 *已登記數量和無庫存產品* 選項的行為相配對。<br><br>當您使用 *已登記數量和服務* 數量選項過帳產品收據或廠商發票時，系統會過帳已登記的庫存產品數量並過帳剩餘的無庫存產品數量 (包括服務和非服務)。 如果沒有此功能，系統仍會過帳已登記的庫存產品數量 (包括設定為庫存品項的服務)，但一律過帳無庫存服務產品的全部訂購數量 (並忽略非 *服務* 類型的無庫存產品)。 |
| 採購和資源開發 | 同步公司間銷售和訂購單行上的追蹤維度 | 此功能可讓您控制是否跨公司間銷售和訂購單行同步序號和批次編號追蹤維度。 它為客戶和廠商的 **公司間** 設定頁面的 **訂購單原則** 和 **銷售訂單原則** 索引標籤新增了新設定。 為了清楚起見，它還更新了一些附近的相關設定名稱。<br><br>請注意，如果您使用的是進階倉庫管理 (WMS)，那麼只有當這些維度高於目標目的地預留層次結構中的位置時，此功能才會同步批次和序號。 |
| 產品資訊管理 | 清理產品屬性值 | 此功能新增了名為 **清理產品屬性值** 的週期性工作，其透過產品類別清理不再與任何產品關聯的產品屬性值記錄。 |
| 庫存和倉庫管理 | (俄羅斯) 為包含啟用 WMS 品項的訂購單簽發 GTD 時防止出現不一致 | 此功能僅適用於俄文當地語系化。 它可以防止在為包含啟用進階倉儲 (WMS) 品項的進口訂購單簽發俄羅斯海關申報編號 (GTD) 時出現不一致。 GTD 開立流程改變了自訂日記帳中包含的發票相關庫存交易上的一些庫存維度值，這導致訂購單的工作記錄與採購的庫存交易記錄之間出現不一致。 啟用此功能後，GTD 開立流程會產生調整工作以消除此類不一致。 |
| 庫存管理 | GS1 條碼的增強剖析器 | 此功能為 GS1 符號資料新增了增強剖析器。 新的剖析器實現了 GS1 通用規格演算法來解析 GS1 符號並提供更強大的資料驗證。 |
| 庫存管理 | 新的負載規劃工作台頁面 | 新增兩個新的負載規劃工作台頁面：**入庫負載規劃工作台** 和 **出庫負載規劃工作台**。 |
| 庫存管理 | Warehouse Management 應用程式 - 空白 GTD | 此功能僅適用於俄文當地語系化。 它可讓使用 Warehouse Management 行動應用程式的工人在需要時將俄羅斯海關申報編號 (GTD) 留空。 如果 GTD 追蹤維度設定為允許空白值，則系統將接受用於庫存工序的 GTD 的空白值，前提是現有庫存可用。 |

## <a name="new-and-updated-documentation-resources"></a>新增和更新的文件資源

我們最近新增或大幅更新了以下說明主題。 這些主題不一定與為此版本新增的新功能相關，如上幾節中所列。 但是，它們可能會幫助您充分利用現有功能。

| 功能區域 | 新增或更新的主題 |
|---|---|
| 成本管理 | 以下每個主題都新增了更新的範例和圖表：<ul><li>[具有實際成本和標記的先進先出方法](../cost-management/fifo-physical-value-marking.md)</li><li>[具有實際成本和標記的後進先出方法](../cost-management/lifo-physical-value-marking.md)</li><li>[具有實際成本和標記的後進先出日期](../cost-management/lifo-date-physical-value-marking.md)</li><li>[移動平均成本價](../cost-management/running-average-cost-price.md)</li><li>[具有實際成本和標記的加權平均](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |
| 採購和資源開發 | [訂購單行資料差異](../troubleshooting/procurement/purchase-order-line-data-issues.md) |

## <a name="additional-resources"></a>其他資源

### <a name="platform-updates-for-finance-and-operations-apps"></a>財務和營運應用程式的平台更新

Microsoft Dynamics 365 Supply Chain Management 10.0.26 包括平台更新。 若要深入了解，請參閱[財務和營運應用程式版本 10.0.26 (2022 年 5 月) 的平台更新](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md)。<!-- KFM Confirm link -->

### <a name="bug-fixes"></a>錯誤修正

有關 10.0.26 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS) ，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864)。

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
