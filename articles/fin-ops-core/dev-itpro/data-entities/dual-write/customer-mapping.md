---
title: 整合的客戶主資料
description: 本主題介紹 Finance and Operations 與 Dataverse 之間的客戶資料整合。
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 41e4b6c192b6125a144e4d5ef952ba0975821d44
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460366"
---
# <a name="integrated-customer-master"></a>整合的客戶主資料

[!include [banner](../../includes/banner.md)]



客戶資料可以在多個 Dynamics 365 應用程式中掌握。 例如，客戶行可以源自 Dynamics 365 Sales (Customer Engagement 應用程式) 中的銷售活動，或者可以源自 Dynamics 365 Commerce (財務和營運應用程式) 中的零售活動。 無論客戶資料來自何處，都在幕後進行整合。 整合的客戶主資料使您能夠靈活地掌握任何 Dynamics 365 應用程式中的客戶資料，並提供 Dynamics 365 應用程式套件中客戶的全面視圖。

## <a name="customer-data-flow"></a>客戶資料流程

*客戶* 是應用程式中定義明確的概念。 因此，客戶資料的整合只涉及協調兩個應用程式之間的客戶概念。 下圖顯示了客戶資料流程。

![客戶資料流程。](media/dual-write-customer-data-flow.png)

客戶可以大致分為兩類：商業/組織客戶和消費者/終端使用者。 這兩種類型的客戶在 Finance and Operations 和 Dataverse 中的儲存和處理方式不同。

在 Finance and Operations 中，商業/組織客戶和消費者/終端使用者都掌握在一個名為 **CustTable** (CustCustomerV3Entity) 的表中，並根據 **類型** 屬性對其進行分類。 (如果 **類型** 設定為 **組織**，則客戶是商業/組織客戶，如果 **類型** 設定為 **人員**，則客戶是消費者/終端使用者。) 主要聯絡人資訊透過 SMMContactPersonEntity 表處理。

在 Dataverse 中，商業/組織客戶在帳戶表中被掌握，並且在 **RelationshipType** 屬性設定為 **客戶** 時被識別為客戶。 消費者/終端使用者和聯絡人都由聯絡人資料表表示。 為了在消費者/終端使用者和聯絡人之間提供清晰的分隔，**聯絡人** 表有一個名為 **Sellable** 的布林值標誌。 當 **Sellable** 為 **True** 時，聯絡人是消費者/終端使用者，可以為該聯絡人建立報價和訂單。 當 **Sellable** 為 **False** 時，聯絡人只是客戶的主要聯絡人。

當不可售聯絡人參與報價或訂單流程時，**Sellable** 設定為 **True** 以將該聯絡人標記為可售聯絡人。 已成為可銷售聯絡人的聯絡人仍然是可銷售聯絡人。

## <a name="templates"></a>範本

客戶資料包括有關客戶的所有資訊，例如客戶組、地址、聯絡資訊、付款資料、發票資料和忠誠度狀態。 在客戶資料交流過程中，一組資料表對應協同工作，如下表所示。

財務和營運應用程式 | Customer Engagement 應用程式         | 描述
----------------------------|---------------------------------|------------
[CDS 聯絡人 V2](mapping-reference.md#115) | 聯絡人 | 此範本同步客戶和廠商的所有主要、次要和第三聯絡資訊。
[客戶群組](mapping-reference.md#126) | msdyn_customergroups | 該範本同步客戶群資訊。
[客戶付款方式](mapping-reference.md#127) | msdyn_customerpaymentmethods | 該範本同步客戶付款方式資訊。
[客戶 V3](mapping-reference.md#101) | 客戶 | 此範本同步商業和組織客戶的客戶主資訊。
[客戶 V3](mapping-reference.md#116) | 聯絡人 | 此範本為消費者和終端使用者同步客戶主資料。
[名稱附加](mapping-reference.md#155) | msdyn_nameaffixes | 此範本為客戶和廠商同步名稱附加參考資料。
[付款日明細 CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | 此範本為客戶和廠商同步付款日明細參考資料。
[付款日 CDS](mapping-reference.md#158) | msdyn_paymentdays | 此範本為客戶和廠商同步付款日參考資料。
[付款排程明細](mapping-reference.md#159) | msdyn_paymentschedulelines | 同步客戶和廠商的付款排程明細參考資料。
[付款排程](mapping-reference.md#160) | msdyn_paymentschedules | 此範本為客戶和廠商同步付款排程參考資料。
[付款條款](mapping-reference.md#161) | msdyn_paymentterms | 此範本為客戶和廠商同步付款條款 (付款條款) 參考資料。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
