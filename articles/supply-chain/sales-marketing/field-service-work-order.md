---
title: 將 Field Service 工單同步處理為 Supply Chain Management 銷售訂單
description: 本主題討論用於同步處理 Field Service 工單至 Supply Chain Management 銷售訂單的範本和基礎工作。
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
ms.openlocfilehash: b7b311701aff12d58392fc036d0f1174678b7dc3
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449814"
---
# <a name="synchronize-work-orders-in-field-service-to-sales-orders-in-supply-chain-management"></a>將 Field Service 工單同步處理為 Supply Chain Management 銷售訂單

[!include[banner](../includes/banner.md)]



本主題討論用於同步處理 Dynamics 365 Field Service 工單至 Dynamics 365 Supply Chain Management 銷售訂單的範本和基礎工作。

[![Supply Chain Management 和 Field Service 之間的業務流程同步。](./media/field-service-integration.png)](./media/field-service-integration.png)


## <a name="templates-and-tasks"></a>範本和工作

以下範本和基礎工作會用來同步處理 Field Service 工單至 Supply Chain Management 銷售訂單。

### <a name="names-of-the-templates-in-data-integration"></a>資料整合中的範本名稱

執行同步處理程序所用的範本為 **工單到銷售訂單 (Field Service 到 Supply Chain Management)**。

### <a name="names-of-the-tasks-in-the-data-integration-project"></a>資料整合專案中的工作名稱

- WorkOrderHeader
- WorkOrderServiceLineEstimate
- WorkOrderServiceLineUsed
- WorkOrderProductLineEstimate
- WorkOrderProductLineUsed

在同步處理銷售訂單抬頭和明細之前，需要執行以下同步工作：

- Field Service 產品 (Supply Chain Management 到 Field Service)
- 帳款 (Sales 到 Supply Chain Management) - 直接

## <a name="entity-set"></a>實體集

| **Field Service** | **Supply Chain Management** |
|-------------------------|-------------------------|
| msdyn_workorders        | Dataverse 銷售訂單抬頭 |
| msdyn_workorderservices | Dataverse 銷售訂單明細   |
| msdyn_workorderproducts | Dataverse 銷售訂單明細   |

## <a name="entity-flow"></a>實體流程

在 Field Service 中建立的工單。 如果工單僅包括外部維護的產品，且 **工單狀態** 的值並非 **開放-未排程** 和 **關閉 - 已取消**，則可以透過 Microsoft Dataverse 資料整合專案將工單同步至 Supply Chain Management。 工單的更新內容將同步處理為 Supply Chain Management 銷售訂單。 這些更新內容包括來源類型和狀態的相關資訊。

## <a name="estimated-versus-used"></a>「已預估」與「已使用」

在 Field Service 中，工單上的產品和服務數量和金額都同時具有 **已預估** 值和 **已使用** 值。 然而，Supply Chain Management 中的銷售訂單沒有相同的 **已預估** 值和 **已使用** 值的概念。 為了能根據 Supply Chain Management 銷售訂單上的預期數量分配產品，同時保留應消耗及開立發票的使用數量，系統會執行兩組工作來同步處理工單上的產品和服務。 一組工作針對 **已預估** 值，另一組工作針對 **已使用** 值。

如此一來，即可在 Supply Chain Management 中使用「已預估」值進行分配或預留，同時將「已使用」值用於消耗及開立發票。

### <a name="estimated"></a>已預估

若為產品明細的同步作業，當 **明細狀態** 值為 **已預估**、**已分配** 選項設為 **是**，且 **系統狀態** 值不是 **已關閉 - 已過帳** 時，系統就會使用 **已預估** 值。

若為服務明細的同步作業，當 **明細狀態** 值為 **已預估**，且 **系統狀態** 值不是 **已關閉 - 已過帳** 時，系統就會使用 **已預估** 值。

### <a name="used"></a>已使用

**已使用** 值用於消耗和開立發票。 在這些情況下，會同步 **已使用** 值。

下表概述了產品明細的各種組合。

| 系統狀態 <br>(Field Service) | 明細狀態 <br>(Field Service) | 已分配 <br>(Field Service) |已同步的值 <br>(Supply Chain Management) |
|--------------------|-------------|-----------|---------------------------------|
| 開放 - 已排程   | 已預估   | 是       | 已預估                       |
| 開放 - 已排程   | 已預估   | 否        | 已使用                            |
| 開放 - 已排程   | 已使用        | 是       | 已使用                            |
| 開放 - 已排程   | 已使用        | 否        | 已使用                            |
| 開放 - 處理中 | 已預估   | 是       | 已預估                       |
| 開放 - 處理中 | 已預估   | 否        | 已使用                            |
| 開放 - 處理中 | 已使用        | 是       | 已使用                            |
| 開放 - 處理中 | 已使用        | 否        | 已使用                            |
| 開放 - 已完成   | 已預估   | 是       | 已預估                       |
| 開放 - 已完成   | 已預估   | 否        | 已使用                            |
| 開放 - 已完成   | 已使用        | 是       | 已使用                            |
| 開放 - 已完成   | 已使用        | 否        | 已使用                            |
| 關閉 - 已過帳    | 已預估   | 是       | 已使用                            |
| 關閉 - 已過帳    | 已預估   | 否        | 已使用                            |
| 關閉 - 已過帳    | 已使用        | 是       | 已使用                            |
| 關閉 - 已過帳    | 已使用        | 否        | 已使用                            |

下表概述了服務明細的各種組合。

| 系統狀態 <br>(Field Service) | 明細狀態 <br>(Field Service) | 已同步的值 <br>(Supply Chain Management) |
|--------------------|-------------|-----------|
| 開放 - 已排程   | 已預估   | 已預估 |
| 開放 - 已排程   | 已使用        | 已使用      |
| 開放 - 處理中 | 已預估   | 已預估 |
| 開放 - 處理中 | 已使用        | 已使用      |
| 開放 - 已完成   | 已預估   | 已預估 |
| 開放 - 已完成   | 已使用        | 已使用      |
| 關閉 - 已過帳    | 已預估   | 已使用      |
| 關閉 - 已過帳    | 已使用        | 已使用      |

**已預估** 值與 **已使用** 值的同步作業是透過產品明細和服務明細的兩組工作管理。 預先定義的篩選器會觸發正確的工作，基礎對應作業有助於確保正確同步 **已預期** 值與 **已使用** 值。

### <a name="example"></a>範例

1. 工單會在 Field Service 中建立及排程。

    **系統狀態** 值為 **開放 - 已排程**。

    - **產品明細：** 預估數量 = 5 個，已使用數量 = 0 個，明細狀態 = 已預估，已分配 = 否
    - **服務明細：** 預估數量 = 2 小時，已使用數量 = 0 小時，明細狀態 = 已預估

    在此範例中，產品的 **已使用數量** 值 **0** (零) 和服務的 **預估數量** 值 **2 小時** 會同步到 Supply Chain Management。

2. 產品會在 Field Service 中分配。

    **系統狀態** 值為 **開放 - 已排程**。

    - **產品明細：** 預估數量 = 5 個，已使用數量 = 0 個，明細狀態 = 已預估，已分配 = 是
    - **服務明細：** 預估數量 = 2 小時，已使用數量 = 0 小時，明細狀態 = 已預估

    在此範例中，產品的 **預估數量** 值 **5 個** 和服務的 **預估數量** 值 **2 小時** 會同步到 Supply Chain Management。

3. 服務技術人員會開始處理工單並將材料使用量登記為 6。

    **系統狀態** 值為 **開放 - 處理中**。

    - **產品明細：** 預估數量 = 5 個，已使用數量 = 6 個，明細狀態 = 已使用，已分配 = 是
    - **服務明細：** 預估數量 = 2 小時，已使用數量 = 0 小時，明細狀態 = 已預估

    在此範例中，產品的 **已使用數量** 值 **6** 和服務的 **預估數量** 值 **2 小時** 會同步到 Supply Chain Management。

4. 服務技術人員完成工單並將處理時間登記為 1.5 小時。

    **系統狀態** 值為 **開放 - 已完成**。

    - **產品明細：** 預估數量 = 5 個，已使用數量 = 6 個，明細狀態 = 已使用，已分配 = 是
    - **服務明細：** 預估數量 = 2 小時，已使用數量 = 1.5 小時，明細狀態 = 已使用

    在此範例中，產品的 **已使用數量** 值 **6** 和服務的 **已使用數量** 值 **1.5 小時** 會同步到 Supply Chain Management。

## <a name="sales-order-origin-and-status"></a>銷售訂單來源和狀態

### <a name="sales-origin"></a>銷售來源

若要追蹤源自工單的銷售訂單，您可以建立銷售來源，然後將其中的 **來源類型指派** 選項設為 **是**，以及將 **銷售來源類型** 欄位設為 **工單整合**。

在預設情況下，系統針對所有從工單建立的銷售訂單對應的銷售來源類型為 **工單整合**。 在 Supply Chain Management 中處理銷售訂單時，此行為很實用。 您必須確保源自工單的銷售訂單不會同步回 Field Service 工單。

有關如何在 Supply Chain Management 中正確設定銷售來源的詳細資訊，請參閱本主題的「先決條件和對應設定」部分。

### <a name="status"></a>狀態

當銷售訂單源自工單時，銷售訂單抬頭的 **設定** 索引標籤會顯示 **外部工單狀態** 欄位。 此欄位顯示 Field Service 工單的系統狀態，以協助追蹤 Supply Chain Management 銷售訂單的已同步工單狀態。 此欄位還可以協助使用者判斷銷售訂單應何時出貨或開立發票。

**外部工單狀態** 欄位可能顯示的值如下：

- 開放 - 已排程
- 開放 - 處理中
- 開放 - 已完成
- 關閉 - 已過帳

## <a name="field-service-crm-solution"></a>Field Service CRM 解決方案

為了支援 Field Service 和 Supply Chain Management 之間的整合作業，需使用 Field Service CRM 解決方案的附加功能。 該解決方案包括以下變更。

### <a name="work-order-entity"></a>工單實體

**僅具有外部維護的產品** 欄位已新增至 **工單** 實體並顯示在頁面上。 該欄位用於持續追蹤工單是否僅包含外部維護的產品。 如果所有外部維護的產品都在 Supply Chain Management 中維護，則工單僅會包含這些產品。 此欄位有助於確保使用者不會同步處理到具有未知產品的工單。

### <a name="work-order-product-entity"></a>工單產品實體

- **僅具有外部維護的產品** 欄位已新增至 **工單產品** 實體並顯示在頁面上。 該欄位用於持續追蹤工單產品是否在 Supply Chain Management 中維護。 此欄位有助於確保使用者不會同步處理到 Supply Chain Management 判定為未知產品的工單產品。
- **標題系統狀態** 欄位已新增至 **工單產品** 實體並顯示在頁面上。 該欄位用於持續追蹤工單的系統狀態，並在工單產品同步至 Supply Chain Management 時協助確保正確篩選。 在整合工作中設定篩選器時，**標題系統狀態** 資訊也用於判斷是否應同步「已預估」值或「已使用」值。
- **已開立發票單位金額** 欄位顯示按實際使用單位開立發票的金額。 該值是以 **總金額** 值除以 **實際數量** 值來計算。 該欄位用於整合至不支援已使用數量值和已計費數量值不同的系統。 此欄位不會顯示在使用者介面 (UI) 中。 
- **已開立發票折扣金額** 欄位是以 **折扣金額** 值加上四捨五入的 **已開立發票單位金額** 值來計算。 此欄位用於整合作業，不會顯示在 UI 中。
- **十進位數量** 欄位將 **數量** 欄位值儲存為十進位數字。 此欄位用於整合作業，不會顯示在 UI 中。 
- 如果工單產品的 **明細狀態** 值從 **已使用** 變更為 **已預估**，**已使用** 欄位的值會重設為 **0** (零)。 在 **明細狀態** 值為 **已預估** 且 **已分配** 選項設為 **否** 的情況下，這項變更有助於防止系統同步處理錯誤輸入的已使用數量。

### <a name="work-order-service-entity"></a>工單服務實體

- **僅具有外部維護的產品** 欄位已新增至 **工單服務** 實體並顯示在頁面上。 該欄位用於持續追蹤工單服務是否在 Supply Chain Management 中維護。 此欄位有助於確保使用者不會同步處理到 Supply Chain Management 判定為未知服務的工單服務。
- **標題系統狀態** 欄位已新增至 **工單服務** 實體並顯示在頁面上。 該欄位用於持續追蹤工單的系統狀態，並在工單服務同步至 Supply Chain Management 時協助確保正確篩選。 在整合工作中設定篩選器時，**標題系統狀態** 資訊也用於判斷是否應同步「已預估」值或「已使用」值。
- **持續時間 (小時)** 欄位會儲存從分鐘轉換為小時後的 **持續時間** 值。 此欄位用於整合作業，不會顯示在 UI 中。
- **預估持續時間 (小時)** 欄位會儲存從分鐘轉換為小時後的 **預估持續時間** 值。 此欄位用於整合作業，不會顯示在 UI 中。
- **已開立發票單位金額** 欄位儲存按實際使用單位開立發票的金額。 該值是以 **總金額** 值除以 **實際數量** 值來計算。 此欄位用於整合至不支援已使用數量值和已計費數量值不同的系統。 該欄位不會顯示在使用者介面 (UI) 中。
- **已開立發票折扣金額** 欄位是以 **折扣金額** 值加上四捨五入的 **已開立發票單位金額** 值來計算。 此欄位用於整合作業，不會顯示在 UI 中。
- **外部明細訂單** 欄位是經計算得出的負數明細訂單編號，可在合併工單產品和服務明細的外部系統中使用。 在此欄位中插入的工單產品明細編號為正數，工單服務明細編號則為負數。 此欄位的值是以 **明細訂單** 值乘以 -1 來計算。 此欄位不會顯示在使用者介面 (UI) 中。
- 如果工單服務的 **明細狀態** 值基於某些原因而從 **已使用** 變更為 **已預估**，**已使用** 欄位的值會重設為 **0** (零)。 在 **明細狀態** 值為 **已預估** 且 **標題系統狀態** 值為 **關閉 - 已過帳** 的情況下，這項變更有助於防止系統同步處理錯誤輸入的已使用數量。

## <a name="preconditions-and-mapping-setup"></a>先決條件和對應設定

在同步工單之前，請務必更新系統中的以下設定。

### <a name="setup-in-field-service"></a>Field Service 設定

- 請確保在 Field Service 工單編號序列不會與 Supply Chain Management 銷售訂單編號序列重疊。 否則，Field Service 或 Supply Chain Management 中的現有銷售訂單可能會錯誤更新。
- **工單發票建立** 欄位必須設為 **永不**，因為發票開立作業將由 Supply Chain Management 完成。 請前往 **Field Service** \> **設定** \> **管理** \> **Field Service 設定** 確認 **工單發票建立** 欄位設為 **永不**。

### <a name="setup-in-supply-chain-management"></a>Supply Chain Management 設定

您需要設定銷售來源才能整合工單。 銷售來源用於區分從 Field Service 工單建立的 Supply Chain Management 銷售訂單。 當銷售訂單的訂單來源類型為 **工單整合** 時，銷售訂單抬頭會顯示 **外部工單狀態** 欄位。 此外，銷售來源可確保從 Supply Chain Management 將處理銷售訂單同步到 Field Service 的期間，篩選掉從 Field Service 工單建立的銷售訂單。

1. 依序前往 **銷售和行銷** \> **設定** \> **銷售訂單** \> **銷售來源**。
2. 選擇 **新增** 以建立新的銷售來源。
3. 在 **銷售來源** 欄位中輸入銷售來源名稱，例如 **WorkOrder**。
4. 在 **描述** 欄位中輸入描述，例如 **Field Service 工單**。
5. 選擇 **來源類型指派** 核取方塊。
6. 將 **銷售來源類型** 欄位設為 **工單整合**。
7. 選擇 **儲存**。


### <a name="setup-in-data-integration"></a>資料整合設定

確認 **整合金鑰** 顯示為 **msdyn_workorders**
1. 前往資料整合
2. 選擇 **連接集** 索引標籤
3. 選擇要用於同步處理工單的連接集
4. 選擇 **整合金鑰** 索引標籤
5. 找出 msdyn_workorders 並檢查是否已新增金鑰 **msdyn_name (工單編號)**。 如果未顯示，請點選頁面頂端的 **新增金鑰**，然後點選 **儲存**

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖顯示資料整合中的範本對應。

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderheader"></a>工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderHeader

篩選條件：(msdyn_systemstatus ne 690970005)、(msdyn_systemstatus ne 690970000) 和 (msdynce_hasexternallymaintainedproductsonly eq true)

[![資料整合中的「工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderHeader」範本對應。](./media/FSWorkOrder1.png )](./media/FSWorkOrder1.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderservicelineestimate"></a>工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderServiceLineEstimate

篩選條件：(msdynce_headersystemstatus ne 690970005)、(msdynce_headersystemstatus ne 690970000)、(msdynce_orderhasexternalmaintainedproductsonly eq true)、(msdyn_linestatus eq 690970000) 和 (msdynce_headersystemstatus ne 690970004)

[![資料整合中的「工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderServiceLineEstimate」範本對應。](./media/FSWorkOrder2.png )](./media/FSWorkOrder2.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderservicelineused"></a>工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderServiceLineUsed

篩選條件：(msdynce_headersystemstatus ne 690970005)、(msdynce_headersystemstatus ne 690970000)、(msdynce_orderhasexternalmaintainedproductsonly eq true) 和 ((msdyn_linestatus eq 690970001) 或 (msdynce_headersystemstatus eq 690970004))

[![資料整合中的「工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderServiceLineUsed」範本對應。](./media/FSWorkOrder3.png )](./media/FSWorkOrder3.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderproductlineestimate"></a>工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderProductLineEstimate

篩選條件：(msdynce_headersystemstatus ne 690970005)、(msdynce_headersystemstatus ne 690970000)、(msdynce_orderhasexternalmaintainedproductsonly eq true)、(msdyn_linestatus eq 690970000)、(msdynce_headersystemstatus ne 690970004) 和 (msdyn_allocated eq true)

[![資料整合中的「工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderProductLineEstimate」範本對應。](./media/FSWorkOrder4.png )](./media/FSWorkOrder4.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderproductlineused"></a>工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderProductLineUsed

篩選條件：(msdynce_headersystemstatus ne 690970005)、(msdynce_headersystemstatus ne 690970000)、(msdynce_orderhasexternalmaintainedproductsonly eq true) 和 ((msdyn_linestatus eq 690970001) 或 (msdynce_headersystemstatus eq 690970004) 或 (msdyn_allocated ne true))

[![資料整合中的「工單到銷售訂單 (Field Service 到 Supply Chain Management)：WorkOrderProductLineUsed」範本對應。](./media/FSWorkOrder5.png )](./media/FSWorkOrder5.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]