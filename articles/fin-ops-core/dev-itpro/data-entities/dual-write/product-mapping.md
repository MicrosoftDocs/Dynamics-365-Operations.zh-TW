---
title: 統一的產品體驗
description: 本主題介紹財務和營運應用程式與 Dataverse 之間的產品資料整合。
author: t-benebo
ms.date: 12/12/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1b3dc1d16fc34992df0c9478b8b4d163c310b67b
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460254"
---
# <a name="unified-product-experience"></a>統一的產品體驗

[!include [banner](../../includes/banner.md)]



當商業生態系統由 Dynamics 365 應用程式 (例如 Finance、Supply Chain Management 和 Sales) 組成時，企業通常使用這些應用程式來獲取產品資料。 這是因為這些應用程式提供了強大的產品基礎結構，並輔以複雜的定價概念和準確的現有庫存資料。 使用外部 Product Lifecycle Management (PLM) 系統來獲取產品資料的企業可以將產品從財務和營運應用程式引導到其他 Dynamics 365 應用程式。 統一的產品體驗將整合的產品資料模型引入 Dataverse，以便所有應用程式使用者，包括 Power Platform 使用者，都可以利用來自財務和營運應用程式的大量產品資料。

這是來自 Sales 的產品資料模型。

![CE 中產品的資料模型。](media/dual-write-product-4.jpg)

這是來自財務和營運應用程式的產品資料模型。

![財務和營運應用程式中產品的資料模型。](media/dual-write-products-5.jpg)

這兩個產品資料模型已整合到 Dataverse 中，如下所示。

![Dynamics 365 應用程式中產品的資料模型。](media/dual-write-products-6.jpg)

產品的雙重寫入表對應旨在僅以一種方式將資料從財務和營運應用程式以接近即時的速度流向 Dataverse。 然而，產品的基礎結構已經開放，以便在需要時使其成為雙向的。 儘管您可以自訂它，但風險自負，因為 Microsoft 不推薦這種方法。

## <a name="templates"></a>範本

產品資訊包含與產品及其定義相關的所有資訊，如產品尺寸或追蹤和儲存尺寸。 如下表所示，建立了一組表對應來同步產品和相關資訊。

財務和營運應用程式 | 其他 Dynamics 365 應用程式 | 描述
-----------------------|--------------------------------|---
[所有產品](mapping-reference.md#138) | msdyn_globalproducts | 所有產品表包含財務和營運應用程式中可用的所有產品，包括已發佈產品和未發佈產品。
[CDS 發佈獨特產品](mapping-reference.md#213) | 產品 | **產品** 資料表包含定義產品的資料欄。 它包括單個產品 (具有產品子類型的產品) 和產品變型。 下表顯示對應。
[色彩](mapping-reference.md#170) | msdyn\_productcolors
[配置](mapping-reference.md#171) | msdyn\_productconfigurations
[預設訂單設定值](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[產品類別](mapping-reference.md#166) | msdyn_productcategories | 每個產品類別以及有關其結構和特徵的資訊都包含在產品類別表中。
[產品類別指派](mapping-reference.md#167) | msdyn_productcategoryassignments | 若要將產品指派給類別，可以使用產品類別指派表。
[產品類別階層](mapping-reference.md#168) | msdyn_productcategoryhierarchies | 您使用產品階層對產品進行分類或分組。 該類別階層在 Dataverse 中使用產品類別階層表可用。
[產品類別階層角色](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | 產品階層可用於 D365財務和營運應用程式中的不同角色。 它們指定使用產品類別角色表的每個角色中使用的類別。
[產品預設訂單設定 V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[產品尺寸群組](mapping-reference.md#173) | msdyn\_productdimensiongroups | 該產品尺寸組定義了哪些產品尺寸定義了產品。
[基準產品顏色](mapping-reference.md#187) | msdyn_sharedproductcolors | **共用產品顏色** 表指示特定基準產品可以有的顏色。 這個概念被移轉到 Dataverse 以保持資料一致。
[基準產品設定](mapping-reference.md#188) | msdyn_sharedproductconfigurations | **共用產品設定** 表指示特定基準產品可以有的設定。 這個概念被移轉到 Dataverse 以保持資料一致。
[基準產品大小](mapping-reference.md#190) | msdyn_sharedproductsizes | **共用產品尺寸** 表指示特定基準產品可以有的尺寸。 這個概念被移轉到 Dataverse 以保持資料一致。
[基準產品樣式](mapping-reference.md#191) | msdyn_sharedproductstyles | **共用產品樣式** 表指示特定基準產品可以有的樣式。 這個概念被移轉到 Dataverse 以保持資料一致。
[產品編號識別的條碼](mapping-reference.md#164) | msdyn\_productbarcodes | 產品條碼用於單獨識別產品。
[產品專用單位換算](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[已發佈產品 V2](mapping-reference.md#189) | msdyn\_sharedproductdetails | **msdyn\_sharedproductdetails** 表包含來自財務和營運應用程式的定義產品的資料欄，並包含產品的財務和管理資訊。
[尺寸](mapping-reference.md#174) | msdyn\_productsizes
[儲存維度群組](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | 產品儲存尺寸組表示用於定義產品在倉庫中的放置的方法。
[樣式](mapping-reference.md#178) | msdyn\_productsytles
[追蹤維度群組](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups | 產品追蹤維度組表示用於追蹤庫存中產品的方法。
[單位](mapping-reference.md#219) | uoms
[單位轉換](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="integration-of-products"></a>產品的整合

在此模型中，產品由 Dataverse 中的兩個表的組合表示：**產品** 和 **msdyn\_sharedproductdetails**。 第一個資料表包含產品的定義 (產品的唯一識別碼、產品名稱和描述)，而第二個資料表包含儲存在產品級別的資料欄。 這兩個表的組合用於根據庫存單位 (SKU) 的概念來定義產品。 每個發佈的產品都將在上述表格 (產品和共用產品詳情) 中包含其資訊。 為了追蹤所有產品 (已發佈和未發佈)，使用 **全域產品** 表。

由於產品表示為 SKU，因此可以透過以下方式在 Dataverse 中捕獲不同產品、產品主資料和產品變型的概念：

- **具有子類型產品的產品** 是自己定義的產品。 無需定義尺寸。 範例是特定的帳冊。 對於這些產品，在 **產品** 表中建立一列，在 **msdyn\_sharedproductdetails** 表中建立一列。 未建立產品系列資料列。
- **基準產品** 用作通用產品，其中包含確定業務流程中行為的定義和規則。 基於這些定義，可以產生被稱為產品變型的不同產品。 比如 T 恤就是基準產品，它可以用顏色和尺寸作為維度。 可以發佈具有這些尺寸的不同組合的變型，例如小號的藍色 T 恤或中號的綠色 T 恤。 在整合中，在產品表中為每個變型建立一列。 此列包含特定於變型的資訊，例如不同的維度。 產品的通用資訊儲存在 **msdyn\_sharedproductdetails** 表中。 (此通用資訊儲存在基準產品中。) 一旦建立發佈的基準產品 (但在發佈變型之前)，基準產品資訊就會同步到 Dataverse。
- **獨特產品** 指所有產品子類型產品和所有產品變型。

![產品的資料模型。](media/dual-write-product.png)

啟用雙重寫入函數後，財務和營運應用程式的產品將在處於 **草稿** 狀態的其他 Dynamics 365 產品中同步。 它們被新增到第一個價目表中，其貨幣與客戶業務開發應用程式中使用的貨幣相同，並在價目表名稱上使用字母排序。 換言之，它們將新增到 Dynamics 365 應用程式中的第一個價目表，該價目表與您在財務和營運應用程式中發佈產品的法定表的貨幣相符。 如果給定貨幣沒有價目表，將自動建立價目表並將產品指派給它。

將預設價目表與單位相關聯的雙重寫入外掛程式的目前的實作查詢與財務和營運應用程式關聯的貨幣，並使用價目表名稱的字母排序在客戶參與應用程式中查詢第一個價目表。 當您有多種貨幣的價目表時，若要為該貨幣設定一個預設的價目表，您必須將價目表的名稱更新為比該貨幣的任何其他價目表在字母順序上更早的名稱。 如果它沒有給定貨幣的任何價目表，則會建立一個新的價目表。

在預設情況下，財務和營運應用程式中的產品同步到處於 **草稿** 狀態的其他 Dynamics 365 應用程式。 若要將產品同步為 **有效** 狀態，以便您可以直接在銷售訂單報價中使用它，例如，需要選取以下設定：**系統 > 管理 > 系統管理 > 系統設定 > 銷售** 索引標籤並選取 **建立處於有效狀態的產品= 是**。

同步產品時，您必須在財務和營運應用程式中輸入 **銷售單位** 欄位的值，因為它是銷售中的必填欄位。

產品的雙重寫入同步不支援從 Dynamics 365 Sales 建立產品系列。

產品同步從財務和營運應用程式到 Dataverse。 這代表產品表欄的值可以在 Dataverse 中更改，但是當觸發同步時 (在財務和營運應用程式中修改產品欄時)，這將覆寫 Dataverse 中的值。

財務和營運應用程式 | 客戶業務開發應用程式 |
---|---
[CDS 發佈獨特產品](mapping-reference.md#213) | 產品 |
[已發佈產品 V2](mapping-reference.md#189) | msdyn_sharedproductdetails |
[所有產品](mapping-reference.md#138) | msdyn_globalproducts |

## <a name="product-dimensions"></a>產品尺寸

產品尺寸是識別產品變型的特徵。 四個產品尺寸 (顏色、尺寸、樣式和設定) 也對應到 Dataverse 以定義產品變型。 下圖顯示了產品尺寸顏色的資料模型。 相同的模型適用於尺寸、樣式和設定。

![產品尺寸的資料模型。](media/dual-write-product-two.png)

財務和營運應用程式 | 客戶業務開發應用程式 |
---|---
[色彩](mapping-reference.md#170) | msdyn\_productcolors
[尺寸](mapping-reference.md#174) | msdyn\_productsizes
[樣式](mapping-reference.md#178) | msdyn\_productsytles
[配置](mapping-reference.md#171) | msdyn\_productconfigurations

當產品具有不同的產品尺寸時 (例如，基準產品將尺寸和顏色作為產品尺寸)，每個不同的產品 (即每個產品多屬性) 都被定義為這些產品尺寸的組合。 例如，產品編號 B0001 是黑色特小 T 恤，而產品編號 B0002 是黑色小 T 恤。 在這種情況下，定義了產品尺寸的現有組合。 例如，前述範例中的 T 恤可以是特小號和黑色、小號和黑色、中號和黑色，或大號和黑色，但不可能是特大號和黑色。 也就是說，指定了基準產品可以採用的產品尺寸，可以根據這些值發佈變型。

為了追蹤基準產品可以採用的產品尺寸，在 Dataverse 中為每個產品尺寸建立並對應了以下資料表。 如需相關資訊，請參閱[產品資訊概述](../../../../supply-chain/pim/product-information.md)。

財務和營運應用程式 | 客戶業務開發應用程式 |
---|---
[基準產品顏色](mapping-reference.md#187) | msdyn_sharedproductcolors |
[基準產品設定](mapping-reference.md#188) | msdyn_sharedproductconfigurations |
[基準產品大小](mapping-reference.md#190) | msdyn_sharedproductsizes |
[基準產品樣式](mapping-reference.md#191) | msdyn_sharedproductstyles |
[產品編號識別的條碼](mapping-reference.md#164) | msdyn\_productbarcodes |

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>預設訂單設定和特定產品的預設訂單設定

預設訂單設定，定義採購或儲存項目的位置和倉庫、用於交易或庫存管理的最小、最大、倍數和標準數量、交貨時間、停止標誌和訂單承諾方法。 此資訊在 Dataverse 中使用預設訂單設定和特定於產品的預設訂單設定實體可用。 您可以在[預設訂單設定主題](../../../../supply-chain/production-control/default-order-settings.md)中參閱有關該函數的更多資訊。

財務和營運應用程式 | 客戶業務開發應用程式 |
---|---
[預設訂單設定值](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[產品預設訂單設定 V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>測量單位和測量單位轉換

測量單位及其各自的轉換在 Dataverse 中提供，遵循圖中所示的資料模型。

![測量單位的資料模型。](media/dual-write-product-three.png)

測量單位概念整合在財務和營運應用程式和其他 Dynamics 365 應用程式之間。 對於財務和營運應用程式中的每個單元類別，會在 Dynamics 365 應用程式中建立一個單位組，其中包含屬於該單位類別的單位。 還會為每個單位組建立一個預設基準單位。

財務和營運應用程式 | 客戶業務開發應用程式 |
---|---
[產品專用單位換算](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[單位](mapping-reference.md#219) | uoms
[單位轉換](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>財務和營運應用程式與 Dataverse 之間的單位資料相符的初始同步處理

### <a name="initial-synchronization-of-units"></a>單元的初始同步處理

啟用雙重寫入後，財務和營運應用程式中的單位將同步到其他 Dynamics 365 應用程式。 從 Dataverse 中的財務和營運應用程式同步的單位組有一個標幟集，表明它們是「外部維護」。

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>比對來自財務和營運應用程式和其他 Dynamics 365 應用程式的單位和單位類別/組資料

首先，需要注意的是單位的整合金鑰是 msdyn_symbol。 因此，此值在 Dataverse 或其他 Dynamics 365 應用程式中必須是唯一的。 因為在其他 Dynamics 365 應用程式中，定義單元的唯一性的是「單元組 ID」和「名稱」對，因此您需要考慮不同的方案來比對財務和營運應用程式和 Dataverse 之間的單中繼資料。

對於財務和營運應用程式和其他 Dynamics 365 應用程式中的單位比對/重疊：

+ **該單位屬於其他 Dynamics 365 應用中的單位組，該組對應於財務和營運應用程式應用中的關聯單位類別**。 在這種情況下，其他 Dynamics 365 應用程式中的 msdyn_symbol 欄必須使用財務和營運應用程式中的單位符號填入。 因此，何時比對資料，並且單元組將在其他 Dynamics 365 應用程式中設定為「外部維護」。
+ **該單位屬於其他 Dynamics 365 應用程式中的一個單位組，該單位組與財務和營運應用程式中的關聯單位類別不相符 (財務和營運應用程式中沒有其他 Dynamics 365 應用程式中的單位類別的現有單位類程式)。** 在這種情況下，必須用隨機字串填入 msdyn_symbol。 請注意，這個值在其他 Dynamics 365 應用程式中必須是唯一值。

對於其他 Dynamics 365 應用程式中不存在的財務和營運應用程式中的單位和單位類別：

作為雙重寫入的一部分，財務和營運應用程式的單元組及其相應的單元在其他 Dynamics 365 應用程式和 Dataverse 中被建立和同步，單元組將被設定為「外部維護」。 不需要額外的啟用載入工作。

對於財務和營運應用程式中不存在的其他 Dynamics 365 應用程式中的單位：

必須為所有單位填入 msdyn_symbol 欄。 這些單位可以一直在財務和營運應用程式中的相應單位類別 (如果存在) 中建立。 如果單元類別不存在，先必須建立與其他 Dynamics 365 應用程式單元組相符的單元類別 (請注意，如果要擴展列舉，則無法在財務和營運應用程式中建立單元類別，除非透過擴充功能)。 然後您可以建立單位。 請注意，財務和營運應用程式中的單位符號必須是之前在其他 Dynamics 365 應用程式中為該單位指定的 msdyn_symbol。

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>產品策略：維度、追蹤和儲存組

產品策略是用於定義產品及其庫存特徵的策略集。 產品尺寸組、產品追蹤維度組和儲存維度組可以作為產品策略找到。

財務和營運應用程式 | 客戶業務開發應用程式 |
---|---
[產品尺寸群組](mapping-reference.md#173) | msdyn\_productdimensiongroups |
[儲存維度群組](mapping-reference.md#177) | msdyn_productstoragedimensiongroups |
[追蹤維度群組](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups |

## <a name="product-hierarchies"></a>產品階層

財務和營運應用程式 | 客戶業務開發應用程式 |
---|---
[產品類別指派](mapping-reference.md#167) | msdyn_productcategoryassignments |
[產品類別階層](mapping-reference.md#168) | msdyn_productcategoryhierarchies |
[產品類別階層角色](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles |

## <a name="integration-key-for-products"></a>產品整合金鑰

為了在 Dynamics 365 for Finance and Operations 和 Dataverse 中的產品之間唯一識別產品，使用了整合金鑰。
對於產品，**(productnumber)** 是在 Dataverse 中識別產品的唯一金鑰。 它由以下連線組成：**(company, msdyn_productnumber)**。 **公司** 表示財務和營運應用程式中的法律實體，**msdyn_productnumber** 表示財務和營運應用程式中特定產品的產品編號。

對於其他 Dynamics 365 應用程式的使用者，產品在 UI 中使用 **msdyn_productnumber** 識別 (請注意，該欄的標籤是 **產品編號**)。 在產品表單中顯示了公司和 msydn_productnumber。 但是，沒有顯示 (productnumber) 欄，即產品的唯一金鑰。

如果您在 Dataverse 上構建應用程式，則應注意使用 **productnumber** (唯一的產品 ID) 作為整合金鑰。 不要使用 **msdyn_productnumber**，因為它不是唯一值。

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>產品的初始同步以及資料從 Dataverse 到財務和營運應用程式的移轉

### <a name="initial-synchronization-of-products"></a>產品的初始同步處理

啟用雙重寫入後，財務和營運應用程式中的產品將同步到 Dataverse 和客戶業務開發應用程式。 在發佈雙重寫入之前在 Dataverse 和其他 Dynamics 365 應用程式中建立的產品將不會更新或與財務和營運應用程式中的產品資料相符。

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>比對來自財務和營運應用程式和其他 Dynamics 365 應用程式的產品資料

如果在財務和營運應用程式以及 Dataverse 和其他 Dynamics 365 應用程式中保留 (重疊/比對) 相同的產品，當啟用雙重寫入時，財務和營運應用程式中的產品將會同步，並且重複資料列將出現在 Dataverse 中 相同的產品。
為了避免前面的情況，如果其他 Dynamics 365 應用程式的產品與財務和營運應用程式重疊/比對，那麼啟用雙重寫入的管理員必須在產品同步之前引導資料欄 **公司** (例如："USMF") 和 **msdyn_productnumber** (例如："1234：Black：S")。 換句話說，在 Dataverse 的產品中，這兩欄必須填入產品需要比對的財務和營運應用程式的相應公司，以及其產品編號。

然後，在啟用和進行同步處理時，財務和營運應用程式的產品將與 Dataverse 和其他 Dynamics 365 應用程式中的比對產品進行同步。 這適用於獨特產品和產品變體。

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>將產品資料從其他 Dynamics 365 應用程式移轉到財務和營運應用程式

如果其他 Dynamics 365 應用程式的產品沒有出現在財務和營運應用程式中，該管理員可以先使用 **EcoResReleasedProductCreationV2Entity** 來匯入財務和營運應用程式中的這些產品。 其次，比對來自財務和營運應用程式和其他 Dynamics 365 應用程式的產品資料，如上所述。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
