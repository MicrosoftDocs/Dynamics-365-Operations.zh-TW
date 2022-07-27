---
title: 庫存能見度提示
description: 本主題提供了一些提示，您在設定和使用庫存能見度增益集時應考慮這些提示。
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1f6ade36ac184a3c8bf790fc0d899ea01d90c8d2
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2022
ms.locfileid: "8449613"
---
# <a name="inventory-visibility-tips"></a>庫存能見度提示

[!include [banner](../includes/banner.md)]

以下提供了一些提示，您在設定和使用庫存能見度增益集時應考慮這些提示：

- 目前庫存能見度增益集僅支援以 Microsoft Dynamics Lifecycle Services (LCS) 建立的 Microsoft Dataverse 環境。 如果您的 Dataverse 環境是以其他方式建立 (例如使用 Power Apps 系統管理中心)，且如果該環境連結到您的 Dynamics 365 Supply Chain Management 環境，您首先必須要求庫存能見度產品團隊修復對應問題。 您可透過以下方式聯繫團隊：[inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com)。 您的環境準備好安裝庫存能見度時，該團隊會通知您。
- 如果您有多個 LCS 環境，請為每個環境建立一個不同的 Azure Active Directory (Azure AD) 應用程式。 如果您使用相同的應用程式識別碼和租用戶識別碼為不同的環境安裝庫存能見度增益集，則舊環境會出現權杖問題。 只有最後安裝的庫存能見度增益集執行個體有效。
- 庫存能見度目前不支援雲端託管環境， 僅支援第 2 層或更高層環境。
- 應用程式開發介面 (API) 目前支援透過 `ProductID` 值查詢多達 100 項個別項目。 每個查詢中也可以指定多項 `SiteID` 和 `LocationID`。 最大限制定義為 `NumOf(SiteID) * NumOf(LocationID) <= 100`。
- 批量 API 最多可為每個要求傳回 512 條記錄。
- `fno` 資料來源保留用於 Supply Chain Management。 如果您的庫存能見度增益集與 Supply Chain Management 環境整合，我們建議您不要刪除與[資料來源](inventory-visibility-configuration.md#data-source-configuration)中 `fno` 有關的設定。
- 庫存能見度不能變更 `fno` 資料來源的任何資料。 資料流程是單向的，這意味著 `fno` 資料來源的所有數量變更，必須來自您的 Supply Chain Management 環境。 因此，您不能使用 API 為 `fno` 資料來源傳送現有變更或保留要求。
- 如果您將一項或多項新措施新增到您的 Supply Chain Management 環境，您還應該將它們新增到庫存能見度中。 但是，新措施的所有數量變更都必須來自您的 Supply Chain Management 環境。
- [分割區設定](inventory-visibility-configuration.md#partition-configuration)目前由兩個基本維度組成 (`SiteId` 和 `LocationId`)，表示資料的分佈方式。 同一分割區下的作業能以更低成本提供更高效能。 解決方案預設包含此分割區設定。 因此 *您不必自己定義*。 不要自訂預設分割區設定。 如果您刪除或變更它，可能會導致意外錯誤。
- 分割區設定中定義的基本維度，不應在[產品索引階層設定](inventory-visibility-configuration.md#index-configuration)中定義。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
