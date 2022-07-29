---
title: 為稅務計算設定啟用主資料查詢
description: 本主題說明如何設定和啟用稅務計算主資料查詢功能。
author: kai-cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 455e8becfdfa910a3733719653e1a91557b2f59a
ms.sourcegitcommit: ac23a0a1f0cc16409aab629fba97dac281cdfafb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/29/2021
ms.locfileid: "8451203"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>為稅務計算設定啟用主資料查詢 

[!include [banner](../includes/banner.md)]

本主題說明如何設定和啟用稅務計算主資料查詢功能。 下拉式列表可用在稅務計算設定中為 **法律實體**、**廠商帳戶**、**項目代碼** 和 **交付條款** 等欄位選擇值。 這些值來自使用 Microsoft Dataverse 資料來源的連接 Microsoft Dynamics 365 Finance環境。

> [!NOTE] 
> 稅務計算主資料查詢功能是可選功能。 如果您停用 Regulatory Configuration Service (RCS) 中的 **稅務服務 Dataverse資料來源支援** 功能，則可略過以下步驟。 但是，在這種情況下，下拉式列表在稅務計算設定中將不可使用。

1. 在 Microsoft Dynamics Lifecycle Services (LCS) 中設定 Microsoft Power Platform 整合。 如需更多資訊，請參閱 [Microsoft Power Platform 整合 - 增益集概觀](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md)。 完成此步驟後，Microsoft Power Platform環境的名稱會出現在 **Power Platform 整合** 部分。
2. 前往[Microsoft Power Platform 系統管理中心](https://admin.powerplatform.microsoft.com/environments)，然後選擇環境名稱。 提供了環境 URL。
3. 設定 Dynamics 365 Finance 及 Dataverse。 如需更多資訊，請參閱[獲取虛擬實體解決方案](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution)及[驗證和授權](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization)。
4. 設定以下實體。 如需更多資訊，請參閱[啟用 Microsoft Dataverse 虛擬實體](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md)。

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCityEntity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity

5. 設定 Regulatory Configuration Service (RCS)。 開啟 **功能管理** 工作區，然後啟用下列功能: 

    - 電子報告 Dataverse 資料來源支援
    - 稅務服務 Dataverse 資料來源支援
    - 全球化功能

6. 使用租用戶管理帳戶登錄 RCS。
7. 前往 **電子報告** > **連接的應用程式**。 
8. 選擇 **新增** 新增記錄，然後輸入以下欄位資訊。 

    - 在 **名稱** 欄位輸入名稱。
    - 在 **類型** 欄位選擇 **Dataverse**。
    - 在 **Application** 欄位內輸入您的 Dataverse URL。
    - 在 **租用戶** 欄位輸入您的租用戶。
    - 在 **自訂 URL** 欄位輸入您的 Dataverse URL 並附加 “/api/data/v9.1”。

9. 選擇 **檢查連接**，並完成連接程序。 

    [![檢查連接按鈕。](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. 前往 **電子報告** > **稅務設定**，並從[稅務設定 ](https://go.microsoft.com/fwlink/?linkid=2158352)匯入稅務設定。

    [![稅務設定頁面，稅務資料模型樹。](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. 如果您使用的是 Microsoft 設定，請前往 **應稅文件模型對應** 或 **Dataverse模型對應**，然後在 **連接的應用程式** 欄位選擇您在步驟 7 建立的記錄。
12. 將 **模型對應的預設** 選項設為 **是**。

    [![模型對應頁面](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
