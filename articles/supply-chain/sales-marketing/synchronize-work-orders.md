---
title: 將具有專案的工單從 Field Service 同步到 Supply Chain Management
description: 本主題討論用來將具有專案的工單從 Dynamics 365 Field Service 同步到 Dynamics 365 Supply Chain Management 的範本和基礎工作。
author: Henrikan
ms.date: 03/12/2019
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
ms.openlocfilehash: f0b3214aba5882a585664030d6c1aebe34de455c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448533"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>將具有專案的工單從 Field Service 同步到 Supply Chain Management

[!include[banner](../includes/banner.md)]

本主題討論用來將具有專案的工單從 Dynamics 365 Field Service 同步到 Dynamics 365 Supply Chain Management 的範本和基礎工作。

[![Supply Chain Management 和 Field Service 之間的業務流程同步。](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

所用 **具有專案的工單 (Field Service 到 Supply Chain Management)** 範本是基於 **Field Service 產品 (Field Service 到 Supply Chain Management)** 範本。 有關詳細資訊，請參閱[將 Field Service 中的工單直接同步到 Supply Chain Management 中的工單](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)。

本主題僅描述兩個範本之間的差異：
- **具有專案的工單 (Field Service to Supply Chain Management)**
- **工單 (Field Service to Supply Chain Management)**

主要區別在於，此範本包括指派給 Field Service 工單的專案編號對應，確保在 Supply Chain Management 中建立的銷售訂單包含專案編號，並且可以在相關專案上開立發票。 除此之外，範本使用進階查詢和篩選。

## <a name="templates-and-tasks"></a>範本和工作

**資料整合中的範本名稱：**

- 具有專案的工單 (Field Service to Supply Chain Management)

**資料整合專案中的工作名稱：**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Field Service CRM 解決方案
**外部專案** 欄位已新增到 [工單] 實體。 此欄位是標記專案的工單的查詢和購買，銷售訂單隨後將連接到 Supply Chain Management 內的專案。 **系統狀態** 從 [打開 – 進行中(690,970,000)] 變更為更高狀態後，**外部專案** 欄位將鎖定，您將無法新增、刪除或變更值。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖顯示資料整合中的範本對應。

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>具有專案的工單 (Field Service to Supply Chain Management)：WorkOrderHeader

[![資料整合中的範本對應，具有專案的工單 (Field Service 到 Supply Chain Management)：WorkOrderHeader。](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>具有專案的工單 (Field Service to Supply Chain Management)：WorkOrderHeaderProject

[![資料整合中的範本對應，具有專案的工單 (Field Service 到 Supply Chain Management)：WorkOrderHeaderProject。](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>具有專案的工單 (Field Service to Supply Chain Management)：WorkOrderProduct

[![資料整合中的範本對應，具有專案的工單 (Field Service 到 Supply Chain Management)：WorkOrderProduct。](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>具有專案的工單 (Field Service to Supply Chain Management)：WorkOrderService

[![資料整合中的範本對應，具有專案的工單 (Field Service 到 Supply Chain Management)：WorkOrderService。](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]