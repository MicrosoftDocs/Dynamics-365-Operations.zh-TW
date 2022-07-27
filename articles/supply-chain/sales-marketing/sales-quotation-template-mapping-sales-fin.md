---
title: 將銷售報價單標題和行直接從 Sales 同步到 Supply Chain Management
description: 本主題討論用於將銷售報價單標題和行直接從 Dynamics 365 Sales 同步到 Dynamics 365 Supply Chain Management 的範本和基礎工作
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
ms.openlocfilehash: 362b6c290b1784d05e42ecb650911cc51aa8478a
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449826"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a>將銷售報價單標題和行直接從 Sales 同步到 Supply Chain Management

[!include [banner](../includes/banner.md)]



本主題討論用於將銷售報價單標題和行直接從 Dynamics 365 Sales 同步到 Dynamics 365 Supply Chain Management 的範本和基礎工作

> [!NOTE]
> 在使用 Prospect to cash 解決方案之前，您必須熟悉[將應用程式資料整合到 Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator)。

## <a name="data-flow-in-prospect-to-cash"></a>從潛在客戶到現金的資料流程

「從潛在客戶到現金」解決方案使用資料整合功能，在 Supply Chain Management 和 Sales 執行個體之間同步資料。 提供資料整合功能的「從潛在客戶到現金」範本啟用 Supply Chain Management 與 Sales 之間的帳戶、連絡人、產品、銷售報價、銷售訂單和銷售發票的資料流程。 下圖顯示了資料如何在 Supply Chain Management 和 Sales 之間同步。

[![從潛在客戶到現金中的資料流程](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>範本和工作

以下範本和基礎工作用於將銷售報價單標題和行直接從 Sales 同步到 Supply Chain Management：

- **資料整合中範本的名稱：** 銷售報價單 (Sales 到 Supply Chain Management) - 直接
- **資料整合專案中的工作名稱：**

    - QuoteHeader
    - QuoteLine

在同步銷售報價單標題和行之前，需要執行以下同步工作：

- 產品 (Supply Chain Management 到 Sales) - 直接
- 科目 (Sales 到 Supply Chain Management) - 直接 (如果使用)
- 從連絡人到客戶 (Sales 到 Supply Chain Management) - 直接 (如果使用)

## <a name="entity-set"></a>實體集

| 銷售        | Supply Chain Management     |
|--------------|----------------------------|
| 報價單       | Dataverse 銷售報價單標題 |
| QuoteDetails | Dataverse 銷售報價單行  |

## <a name="entity-flow"></a>實體流程

銷售報價單在 Sales 中建立並同步到 Supply Chain Management。

僅當滿足以下條件時，才會同步來自 Sales 的銷售報價單：

- 銷售報價單上的所有報價產品均由外部維護。
- 點選 **啟動報價** 後，銷售報價為使用中。

## <a name="prospect-to-cash-solution-for-sales"></a>從潛在客戶到現金解決方案

**僅具有外部維護的產品** 欄位已新增到 **報價** 實體來持續追蹤銷售報價單是否完全由外部維護的產品組成。 如果銷售報價單僅由外部維護的產品組成，則產品將在 Supply Chain Management 中進行維護。 此行為有助於確保您不會嘗試將具有未知產品的銷售報價單行同步到 Supply Chain Management 。

銷售報價單上的所有報價產品都使用來自銷售報價單標題的 **僅具有外部維護的產品** 資訊進行更新。 此資訊可在 **QuoteDetails** 實體上的 **報價單僅具有外部維護的產品** 欄位中找到。

可以將折扣新增到報價產品中，並將其同步到 Supply Chain Management。 標題上的 **折扣**、**費用** 和 **稅金** 欄位由 Supply Chain Management 中的設定控制。 目前，此設定不支援整合對應。 在目前的設計中，**價格**、**折扣**、**費用** 和 **稅金** 欄位在 Supply Chain Management 中維護和處理。

在 Sales 中，因為這些值未同步到 Supply Chain Management，解決方案將以下欄位設為唯讀：

- 銷售報價單標題上的唯讀欄位：**折扣 ％**、**折扣** 和 **運費**
- 報價產品的唯讀欄位：**稅金**

## <a name="preconditions-and-mapping-setup"></a>先決條件和對應設定

在同步銷售報價單之前，請務必更新以下設定。

### <a name="setup-in-sales"></a>Sales 中的設定

- 確保為 Sales 連接集中的使用者指派到的團隊設定了權限。 如果使用的示範資料，使用者通常具有管理員存取權，但團隊沒有管理員存取權。 如果團隊沒有管理員存取權，當您從資料整合執行專案時，將收到錯誤訊息，指出缺少主體團隊。

    若要為團隊設定權限，請移至 **設定** &gt; **安全** &gt; **團隊**，並選擇相關團隊。 選擇 **管理角色**，然後選擇具有所需權限的角色，例如 **系統管理員**。

- 移至 **設定** &gt; **管理** &gt; **系統設定** &gt; **Sales**，並確保使用以下設定：

    - **使用系統定價計算系統** 選項設為 **是**。
    - **折扣計算方法** 欄位設為 **明細品項**。

### <a name="setup-in-the-data-integration-project"></a>資料整合專案中的設定

#### <a name="quoteheader"></a>QuoteHeader

- 確保存在 **Shipto\_country** 到 **DeliveryAddressCountryRegionISOCode** 所需的對應。 在值對應中，您可以定義值保留空白時使用的預設值。 只需將左側保留空白，將右側設為所需的國家或地區。 這樣，您就不必為國家訂單輸入國家或地區。

    範本值是對應了多個國家或地區的值對應，其中空白值為值 **US**。

#### <a name="quoteline"></a>QuoteLine

- 確保在 Supply Chain Management 中存在所需的 **SalesUnitSymbol** 值對應。
- 確保在 Sales 中定義了所需的單位。

    為 **oumid.name** 到 **SalesUnitSymbol** 定義具有值對應的範本值。

- 選用：如果沒有來自客戶或產品的預設資訊，您可以新增以下對應以幫助確保將銷售報價單行匯入 Supply Chain Management 中：

    - **SiteId** – 在 Supply Chain Management 中產生報價單和銷售訂單行所需的站點。 **SiteId** 沒有預設範本值。
    - **WarehouseId** – 在 Supply Chain Management 中處理報價單和銷售訂單行所需的倉庫。 **WarehouseId** 沒有預設範本值。

## <a name="template-mapping-in-data-integrator"></a>機料整合器中的範本對應

> [!NOTE]
> - **折扣**、**費用** 和 **稅金** 欄位由 Supply Chain Management 中的複雜設定控制。 目前，此設定不支援整合對應。 在目前的設計中，**價格**、**折扣**、**費用** 和 **稅金** 欄位由 Supply Chain Management 處理。
> - **付款條款**、**貨運條款**、**交貨條款**、**運送方式** 和 **交貨方式** 欄位不包含在預設對應中。 若要對應這些欄位，必須設定特定於在其中同步實體之組織中的資料值對應。

下圖顯示資料整合器中的範本對應範例。

### <a name="quoteheader"></a>QuoteHeader

![機料整合器中的範本對應，QuoteHeader。](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![機料整合器中的範本對應，QuoteLine。](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>相關主題

[潛在客戶到現金](prospect-to-cash.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]