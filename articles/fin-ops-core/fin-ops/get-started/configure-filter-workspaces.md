---
title: 設定和過濾工作區
description: 本文概述瞭如何設定和篩選工作區。
author: jasongre
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace, HcmBenefitWorkspace, BudgetPlanningWorkspace, BusinessProcessGenericWorkspace, RetailCatalogManagementWorkspace, RetailCategoryAndProductWorkspace, RetailChannelManagementWorkspace, HcmCompensationWorkspace, CAMCostAccountingLedgerAdminWorkspace, CostAdminWorkspace, CostAnalysisWorkspace, CAMCostControlWorkspace, CustomerCollectionManagerWorkspace, CustomerInvoiceWorkspace, CustPaymentWorkspace, DataManagementWorkspace, DataValidationWorkspace, ERWorkspace, LedgerPeriodCloseProjectWorkspace, AssetWorkspace, GeneralJournalEntryWorkspace, VendVendorPortalInvoiceWorkspace, BudgetTrackingWorkspace, ReqCreatePlanWorkspace, BusinessProcessGenericOwnerWorkspace, SelfHealingWorkspace, WHSOutboundWorkMonitoringWorkspace, WHSWavePlanningWorkspace, PayrollWorkspace, HcmWorkforceWorkspace, RetailDiscountPricingWorkspace, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, EcoResProductVariantMaintainWorkspace, JmgShopSupervisorWorkspace, ProjProjectManagementWorkspace, VendVendorPortalWorkspace, PurchOrderMaintainWorkspace, PurchOrderProcessReceiptsWorkspace, HcmRecruitmentWorkspace, EcoResProductMaintainWorkspace, FMClerkWorkspace, OpResLifecycleManagementWorkspace, RetailITWorkspace, RetailChannelOperationsWorkspace, RetailStoreManagementWorkspace, SalesOrderProcessingWorkspace, SalesReturnWorkspace, SystemAdministrationWorkspaceForm, VendVendorRequestForQuotationsWorkspace, VendVendorProfileManagementWorkspace, VendInvoiceWorkspace, VendPaymentWorkspace
audience: Application User
ms.reviewer: sericks
ms.custom: 17491
ms.assetid: 541e6012-4680-4684-8494-e9b5ca4684ee
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e96b61457f222836d50a75ed15305c3c1267600c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460419"
---
# <a name="configure-and-filter-workspaces"></a>設定和過濾工作區

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本文概述瞭如何設定和篩選工作區。

## <a name="configuring-a-workspace"></a>設定工作區

您可以透過更新應用於整個工作區的設定來更改某些工作區的外觀和行為。 當可以設定工作區時，操作窗格包含一個按鈕，指示您點選它以進行設定更改。 例如，在下圖中，該按鈕被命名為 **設定我的工作區**。

[![設定和過濾工作區。](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)

點選該按鈕時，會出現一個對話方塊，您可以在其中修改工作區的預定義設定。 您在此對話方塊中看到的特定設定因工作區而異，並且取決於工作區中可用的特定控制項目和商業資料。

[![設定我的工作區。](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)

## <a name="filtering-a-workspace"></a>過濾工作區

許多工作區允許您過濾出現在其中的內容。 可用的控制項目可以讓您過濾工作區中的所有內容或僅過濾工作區特定部分中的內容。 工作區上的過濾器可以是查詢、組合方塊、自由格式文字欄位或其他類型的控制項目。 但是，每種類型的過濾器都具有相同的效果，如以下部分所述。

### <a name="workspace-wide-filters"></a>工作區範圍的過濾器

您可以使用工作區範圍的過濾器來過濾整個工作區。 工作區範圍的過濾器出現在工作區的左上角。 當您在下拉式清單中選取特定值時，工作區的內容將根據該選取進行過濾。

[![工作區過濾器。](./media/workspace-filter.png)](./media/workspace-filter.png)

當您點選打開過濾器時，您會看到幾個選項。

[![工作區過濾器擴展。](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)

選取一個選項以根據該選項過濾工作區。

### <a name="workspace-section-filters"></a>工作區區段過濾器

如果工作區的各個區段具有過濾器，您可以單獨過濾每個區段。 在下圖中，過濾器 (包含文字「過濾器」的欄位) 是自由格式文字欄位過濾器的範例。

[![工作區區段過濾器。](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)

與工作區範圍的過濾器一樣，在欄位中選取或輸入一個值以過濾該部分的內容。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]