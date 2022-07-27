---
title: 整合的廠商主資料
description: 本主題介紹財務和營運應用程式與 Dataverse 之間的廠商資料整合。
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 7794f33aed7364b76a7d5ffd08a068342887e468
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460448"
---
# <a name="integrated-vendor-master"></a>整合的廠商主資料

[!include [banner](../../includes/banner.md)]



*供應商* 一詞是指供應商組織或向企業提供商品或服務的獨資經營者。 儘管 *供應商* 是 Microsoft Dynamics 365 Supply Chain Management 中的一個既定概念，但客戶業務開發應用程式中不存在供應商概念。 但是，您可以超載 **帳戶/聯絡人** 表來儲存廠商資訊。 整合的基準廠商在客戶業務開發應用程式中引入了明確的廠商概念。 您可以使用新的廠商設計或將廠商資料儲存在 **帳戶/聯絡人** 表中。 雙重寫入支援這兩種方法。

在這兩種方法中，供應商資料都整合在 Dynamics 365 Supply Chain Management、Dynamics 365 Sales、Dynamics 365 Field Service 和 Power Apps 入口網站之間。 在 Supply Chain Management 中，資料可用於採購申請和訂購單等工作流程。

## <a name="vendor-data-flow"></a>廠商資料流程

如果您不想將廠商資料儲存在 Dataverse 的 **帳戶/聯絡人** 表中，則可以使用新的廠商設計。

![廠商資料流程。](media/dual-write-vendor-data-flow.png)

如果要繼續在 **帳戶/聯絡人** 表中儲存廠商資料，可以使用擴展廠商設計。 若要使用擴展的廠商設計，您必須在雙重寫入解決方案包中設定廠商工作流程。 如需相關資訊，請參閱[在廠商設計之間切換](vendor-switch.md)。

![擴展廠商資料流程。](media/dual-write-vendor-detail.jpg)

> [!TIP]
> 如果您將 Power Apps 入口網站用於自助服務廠商，則廠商資訊可以直接流向財務和營運應用程式。

## <a name="templates"></a>範本

廠商資料包括有關廠商的所有資訊，例如廠商組、地址、聯絡資訊、付款資料和發票資料。 在廠商資料交流過程中，一組資料表對應協同工作，如下表所示。

財務和營運應用程式 | Customer Engagement 應用程式     | 描述
----------------------------|-----------------------------|------------
[CDS 聯絡人 V2](mapping-reference.md#115) | 聯絡人 | 此範本同步客戶和廠商的所有主要、次要和第三聯絡資訊。
[名稱附加](mapping-reference.md#155) | msdyn_nameaffixes | 此範本為客戶和廠商同步名稱附加參考資料。
[付款日明細 CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | 此範本為客戶和廠商同步付款日明細參考資料。
[付款日 CDS](mapping-reference.md#158) | msdyn_paymentdays | 此範本為客戶和廠商同步付款日參考資料。
[付款排程明細](mapping-reference.md#159) | msdyn_paymentschedulelines | 同步客戶和廠商的付款排程明細參考資料。
[付款排程](mapping-reference.md#160) | msdyn_paymentschedules | 此範本為客戶和廠商同步付款排程參考資料。
[付款條款](mapping-reference.md#161) | msdyn_paymentterms | 此範本為客戶和廠商同步付款條款 (付款條款) 參考資料。
[廠商 V2](mapping-reference.md#202) | msdyn_vendors | 由於財務和營運應用程式整合，使用自訂廠商解決方案的企業可以利用 Dataverse 中引入的立即可用廠商概念。
[廠商群組](mapping-reference.md#200) | msdyn_vendorgroups | 該範本同步廠商群資訊。
[廠商付款方式](mapping-reference.md#201) | msdyn_vendorpaymentmethods | 該範本同步廠商付款方式資訊。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
