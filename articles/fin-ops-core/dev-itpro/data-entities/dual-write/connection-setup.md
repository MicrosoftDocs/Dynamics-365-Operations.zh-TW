---
title: 雙重寫入安裝指南
description: 本主題介紹雙重寫入安裝支援的方案。
author: RamaKrishnamoorthy
ms.date: 10/12/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6de449b14bcdd82336e3e255bf62ad069d3daaf5
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460369"
---
# <a name="guidance-for-dual-write-setup"></a>雙重寫入安裝指南

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]



您可以在 Finance and Operations 環境與 Dataverse 環境之間安裝雙重寫入建立連線。

+ **Finance and Operations 環境** 為 **財務和營運應用程式** (例如 Microsoft Dynamics 365 Finance、Dynamics 365 Supply Chain Management、Dynamics 365 Commerce 和 Dynamics 365 Human Resources) 提供基礎平台。
+ **Dataverse 環境** 為 **Customer Engagement 應用程式** (Dynamics 365 Sales、Dynamics 365 Customer Service、Dynamics 365 column Service、Dynamics 365 Marketing 和 Dynamics 365 Project Service Automation) 提供基礎平台。

> [!IMPORTANT]
> Dynamics 365 Finance 中的 Human Resources 模組支援雙重寫入連線，但 Dynamics 365 Human Resources 應用程式則不提供支援。

該安裝機制會有所不同，具體取決於您的訂用帳戶和環境：

+ 對於財務和營運應用程式的新實體，雙重寫入連線的安裝從 Microsoft Dynamics Lifecycle Services (LCS) 開始。 如果您擁有 Microsoft Power Platform 的許可證，如果您的租使用者沒有，您將獲得一個新的 Dataverse 環境。
+ 對於財務和營運應用程式的現有實體，雙重寫入連線的安裝在 Finance and Operations 環境開始。

在開始對實體進行雙重寫入之前，您可以執行初始同步以處理雙方的現有資料：財務和營運應用程式和 Customer Engagement 應用程式。 如果您不必在兩個環境之間同步資料，則可以跳過初始同步。

初始同步可讓您將現有資料從一個應用程式雙向複製到另一個應用程式。 有幾種安裝方案，具體取決於您已有的環境和其中的資料類型。

支援以下安裝案例：

+ [新的財務和營運應用程式實體和新的 Customer Engagement 應用程式實體](#new-new)
+ [新的財務和營運應用程式實體和現有的 Customer Engagement 應用程式實體](#new-existing)
+ [具有資料的新財務和營運應用程式實體和新的 Customer Engagement 應用程式實體](#new-data-new)
+ [具有資料的新財務和營運應用程式實體和現有的 Customer Engagement 應用程式實體](#new-data-existing)
+ [現有的財務和營運應用程式實體和新的 Customer Engagement 應用程式實體](#existing-new)
+ [現有的財務和營運應用程式實體和現有的 Customer Engagement 應用程式實體](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a>新的財務和營運應用程式實體和新的 Customer Engagement 應用程式實體

若要在沒有資料的財務和營運應用程式的新實體和 Customer Engagement 應用程式的新實體之間安裝雙重寫入連線，請按照[Lifecycle Services 的雙重寫入安裝](lcs-setup.md)中的步驟。 連線安裝完成後，會自動執行以下操作：

- 提供了一個全新空白的 Finance and Operations 環境。
- 預配了全新空白的 Customer Engagement 應用程式實體，其中安裝了 CRM prime 解決方案。
- 為 DAT 公司資料建立雙重寫入連線。
- 啟用表對應以進行即時同步處理。

然後，兩個環境都準備好進行即時資料同步處理。

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a>新的財務和營運應用程式實體和現有的 Customer Engagement 應用程式實體

若要在沒有資料的財務和營運應用程式的新實體和 Customer Engagement 應用程式的現有實體之間安裝雙重寫入連線能力，請按照[Lifecycle Services 的雙重寫入安裝](lcs-setup.md)中的步驟。 連線安裝完成後，會自動執行以下操作：

- 提供了一個全新空白的 Finance and Operations 環境。
- 為 DAT 公司資料建立雙重寫入連線。
- 啟用表對應以進行即時同步處理。

然後，兩個環境都準備好進行即時資料同步處理。

若要將現有 Dataverse 資料同步到財務和營運應用程式，請執行以下步驟。

1. 在財務和營運應用程式中建立新公司。
2. 將公司新增到雙重寫入連線安裝中。
3. 使用三字母國際標準化組織 (ISO) 公司代碼[啟動載入](bootstrap-company-data.md) Dataverse 資料。
4. 為要同步資料的表執行 **初始同步** 功能。

如需範例和替代方法的相關連結，請參閱本主題後面的[範例](#example)章節。

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a>具有資料的新財務和營運應用程式實體和新的 Customer Engagement 應用程式實體

若要在具有資料的財務和營運應用程式的新實體和 Customer Engagement 應用程式的新實體之間安裝雙重寫入連線，請按照本主題前面的[新的財務和營運應用程式實體和新的 Customer Engagement 應用程式實體](#new-new)章節中的步驟操作。 連線安裝完成後，如果您要將資料同步到 Customer Engagement 應用程式，請按照以下步驟操作。

1. 從 LCS 頁面打開財務和營運應用程式，登入，然後進入 **登入\>雙重寫入**。
2. 為要同步資料的表執行 **初始同步** 功能。

如需範例和替代方法的相關連結，請參閱[範例](#example)章節。

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a>具有資料的新財務和營運應用程式實體和現有的 Customer Engagement 應用程式實體

若要在具有資料的財務和營運應用程式的新實體和 Customer Engagement 應用程式的現有實體之間安裝雙重寫入連線，請按照本主題前面的[新的財務和營運應用程式實體和現有的 Customer Engagement 應用程式實體](#new-existing)章節中的步驟操作。 連線安裝完成後，如果您要將資料同步到 Customer Engagement 應用程式，請按照以下步驟操作。

1. 從 LCS 頁面打開財務和營運應用程式，登入，然後進入 **登入\>雙重寫入**。
2. 為要同步資料的表執行 **初始同步** 功能。

若要將現有 Dataverse 資料同步到財務和營運應用程式，請執行以下步驟。

1. 在財務和營運應用程式中建立新公司。
2. 將公司新增到雙重寫入連線安裝中。
3. 使用三字母 ISO 公司代碼[啟動載入](bootstrap-company-data.md) Dataverse 資料。
4. 為要同步資料的表執行 **初始同步** 功能。

如需範例和替代方法的相關連結，請參閱[範例](#example)章節。

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a>現有的財務和營運應用程式實體和新的 Customer Engagement 應用程式實體

在財務和營運應用程式的現有實體和 Customer Engagement 應用程式的新實體之間的雙重寫入連線安裝發生在 Finance 和 Operation 環境中。

1. [從財務和營運應用程式安裝連線](enable-dual-write.md)。
2. 為要同步資料的表執行 **初始同步** 功能。

如需範例和替代方法的相關連結，請參閱[範例](#example)章節。

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a>現有的財務和營運應用程式實體和現有的 Customer Engagement 應用程式實體

在財務和營運應用程式的現有實體和 Customer Engagement 應用程式的現有實體之間的雙重寫入連線安裝發生在 Finance 和 Operation 環境中。

1. [從財務和營運應用程式安裝連線](enable-dual-write.md)。
2. 若要將現有 Dataverse 資料同步到財務和營運應用程式，請使用三字母 ISO 公司代碼[啟動載入](bootstrap-company-data.md) Dataverse 資料。
3. 為要同步資料的表執行 **初始同步** 功能。

如需範例和替代方法的相關連結，請參閱[範例](#example)章節。

## <a name="example"></a>範例

例如，請參閱[啟用客戶 V3 - 聯絡人表對應](enable-entity-map.md#enable-table-map)

如需基於必須執行初始同步的每個實體中的資料量的相關替代方法，請參閱[初始同步的注意事項](initial-sync-guidance.md)。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]