---
title: 庫存能見度增益集概觀
description: 本主題解釋什麼是庫存能見度並說明其功能。
author: yufeihuang
ms.date: 10/26/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8871d10dac9103f17780989bc547b6c20ba79b76
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449748"
---
# <a name="inventory-visibility-add-in-overview"></a>庫存能見度增益集概觀

[!include [banner](../includes/banner.md)]

庫存能見度增益集 (也稱為 *庫存能見度*) 是一個獨立且可高度調整的微服務，可實現即時庫存追蹤。 因此其中可全面檢閱庫存。

外部系統透過 RESTful API 存取服務。 這樣系統既可以查詢特定維度集的現有資訊，也可以在不同的自訂資料來源中變更您的庫存。

庫存能見度是建立在 Microsoft Dataverse 的微服務，提供了可擴展性。 您可以使用 Power Apps 建構應用程式。 您也可以套用 Power BI 提供滿足業務需求的自訂功能。

透過設定標準化庫存維度的設定選項和設定交易類型，您可以將庫存能見度與多個第三方系統整合。 庫存能見度也透過可設定的計算數量支援自訂的可擴展性。

## <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>庫存能見度與 Dynamics 365 Supply Chain Management 整合

整合式解決方案從 Dynamics 365 Supply Chain Management 取得庫存資料，並持續追蹤庫存變化。 詳細資訊請參閱[安裝和設定庫存能見度](inventory-visibility-setup.md)和[設定庫存能見度](inventory-visibility-configuration.md)。

## <a name="get-a-global-view-of-inventory"></a>全面檢閱庫存

整合式解決方案可讓您定義自己的資料來源並集中庫存資料。 如需詳細資訊，請參閱[設定庫存能見度](inventory-visibility-configuration.md)。

查看庫存的方法有兩種：

- 透過高效能 API 提交查詢。 此 API 可以直接從快取執行個體傳回近即時庫存資料。 您可以在[庫存能見度公共 API](inventory-visibility-api.md) 找到合約及範例。
- 查看原始的現有清單。 此清單定期從快取執行個體同步，並可在 Dataverse 檢視。 如需詳細資訊，請參閱[庫存能見度應用程式](inventory-visibility-power-platform.md)。

## <a name="soft-reservations"></a>軟性保留

企業必須保留特定數量的產品以支援 (例如避免過度銷售的銷售訂單履行) 時，就適用軟性保留。 在 Supply Chain Management 或其他訂單管理系統中建立並確認銷售訂單時，會向庫存能見度發送保留數量的請求。 庫存能見度允許您保留具有維度詳細資訊和特定庫存交易類型的產品。 (有關詳細資訊，請參閱[庫存能見度應用程式](inventory-visibility-power-platform.md)。) 數量成功保留後，將傳回保留識別碼。 您可以使用此保留識別碼連結回 Supply Chain Management 或其他訂單管理系統中的原始訂單。

該功能旨在使庫存能見度中的保留不會變更總數量， 而是只標記保留數量。 (因此，此功能稱為 *軟性保留*。) 在 Supply Chain Management 或第三方系統消費產品時，再次叫用 API 進行減量並更新庫存能見度中的總數量，可以抵銷軟性保留數量。 如需詳細資訊，請參閱[庫存能見度保留](inventory-visibility-reservations.md)。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
