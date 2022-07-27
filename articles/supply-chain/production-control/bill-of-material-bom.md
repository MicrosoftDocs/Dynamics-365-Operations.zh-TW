---
title: 物料清單配方
description: 本主題說明物料清單 (BOM) 和配方，它們是產品和產品變型定義的核心部分。
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace, ProdBOM, ProdJournalTransBOM, ProdBOMCurrent, PmfBOMDesignerEditCoBy, ProdJournalPickingListLineSummary, ProdBOMOverview, PmfCoReqPlanning, EcoResProductProdTypeFormulaNoActiveFormulaFormPart, EcoResItemsMissingActiveRouteVersionFormPart, EcoResItemsProdTypeBOMExpiringBOMFormPart, BOMDesignerBOMVersion, BOMExpandPurch, BOMChangeLine, BOMExpandSales, EcoResItemsProdTypeBOMExpiringRouteFormPart, EngChgEcmBomDesigner, EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmBOMCopyDialog, EngChgEcmBomDesignerEditBom, BOMDesignerFilterDialog, BOMDesignerFilterDialog, BOMPartOf, BOMSetupReportFinish, EcoResItemsMissingActiveBOMVersionFormPart, BOMIdLookup, EcoResProductProdTypeFormulaNoActiveRouteFormPart, BOMExpandPurchRFQ, EngChgCaseRouteTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12a70720775d9903a875dd1759ea2372f1f3b122
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449064"
---
# <a name="bills-of-materials-and-formulas"></a>物料清單配方

[!include [banner](../includes/banner.md)]

本主題說明物料清單 (BOM) 和配方，它們是產品和產品變型定義的核心部分。 BOM 和配方指定特定產品需要的材料或成分。 配方也指定在特定生產環境中收到的聯產品和副產品。 

## <a name="bills-of-materials"></a>物料清單

物料清單 (BOM) 定義了生產產品需要的組件。 成分可以是原材料、半成品或成分。 在某些情況下，可以在 BOM 中引用服務。 但是，BOM 通常說明必要的 *物料資源*。  

當它與構建產品需要的作業和資源的途程或生產流程相結合時，BOM 構成了計算產品估計成本的基礎。  

BOM 是由以下資訊表達的單個實體：

-   BOM 識別碼
-   BOM 名稱
-   BOM 明細，說明組件和成分
-   BOM 版本，定義可使用 BOM 的產品和期間

單個 BOM 說明由唯一為識別碼識別的單個層級。 組件可能具有被 BOM 版本引用的 BOM。 在 BOM 設計器中，您可以顯示和編輯特定產品的 BOM 的完整階層。

### <a name="formulas-co-products-and-by-products"></a>配方、聯產品，和副產品

配方是 BOM 的子類型，通常用於流程製造。 除了組件和成分外，配方還說明了聯產品和副產品。 在實際版本中，需要配方版本定義配方的聯產品和副產品。 配方的定義通是常對於在配方版本定義中的一個特定成品 (配方或計劃品項)。

### <a name="boms-in-the-product-lifecycle"></a>產品生命週期中的 BOM

在產品生命週期中，可能會因各種原因建立多種類型的 BOM：

-   **草圖/草稿 BOM**–此 BOM 提供了早期設計階段所需材料的草稿估算，並幫助您對成本和估計的產品屬性進行粗略估計。 BOM 通常不用於企業資源計劃 (ERP)。
-   **工程 BOM**–當您基於現有產品組合設計產品時，通常會使用此 BOM。 工程 BOM 的結構可簡化設計過程並將複雜產品分組到工程模組中。 對於簡單的產品，工程 BOM 可以用於實際生產過程。 但是，對於其他產品，必須將工程 BOM 轉換為實際的生產 BOM。 工程 BOM 通常由 BOM 階層中的虛擬件表示。 儘管工程 BOM 可用於製造作業的計劃和執行，但這種方法可能會導致效率低下，尤其是在建立許多訂單的重複作業中。
-   **計劃 BOM**–此 BOM 用於計劃物料需求。 組件和成分的需求量是根據成品的需求計算的。 與成本核算 BOM 一樣，計劃 BOM 可能代表一段時間內使用的特定材料組合。
-   **生產 BOM**–這是用於特定生產的實際 BOM。 生產 BOM 必須考慮用於生產產品的實際資源。 在建立生產訂單、批次訂單或看板時，由虛擬件表示的多級 BOM 將折疊為一個級別並分配在訂單的作業中。
-   **成本核算 BOM** 此 BOM 用於計算產品的估計成本的價格。 例如，當使用標準成本或計算指定產品的估計計劃成本時，您可以使用成本核算 BOM。 成本核算 BOM 可以涉及預期使用的特定材料混合組和資源。 因此，您可以使用成本核算 BOM 來建立一個期間的代表性估計成本，並幫助避免隨著時間出現差異。

實作中實際使用的 BOM 類型取決於實作，也取決於業務案例和需求。 在簡單的實作中，可以將計劃 BOM、生產 BOM 和成本核算 BOM 模型化為一個 BOM。 在具有頻繁工程變更和多個替代途程的環境中，可能需要更大的 BOM 類型集。

### <a name="approval-of-boms-and-formulas"></a>核准 BOM 和配方

每個 BOM 和配方都可以分別核准並單獨未核准。 通常，當第一個相關的 BOM 版本被核准時，第一個 BOM 或配方版本就會獲得核准。 但是，在某些業務案例中，這些核准可能是流程中的不同步驟，並且可能涉及不同的流程負責者。  

請注意，如果 BOM 為未核准，則所有相關的 BOM 版本也是未核准。

## <a name="bom-and-formula-versions"></a>BOM 和配方版本
要將特定 BOM 或配方與可生產的產品變型相關聯，您必須建立 BOM 版本或配方版本。 BOM 版本和配方版本的有效性可受期間、數量、站點、特定產品尺寸和其他標準的限制。 配方版本具有額外的重要屬性，例如產量、聯產品和副產品定義，以及配方的成本分配說明。

### <a name="approval-of-bom-and-formula-versions"></a>核准 BOM 和配方版本

BOM 版本必須先獲得核准，然後才能用於規劃或製造程序。 當一個 BOM 版本被核准時，相關的 BOM 也可以被核准，這取決於使用者的選取和驗證權限。 但請注意，只有相關的 BOM 版本核准，BOM 版本才能被核准。

### <a name="activation-of-the-default-bom-or-formula-version"></a>啟用預設 BOM 或配方版本

若要將特定 BOM 或配方設定為預設的 BOM 版本或配方版本，並將由主計劃使用或用於建立生產訂單，您必須啟用該版本。 啟用版本時，將驗證指定限制 (例如，期間、站點或數量) 的版本唯一性。 如果您嘗試啟用的版本與已啟用的版本衝突，會收到錯誤訊息。 為了防止不明確的啟用，您必須停用衝突的版本或修改版本的限制 (通常是期間)。

### <a name="product-change-with-case-management"></a>案例管理的產品變更

在核准和啟用新的或已變更的 BOM 和 BOM 版本時，其產品變更案例，提供了一種查看 BOM 版本限制式的簡單方法。 對相同啟用日期，您還可以核准和啟用與特定變更相關的所有 BOM 和配方。

### <a name="alternative-bom-versions"></a>替代 BOM 版本

有時，啟用的 BOM 版本或配方版本不應使用在預測、銷售或上層產品。 在這種情況下，作為要求 (預測明細、銷售明細或 BOM 明細) 的一部分，您可以選擇特定的核准 BOM，只要備選 BOM 或配方中存在已核准的 BOM 版本或公式版本。  

建立計劃訂單、生產訂單或看板時，只要是在請求的計劃生產日期有效的任何核准的 BOM 版本，計劃員或車間主管都可以使用來計劃或生產特定產品。 使用的 BOM 版本不必啟用為預設 BOM 版本。

## <a name="bom-and-formula-lines"></a>BOM 和配方明細
為每種物料、服務或成分建立 BOM 明細。 該明細定義了指定產品變型的計劃消耗，還定義了與計劃消耗相關的各種屬性。  

BOM 明細可以具有以下明細類型：**物品**、**虛擬件**、**掛鉤供應**、**供應商**。

### <a name="item"></a>項目

對直接消耗的材料或服務，不需要進一步的展開或掛鉤供應，選取 **品項** 明細類型。

### <a name="phantom"></a>虛擬件

當您想要展開包含在 BOM 明細中的任何較低層面的 BOM 品項時，選取 **虛擬件** 明細類型。 在使用 **虛擬件** 類型的 BOM 明細的總排程、計劃成本計算或生產訂單估計，上層 BOM 明細若涉及具有虛擬 BOM 的產品變型，將替換為在該 BOM 中列為 BOM 明細的組件品項，由該產品變型適用的有效 BOM 版本決定。 如果產品變型具有適用的現行途程，則該途程的作業將合併上層路線中。  

請注意，虛擬件通常用於簡化工程過程。 在多個級別廣泛使用虛擬 BOM 會對性能產生影響，尤其是在經常重複的製造場景中。 為了提高性能，您應該避免虛擬件出現深層層次結構。 相反，使用預先展開的生產 BOM 和途程。

### <a name="pegged-supply"></a>掛鉤供應

當您要為 BOM 明細引用的任何產品變型建立子生產、BOM 明細事件看板或直接採購訂單時，可以選取 **掛鉤供應** 明細類型。 估計生產訂單時會建立從屬生產、事件看板或訂購單。 需要的品項數量會自動為生產訂單的耗用進行保留。

### <a name="vendor"></a>廠商

如果生產流程使用分包商，並且您希望為分包商自動建立從屬生產或訂購單，則選取 **供應商** 明細類型。  

**關於 BOM 中的分包作業的注意事項：** 分包商執行的服務或工作必須建立為庫存追蹤的服務項目。 您必須將服務項目作為 BOM 明細附加到上層品項。 途程必須包含指派至分包商營運資源的作業。





[!INCLUDE[footer-include](../../includes/footer-banner.md)]