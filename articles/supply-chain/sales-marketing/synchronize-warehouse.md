---
title: 將 Supply Chain Management 的倉庫同步到 Field Service
description: 本主題討論用來將倉庫從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。
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
ms.openlocfilehash: f38d2dfdba1f2afa1005bd740cba27afe9dcb0ec
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449832"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a>將 Supply Chain Management 的倉庫同步到 Field Service

[!include[banner](../includes/banner.md)]



本主題討論用來將倉庫從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。

[![Supply Chain Management 和 Field Service 之間的業務流程同步。](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>範本和工作
以下範本和基礎工作用於執行倉庫從 Supply Chain Management 到 Field Service 的同步。

**資料整合中的範本**
- 倉庫 (Supply Chain Management 到 Field Service)

**資料整合專案中的工作**
- 倉庫

## <a name="table-set"></a>資料表集
| Field Service    | Supply Chain Management                 |
|------------------|----------------------------------------|
| msdyn_warehouses | 倉庫                             |

## <a name="table-flow"></a>資料表流程
可透過 Microsoft Dataverse 資料整合專案將在 Supply Chain Management 中建立和維護的倉庫同步到 Field Service。 您想要同步到 Field Service 的倉庫將透過專案的進階查詢和篩選來控制。 從 Supply Chain Management 同步的倉庫是在 Field Service 中建立，**外部維護** 資料行設定為 **是**，記錄為唯讀。

## <a name="field-service-crm-solution"></a>Field Service CRM 解決方案
為了支援 Field Service 和 Supply Chain Management 之間的整合作業，需使用 Field Service CRM 解決方案的附加功能。 在解決方案中，**外部維護** 資料行已新增到 **倉庫 (msdyn_warehouses)** 資料表。 此資料行有助於確定倉庫是否是從 Supply Chain Management 處理，還是僅存在於 Field Service 中。 此資料行的設定包括：
- **是** – 倉庫源自 Supply Chain Management，無法在 Sales 中進行編輯。
- **否** – 倉庫在 Field Service 中直接輸入並在此處維護。

**外部維護** 資料行有助於控制工作訂單上的庫存水準、調整、轉移和使用的同步。 只有 **外部維護** 設定為 **是** 的倉庫可用於直接同步到其他系統中的同一個倉庫。 

> [!NOTE]
> 可以在 Field Service (**外部維護 = 否**) 中建立多個倉庫，然後使用進階查詢和篩選功能將它們對應到單個倉庫。 這用於您希望 Field Service 掌握詳細的庫存水準並僅將更新發送到 Supply Chain Management 的情況。 在這種情況下，Field Service 將不會從 Supply Chain Management 接收庫存水準更新。 有關其他資訊，請參閱[將庫存調整從 Field Service 同步到財務與營運](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) 和[將 Field Service 中的工作訂單與財務與營運中連結到專案的銷售訂單同步](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)。

## <a name="prerequisites-and-mapping-setup"></a>先決條件和對應設定
### <a name="data-integration-project"></a>資料整合專案
在同步倉庫之前，請確保更新專案的進階查詢和篩選，以僅包括您希望從 Supply Chain Management 引入 Field Service 的倉庫。 請注意，您將需要 Field Service 中的倉庫將其套用於工單、調整和轉移。  

為確保存在 **msdyn_warehouses** 的 **整合鍵**：
1. 移至資料整合。
2. 選擇 **連接集** 標籤。
3. 選擇用於工單同步的連接集。
4. 選擇 **整合鍵** 索引標籤。
5. 找到 msdyn_warehouses 並確認是否新增了 **msdyn_name (名稱)** 鍵。 如果未顯示，請點選頁面頂端的 **新增鍵**，然後點選 **儲存**。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖顯示資料整合中的範本對應。

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a>倉庫 (Supply Chain Management 到 Field Service)：倉庫

[![資料整合中的範本對應。](./media/Warehouse1.png)](./media/Warehouse1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]