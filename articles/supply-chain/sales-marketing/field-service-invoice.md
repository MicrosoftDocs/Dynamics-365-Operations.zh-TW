---
title: 將 Field Service 合約發票同步處理為 Supply Chain Management 普通發票
description: 本主題討論用於同步處理 Dynamics 365 Field Service 合約發票至 Dynamics 365 Supply Chain Management 普通發票的範本和基礎工作。
author: Henrikan
ms.date: 04/10/2018
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
ms.openlocfilehash: 70f1c072c3a2a1b201aac1f1d2beea9979a3b792
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449802"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>將 Field Service 合約發票同步處理為 Supply Chain Management 普通發票

[!include[banner](../includes/banner.md)]



本主題討論用於同步處理 Dynamics 365 Field Service 合約發票至 Dynamics 365 Supply Chain Management 普通發票的範本和基礎工作。

## <a name="templates-and-tasks"></a>範本和工作

以下範本和基礎工作用於同步處理 Field Service 合約發票至 Supply Chain Management 普通發票。

**資料整合中的範本名稱**

- 合約發票 (Field Service 到 Supply Chain Management)

**資料整合專案中的工作名稱**

- 發票抬頭
- 發票明細

在同步合約發票之前，需要執行以下同步工作：

- 帳款 (Sales 到 Supply Chain Management) - 直接

## <a name="entity-set"></a>實體集

| Field Service  | Supply Chain Management                 |
|----------------|----------------------------------------|
| invoices       | Dataverse 客戶普通發票抬頭 |
| invoicedetails | Dataverse 客戶普通發票明細   |

## <a name="entity-flow"></a>實體流程

根據 Field Service 中的合約建立的發票可以透過 Microsoft Dataverse 資料整合專案同步至 Supply Chain Management。 如果 Supply Chain Management 普通發票的會計狀態為 **處理中**，對這類合約發票進行的更新也會同步至普通發票。 普通發票在 Supply Chain Management 中過帳，且會計狀態更新為 **已完成** 後，您就無法再從 Field Service 同步更新。

## <a name="field-service-crm-solution"></a>Field Service CRM 解決方案

**具有來源為合約的明細** 欄已新增至 **發票** 資料表。 此欄可確保僅同步處理從合約建立的發票。 如果發票包含至少一項源自合約的發票明細，則值為 **true**。

**來源為合約** 欄已新增至 **發票明細** 資料表。 此欄可確保僅同步處理從合約建立的發票明細。 如果發票明細源自合約，則值為 **true**。

**發票日期** 是 Supply Chain Management 中的必填欄位。 因此在同步處理之前，必須在該欄填入 Field Service 中的一個值。 為了滿足這項要求，系統加入了以下邏輯：

- 如果 **發票** 資料表中的 **發票日期** 欄為空白 (亦即該欄未填入值)，則設為合約發票明細的新增日期。
- 使用者可以變更 **發票日期** 欄。 不過，當使用者嘗試儲存源自合約的發票時，如果發票上的 **發票日期** 欄為空白，業務流程會發生錯誤。

## <a name="prerequisites-and-mapping-setup"></a>先決條件和對應設定

### <a name="in-supply-chain-management"></a>在 Supply Chain Management 中

必須為整合作業設定發票來源，才能區分從 Field Service 合約發票建立的 Supply Chain Management 普通發票。 當發票來源屬於 **合約發票** 整合類型時，**銷售發票** 抬頭會顯示 **外部發票編號** 欄位。

除了顯示在發票抬頭之外，**外部發票編號** 資訊可以在同步處理 Supply Chain Management 發票至 Field Service 的期間，協助篩掉從 Field Service 合約發票建立的發票。

1. 前往 **應收帳款** \> **設定** \> **發票來源代碼**。
2. 選擇 **新增** 以建立新的發票來源。
3. 在 **發票來源** 欄位中，輸入發票來源的名稱，例如 **FS**。
4. 在 **描述** 欄位中輸入描述，例如 **Field Service 合約發票**。
5. 選擇 **來源類型指派** 核取方塊。
6. 將 **發票來源類型** 欄位設為 **合約發票整合**。
7. 選擇 **儲存**。

### <a name="in-the-data-integration-project"></a>在資料整合專案中

工作：**發票明細**  

確認 Supply Chain Management 的 **主要帳款顯示值** 欄位預設值已更新為所需的值。

預設範本值為 **401100**。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖顯示資料整合中的範本對應。

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>合約發票 (Field Service 到 Supply Chain Management)：發票抬頭

[![資料整合中的發票抬頭範本對應。](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>合約發票 (Field Service 到 Supply Chain Management)：發票明細

[![資料整合中的發票明細範本對應。](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]