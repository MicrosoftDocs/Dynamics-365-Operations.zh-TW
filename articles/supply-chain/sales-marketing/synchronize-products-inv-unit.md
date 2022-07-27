---
title: 將具有庫存單位的產品從 Supply Chain Management 同步到 Field Service
description: 本主題討論用來將具有庫存單位的產品從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。
author: Henrikan
ms.date: 03/13/2019
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
ms.openlocfilehash: 6ac346d735bc44e9f9660c60b23a73057e4b7306
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447912"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>將具有庫存單位的產品從 Supply Chain Management 同步到 Field Service

[!include[banner](../includes/banner.md)]

本主題討論用來將具有庫存單位的產品從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。

[![Supply Chain Management 和 Field Service 之間的業務流程同步。](./media/FSProductsOW.png)](./media/FSProductsOW.png)

所用 **具有庫存單位的 Field Service 產品 (Supply Chain Management 到 Field Service)** 範本是基於 **Field Service 產品 (Supply Chain Management 到 Field Service)** 範本。 有關詳細資訊，請參閱[將 Supply Chain Management 中的產品直接同步到 Field Service 中的產品](field-service-product.md)。

本主題僅描述兩個範本之間的差異： 
- **具有庫存單位的 Field Service 產品 (Supply Chain Management 到 Sales)**
- **Field Service 產品 (Supply Chain Management 到 Field Service)** 

## <a name="templates-and-tasks"></a>範本和工作

**資料整合中的範本名稱：**

- 具有庫存單位的 Field Service 產品 (Supply Chain Management 到 Sales)

**資料整合專案中的工作名稱：**

- 產品

**具有庫存單位的 Field Service 產品 (Supply Chain Management 到 Field Service)** 範本中包含 **Field Service 產品 (Supply Chain Management 到 Field Service)** 範本中不包含的一個對應。 此對應確保包含庫存水準同步所需的庫存單位。

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖顯示資料整合中的範本對應。

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>具有庫存單位的 Field Service 產品 (Supply Chain Management 到 Field Service)：產品

[![資料整合中的範本對應。](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]