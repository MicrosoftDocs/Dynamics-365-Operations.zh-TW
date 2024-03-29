---
title: 生產流程概覽
description: 本主題概述生產過程。 說明生產訂單、批次訂單和看板的各個階段，從訂單建立到財務期間結束。
author: johanhoffmann
ms.date: 09/13/2019
ms.topic: overview
ms.search.form: JmgShopSupervisorWorkspace, Kanban, ProdTable, ProdTableOverview, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, OpResLifecycleManagementWorkspace, ProdParmCostEstimation, ProdParmRelease, ProdSchedule, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19832"
- intro-internal
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c9eac4d3f984b6fe511d7cc5ebab67e6c24c722
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449694"
---
# <a name="production-process-overview"></a>生產流程概覽

[!include [banner](../includes/banner.md)]

本主題概述生產過程。 說明生產訂單、批次訂單和看板的各個階段，從訂單建立到財務期間結束。

產品的生產，也稱為生產生命週期的過程，遵循完成品項製造所需的特定步驟。 生命週期從建立生產訂單、批次訂單或看板開始。 以完成的製造項目結束，且該項目已準備好供客戶或其他生產階段使用。 生命週期中的每個步驟都需要不同種類的資訊來完成過程。 隨著每個步驟的完成，生產訂單、批次訂單或看板都會顯示生產狀態的變化。 不同類型的產品需要不同的製造過程。

**產品控制** 模組連結到其他模組，例如 **產品資訊管理**、**庫存管理**、**總帳**、**倉庫管理**、**項目會計**，以及 **組織管理**。 這種整合支援完成成品製造所需的資訊流程。

生產過程通常受到為特定生產過程選擇的成本會計和庫存評估方法的影響。 Supply Chain Management 支援實際成本 (先進先出\[FIFO\]；後進先出\[LIFO\]；移動平均；和定期加權平均) 和標準成本法。 精益製造是根據倒推成本法原則實施的。

成本計量方法的選擇也定義報告生產過程中材料和資源消耗的要求。 通常，實際成本方法需要準確報告工作級別，而定期成本計算方法允許對材料和資源消耗進行較少精度的報告。

## <a name="mixed-mode-manufacturing"></a>混合模式製造

不同的產品和生產拓撲需要應用不同的訂單類型。 Supply Chain Management 可以透過混合模式應用各種訂單類型。 換句話說，所有訂單類型都可以在生產一種成品的端到端過程中發生。

- **產品訂單**–這是在特定日期以給定數量生產特定產品或產品變型的經典訂單類型。 生產訂單以物料清單 (BOM) 和路線作為根據。
- **批次訂單**–此訂單類型用於流程工業和離散流程，其中製造轉換以公式為根據，或者聯產品和副產品可以是最終產品，可以是主產品的補充或替代。 批次訂單使用 **配方** 類型 BOM 和路線。
- **看板**–看板用於指示以生產流程、看板規則和 BOM 為根據，具重複性的精益製造流程。
- **專案**–製造專案將產品和服務與給定的時間表和預算結合。 專案的製造部分可以透過任何其他訂單類型交付。

## <a name="manufacturing-principles"></a>製造原理

若要選擇最適用於特定產品和相關市場的製造原則，您必須考慮生產和物流的要求，以及客戶對交貨提前期的期望。

- **備貨**–這是經典的製造原則，根據預測或最低庫存補充量 (後者通常根據預測或歷史消耗量計算) 為庫存生產產品。
- **訂做**–標準產品按訂單生產或按訂單完成。 儘管可以使用按庫存原則進行前置生產，但價值鏈中昂貴的步驟或建立變型的步驟是由銷售訂單或轉移訂單觸發的。
- **按訂單設定**–按訂單生產原則，價值鏈的最終操作是按訂單生產的。 實際生產的產品變型不是預先定義的，而是在輸入訂單時根據銷售產品的設定模型建立。 按訂單設定原則要求給定產品線具有一定程度的流程統一性。
- **工程師訂購**–工程師訂購流程通常由專案解決，通常從工程階段開始。 在工程階段，設計和說明完成訂單所需的實際產品。 然後可以建立生產訂單、批次訂單或看板來生產產品。

## <a name="overview-of-the-production-life-cycle"></a>生產生命週期概述

對於混合模式製造的所有訂單類型，生產生命週期中的以下步驟都可能發生。 但是，並非所有這些都表示為明確的訂單狀態。

1. **已建立**–您可以手動建立生產訂單、批次訂單或看板，也可以將系統設定為根據各種需求信號產生這些項目。 總規劃透過確定計劃訂單來建立生產訂單、批次訂單或看板。 其他需求信號是來自其他生產訂單或看板的銷售訂單或掛鉤供應信號。 對於固定數量的看板，當看板登記為空白時會產生需求信號。
1. **預估**–您可以計算材料和資源消耗的預估值。 該預估為狀態為 **訂購** 的原物料產生庫存交易。 預估生產訂單或批次訂單時會產生主產品、聯產品和副產品的收據。 如果 BOM 包含以下明細 **掛鉤供應** 類型、物料或分包作業服務的採購訂單產生，並與生產訂單或批次訂單掛鉤。 根據生產訂單的預留策略預留項目或訂單，根據參數設定計算成品價格。
1. **已排程**–您可以根據操作、單個作業或兩者來安排生產。

    - **已排程**–這種排程方法可提供粗略長期計劃。 使用此方法，您可以為生產訂單分配開始日期和結束日期。 如果生產訂單附加到路線作業，您可以將生產訂單指派給成本中心群組。
    - **作業排程**–這種排程方法提供詳細的計劃。 每項作業都分解為具有特定日期、時間和指派的作業資源的單獨作業。 如果使用有限容量，則作業會根據可用性指派給營運資源。 您可以在甘特圖中查看和變更排程。
    - **看板時間表**–看板作業在看板排程面板上排程，或根據看板規則的自動規劃設定來自動排程。

1. **已發佈**–當計劃完成並且可以提取或準備材料時，您可以下達生產訂單或批次訂單。 物料可用性檢查可幫助工廠主管評估生產訂單或批次訂單的物料可用性。 您還可以列印生產訂單文件，例如揀料單、作業卡、路線卡和路線作業。 下達生產訂單後，訂單狀態會更改以指示可以開始生產。 使用倉庫管理時，生產訂單或批次訂單的下達將生產 BOM 行發佈到倉庫管理。 然後根據倉庫的設定產生倉庫波次和倉庫工作。
1. **已準備**/**已領料**– 當所有材料和資源都已暫存在生產地點時，生產 BOM 明細或看板明細將更新為狀態 **已領料**。 掛鉤供應訂單和相關的倉庫工作通常在此階段完成。 應分配和列印報告生產進度所需的看板卡或作業卡。
1. **已開始**–啟動生產訂單、批次訂單或看板時，您可以根據訂單報告材料和資源消耗。 系統可以設定為在訂單啟動時自動過帳分配給訂單的材料和資源消耗。 這種分配稱為預先耗用、向前耗用或自動消耗。 您可以透過建立額外的揀料單日記帳，將材料手動分配到生產訂單或批次訂單。 您還可以手動將人工和其他路線成本分配給訂單。 如果您使用操作排程，您可以透過建立途程卡日記帳來分配這些成本。 如果您使用作業排程，您可以透過建立作業卡日記帳來分配這些成本。 生產訂單或批量訂單可以按要求的最終數量批次啟動。 在生產訂單、批次訂單或看板中，建立的作業可以透過日誌、製造執行終端 (MES 終端) 或看板單獨啟動和報告。
1. 報告進度/**完全的** 作業–使用 MES 終端、生產日記帳、看板或行動掃描功能按作業或資源報告生產進度。 材料和資源消耗將會發布，相關看板、生產訂單和批次訂單的狀態可能會更新為 **已收到** 或 **報告為完成**。 根據倉庫設定，可能會建立倉庫的入庫工作。
1. **報告為完成**(產品收據)–當生產訂單或批次訂單報告為已完成時，已完成的成品數量會在庫存中更新。 該數量包括相關聯產品和副產品的數量。 如果您使用在製品 (WIP) 會計，則會產生分類帳日記帳以減少 WIP 帳戶並增加成品庫存。 計算生產訂單的成本時，會過帳生產的實際成本。 如果與生產相關的材料和人工成本尚未在日記帳中或透過預先耗用分配，則可以透過反向耗用自動分配。 透過反向耗用分配涉及庫存交易過程的事後扣除。 如果生產訂單已完成，請選擇 **結束工作** 核取方塊將剩餘狀態更改為 **結束**。 否則，將該欄位留空以啟用額外生產數量的報告。
1. **品質評估**–產品收據可以觸發建立品質訂單，實際取決於測試流程的設定和為特定產品建立的品質規則。 由於品質檢驗訂單可以更新被測產品的庫存狀態或批次屬性，因此品質評估是許多行業的強制流程。
1. **入庫** 和 **按訂單出貨**–在產品收貨和品質評估之後，可選的上架工作將收到的產品引導至下一個消費點、成品倉庫或裝運區 (如果有按訂單出貨的要求)。
1. **結束**–在生產結束之前，會針對生產的數量計算實際成本。 材料、人力和間接費用的所有估計成本都會沖銷並替換為實際成本。 如果您在執行成本計算時選取 **結束工作** 核取方塊，生產訂單狀態會變更為 **已結束**。 此狀態可防止將任何附加成本過帳到已完成的生產訂單。
1. **期間關閉**–一些成本會計原則，例如定期平均、反沖成本法、先進先出或後進先出法，需要定期活動來關閉庫存或財務期間。 一般來說，系統會在期間關閉之前嘗試報告所有材料和資源消耗，以及庫存和報廢情形的修正。 此報告通常透過使用庫存變動日記帳或調整日記帳來完成。 目標是評估每個時期營運單位的經濟績效。 在某些情況下，當使用跨越財務報告期的長期生產訂單時，生產日記帳用於報告期末的生產進度和資源消耗。

## <a name="additional-resources"></a>其他資源

- [生產意見反應](production-feedback.md)
- [產品設定模型概觀](../pim/product-configuration-models.md)
- [精益製造概述](lean-manufacturing-overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
