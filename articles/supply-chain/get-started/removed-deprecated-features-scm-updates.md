---
title: Dynamics 365 Supply Chain Management 中已移除或已取代的功能
description: 本主題說明 Dynamics 365 Supply Chain Management 中已移除或計畫移除的功能。
author: kamaybac
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: e7350e697beec42b349082df06b77a89d526c27c
ms.sourcegitcommit: ddcab9726e9dbcf3296cb0988b97a3ae7ccb3dfb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2022
ms.locfileid: "8450111"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 中已移除或已取代的功能

[!include [banner](../includes/banner.md)]

本主題將隨著新刪除或取代的功能而更新 Dynamics 365 Supply Chain Management 文件。

- *已移除* 功能不再於產品中提供該功能。
- *已取代* 功能未進行開發，可能會在未來的更新中移除。

此清單旨在幫助您在您自己的計劃中考慮這些功能的移除和棄用。

> [!NOTE]
> 有關財務和營運應用程式中對象的詳細資訊，可在[技術參考報告](/dynamics/s-e/)中找到。 您可以比較這些不同版本的報告，以了解每個版本的財務和營運應用程式中已更改或移除的對象。


## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10019-release"></a>Supply Chain Management 10.0.19 版本中已移除或取代的功能

### <a name="job-card-device"></a>工作卡裝置

| &nbsp;  | &nbsp;  |
|---|---|
| **棄用/移除的原因** | [工作卡裝置](../production-control/config-job-card-device.md)正被新的[生產現場執行界面](../production-control/production-floor-execution-configure.md)取代。 |
| **被其他功能取代？**   | 是，[工作卡裝置](../production-control/config-job-card-device.md)將被新的[生產現場執行界面](../production-control/production-floor-execution-configure.md)取代。 |
| **受影響的產品領域** | Supply Chain Management - 生產控制 |
| **部署選項** | 雲端和內部部署 |
| **狀態** | 已取代。 工作卡裝置將獲得錯誤和安全修復支援，但將不再提供功能增強。 2022 年 4 月之後，將不再支援工作卡裝置，並要求客戶移到新的生產現場執行界面。 |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Supply Chain Management 10.0.18 版本中已移除或取代的功能

### <a name="dynamics-365-for-finance-and-operations---warehousing-the-warehouse-app"></a>Dynamics 365 for Finance and Operations - 倉庫 (倉庫應用程式)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 自 2021 年 4 月起生效，*Dynamics 365 for Finance and Operations - 倉庫* (倉庫應用程式) 已棄用，2022 年 4 月後將不再受支援。 它現在將由 *Warehouse Management 行動應用程式* 取代，其隨 Supply Chain Management 10.0.17 版本一起發佈。 新應用程式是一個完整的替代品，但使用相同的基礎框架，這使得移轉變得容易。 如果需要，這兩個應用程式可以並排使用，以幫助使用者在學習使用新應用程式時逐漸習慣。<br><br>有關新 Warehouse Management 行動應用程式的詳細資訊，請參閱[Warehouse Management 行動應用程式](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application)，以及[安裝並連線 Warehouse Management 行動應用程式](../warehousing/install-configure-warehouse-management-app.md)。 |
| **被其他功能取代？**   | 是，已由新的 Warehouse Management 行動應用程式取代。 |
| **受影響的產品領域**         | Supply Chain Management - 倉庫應用程式 |
| **部署選項**              | 雲端和內部部署 |
| **狀態**                         | 已取代。 倉庫應用程式將獲得錯誤和安全修復支援，但將不再提供功能增強。 2022 年 4 月之後，將不再支援舊版倉庫應用程式，並要求客戶移到新的 Warehouse Management 行動應用程式。 然後，將從 Microsoft Store 和 Google Play 商店中刪除舊版倉庫應用程式。  |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Supply Chain Management 10.0.15 版本中已移除或取代的功能

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>已棄用 Dynamics 365 的 Internet Explorer 11 支援

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 自 2020 年 12 月起，所有 Dynamics 365 產品 的 Microsoft Internet Explorer 11 支援已棄用，並且 2021 年 8 月之後將不再支援 Internet Explorer 11。<br><br>這將影響使用旨在透過 Internet Explorer 11 界面使用的 Dynamics 365 產品的客戶。 2021 年 8 月之後，此類 Dynamics 365 產品將不再支援 Internet Explorer 11。 |
| **被其他功能取代？**   | 我們建議客戶轉換到 Microsoft Edge。|
| **受影響的產品領域**         | 所有 Dynamics 365 產品 |
| **部署選項**              | 全部|
| **狀態**                         | 已取代。 2021 年 8 月之後將不再支援 Internet Explorer 11。|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>將內建的 Supply Chain Management 總體規劃引擎用於製造案例

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 為了在主計劃執行期間提高性能並盡可能減小 SQL 資料庫負載，「規劃最佳化」已取代內建的 Supply Chain Management 總體規劃引擎。 利用「規劃最佳化」，即使在辦公時間也可以執行快速執行計劃。 這使計劃人員可以立即對需求或計劃參數的變化做出反應。 |
| **被其他功能取代？**   | 是的，「規劃最佳化」將取代現有內建的 Supply Chain Management 總體規劃引擎。 |
| **受影響的產品領域**         | Supply Chain Management - 總體規劃 |
| **部署選項**              | 僅限雲端。 「規劃最佳化」不支援內部部署。 |
| **狀態**                         | 已取代。 2022 年 4 月 1 日之後，內建 Supply Chain Management 總體規劃引擎將不再支援製造案例。 自該日期起，Microsoft 將停止針對內建規劃引擎的製造案例的所有開發，不會發佈任何新功能，只會發佈關鍵錯誤修正。 在該日期之後，所有需要製造案例支援的公司都必須使用「規劃最佳化」進行總體規劃計算。 「規劃最佳化」預計將在 2022 年 10 月之前全面支援製造案例。 有關詳細資訊，請參閱[規劃最佳化文件](../master-planning/planning-optimization/planning-optimization-overview.md)。<br><br>在 2022 年 4 月之後，內部部署 Supply Chain Management 的公司可以繼續使用內建總體規劃引擎來處理製造案例。 但是，將不再提供其他的功能增強。 |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Supply Chain Management 10.0.11 版本中已移除或取代的功能

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>將內建的 Supply Chain Management 總體規劃引擎用於分配案例

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **棄用/移除的原因** | 為了在主計劃執行期間提高性能並盡可能減小 SQL 資料庫負載，「規劃最佳化」已取代內建的 Supply Chain Management 總體規劃引擎。 利用「規劃最佳化」，即使在辦公時間也可以執行快速執行計劃。 這使計劃人員可以立即對需求或計劃參數的變化做出反應。 |
| **被其他功能取代？**   | 是的，「規劃最佳化」將取代現有內建的 Supply Chain Management 總體規劃引擎。 |
| **受影響的產品領域**         | Supply Chain Management - 總體規劃 |
| **部署選項**              | 僅限雲端。 「規劃最佳化」不支援內部部署。 |
| **狀態**                         | 已取代。 2021 年 4 月 1 日之後，內建 Dynamics 365 Supply Chain Management 總體規劃引擎將不再支援分配案例。 對於分配方案，客戶必須使用「規劃最佳化」進行總體規劃計算。 有關詳細資訊，請參閱[規劃最佳化文件](../master-planning/planning-optimization/planning-optimization-overview.md)。 在 2021 年 4 月之後，內部部署 Dynamics 365 Supply Chain Management 的客戶可以繼續使用 Supply Chain Management 總體規劃引擎來處理分配案例。 但是，將不再提供其他的功能增強。 |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>先前關於已移除或棄用功能的公告

若要進一步了解先前版本中已刪除或棄用的功能，請參閱[以前版本中刪除或棄用的功能](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
