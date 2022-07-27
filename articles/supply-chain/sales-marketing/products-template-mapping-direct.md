---
title: 直接將產品從 Supply Chain Management 同步到 Sales 中的產品
description: 本主題討論用來將產品從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Sales 的範本和基礎工作
author: Henrikan
ms.date: 06/10/2019
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
ms.openlocfilehash: dd84f96a5597c480648ae30b6d0274e15d750ff6
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449838"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>直接將產品從 Supply Chain Management 同步到 Sales 中的產品

[!include [banner](../includes/banner.md)]



> [!NOTE]
> 在使用 Prospect to cash 解決方案之前，您必須熟悉[將應用程式資料整合到 Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator)。

本主題討論用來將產品直接從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Sales 的範本和基礎工作。

## <a name="data-flow-in-prospect-to-cash"></a>從潛在客戶到現金的資料流程

「從潛在客戶到現金」解決方案使用資料整合功能，在 Supply Chain Management 和 Sales 執行個體之間同步資料。 具備資料整合功能的從潛在客戶到現金範本，可以在 Supply Chain Management 和 Sales 之間同步處理有關帳戶、連絡人、產品、銷售報價、銷售訂單和銷售發票的資料流程。 下圖顯示了資料如何在 Supply Chain Management 和 Sales 之間同步。

[![從潛在客戶到現金中的資料流程](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>範本和工作

若要存取可用的範本，請打開 [Power Apps 系統管理中心](https://admin.powerapps.com/dataintegration)。 選取 **專案**，然後選取右上角的 **新專案** 以選擇公用範本。

以下範本和基礎工作用來將產品從 Supply Chain Management 同步到 Sales。

- **資料整合中的範本名稱：** 產品 (Supply Chain Management 到 Sales) - 直接
- **資料整合專案中的工作名稱：** 產品

在產品同步之前不需要同步工作。

## <a name="entity-set"></a>實體集

| Supply Chain Management    | 銷售    |
|----------------------------|----------|
| 可銷售的已發布產品 | 產品 |

## <a name="entity-flow"></a>實體流程

產品在 Supply Chain Management 中管理並同步到 Sales。 Supply Chain Management 中 **可銷售的已發佈產品** 資料實體只會導出 *可銷售* 的產品。 可銷售產品是指具有用於銷售訂單所需資訊的產品。 當產品使用 **已發佈產品** 頁面的 **驗證** 功能進行驗證時，適用於相同規則。

產品編號作為金鑰使用。 因此，當產品變型同步到 Sales 時，每個產品變型都會有單獨的產品識別碼。

## <a name="prospect-to-cash-solution-for-sales"></a>從潛在客戶到現金解決方案

在 Sales 中，新的 **外部維護** 欄位已新增到產品中，以表示某些產品是在外面進行維護。 根據預設，在匯入到 Sales 期間，該值設定為 **是**。 以下是可供使用的值：

- **是** – 產品源自 Supply Chain Management，無法在 Sales 中進行編輯。
- **否** – 產品直接輸入到 Sales 中。
- **(空白)** – 在啟用「從潛在客戶到現金」解決方案之前，產品存在於 Sales。

**外部維護** 欄位可以確保只有具有外部維護產品的報價和銷售訂單才會同步到 Supply Chain Management。

外部維護的產品會自動金曾到擁有相同貨幣的第一個有效價目表中。 價目表按名稱的字母順序排列。 Supply Chain Management 中的產品銷售價格用作價目表上的價格。 因此，Supply Chain Management 中的每個產品銷售幣種在 Sales 中都必須有一個價目表。 已下達的可銷售產品的幣種設為產品出口所在法人的記帳幣種。

> [!NOTE]
> - 除非存在具備相符貨幣的價目表，否則產品同步不會成功。
> - 您可以透過將資料整合專案中的 pricelevelid.name [預設價目表 (名稱)] 來控制使用的價目表。 輸入內容必須全部為小寫字母。 例如，Sales 中名為「Standard」的價目表預設值為：目的地欄位：pricelevelid.name [預設價目表 (名稱)] 和地圖類型：[ { "transformType": "Default", "defaultValue": "standard" } ]。

## <a name="preconditions-and-mapping-setup"></a>先決條件和對應設定

- 在首次執行同步之前，您必須為 Supply Chain Management 中的現有產品填寫獨特產品表格。 在此作業完成之前，現有產品不會進行同步。

    1. 在 Supply Chain Management 中，使用搜尋來搜尋 **填充獨特產品表格**。
    2. 選擇 **填充獨特產品表格** 以執行作業。 這項作業只能執行一次。

- 確保 **SalesUnitSymbol** 到 **DefaultUnit (Name)** 的對應中具有 Supply Chain Management 和 Sales 之間的銷售測量單位 (UOM) 所需的值。
- 更新 **單位群組** (**defaultuomscheduleid.name**) 的值對應，使值對應與 Sales 中的 **單位群組** 相同。

    預設範本值為 **Default unit**。

- 確保 Sales 中存在 Supply Chain Management 中所有產品的銷售 UOM。
- 確保，Supply Chain Management 中的每個產品銷售幣種在 Sales 中都有價目表。
- 在 Sales 中建立產品時，產品狀態可為 **草稿** 或 **使用中**。 行為是在 Sales 的 **設定** > **管理** > **系統設定** > **Sales** 中進行控制。

    狀態為 **草稿** 的產品必須先啟用，才能將這些產品新增到報價單或銷售訂單中。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖為資料整合的範本對應範例。 

> [!NOTE]
> 對應顯示哪些欄資訊將從 Sales 同步到 Supply Chain Management。

![資料整合中的範本對應](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>相關主題

[潛在客戶到現金](prospect-to-cash.md)

[直接將帳戶從 Sales 同步到 Supply Chain Management 中的客戶](accounts-template-mapping-direct.md)

[直接將連絡人從 Sales 同步到 Supply Chain Management 中的連絡人或客戶](contacts-template-mapping-direct.md)

[直接在 Sales 和 Supply Chain Management 之間同步銷售訂單](sales-order-template-mapping-direct-two-ways.md)

[將銷售發票抬頭和明細直接從 Supply Chain Management 同步到 Sales](sales-invoice-template-mapping-direct.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]