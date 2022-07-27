---
title: 直接將連絡人從 Sales 同步到 Supply Chain Management 中的連絡人或客戶
description: 本主題討論用於將 Contact (Contacts) 和 Contact (Customers) 實體直接從 Dynamics 365 Sales 同步到 Dynamics 365 Supply Chain Management 的範本和基礎工作。
author: Henrikan
ms.date: 10/25/2018
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
ms.openlocfilehash: 57a9c2a860e99855e841f0f4276ba2f92767c2b1
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449844"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>直接將連絡人從 Sales 同步到 Supply Chain Management 中的連絡人或客戶

[!include [banner](../includes/banner.md)]



> [!NOTE]
> 在使用 Prospect to cash 解決方案之前，您必須熟悉[將應用程式資料整合到 Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator)。

本主題討論用於將 Contact (Contacts) 和 Contact (Customers) 表格直接從 Dynamics 365 Sales 同步到 Dynamics 365 Supply Chain Management 的範本和基礎工作。

## <a name="data-flow-in-prospect-to-cash"></a>從潛在客戶到現金的資料流程

「從潛在客戶到現金」解決方案使用資料整合功能，在 Supply Chain Management 和 Sales 執行個體之間同步資料。 具備資料整合功能的從潛在客戶到現金範本，可以在 Supply Chain Management 和 Sales 之間同步處理有關帳戶、連絡人、產品、銷售報價、銷售訂單和銷售發票的資料流程。 下圖顯示了資料如何在 Supply Chain Management 和 Sales 之間同步。

[![從潛在客戶到現金中的資料流程](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>範本和工作

若要存取可用的範本，請打開 [PowerApps 系統管理中心](https://preview.admin.powerapps.com/dataintegration)。 選取 **專案**，然後選取右上角的 **新專案** 以選擇公用範本。

以下範本和基礎工作用於將 Sales 中的 Contact (Contacts) 表格同步到 Supply Chain Management 中的 Contact (Customers) 表格。

- **Data Integration 中的範本名稱**

    - 連絡人 (Sales 到 Supply Chain Management) - 直接
    - 從連絡人到客戶 (Sales 到 Supply Chain Management) - 直接

- **資料整合專案中的工作名稱**

    - 連絡人
    - ContactToCustomer

在發生連絡人同步之前，需要執行以下同步工作：科目 (Sales 到 Supply Chain Management)

## <a name="entity-sets"></a>實體集

| 銷售    | Supply Chain Management |
|----------|------------------------|
| 連絡人 | Dataverse 連絡人           |
| 連絡人 | 客戶 V2           |

## <a name="entity-flow"></a>實體流程

連絡人在 Sales 中管理並同步到 Supply Chain Management。

Sales 中的連絡人可以成為 Supply Chain Management 中的連絡人或客戶。 要決定 Sales 中的連絡人是否應作為連絡人或客戶同步到 Supply Chain Management，系統會查看 Sales 中連絡人的以下屬性：

- **與 Supply Chain Management 中的客戶同步：** 連絡人 **是活躍客戶** 設定為 **是**
- **與 Supply Chain Management 中的連絡人同步：** 連絡人 **是活躍客戶** 設定為 **否** 和 **公司** (上層客戶/連絡人) 指向一個帳戶 (不是連絡人)

## <a name="prospect-to-cash-solution-for-sales"></a>從潛在客戶到現金解決方案

一個新的 **是活躍客戶** 欄已加入連絡人。 此欄用於區分有銷售活動的連絡人和沒有銷售活動的連絡人。 **是活躍客戶** 設為 **是** 僅適用於具有相關報價、訂單或發票的連絡人。 只有這些連絡人作為客戶同步到 Supply Chain Management。

一個新的 **IsCompanyAnAccount** 欄已加入連絡人。 此欄指示連絡人是否連結到該 **帳戶** 類型的公司 (上層客戶/連絡人)。 此資訊用於將應同步到 Supply Chain Management 的連絡人識別為連絡人。

一個新的 **連絡人號碼** 欄已加入連絡人，以幫助確保整合為自然且唯一的索引鍵。 建立新連絡人時，**連絡人號碼** 值是使用數字序列自動產生。 該值包括 **CON**，後跟一個遞增的數字序列，然後後綴六個字元。 這是一個例子：**CON-01000-BVRCPS**

套用 Sales 的整合解決方案時，升級指令碼會使用前面提到的編號規則，為現有連絡人設定 **連絡人號碼** 欄。 升級指令碼也會將任何有銷售活動的連絡人的 **是活躍客戶** 欄設為 **是**。

## <a name="in-supply-chain-management"></a>在 Supply Chain Management 中

連絡人使用 **IsContactPersonExternallyMaintained** 屬性標記。 此屬性表示特定的連絡人是由外部維護。 此時外部維護的連絡人在 Sales 中維護。

## <a name="preconditions-and-mapping-setup"></a>先決條件和對應設定

### <a name="contact-to-customer"></a>連絡人對客戶

- **CustomerGroup** 在 Supply Chain Management 中必填。 為幫助防止同步錯誤，您可以在對應中指定預設值。 如果該欄在 Sales 中留空，則使用該預設值。

    預設範本值為 **10**。

- 通過新增以下動應，有助於減少 Supply Chain Management 中需要手動更新數量。 您可以使用預設值或從 **國家/地區** 或 **城市** 等對應值。

    - **SiteId** - 也可以在 Supply Chain Management 中的產品定義預設站點。 在 Supply Chain Management 需要站點以產生報價和銷售訂單。

        範本值 **SiteId** 未定義。

    - **WarehouseId** - 也可以在 Supply Chain Management 中的產品定義預設倉庫。 在 Supply Chain Management 需要倉庫以產生報價和銷售訂單。

        範本值 **WarehouseId** 未定義。

    - **LanguageId** – 用來在 Supply Chain Management 中產生報價單和銷售訂單明細的必要語言。
    
        預設範本值為 **en-us**。

## <a name="template-mapping-in-data-integration"></a>資料整合中的範本對應

下圖顯示資料整合中的範本對應範例。 

> [!NOTE]
> 對應顯示哪些欄的資訊將從 Sales 同步到 Supply Chain Management。

### <a name="contact-to-contact-example"></a>連絡人對連絡人範例

![資料整合中的連絡人對連絡人範本對應。](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer-example"></a>連絡人對客戶範例

![資料整合中的連絡人對客戶範本對應。](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>相關主題

[潛在客戶到現金](prospect-to-cash.md)

[直接將帳戶從 Sales 同步到 Supply Chain Management 中的客戶](accounts-template-mapping-direct.md)

[將產品直接從 Supply Chain Management 同步到 Sales 中的產品](products-template-mapping-direct.md)

[直接在 Sales 和 Supply Chain Management 之間同步銷售訂單](sales-order-template-mapping-direct-two-ways.md)

[將銷售發票抬頭和明細直接從 Supply Chain Management 同步到 Sales](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]