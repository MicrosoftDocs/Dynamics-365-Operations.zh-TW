---
title: 從潛在客戶到現金
description: 本主題概述了 Dynamics 365 Supply Chain Management和 Dynamics 365 Sales 之間使用的從潛在客戶到現金解決方案。
author: Henrikan
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b96f22d711ce5b34c2f8de5a86caf5f89dd3f337
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449169"
---
# <a name="prospect-to-cash"></a>從潛在客戶到現金

[!include [banner](../includes/banner.md)]

從潛在客戶到現金解決方案可提供橫跨 Dynamics 365 Supply Chain Management 和 Dynamics 365 Sales 的直接同步處理作業。 具備資料整合功能的從潛在客戶到現金範本，可以同步處理有關帳戶、連絡人、產品、銷售報價、銷售訂單和銷售發票的資料流程。 傳輸資料時，您可以在 Sales 中執行銷售和行銷活動，並可使用 Supply Chain Management 中的庫存管理來處理訂單履行。 

若需更多從潛在客戶到現金整合的資訊，請觀看 YouTube 短片 [從潛在客戶到現金整合](https://www.youtube.com/watch?v=AVV9x5x-XCg)。

在目前版本中，從潛在客戶到現金解決方案提供以下類型的直接同步：

- [直接將帳戶從 Sales 同步到 Supply Chain Management 中的客戶](accounts-template-mapping-direct.md)
- [將產品直接從 Supply Chain Management 同步到 Sales 中的產品](products-template-mapping-direct.md)
- [直接將連絡人從 Sales 同步到 Supply Chain Management 中的連絡人或客戶](contacts-template-mapping-direct.md)
- [將銷售報價抬頭和明細直接從 Sales 同步到 Supply Chain Management](sales-quotation-template-mapping-sales-fin.md)
- [直接在 Sales 和 Supply Chain Management 之間同步銷售訂單](sales-order-template-mapping-direct-two-ways.md)
- [將銷售發票抬頭和明細直接從 Supply Chain Management 同步到 Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a>Supply Chain Management 的系統要求
以下版本支援從潛在客戶到現金整合：

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations，Enterprise Edition 7.3 (2017 年 12 月)

- Dynamics 365 for Finance and Operations，Enterprise Edition (2017 年 12 月) - 應用程式組建 7.3.11971.56116 與平台更新 12 (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations，Enterprise Edition (2017 年 7 月)

- Dynamics 365 for Finance and Operations，Enterprise Edition (2017 年 7 月) - 與平台更新 8 (應用程式組建 7.2.11792.56024 與平台更新 7.0.4565.16212)。
- 需要以下修補程式：

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – 此修補程式可以透過資料整合功能，進行從 Sales 到 Supply Chain Management 的銷售訂單同步處理。 此外還提供一些其他增強功能。
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – 此修補程式可以透過資料整合功能，進行從 Supply Chain Management 到 Sales 的銷售訂單明細同步處理。
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)**– 此修補程式可以透過資料整合功能，進行從 Supply Chain Management 到 Sales 的銷售訂單同步處理。

    > [!NOTE]
    > 您只需安裝 KB4045570，因為這項安裝包含其他修補城式的異動。 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations 1611 版 (2016 年 11 月)

- Dynamics 365 for Finance and Operations 1611 版 (2016 年 11 月)，與平台更新 8 或更新版本

- 需要以下修補程式：

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - 可以透過資料整合功能，進行從 Supply Chain Management 到 Sales 的銷售訂單同步處理。 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - 可以透過資料整合功能，進行從 Supply Chain Management 到 Sales 的銷售訂單標題和明細同步處理。
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - 需要透過資料實體支援從潛在客戶到現金的整合。
    
    > [!NOTE]
    > 安裝修補程式後，您必須從 **SalesPopulateProspectToCash** 表單觸發下列批次作業。 此表單是隱藏的，因為您只需要使用此表單一次。 若要存取表單，請登入環境並將以下內容新增到瀏覽器地址中的 URL： *&mi=action:SalesPopulateProspectToCash*，例如， `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`。 表單開啟後，點選 [確定]。 這會在 **SalesLine**、**SalesQuotationLine** 和 **CustInvoiceTrans** 中填入新的 **LineCreationSequnceNumber** 欄位，其中包含不重複值，並且系統會重新整理產品清單。 這是確保潛在客戶到現金整合正常執行的必要作業。


## <a name="system-requirements-for-sales"></a>Sales 系統需求

要使用從潛在客戶到現金解決方案，您必須安裝以下組件：

- Dynamics 365 Sales 版本 1612 (8.2.1.207) (DB 8.2.1.207) 線上或更新版本
- Dynamics 365 Sales 的從潛在客戶到現金解決方案，1.15.0.0 或更新版本。 您可以在 AppSource 下載此解決方案。 [下載 Dynamics 365，從潛在客戶到現金](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]