---
title: 產品維度
description: 有五種產品維度 - 顏色、配置、尺寸、樣式及版本。 您在維度群組中組合產品維度，並將維度群組指派基準產品。 產品維度的組合可決定如何定義產品變型。
author: t-benebo
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 46079daafc744421abcbdf0a3539428f2a39f13c
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449595"
---
# <a name="product-dimensions"></a>產品維度

[!include [banner](../includes/banner.md)]

有五種產品維度：顏色、配置、尺寸、樣式及版本。 您在維度群組中組合產品維度，並將維度群組指派基準產品。 產品維度的組合可決定如何定義產品變型。

產品維度是用於識別產品變型的特徵。 您可以使用產品維度組合來定義產品變型。 您必須為基準產品定義至少一個產品維度，才能建立產品變型。

## <a name="product-variants"></a>產品變型

產品變型也稱為品項。 品項是有形的產品，與服務不同。 也可以使用服務類型來定義基準產品。 透過使用服務類型，您可以指定包含服務的產品變型。 例如，您可以為諮詢工作指定基準產品，為由高級顧問與初級顧問執行的工作指定產品變型。

## <a name="product-dimensions"></a>產品維度

系統會根據產品維度值產生產品變型。

可以在以下位置建立尺寸、顏色和樣式維度的產品維度值：

- **尺寸** 頁面 (**產品資訊管理 \> 設定 \> 維度與變型群組 \> 尺寸**)
- **顏色** 頁面 (**產品資訊管理 \> 設定 \> 維度與變型群組 \> 顏色**)
- **樣式** 頁面 (**產品資訊管理 \> 設定 \> 維度與變型群組 \> 樣式**)

配置維度的產品維度值通常是使用產品設定程式或以維度為基礎的設定程式建立的。 

通常會隨著產品在其生命週期的發展，針對特定版本建立產品版本。 本主題稍後會詳細介紹產品版本。

也可以在 **產品維度** 頁面上建立與維護產品維度，您可以從以下位置存取此頁面：

- 前往 **產品資訊管理 \> 產品 \> 基準產品**。 在動作窗格上，選取 **產品維度**。
- 前往 **產品資訊管理 \> 產品 \> 所有產品和基準產品**。 選擇基準產品。 在動作窗格上，選取 **產品維度**。
- 移至 **產品資訊管理 \> 已發佈產品**。 選擇基準產品。 在動作窗格的 **產品** 索引標籤上，在 **基準產品** 群組中選取 **產品維度**。

您可以為品項建立的變型數目受可能的產品維度組合數目所限制。

> [!TIP]
> 例如，當您使用訂單行上的產品時，您可以選擇產品維度來識別您要使用的產品變型。

## <a name="example"></a>範例

有一家公司銷售牛仔褲。 *牛仔褲* 品項使用顏色和尺寸產品維度。 銷售的牛仔褲有三種不同的顏色，六種不同的尺寸。 顏色有藍色、黑色和咖啡色。 尺寸有 XS、S、M、L、XL 和 XXL。 並非所有尺寸皆提供所有三種顏色。 如果所有的組合皆可用，就會有 18 種不同類型的牛仔褲。 但是在此範例中，只會產生以下九種產品變型組合。

| 色彩 | 大小 |
|-------|------|
| 藍色  | XS   |
| 藍色  | S    |
| 藍色  | M    |
| 黑色 | M    |
| 黑色 | L    |
| 黑色 | XL   |
| 褐色 | L    |
| 褐色 | XL   |
| 褐色 | XXL  |

## <a name="the-version-product-dimension"></a>版本產品維度

版本是一個產品維度，旨於幫助您在整個供應鏈中維護和追蹤產品的多個版本。 在這個產品生命週期不斷縮短、品質和可靠性要求不斷提高，以及更加重視產品安全性的時代中，版本追蹤對於製造商營運是否成功而言至關重要。

版本作為標準產品維度，其行為將與現有產品維度 (尺寸、樣式、顏色和配置) 類似。 因此除了追蹤產品版本之外，您還可以將它用於其他目的。

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>開啟版本維度

#### <a name="before-you-turn-on-the-version-dimension"></a>開啟版本維度之前

當您開啟版本維度時，如果您已安裝其他解決方案可將自訂項目新增至庫存維度，某些功能可能會損壞或如預期停止工作。 若要讓版本維度完全發揮作用，您可能必須更新這些解決方案，便其能夠在其對庫存維度的參考中包含版本維度。

當您測試解決方案與版本維度的相容性時，請尋找以下元素：

1. **功能：** 最重要的是，必須評估任何涉及庫存維度的自訂項目，以確保它們可以與版本維度一起運作。
1. **庫存維度參考：** 注意對庫存維度的參考 (亦即明確參考維度的位置)。 對 `InventDimId` 的參考應為開箱即用，但會查尋對樣式或顏色的參考。 例如，一定要檢查以下元素：

    - 已延伸類別中的 API 呼叫
    - 對延伸代碼中特定庫存維度的所有參考 (此代碼必須與樣式、顏色和尺寸維度一起浮動)。

1. **對過時 API 呼叫的參考：** Microsoft 在引入版本維度時，曾嘗試讓過時的 API 數目盡可能降到最低。 少數已過時的 API 會在您開啟 **產品維度 - 版本** 組態金鑰時發生錯誤。 必須先在延伸的解決方案中修正對這些 API 的呼叫，您才能在生產系統中開啟版本維度。 以下是版本特有的過時 API：

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **地圖：** 如果任何地圖使用庫存維度，則必須更新對這些地圖的相對應關係對應，讓地圖能夠包含版本維度。 在已延伸模型或資料表延伸模組中，請注意其中的欄位包含庫存維度的資料表。
1. **Microsoft Dynamics 365 Commerce 功能：** 開啟後，版本維度將在 Dynamics 365 Supply Chain Management 中的整個 Commerce 特定程式碼中出現。 但是，Commerce 管道資料庫或在銷售點 (POS) 或電子商務應用程式中尚不支持版本維度。 這些 Commerce 特定的應用程式將不支援使用者按版本維度別銷售/運送或退貨/收貨庫存。 庫存可用性查詢功能在 Commerce 應用程式中不會按版本維度分辨庫存。 此行為類似於目前在整個 Commerce 中維度中設定維度的行為。

#### <a name="turn-on-the-version-dimension"></a>開啟版本維度

版本維度必須先在系統中開啟後才可供使用。 此工作需要管理員權限。

1. 前往 **系統管理 \> 工作區 \> 功能管理**。
1. 開啟名為 *產品維度版本* 的功能。 (如需詳細資訊，請參閱[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)。)
1. 讓您的系統進入[維護模式 ](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)。
1. 前往 **系統管理 \> 設定 \> 授權設定**。
1. 在 **組態金鑰** 索引標籤上，展開 **經銷商**，然後選取 **產品維度 - 版本** 核取方塊。
1. 關閉[維護模式 ](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)。

### <a name="areas-where-the-version-dimension-isnt-supported"></a>不支持版本維度的區域

以下區域不支持版本維度 (您仍然可以使用這些區域，但您將無法將版本化產品 (使用版本維度的產品) 新增至這些區域)。 例如，您不能將版本化項目新增至廠商目錄。 這是因為將具有版本維度的產品新增至這些區域會導致中斷性變更。

- 成本物件每月報表
- 成本物件報表快取
- 每件品項的 MCR 銷售統計資料
- 廠商目錄
- EcoResProductDimensionGroupEntity

此外，Commerce 中的訂單建立和訂單處理功能 (例如，針對 POS、客服中心和電子商務訂單) 不支持版本維度。 至於何時將增強 Commerce 訂單以支援它，沒有確定的時間表。

### <a name="functional-characteristics-of-the-version-dimension"></a>版本維度的功能特徵

版本維度的運作方式類似其他產品維度。 但是由於其特定的性質，且因為它旨於維護和追蹤產品的多個版本，因此它的行為略有不同。 以下是一些相異和相似之處：

- **沒有版本群組。**

    儘管尺寸、顏色和樣式 (顏色群組、尺寸群組和樣式群組) 有群組概念存在，但沒有版本群組概念。 群組可讓您預先定義適用的值，例如當您將顏色群組分配給產品時，產品可以使用該顏色群組中的所有顏色。 此概念不適用於版本維度，因為產品所採用的版本未在建立產品時預先定義。 相反的，版本是在產品的生命週期根據需要建立的。 一般而言，如果產品的形式、適配度和功能保持不變，您建立的是一個新版本，而不是新產品。

- **產品變型建議的運作方式與目前方式相同。**

    產品變型建議將為所有版本維度值建立建議，就如同它們為其他維度所做的一般。 建立和發佈版本化產品的流程與使用其他維度的產品相同。 建立版本化產品時，將建立第一個版本 (V1) 作為產品維度，並發佈變型。 隨著產品的變化而需要一個新的版本時，便會新增新的版本值 (V2)，並發佈所需的變型。 不預期會提前為產品建立所有的版本 (V1、V2 和 V3)。

> [!IMPORTANT]
> 如果您開啟並使用版本維度，則某些參考該庫存維度的解決方案可能會如預期般停止運作。 若要確認並修復這些問題，請連絡獨立軟體供應商 (ISV) 以瞭解受影響的解決方案。 如需詳細資訊，請參閱[啟用版本維度](#enable-version-dim)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]