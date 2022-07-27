---
title: Microsoft Dynamics 365 Field Service 整合作業概觀
description: 本主題概述 Microsoft Dynamics 365 Field Service 整合作業。
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 9428308211d51e7de8c61fb9aadef6ce1fd9886f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449850"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>Microsoft Dynamics 365 Field Service 整合作業概觀

[!include[banner](../includes/banner.md)]



Supply Chain Management 可同步處理 Dynamics 365 Supply Chain Management 與 Dynamics 365 Field Service 之間的業務流程。 使用可擴充的資料整合器範本和 Microsoft Dataverse 即可設定整合方案來同步處理業務流程。
標準範本可用於建立對應至其他標準和自訂資料欄/表格的自訂整合專案，以調整整合內容並滿足特定業務需求。 

Field Service 整合建立在現有的潛在客戶到現金功能上。

![Supply Chain Management 和 Field Service 之間的業務流程同步。](./media/field-service-integration.png)

Field Service 和 Supply Chain Management 之間的第一階段整合重點，是能在 Supply Chain Management 中為 Field Service 工單及合約開立發票。 支援的流程從 Field Service 開始，其中的工單資訊會做為銷售訂單同步到 Supply Chain Management。 Supply Chain Management 則會對銷售訂單開立發票以產生發票文件。 此外，Field Service 合約發票資訊會同步到 Supply Chain Management。 Microsoft Dynamics 365 資料整合器將使用可自訂的專案同步處理資料。 標準範本可用於建立對應至其他標準和自訂資料欄/表格的自訂整合專案，以調整整合內容並滿足特定需求。

Field Service 和 Supply Chain Management 之間的第一階段整合為同步處理以下項目：

- [將產品從 Supply Chain Management 同步到 Field Service 中](field-service-product.md)
- [將 Field Service 工單同步處理為 Supply Chain Management 銷售訂單](field-service-work-order.md)
- [將 Field Service 合約發票同步處理為 Supply Chain Management 普通發票](field-service-invoice.md)

若要查看在 Field Service 和 Supply Chain Management 之間同步處理工單的範例，請觀看 YouTube 短片《[如何使用 Microsoft Dynamics 365 整合功能同步處理工單](https://www.youtube.com/watch?v=46ylO7raZAo)》。

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>整合 Field Service 庫存和專案資訊

第二階段整合的其他功能在於讓現場技術人員深入解析 Supply Chain Management 的庫存資訊，以便更新庫存量及轉移原料。 此外，從專案整合有助於安裝或維修所售商品的公司進一步控管及掌握完整銷售和服務流程。

### <a name="functionality-includes-integration-of"></a>功能包括整合以下資訊：
- 倉庫資訊
- 現有庫存資訊
- 庫存轉移資訊
- 庫存調整資訊
- 與 Dynamics 365 Field Service 工單連結的 Supply Chain Management 專案
- 連結至 Supply Chain Management 專案的 Dynamics 365 Field Service 工單，將此專案號碼套用至銷售訂單以允許從專案開立發票。 

![同步處理 Supply Chain Management 與 Field Service 之間的業務流程，包括庫存和專案資訊。](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>Field Service 和 Supply Chain Management 之間的第二階段整合為同步處理以下範本：
- 倉庫 (Supply Chain Management 到 Field Service) - 將 Supply Chain Management 倉庫資訊同步到 Field Service [進階查詢] 
- 產品庫存 (Supply Chain Management 到 Field Service) - 將 Supply Chain Management 產品庫存資訊同步到 Field Service [進階查詢] 
- 庫存調整 (Field Service 到 Supply Chain Management) - 將 Field Service 庫存調整資訊同步到 Supply Chain Management [進階查詢] 
- 庫存轉移 (Field Service 到 Supply Chain Management) - 將 Field Service 庫存轉移資訊同步到 Supply Chain Management [進階查詢] 
- 專案 (Supply Chain Management 到 Field Service) - 將 Supply Chain Management 專案清單同步到 Field Service 
- 含專案的工單 (Field Service 到 Supply Chain Management) - 透過專案將 Field Service 工單同步為 Supply Chain Management 銷售訂單 [進階查詢] 
- 具有庫存單位的 Field Service 產品 (Supply Chain Management 到銷售) - 從 Supply Chain Management「可銷售的已發佈產品」同步到 Field Service 的 Sales「產品」，包括庫存單位 

## <a name="system-requirements"></a>系統要求

### <a name="system-requirements-for-supply-chain-management"></a>Supply Chain Management 的系統要求
Field Service 整合支援以下版本：

- Dynamics 365 for Finance and Operations 版本 8.1.2 (2018 年 12 月) 於 2018 年 12 月發行，應用程式組建編號為 8.1.195，平台更新為 22 (7.0.5095)。 

### <a name="system-requirements-for-field-service"></a>Field Service 的系統要求
若要使用 Field Service 整合解決方案，您必須安裝以下元件：

- Field Service (版本 8.2.0.286) 或 Dynamics 365 9.1.x 以上版本 - 2018 年 11 月發行
- Dynamics 365 的從潛在客戶到現金 (P2C) 解決方案，1.15.0.1 或以上版本。 此解決方案可從 [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3) 下載。
- Dynamics 365 的「Field Service 整合、專案和庫存」解決方案，2.0.0.0 或以上版本。 此解決方案可從 [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2) 下載。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]