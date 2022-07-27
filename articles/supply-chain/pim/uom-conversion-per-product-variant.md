---
title: 每個產品變型的測量單位轉換
description: 本主題說明如何為產品變型設定測量單位轉換。 它包括設定範例。
author: t-benebo
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: c02252abcaf82cb2aab928949827e25ef7cce8c2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449229"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>每個產品變型的測量單位轉換

[!include [banner](../includes/banner.md)]

本主題說明如何為各種產品變型設定測量單位轉換。

您可以使用產品變型來建立單個產品的變型，而不是建立必須維護的多個單獨產品。 例如，產品變型可能是指定尺寸和色彩的 T 恤。

先前只能在基準產品上設定單位轉換。 因此，所有產品變型都具有相同的單位轉換規則。 但當 *產品變型的測量單位轉換* 功能開啟時，如果您的 T 恤以盒裝形式出售，那麼一個盒子裡可以裝的 T 恤數量取決於 T 恤的尺寸，您現在可以在不同的上衣尺寸和用於包裝的盒子之間設定單位轉換。

## <a name="turn-on-the-feature-in-your-system"></a>在您的系統中啟用此功能

如果您尚未在系統中看到此功能，請移至 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)，然後打開 *產品變型的測量單位轉換* 功能。

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a>設定產品的每個變型單位轉換

只能為作為基準產品的產品建立產品變型。 如需詳細資訊，請參閱[建立基準產品](tasks/create-product-master.md)。 *產品變型的測量單位轉換* 功能不適用於為實際稱重流程設定的產品。

若要配置基準產品以支援每個變型的單位轉換，請執行以下步驟。

1. 前往 **產品資訊管理 \> 產品 \> 基準產品**。
1. 建立或開啟基準產品，移至其 **產品詳細資料** 頁面。
1. 設定 **啟用測量單位轉換** 選項 *是*。
1. 在動作窗格的 **產品** 索引標籤上，於 **設定** 群組中選取 **單位轉換**。
1. **單位轉換** 頁面打開。 選擇下列其中一個索引標籤：

    - **組內轉換** – 選擇此索引標籤可在屬於同一單位類別的單位之間進行轉換。
    - **組間轉換** – 選擇此索引標籤可在屬於不同單位類別的單位之間進行轉換。

1. 選擇 **新增** 以新增單位轉換。
1. 將 **建立轉換** 欄位設定為以下值之一：

    - **產品** – 如果選擇此值，您可以為基準產品設定單位轉換。 該單位轉換將用作未定義單位轉換的所有產品變型的遞補。
    - **產品變型** – 如果選擇此值，您可以為特定產品變型設定單位轉換。 使用 **產品變型** 欄位以選擇變型。

    ![新增單位轉換。](media/uom-new-conversion.png "新增的單位轉換")

1. 使用提供的其他欄位來設定單位轉換。
1. 選擇 **確定** 以儲存新的單位轉換。

> [!TIP]
> 您可以從以下任何頁面打開產品或產品變型的 **單位轉換** 頁面：
> 
> - 產品詳細資料
> - 已發佈的產品詳細資料
> - 已發佈的產品變型

## <a name="example-scenario"></a>範例案例

在本案例中，一家公司銷售小號、中號、大號和特大號的 T 恤。 T 恤定義為一種產品，不同的尺寸定義為該產品的變型。 上衣裝在盒子裡。 如果是小號、中號和大號，每個盒子可以裝五件上衣。 但如果是特大號，每個盒子裡只能容納四件上衣。

該公司希望追蹤 *件* 單位中的不同變型，但公司以 *盒子* 為單位進行出售。 對於小型、中型和大型尺寸，庫存單位和銷售單位之間的轉換為 1 盒 = 5 件。 對於特大號，轉換為 1 盒 = 4 件。

1. 從 **T 恤** 產品的 **已發佈產品詳細資料** 頁面，打開 **單位轉換** 頁面。
1. 在 **單位轉換** 頁面，為 **超大** 的已發佈產品變型設定以下單位轉換。

    | 欄位                 | 設定                 |
    |-----------------------|-------------------------|
    | 建立轉換 | 產品變型         |
    | 產品變型       | T 恤 : : 特大 : : |
    | 從單位             | 盒子                   |
    | 係數                | 4                       |
    | 到單位               | 件數                  |

1. 因為 **小號**、**中號** 和 **大號** 產品變型在 *盒子* 和 *件* 單位之間的單位轉換相同，您可以在基準產品上為其定義以下單位轉換。

    | 欄位                 | 設定 |
    |-----------------------|---------|
    | 建立轉換 | 產品 |
    | 產品               | T 恤 |
    | 從單位             | 盒子   |
    | 係數                | 5       |
    | 到單位               | 件數  |

## <a name="using-excel-to-update-the-unit-conversions"></a>使用 Excel 更新單位轉換

如果產品有許多具有不同單位轉換的產品變型，最好將單位轉換匯出到 Microsoft Excel 活頁簿，更新它們，然後將它們發佈回 Dynamics 365 Supply Chain Management。

若要將單位轉換匯出到 Excel，請在 **單位轉換** 頁面的動作窗格上，選擇 **在 Microsoft Office 中開啟**。

## <a name="additional-resources"></a>其他資源

[管理測量單位](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]