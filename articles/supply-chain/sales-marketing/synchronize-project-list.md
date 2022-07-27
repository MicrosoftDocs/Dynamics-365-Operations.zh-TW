---
title: 將 Supply Chain Management 的專案清單同步到 Field Service
description: 本主題討論用來將專案從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。
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
ms.openlocfilehash: b825e2fce61e96b963ba0d41f8db49ca9ba646f6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448434"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>將 Supply Chain Management 的專案清單同步到 Field Service

[!include[banner](../includes/banner.md)]

本主題討論用來將專案從 Dynamics 365 Supply Chain Management 同步到 Dynamics 365 Field Service 的範本和基礎工作。

[![Supply Chain Management 和 Field Service 之間的業務流程同步。](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>範本和工作
以下範本和基礎工作用於執行專案從 Supply Chain Management 到 Field Service 的同步。

**資料整合中的範本**
- 專案 (Supply Chain Management 到 Field Service)

**資料整合專案中的工作**
- 專案

在同步專案清單之前，需要執行以下同步工作：
- 科目 (Sales 到 Supply Chain Management) 

## <a name="entity-set"></a>實體集
| Field Service           | Supply Chain Management  |
|-------------------------|-------------------------|
|msdynce_externalprojects | 專案                |

## <a name="entity-flow"></a>實體流程
專案是在 Supply Chain Management 中建立的。 將 **專案類型** 設定為 **時間和物料** 並將 **專案階段** 設定為 **進行中** 的專案同步到 Field Service 中的 **外部專案** 實體，包括專案編號、專案名稱、專案階段和客戶帳戶資訊。 **外部專案** 清單用於將 Field Service 工單與 Supply Chain Management 專案配對。

## <a name="field-service-crm-solution"></a>Field Service CRM 解決方案
**外部專案** 實體從 Supply Chain Management 中取得所有專案。 **外部專案** 欄位已新增到 **工單** 實體。 這是一個查詢欄位，因此透過使用專案標記您的工單，銷售訂單將連接到 Supply Chain Management 中的專案。 **系統狀態** 將 **打開 – 進行中(690,970,000)** 變更為更高狀態後，**外部專案** 欄位將鎖定，您將無法再新增、刪除或變更值。

## <a name="prerequisites-and-mapping-setup"></a>先決條件和對應設定
### <a name="supply-chain-management"></a>Supply Chain Management
為資料實體專案啟用變更追蹤。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應


### <a name="projects-supply-chain-management-to-field-service-projects"></a>專案 (Supply Chain Management 到 Field Service)：專案

[![資料整合中的範本對應。](./media/FSProject1.png)](./media/FSProject1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]