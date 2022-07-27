---
title: 將 Field Service 的庫存轉移和調整同步到 Supply Chain Management
description: 本主題討論用來將庫存調整和轉移從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。
author: Henrikan
ms.date: 04/30/2019
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
ms.openlocfilehash: cfa7f617cbc4cd75d669972b35f8d33ba3cbcc56
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449823"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>將 Field Service 的庫存轉移和調整同步到 Supply Chain Management

[!include[banner](../includes/banner.md)]



本主題討論用來將庫存調整和轉移從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。

[![Supply Chain Management 和 Field Service 之間的業務流程同步。](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>範本和工作
以下範本和基礎工作用於將庫存調整和轉移從 Field Service 同步到 Supply Chain Management。

**資料整合中的範本**
- 庫存調整 (Field Service 到 Supply Chain Management)
- 庫存轉移 (Field Service 到 Supply Chain Management)

**資料整合專案中的工作**
- 庫存調整
- 庫存轉移

## <a name="table-set"></a>資料表集
| Field Service                     | Supply Chain Management                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts | Dataverse 庫存調整日記帳標題和行 |
| msdyn_inventoryadjustmentproducts | Dataverse 庫存轉移日記帳標題和行   |

## <a name="table-flow"></a>資料表流程
在 **過帳狀態** 從 **已建立** 變更為 **已過帳** 後，在 Field Service 中進行的庫存調整和轉移將同步到 Supply Chain Management。 發生這種情況時，調整或轉移單將鎖定並變為唯讀。 這代表調整和轉移可以在 Supply Chain Management 中過帳，但無法修改。 在 Supply Chain Management 中，您可以設定批次作業以自動過帳調整並轉移整合期間產生的庫存日記帳。 有關如何啟用批次作業的詳細資訊，請參閱以下先決條件。

## <a name="field-service-crm-solution"></a>Field Service CRM 解決方案 
**庫存單位** 資料行已新增到 **產品** 資料表。 之所以需要此資料行，是因為 Supply Chain Management 中的銷售和庫存單位並不總是相同，而 Supply Chain Management 中的倉庫庫存需要庫存單位。
當您在庫存調整產品上設定產品以進行庫存調整和庫存轉移時，將從庫存產品值中擷取單位。 如果找到值，則 **單元** 資料行將鎖定在庫存調整產品上。

**過帳狀態** 資料行已同時新增到 **庫存調整** 資料表和 **庫存轉移** 資料表。 當調整或轉移發送到 Supply Chain Management 時，此資料行會當作篩選使用。 此資料行的預設值為 [已建立 (1)]，但不會發送到 Supply Chain Management。 當您將值更新為 [已過帳 (2)] 後，它才會發送到 Supply Chain Management，但之後您將無法再變更調整或轉移或新增新行。

**編號序列** 資料行已新增到 **庫存調整產品** 資料表。 此資料行確保整合具有唯一編號，因此整合可以建立和更新調整。 當建立第一個庫存調整產品時，將在 **P2C AutoNumber** 資料表中建立新記錄以保持所使用的編號序列和首碼。

## <a name="prerequisites-and-mapping-setup"></a>先決條件和對應設定

### <a name="supply-chain-management"></a>Supply Chain Management
整合產生的整合庫存日記帳可以使用批次作業自動過帳。 這從 **庫存管理 > 定期工作 > Dataverse 整合 > 過帳整合庫存日記帳** 啟用。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖顯示資料整合中的範本對應。

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>庫存調整 (Field Service 到 Supply Chain Management)：庫存調整

[![資料整合中的範本對應，庫存調整 (Field Service 到 Supply Chain Management)：庫存調整。](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>庫存轉移 (Field Service 到 Supply Chain Management)：庫存轉移

[![資料整合中的範本對應，庫存轉移 (Field Service 到 Supply Chain Management)：庫存轉移。](./media/FSTrans1.png)](./media/FSTrans1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]