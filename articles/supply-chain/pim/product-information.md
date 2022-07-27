---
title: 產品資訊概觀
description: 本主題提供有關產品資訊管理的資料。 產品資訊管理與所有法律實體的共享產品定義、分類和識別碼以及產品的特定設定一起使用，以適應業務流程。
author: t-benebo
ms.date: 06/01/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace, EcoResProductVariantPerCompanyImagePart, EcoResProductRelationType,EcoResProductAvailabilityPart,  EcoResProductReleasedSelect, EcoResProductLookup, EcoResProductVariantsPendingReleaseFormPart, EcoResProductSearchLookup, EcoResProductNumberRename, EcoResDimensionBasedConfigWorkspace, EcoResProductVariantImagePart, EcoResProductImagePart, EcoResProductVariantsPerCompanyPart, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleaseSessions, EcoResProductVariantMaintainWorkspaceConfiguration, EcoResProductProcessManufacturingWorkspaceConfiguration, EcoResProductMasterVariantsPart, EcoResProductDiscreteManufacturingWorkspaceConfiguration, EcoResProductVariantAvailabilityPart, EcoResProductInformationFactBox, EcoResProductLookupTest, EcoResProductImageTest, EcoResProductReleasedRecentlyCreatedFormPart, EcoResPhysicalProductDimensions, PdsMRCRegulatedListItem, EcoResProductAvailabilityPart, PdsMRCRestrictionList, InventItemIdLookupAllocationId, EcoResProductAvailability, EcoResProductEntityAttributeTableFieldAssociation, EcoResProductImagePart, EcoResProductRelation, EcoResProductReleaseAddProduct, EcoResProductPerCompanyListPage, EcoResProductParameters, PdsMRCRestrictedItemByCountryState, EngChgCasePreview, InventTablePreview, PdsMRCItemDetails, EngChgCaseAssociate, PdsMRCCustomerHistory, PdsMRCVendorHistory, PdsMRCRestrictedCountryStateByItem, InventItemIdGroupLookup, InventLocationLookup, PdsMRCValidityIntervalbyCountry, PdsMRCValidityIntervalbyCountry, PdsMRCEventTracker, PdsMRCReportingCountry, PdsMRCDocument, PdsMRCReportingList, PdsMRCItemCAS, GraphicsTestForm, EngChgPicklist
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c8aabeed66f864d1d1060a6452a3b554611c295
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449859"
---
# <a name="product-information-overview"></a>產品資訊概觀

[!include [banner](../includes/banner.md)]



本主題提供有關產品資訊管理的資料。 產品資訊管理與所有法律實體的共享產品定義、分類和識別碼以及產品的特定設定一起使用，以適應業務流程。 

產品資訊是所有產業供應鏈和商務應用的骨幹。 它指的是專注於集中管理產品資訊（例如，跨供應鏈）的流程和技術。 使用共享的產品定義、文件、屬性和識別碼至關重要。 在業務解決方案的各個模組中，需要特定產品的資訊和設定來管理與特定產品、產品系列或產品類別相關的業務流程。

## <a name="product-definition"></a>產品定義

產品主要由產品編號、名稱和描述來定義。 但是，為了描述產品或服務，還需要其他資料：

- 產品類型：品項或服務
- 產品子類型：獨特產品或基準產品
- 產品變型模型的定義：

     - 產品維度和維度群組
     - 產品命名法
     - 產品設定模型

- 產品與一個或多個類別的關聯
- 產品和類別屬性的定義
- 產品影像
- 附件
- 測量單位和相關轉換
- 所有名稱和描述的翻譯

## <a name="distribution-export-and-import-of-product-data"></a>產品資料的分發、匯出和匯入

可以在 Supply Chain Management 中建立產品定義。 它也可以從產品生命週期管理 (PLM)、產品資料管理 (PDM) 或產品資訊管理 (PIM) 系統中匯入。 當使用多個 Supply Chain Management 執行個體時，通常會將一個執行個體用作所有其他執行個體的產品資料主控。 這種方法由大量資料實體集合支援，這些資料實體能將產品定義資料從一個執行個體匯出和匯入到另一個執行個體。

為支援將產品資料分發到多個執行個體，Supply Chain Management 能讓您使用 Microsoft Dataverse。 產品定義可以從 Supply Chain Management 的執行個體匯出到 Microsoft Dataverse。 然後可以使用該產品定義為其他商務應用程式（例如 Dynamics 365 Sales）提供產品資料。

請注意，在動態和敏捷的組織中，產品資訊資料每天都在變化。 因此，維護準確和實際的產品資料本身就是一個關鍵的業務流程。

## <a name="product-masters-and-product-variants"></a>基準產品和產品變型

在敏捷的世界中，產品必須快速適應客戶需求，產品定義是指定一組產品而非獨特產品。 在 Supply Chain Management 中，那些一般產品被稱為 *基準產品*。 基準產品具有定義和規則，這些定義和規則指出獨特產品在業務流程中的描述和行為方式。 根據這些定義，可以產生獨特產品。 這些獨特產品被稱為 *產品變型*。

基準產品與產品維度群組和設定技術相關以指明業務規則。 產品維度（顏色、大小、樣式和設定）是一組特定的屬性，可在整個應用程式中用於定義和追蹤相關產品的特定行為。 這些維度還幫助使用者搜尋和識別產品。

## <a name="configuration-technologies"></a>設定技術

您可以在三種設定技術中進行選擇：

- 預定義的變體由預定義的產品維度定義。 變體定義包括特定有效維度組合的定義，例如顏色、樣式和大小。 每種組合都會產生獨特產品變型。
- 維度式設定通常用於製造案例，並讓您在物料清單 (BOM) 的定義中使用設定維度。 選擇特定設定後，系統會使用對該設定有效的 BOM 行子集進行規劃和生產。 這個概念也被稱為 *全球物料清單*，因為一個共用 BOM 用於產品的所有設定。
- 條件式設定使用產品設定模型來描述所有可能的屬性和所需的組件，以便在單個模型中描述產品所有可能的變體。 屬性組合的限制可以透過規則運算式或表格式限制式來描述。 設定模型和設定程式在產品資訊管理中變得更加重要，並在所有產業中使用。

當您計劃 Supply Chain Management 實作時，為業務流程選擇正確的設定技術非常重要。 產品在實作後無法從一種模型轉換為另一種模型。

## <a name="product-variant-model-definition-workspace"></a>產品變型模型定義工作區

此 **產品變型模型定義** 工作區概述了基準產品。 它還顯示向特定法律實體發佈主版和相關變體的狀態。

## <a name="released-products"></a>已發佈產品

發佈給特定法律實體的產品稱為 *已發佈產品*。 產品可以一次大量發佈給一個法律實體或多個法律實體。 因為可能必須為每個法律實體新增產品的各種屬性和屬性，所以 **已發佈產品維護** 工作區可讓您監控和完成每個法律實體或法律實體子組織中近期發佈的產品。

### <a name="released-product-maintenance-workspace"></a>已發佈產品維護工作區

您可以從 **設定我的工作區** 功能表項目設定 **已發佈產品維護** 工作區。 選擇一個類別階層和類別來篩選工作區。 要調整工作區中的相關產品資料，您還可以為 **近期發佈的產品** 和 **停止發佈的產品** 定義以天為單位的時界。

工作區由圖標摘要和兩個清單組成。 這 **未結案例** 清單顯示在所選產品類別階層中具有未完成和關閉的產品的產品變更案例。 該 **近期發佈** 清單顯示在工作區設定中所設的時界內發佈的產品。 對於清單中的每個項目，都會執行驗證，而且會顯示驗證狀態。 此狀態可能表示法律實體所需的設定尚未完成。 從清單中，您可以直接存取 **已發佈產品詳細資料**，**產品屬性維護**，**產品類別維護**，**預設訂單設定**，和 **文字翻譯** 頁面以完成產品的所需設定。

### <a name="manually-creating-a-new-released-product"></a>手動建立新發佈產品

您可以在單次執行中手動建立已發佈產品，具體取決於組織的業務流程以及有關是否應使用此功能的任何規則。 此功能建立新產品並自動將其發佈給當前的法律實體。 要建立新產品，請按一下位在 **已發佈產品維護** 工作區內或 **已發佈產品** 清單頁面上的 **已發佈產品**。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]