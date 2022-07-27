---
title: 將銷售發票抬頭和明細直接從 Supply Chain Management 同步到 Sales
description: 本主題討論用於將銷售發票抬頭和明細直接從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Sales 的範本和基礎工作
author: Henrikan
ms.date: 10/26/2017
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
ms.openlocfilehash: c2f988b4f170c027444ba7cf54a55e0bd846cedf
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448440"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>將銷售發票抬頭和明細直接從「財務和營運」同步到 Sales

[!include [banner](../includes/banner.md)]

本主題討論用於將銷售發票抬頭和明細直接從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Sales 的範本和基礎工作

## <a name="data-flow-in-prospect-to-cash"></a>從潛在客戶到現金的資料流程

「從潛在客戶到現金」解決方案使用資料整合功能，在 Supply Chain Management 和 Sales 執行個體之間同步資料。 具備資料整合功能的從潛在客戶到現金範本，可以在 Supply Chain Management 和 Sales 之間同步處理有關帳戶、連絡人、產品、銷售報價、銷售訂單和銷售發票的資料流程。 下圖顯示了資料如何在 Supply Chain Management 和 Sales 之間同步。

[![從潛在客戶到現金中的資料流程](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>範本和工作

若要存取可用的範本，請打開 [Power Apps 系統管理中心](https://preview.admin.powerapps.com/dataintegration)。 選取 **專案**，然後選取右上角的 **新專案** 以選擇公用範本。

以下範本和基礎工作用於將銷售發票抬頭和明細從 Supply Chain Management 同步到 Sales：

- **資料整合中的範本名稱：** 銷售發票 (Fin and Ops 到 Sales) - 直接
- **資料整合專案中的工作名稱：**

    - SalesInvoiceHeader
    - SalesInvoiceLine

在同步銷售發票抬頭和明細之前，需要執明細以下同步工作：

- 產品 (Supply Chain Management 到 Sales) - 直接
- 科目 (Sales 到 Supply Chain Management) - 直接 (如果使用)
- 連絡人 (Sales 到 Supply Chain Management) - 直接 (如果使用)
- 銷售訂單抬頭和明細 (Supply Chain Management 到 Sales) - 直接

## <a name="entity-set"></a>實體集

| Supply Chain Management                              | 銷售          |
|------------------------------------------------------|----------------|
| 外部維護的客戶銷售發票抬頭 | 發票       |
| 外部維護的客戶銷售發票明細   | InvoiceDetails |

## <a name="entity-flow"></a>實體流程

銷售發票在 Supply Chain Management 中建立並同步到 Sales。

> [!NOTE]
> 目前，與銷售發票抬頭費用相關的稅款不包括在從 Supply Chain Managements 到 Sales 的同步中。 Sales 不支援抬頭等級的稅務資訊。 但是，與明細等級費用相關的稅費包含在同步中。

## <a name="prospect-to-cash-solution-for-sales"></a>從潛在客戶到現金解決方案

- **發票編號** 欄位已新增到 **發票** 實體並顯示在頁面上。
- **銷售訂單** 頁面上的 **建立發票** 按鈕已隱藏，因為發票將在 Supply Chain Management 中建立並同步到 Sales。 無法編輯 **發票** 頁面，因為發票將從 Supply Chain Management 同步。
- 當相關發票從 Supply Chain Management 同步到 Sales 後，**銷售訂單狀態** 值會自動變更為 **已開立發票**。 此外，建立發票之銷售訂單的擁有者被指定為發票的擁有者。 因此，銷售訂單的擁有者可以查看發票。

## <a name="preconditions-and-mapping-setup"></a>先決條件和對應設定

在同步銷售發票之前，請務必更新系統中的以下設定。

### <a name="setup-in-sales"></a>Sales 中的設定

移至 **設定** > **管理** > **系統設定** > **Sales**，並確保使用以下設定：

- **使用系統定價計算系統** 選項設為 **是**。
- **折扣計算方法** 欄位設為 **明細品項**。

### <a name="setup-in-the-data-integration-project"></a>資料整合專案中的設定

#### <a name="salesinvoiceheader-task"></a>SalesInvoiceHeader 工作

- 確保存在所需的 **InvoiceCountryRegionId** 到 **BillingAddress\_Country** 的對應。

    範本值是對應了多個國家或地區的值對應。

- 需要價目表才能在 Sales 中建立發票。 將 **pricelevelid.name\[價目表名稱\]** 的值對應依貨幣更新至 Sales 中使用的價目表。 您可以為單一貨幣使用預設價目表。 或者，如果您的價目表有多種貨幣，則可以使用值對應。

    **pricelevelid.name\[價目表名稱\]** 的範本值是根據具有「USD = 美國 CRM 服務 (範例)」之貨幣的值對應。  
    
#### <a name="salesinvoiceline-task"></a>SalesInvoiceLine 工作

- 確保存在所需 **測量單位** 的對應。
- 確保在 Supply Chain Management 中存在所需的 **SalesUnitSymbol** 值對應。

    為  **SalesUnitSymbol** 到 **Quantity\_UOM** 定義具有值對應的範本值。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

> [!NOTE]
> **付款條款**、**貨運條款**、**交貨條款**、**運送方式** 和 **交貨方式** 欄位不包含在預設對應中。 若要對應這些欄位，必須設定特定於在其中同步實體之組織中的資料值對應。

下圖顯示資料整合中的範本對應範例。 

> [!NOTE]
> 對應顯示哪些欄資訊將從 Sales 同步到 Supply Chain Management。

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![SalesInvoiceHeader 的資料整合中的範本對應。](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![SalesInvoiceLine 的資料整合中的範本對應。](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>相關主題

[潛在客戶到現金](prospect-to-cash.md)

[直接將帳戶從 Sales 同步到 Supply Chain Management 中的客戶](accounts-template-mapping-direct.md)

[將產品直接從 Supply Chain Management 同步到 Sales 中的產品](products-template-mapping-direct.md)

[直接將連絡人從 Sales 同步到 Supply Chain Management 中的連絡人或客戶](contacts-template-mapping-direct.md)

[直接在 Sales 和 Supply Chain Management 之間同步銷售訂單](sales-order-template-mapping-direct-two-ways.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]