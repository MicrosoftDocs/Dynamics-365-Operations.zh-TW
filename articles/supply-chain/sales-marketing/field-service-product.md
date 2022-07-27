---
title: 將產品從 Supply Chain Management 同步到 Field Service 中
description: 本主題討論用來將產品從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。
author: Henrikan
ms.date: 04/09/2018
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
ms.openlocfilehash: 09460139ba2ae7c9be78b1441e1d095952b405f8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447915"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>將產品從 Supply Chain Management 同步到 Field Service 中

[!include[banner](../includes/banner.md)]

本主題討論用來將產品從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。

使用的 **Field Service 產品 (Supply Chain Management 到 Field Service)** 範本為根據從潛在客戶到現金的 **產品 (Supply Chain Management 到 Sales) – 直接** 範本。 若需更多相關資訊，請參閱[產品 (Supply Chain Management 到 Sales) – 直接](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct)。

本主題僅說明 **Field Service 產品 (Supply Chain Management 到 Field Service)** 範本與 **產品 (Supply Chain Management 到 Sales) – 直接** 範本的差異。

## <a name="templates-and-tasks"></a>範本和工作

**資料整合中的範本名稱**

- Field Service 產品 (Supply Chain Management 到 Field Service)

**資料整合專案中的任務名稱**

- 產品 - 產品

**Field Service 產品 (Supply Chain Management 到 Field Service)** 範本包含一個未納入 **產品 (Supply Chain Management 到 Sales) – 直接** 範本的對應。 此對應可確保必要的 Field Service 特定欄位 **服務產品類型** 設定正確。

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

使用的值對應如下。

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

在 Supply Chain Management 中，**可銷售的已發布產品** 資料實體上的 **Field Service 產品類型** 值計算如下：

- **Inventory：** 產品類型 = 產品和項目模型群組，庫存產品 = True
- **NonInventory：** 產品類型 = 產品和項目模型群組，庫存產品 = False
- **Service：** 產品類型：服務

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖顯示資料整合中的範本對應。

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Field Service 產品 (Supply Chain Management 到 Field Service)：產品 - 產品

[![資料整合中的範本對應。](./media/FSProduct.png)](./media/FSProduct.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]