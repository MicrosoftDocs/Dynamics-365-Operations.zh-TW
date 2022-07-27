---
title: 產品生命週期狀態概觀
description: 產品生命週期狀態記錄已發佈產品或產品變體的生命週期狀態。
author: t-benebo
ms.date: 01/06/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: f71ce701adbe60b69b25e41810dda7adeec1d390
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449715"
---
# <a name="product-lifecycle-state-overview"></a>產品生命週期狀態概觀

[!include [banner](../includes/banner.md)]

產品生命週期狀態記錄已發佈產品或產品變體的生命週期狀態。 產品生命週期狀態由使用者 (通常是產品經理或產品主要資料經理) 定義。 特定的業務流程，例如總規劃，可能會受到特定生命週期狀態的影響。

已發佈的產品或產品變型可以與產品生命週期狀態相關，該狀態記錄特定產品或變體當前所處的生命週期狀態。 您可以透過分配狀態名稱和描述來定義許多產品生命週期狀態。 您可以選擇一種生命週期狀態作為新發佈產品的預設狀態。 已發佈的產品變型在建立時從其已發佈的基準產品繼承其產品生命週期狀態。 更改已發佈基準產品的生命週期狀態時，您可以選擇更新所有具有相同原始狀態的現有變體。  

## <a name="create-a-new-product-lifecycle-state"></a>建立新產品生命週期狀態

- 要建立新的產品生命週期狀態，請參閱 [建立新的產品生命週期狀態 ](tasks/new-product-lifecycle-state.md)。

- 要建立預設產品生命週期狀態，請參閱 [建立預設產品生命週期狀態 ](tasks/default-product-lifecycle-state.md)。

## <a name="associate-product-lifecycle-states-to-released-products"></a>將產品生命週期狀態與已發佈產品建立關聯  

有多種方法可以將產品生命週期狀態與已發佈產品或產品變型建立關聯。

- 在建立新發佈的產品時，預設 **產品生命週期狀態** 是自動指派的。
- 向法律實體發佈產品時，預設 **產品生命週期狀態** 是自動指派的。
- 在向法律實體發佈產品變型時，與此法律實體中相關聯的已發佈產品的 **產品生命週期狀態** 會自動指派給新變體。

您可以使用以下方法手動更新產品生命週期狀態：

- **已發佈產品** 清單頁面或 **詳細資料檢視表**。
- **已發佈的產品變型** 清單頁面或 **詳細資料檢視表**。
- 根據需求尋找過時的產品或產品變型，並關聯生命週期狀態。  

如需詳細資訊：

- 要將產品生命週期狀態與已發佈的基準產品建立關聯，請參閱 [將產品生命週期狀態指派給已發佈的基準產品](tasks/product-lifecycle-state-released-product-master.md)。

- 要將產品生命週期狀態與發佈產品建立關聯，請參閱 [將產品生命週期狀態指派給已發佈產品](tasks/product-lifecycle-state-released-product.md)。

## <a name="impact-on-master-planning"></a>對總規劃的影響

產品生命週期狀態只有一個控制標幟：**正在積極進行規劃**。 在預設情況下，對於所有建立的產品生命週期狀態，此設定為 **是**，但可以更改為 **否**。 當設為 **否** 時，相關的已發佈產品或已發佈的產品變型為：

- 排除在總規劃之外。
- 從 BOM 層級計算排除。

有關如何使用產品生命週期狀態從總規劃和 BOM 層級計算中排除產品的詳細資訊，請參閱 [建立產品生命週期狀態以從總規劃中排除產品](tasks/exclude-products-master-planning.md)

> [!NOTE]
> 出於效能原因，強烈建議將所有過時的已發佈產品或產品變型，尤其是在使用不可重複使用的產品設定變體時，與對總規劃停用的產品生命週期狀態建立關聯。  

## <a name="default-migration-import-and-export"></a>預設移轉、匯入和匯出

產品生命週期狀態由資料實體支援，生命週期狀態可以透過已發佈的產品資料實體或已發佈的變體資料實體設為可變狀態。

## <a name="find-obsolete-products-and-products-variants"></a>尋找過時的產品和產品變型

您可以執行模擬分析以尋找過時的已發佈產品或產品變型，然後更新它們的產品生命週期狀態。 要尋找過時的產品，請參閱 [尋找過時的產品變型並指派產品生命週期狀態 ](tasks/obsolete-product-variants.md)。 此主題顯示如何尋找過時的已發佈產品或產品變型，以及如何將產品生命週期狀態與過時產品建立關聯。 它也顯示如何檢視模擬結果，並評估若在沒有模擬的情況下執行更新時，將有多少產品和產品變型與新的產品生命週期狀態相關聯。  

藉由在模擬模式下執行分析，識別為過時的產品和產品變型會以特定形式顯示以便於檢閱。 該分析搜尋交易和特定主資料，以識別在可變期間內沒有需求的產品以及沒有可能導致需求的主資料。 可變時期內新發佈的產品可以排除在該分析之外。 當分析模擬傳回預期結果時，使用者可以執行分析並為所有被分析識別為過時的產品設定新的產品生命週期狀態。  

> [!NOTE]
> 請注意，所有分析和更新都必須在相同的法律實體內完成。  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>選擇和更新已發佈產品或產品變型的標準

使用下列標準選擇和更新已發佈產品及產品變型：

- 產品或產品變型的產品生命週期狀態必須不同於新的期望狀態。
- 產品或產品變型是幾天前根據您在選擇對話方塊中輸入的天數建立的。
- 該產品或產品變型沒有未結生產訂單（= 狀態 < 結束）。
- 該產品或產品變型沒有未結庫存交易（= 狀態問題 ReservPhysical 到 QuotationIssue 或狀態收據 Registrered 到 QuotationReceipt）。
- 該產品或產品變型在最後幾天內沒有庫存交易。
- 沒有該產品或產品變型的未來需求或供應預測。  
- 在該產品或產品變型的品項涵蓋範圍內沒有設定最低庫存等級。
- 該產品或產品變型沒有有效的固定數量看板規則。  
- 沒有該產品或產品變型的服務訂單行。
- 該產品或產品變型沒有有效或未來的銷售或採購合約行。
- 產品或產品變型未在 BOM 中使用，該 BOM 與積極規劃的產品或變體的未過期核准的 BOM 版本相關。

## <a name="related-topics"></a>相關主題

- [建立新的產品生命週期狀態](tasks/new-product-lifecycle-state.md)
- [建立預設產品生命週期狀態](tasks/default-product-lifecycle-state.md)
- [將產品生命週期狀態指派給已發佈的基準產品](tasks/product-lifecycle-state-released-product-master.md)
- [將產品生命週期狀態指派給已發佈產品](tasks/product-lifecycle-state-released-product.md)
- [尋找過時的產品變型並指派產品生命週期狀態](tasks/obsolete-product-variants.md)
- [建立產品生命週期狀態以從總規劃中排除產品](tasks/exclude-products-master-planning.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]