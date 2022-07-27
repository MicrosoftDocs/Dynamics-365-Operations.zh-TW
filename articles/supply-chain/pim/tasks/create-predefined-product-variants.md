---
title: 創建預定義產品的變體
description: 此程序詳細說明使用產品維度的組合，為基準產品創建產品變體。
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6d3a4ae8efd438e01c263af1c0a1746d9484e491
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449952"
---
# <a name="predefined-product-variants"></a>預定義產品的變體

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>範例案例：創建預定義產品的變體

此範例案例，說明如何使用產品維度的組合，為基準產品創建產品變體。

### <a name="make-demo-data-available"></a>設定示範資料為可用

若要遵循此案例中建議使用的值，您必須安裝示範資料，並且必須選擇 *USMF* 法律實體。

### <a name="step-1-create-a-product-master"></a>第 1 步：創建基準產品

若要創建基準產品：

1. 前往 **產品資訊管理 > 產品 > 基準產品**。
1. 選擇 **新增**。
1. 如果 **產品編號** 欄位尚未顯示數字，則輸入一個值。 只有此欄位沒有序列編號時，才需要輸入值。
1. 在 **產品名稱** 欄位中，輸入名稱。
1. 在 **產品維度群組** 欄位，選擇產品維度群組 *SizeCol* (尺寸和顏色)。
1. 選擇 **確定**，以創建並打開新的基準產品。

### <a name="step-2-add-product-dimensions"></a>第 2 步：新增產品維度

此範例顯示如何手動輸入產品維度。 您還可以選擇要使用的產品維度值中，要包含的尺寸、顏色或樣式群組。

若要新增產品維度：

1. 在新的基準產品仍然打開的情況下，選擇動作窗格上的 **產品尺寸**。
1. 打開 **尺寸** 索引標籤，並選擇工具列上的 **新增**，以新增一行到格線。 為新的列進行下列設定：
    - **尺寸：** 選擇一個大小值。
    - **名稱** – 輸入該大小的名稱。
1. 選擇工具列上的 **新增**，然後使用新的 **尺寸** 和 **名稱** 將第二個大小新增至格線。
1. 打開 **顏色** 索引標籤，並選擇工具列上的 **新增**，以新增一行到格線。 為新的列進行下列設定：
    - **顏色：** 選擇一個顏色值。
    - **名稱** – 輸入該顏色的名稱。
1. 選擇工具列上的 **新增**，然後使用新的 **顏色** 和 **名稱** 將第二個顏色新增至格線。
1. 選擇 **儲存**。
1. 關閉頁面，返回到您的新基準產品。

### <a name="step-3-generate-product-variants"></a>第 3 步：生成產品變體

> [!NOTE]
> 本節說明如何在未啟用 *變體建議頁面改進* 功能的時候，生程產品變體。 有關該功能啟用時，如何生成產品變體的詳細資訊，請參閱下一節。

若要生成產品變體：

1. 在新的基準產品仍然打開的情況下，選擇動作窗格上的 **產品變體**。
1. 在動作窗格上，選擇 **產品變體建議**。
1. 系統會生成一個清單，包含您為產品定義的所有可能尺寸和顏色組合。 選擇工具列上的 **全選**。
    - 在此範例中，選擇所有可能的變體。 如果您只想使用可能的產品維度組合的子集，請根據需要僅選中所需的複選框。  
1. 選擇 **創建**。
1. 選擇 **儲存**。

## <a name="improved-variant-suggestions"></a>改進的變體建議

*變體建議頁面改進* 功能，改進 **變體建議** 頁面，為具有大量產品維度組合的公司，解決效能與使用性的問題。 增強後的產品維度值選擇過程，讓確認與發佈一系列相關產品變體，生成變體建議的過程變得更快、更容易。

此功能新增了以下改進：

- **延遲生成變體建議：** **變體建議** 頁面，在您首次打開時不再顯示建議。 相反，您必須明確選擇您需要的值，然後選擇 **建議** 按鈕生成組合。 這使得該過程更加可見和互動。
- **尺寸值的選擇：** 當您有許多維度值時，您通常會希望只生成包含部分變體的建議 (例如，引入一組新顏色或樣式時)。 通過改進的設計，您可以選擇想要生成產品變體建議的尺寸值。 這大大增加了建議變體的相關性，並提高了系統性能和使用者生產力。

### <a name="turn-the-variant-suggestions-page-improvements-feature-on-or-off"></a>打開或關閉變體建議頁面改進功能

從 Supply Chain Management 版本 10.0.25 開始，此功能預設開啟。 管理員可以通過搜索打開或關閉 *變體建議頁面改進* 功能，其位在[功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區。

### <a name="work-with-the-improved-variant-suggestions"></a>使用改進的變體建議

若要在啟用 *變體建議頁面改進* 功能的時候，生程產品變體：

1. 如上一節所述，打開或創建基準產品，並為其新增所需的產品維度。
1. 在基準產品打開的情況下，選擇動作窗格上的 **產品變體**。
1. 在動作窗格上，選擇 **產品變體建議**。
1. 選擇每個維度要使用的值。
1. 在上方工具列，選擇 **建議**。
1. 系統會生成一個清單，包含您所選的所有可能尺寸和顏色組合。 在 **建議的變體** FastTab，選則您每個你要使用的產品維度組合核取方塊，或選擇 **全選** 以全部選擇。  
1. 選擇 **創建**，將變體新增到當前的基準產品。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
