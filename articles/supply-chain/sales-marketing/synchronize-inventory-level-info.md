---
title: 將 Supply Chain Management 的庫存水準資訊同步到 Field Service
description: 本主題討論用來將庫存水準資訊從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。
author: Henrikan
ms.date: 05/07/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 8dfba2d2dc2fdd4af136e3cb20061d794369011f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449805"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>將 Supply Chain Management 的庫存水準資訊同步到 Field Service 

[!include[banner](../includes/banner.md)]



本主題討論用來將庫存水準資訊從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。

[![Supply Chain Management 和 Field Service 之間的業務流程同步。](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>範本和工作
以下範本和基礎工作用於將庫存現有水準從 Supply Chain Management 同步到 Field Service。

**資料整合中的範本**
- 產品庫存 (Supply Chain Management 到 Field Service)
  
**資料整合專案中的工作**
- 產品庫存

在同步庫存水準之前，需要執行以下同步工作：
- 倉庫 (Supply Chain Management 到 Field Service) 
- 具有庫存單位的 Field Service 產品 (Supply Chain Management 到 Sales) 

## <a name="entity-set"></a>實體集

| Field Service                      | Supply Chain Management                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Dataverse 現有庫存 (按倉庫)     |

## <a name="entity-flow"></a>實體流程
Finance and Operation 的庫存水準資訊將發送到 Field Service 以獲取選定產品。 庫存水準資訊包括： 
- 現有數量 (倉庫中目前記錄的實際數量)
- 在訂單數量上 (訂單上記錄的總數量，例如銷售訂單)
- 已訂購數量上 (記錄的總訂購數量，例如採購訂單)

當庫存水準發生變化時，每個倉庫的每個已發放產品都會擷取此資訊，並根據變更追蹤同步。

在 Field Service 中，整合解決方案為增量建立庫存日記帳，以便 Field Service 中的水準與 Supply Chain Management 中的水準相相符。

Supply Chain Management 將充當庫存水準的主水準。 因此，如果在 Field Service 中使用此功能，以及從 Supply Chain Management 同步庫存水準，則必須為從 Field Service 到 Supply Chain Management 的工作訂單、轉移和調整設定整合。

從 Supply Chain Management 掌握庫存水準的產品和倉庫可以透過進階查詢和篩選 (Power Query) 進行控制。

> [!NOTE]
> 可以在 Field Services (**外部維護 = 否**) 中建立多個倉庫，然後使用進階查詢和篩選功能將它們對應到 Supply Chain Management 中的單個倉庫。 這用於您希望 Field Service 掌握詳細的庫存水準並僅將更新發送到 Supply Chain Management 的情況。 在這種情況下，Field Service 將不會從 Supply Chain Management 接收庫存水準更新。 有關其他資訊，請參閱[將庫存調整從 Field Service 同步到 Supply Chain Management](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) 和[將 Field Service 中的工作訂單與 Supply Chain Management 中連結到專案的銷售訂單同步](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)。

## <a name="field-service-crm-solution"></a>Field Service CRM 解決方案
**外部產品庫存** 實體僅用於整合的後端。 此實體從整合中的 Supply Chain Management 接收庫存水準值，然後將這些值轉換為手動庫存日記帳，然後變更倉庫中的庫存產品。

## <a name="prerequisites-and-mapping-setup"></a>先決條件和對應設定

### <a name="data-integration"></a>資料整合
要使專案正常運作，您需要確保更新 msdynce_externalproductinventories 的整合金鑰。
1.  移至 **資料整合 > 連接集**。
2.  選擇使用的連接集。
3.  在 **整合金鑰** 索引標籤中，確保將以下金鑰新增到 msdynce_externalproductinventories：
      - msdynce_productnumber (產品編號)
      - msdynce_warehouseid (倉庫識別碼)
      
### <a name="data-integration-project"></a>資料整合專案
您可以使用進階查詢和篩選套用篩選器，以僅讓某些產品和倉庫將庫存水準資訊從 Supply Chain Management 發送到 Field Service。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>產品庫存 (Supply Chain Management 到 Field Service)：產品庫存

[![資料整合中的範本對應。](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]