---
title: 直接從 Sales 的客戶同步到 Supply Chain Management 中的客戶
description: 本主題討論用來將客戶從 Dynamics 365 Sales 同步到 Supply Chain Management 的範本和基礎工作
author: Henrikan
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b3257f4582ede6cd1be8e593a5ed99f5ffd0ca6f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449856"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>直接從 Sales 的客戶同步到 Supply Chain Management 中的客戶

[!include [banner](../includes/banner.md)]



> [!NOTE]
> 在使用 Prospect to cash 解決方案之前，您必須熟悉[將應用程式資料整合到 Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator)。

本主題討論用來將客戶直接從 Dynamics 365 Sales 同步到 Dynamics 365 Supply Chain Management 的範本和基礎工作

## <a name="data-flow-in-prospect-to-cash"></a>從潛在客戶到現金的資料流程

「從潛在客戶到現金」解決方案使用資料整合功能，在 Supply Chain Management 和 Sales 執行個體之間同步資料。  具備資料整合功能的從潛在客戶到現金範本，可以在 Supply Chain Management 和 Sales 之間同步處理有關帳戶、連絡人、產品、銷售報價、銷售訂單和銷售發票的資料流程。 下圖顯示了資料如何在 Supply Chain Management 和 Sales 之間同步。

[![從潛在客戶到現金中的資料流程](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>範本和工作

若要存取可用的範本，請打開 [Power Apps 系統管理中心](https://preview.admin.powerapps.com/dataintegration)。 選取 **專案**，然後選取右上角的 **新專案** 以選擇公用範本。

以下範本和基礎工作用來將客戶從 Sales 同步到 Supply Chain Management：

- **資料整合中的範本名稱：** 客戶 (Sales 到 Fin 及 Ops) - 直接
- **專案中的工作名稱：** 帳號 - 客戶

在帳戶/客戶同步之前不需要同步工作。

## <a name="entity-set"></a>實體集

| 銷售    | Supply Chain Management |
|----------|------------------------|
| 帳戶 | 客戶 V2           |

## <a name="entity-flow"></a>實體流程

在 Sales 中管理的客戶並同步成 Supply Chain Management 中的客戶 這些客戶的 **外部維護** 屬性設定為 **是的** 以追蹤來自 Sales 的客戶。 在開票期間，此資訊用於篩選同步到 Sales 的發票。

## <a name="prospect-to-cash-solution-for-sales"></a>從潛在客戶到現金解決方案

在 **客戶** 頁面，**客戶編號** 欄可以使用。 為了支援整合，它已成為自然且獨特的金鑰。 客戶關係管理 (CRM) 解決方案的自然金鑰功能可能會影響已經使用 **客戶編號** 欄，但仍不使用唯一的每個帳戶 **帳號編號** 值的客戶。 目前，整合解決方案不支持這種情況。

建立新客戶時，如果 **客戶編號** 值不存在，它會使用數字序列自動生成。 該值包括 **ACC**，後跟一個遞增的數字序列，然後後綴六個字符。 這是一個例子：**ACC-01000-BVRCPS**

套用 Sales 的整合解決方案時，升級腳本會在 Sales 中為現有客戶設定 **客戶編號** 欄。 如果沒有 **帳號編號** 值，使用前面提到的數字序列。

## <a name="preconditions-and-mapping-setup"></a>先決條件和對應設定

- **CustomerGroupId** 對應必須更新為 Supply Chain Management 中的有效值。 您可以指定預設值，也可以使用對應值來設定。

    預設範本值為 **10**。

- 通過新增以下動應，有助於減少 Supply Chain Management 中需要手動更新數量。 您可以使用預設值或從 **國家/地區** 或 **城市** 等對應值。

    - **SiteId** – 在 Supply Chain Management 中產生報價單和銷售訂單行所需的站點。 可以從產品中獲取預設站點，也可以從訂單標頭中的客戶獲取預設站點。

        預設範本值為 **1**。

    - **WarehouseId** – 在 Supply Chain Management 中處理報價單和銷售訂單行所需的倉庫。 可以從產品中獲取預設倉庫，也可以在 Supply Chain Management 訂單標頭中的客戶獲取預設倉庫。

        預設範本值為 **13**。

    - **LanguageId** – 用來在 Supply Chain Management 中產生報價單和銷售訂單明細的必要語言。 預設情況下，使用來自客戶的訂單標頭中的語言。

        預設範本值為 **en-us**。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

> [!NOTE]
> **付款條款**、**貨運條款**、**交貨條款**、**運送方式** 和 **交貨方式** 欄不包含在預設對應中。 若要對應這些資料行，必須設定特定於在其中同步資料表之組織中的資料值對應。

下圖顯示資料整合中的範本對應範例。 

> [!NOTE]
> 對應顯示哪些欄的資訊將從 Sales 同步到 Supply Chain Management。

![資料整合中的範本對應。](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>相關主題


[潛在客戶到現金](prospect-to-cash.md)

[直接將帳戶從 Sales 同步到 Supply Chain Management 中的客戶](accounts-template-mapping-direct.md)

[直接將連絡人從 Sales 同步到 Supply Chain Management 中的連絡人或客戶](contacts-template-mapping-direct.md)

[直接在 Sales 和 Supply Chain Management 之間同步銷售訂單](sales-order-template-mapping-direct-two-ways.md)

[將銷售發票抬頭和明細直接從 Supply Chain Management 同步到 Sales](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]