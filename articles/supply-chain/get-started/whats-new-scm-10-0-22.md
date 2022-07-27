---
title: Dynamics 365 Supply Chain Management 10.0.22 (2021 年 11 月) 的新增功能或變更
description: 本主題說明 Microsoft Dynamics 365 Supply Chain Management 10.0.22 中的新增功能或變更。
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a795f88aed78582ad4a2faa90ab1c2529017850f
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2021
ms.locfileid: "8449433"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10022-november-2021"></a>Dynamics 365 Supply Chain Management 10.0.22 (2021 年 11 月) 的新增功能或變更

[!include [banner](../includes/banner.md)]

本主題列出 Microsoft Dynamics 365 Supply Chain Management 版本 10.0.22 中的新增功能或變更。 此版本的版本編號為 10.0.995，可用時間如下：

- **發行預覽版：** 2021 年 9 月
- **正式發行 (自行更新)：** 2021 年 10 月
- **正式發行 (自動更新)：** 2021 年 11 月

## <a name="features-included-in-this-release"></a>此版本中包含的功能

下表列出了此版本中包含的功能。 *功能* 資料行提供[發行計劃](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)連結，您可以在其中查看每個功能的正式發行日期。 *詳細資訊* 資料行提供更多詳細資料和/或相關文件的連結。 若要決定如何打開功能，請參閱 *啟用者* 資料行。 更多有關如何使用功能管理的資訊，請參閱[功能管理概觀](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。 我們可能會更新此主題以包含在最初發佈此主題後將其納入組建的功能。

| 功能區域 | 功能 | 詳細資訊 | 啟用者   |
|---|---|---|---|
| 計劃 | [規劃最佳化支援功能型資源配置](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [根據功能排程資源選擇](../master-planning/planning-optimization/capability-based-scheduling.md) | 功能管理 (*規劃最佳化的無限產能排程*) |

## <a name="feature-enhancements-included-in-this-release"></a>此版本中包含的功能增強

下表列出了此版本中包含的功能增強。 所有增強功能都為現有功能提供了增量改善。 由於它們只是增強功能，因此未列在[發行計劃](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)中。 但是，為確保這些增強功能不會與您現有的自訂或喜好設定發生衝突，預設情況下它們都處於關閉狀態 (除非另有說明)。 如果您想使用這些功能中的任何一個，必須在[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中啟用它們。

| 模組 | 功能管理中的功能名稱 | 詳細資訊 |
|---|---|---|
| 分佈式混合拓撲 | *(不需要功能管理。)* | <p>此版本擴展了雲端和邊緣縮放單位的倉庫管理工作負載的出庫負載規劃功能。</p><p>更多資訊，請參閱[雲端和邊緣縮放單位的倉庫管理工作負載](../cloud-edge/cloud-edge-workload-warehousing.md)。</p> |
| 工程變更管理 | 產生工程產品的變型 | <p>此功能可讓您根據顏色、尺寸、樣式或設定維度為工程產品產生多個變體。</p><p>如需詳細資訊，請參閱[產生工程產品的變體](../engineering-change-management/engineering-variants.md)。</p> |
| 庫存和倉庫管理 | 庫存能見度與預留沖銷整合 | <p>只有在 *庫存能見度整合* 功能啟用後，此功能才能啟用。 它提供了沖銷在庫存能見度上進行之預留的功能。</p><p>如需詳細資訊，請參閱[庫存能見度預留](../inventory/inventory-visibility-reservations.md)。</p> |

## <a name="new-and-updated-documentation-resources"></a>新增和更新的文件資源

我們最近新增或大幅更新了以下說明主題。 這些主題不一定與為此版本新增的新功能相關，如上一節中所列。 但是，它們可能會幫助您充分利用現有功能。

| 功能區域 | 新增或更新的主題 |
|---|---|
| 工程變更管理 | [工程變更管理概觀](../engineering-change-management/product-engineering-overview.md)現已列出功能管理中可用的所有相關可選功能 |
| 主計劃 | [需求預測設定](../master-planning/demand-forecasting-setup.md) |
| 主計劃 | [具有規劃最佳化的淨需求與需求追蹤資訊](../master-planning/planning-optimization/net-requirements.md) |
| 庫存管理 | [下達到倉庫](../warehousing/release-to-warehouse-process.md)詳細概述了完整的倉庫下達流程 |

## <a name="additional-resources"></a>其他資源

### <a name="platform-updates-for-finance-and-operations-apps"></a>財務和營運應用程式的平台更新

Microsoft Dynamics 365 Supply Chain Management 10.0.22 包括平台更新。 若要深入了解，請參閱[財務和營運應用程式版本 10.0.22 (2021 年 11 月) 的平台更新](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md)。

### <a name="bug-fixes"></a>錯誤修正

有關 10.0.22 中每個更新包含的錯誤修正資訊，請登入 Lifecycle Services (LCS)，並查看[知識庫文章](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299)。

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
