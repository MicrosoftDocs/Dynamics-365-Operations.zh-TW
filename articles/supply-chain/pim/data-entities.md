---
title: 產品資料實體
description: 本主題提供不同實體用於匯入和導出產品資料的資訊。
author: t-benebo
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 2784e552d7984bbea9c74ad800c6305ab2a216e9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447987"
---
# <a name="product-data-entities"></a>產品資料實體

[!include [banner](../includes/banner.md)]

若要匯入和導出產品資料，您必須使用資料實體。 以下資料表提供有關產品相關資料實體的詳細資料，並描述每個實體的用途。

| 實體 | 應用程式物件樹 (AOT) 名稱 (類型) | 附註 |
|--------|-------------------------------------------|-------|
| 產品 V2 | `EcoResProductV2Entity` | 該實體用於匯入和導出共用產品 - 獨特產品和基準產品。 允許更新。 不支援以 SQL 作業為基礎的設定。 可用於開放式資料通訊協定 (OData)。 |
| 已發佈產品 V2 | `EcoResReleasedProductV2Entity` | 該實體用於匯入和導出已發佈產品 - 獨特產品和基準產品。 允許更新。 需要先建立共用產品。 匯入新發佈的產品時，會發佈共用產品。 還有一些單獨的實體，可用於匯入和導出已發佈的基準產品和已發佈的獨特變體。 此實體不支持基於集合的 SQL 操作或刪除操作。 可用於 OData。 |
| 已發佈產品建立 V2 | `EcoResReleasedProductCreationV2Entity` | 該實體可以一次性匯入共用產品和已發佈產品。 雖然支援導出，但不建議使用這種方法，因為實體的目的是建立產品。 不支援更新。 支援有限的欄位 (建立產品對話框中可用的欄位)。 不支援以 SQL 作業為基礎的設定。 對 OData 不公開。 |
| 產品變體 | `EcoResProductVariantEntity` | 此實體用於匯入和導出共用產品變體。 允許更新。 需要先建立維度值。 整合金鑰是基準產品加上產品維度。 該實體不支援以 SQL 作業為基礎的設定。 可用於 OData。 支援刪除作業。 無法透過新增新的產品維度擴展。 |
| 按產品編號識別的產品變體 | `EcoResProductNumberIdentifiedProductVariantEntity` | 此實體用於匯入和導出共用產品變體。 允許更新。 需要先建立維度值。 整合金鑰是產品編號 (而 **產品變體** 的整合金鑰，是基準產品加上產品維度)。 |
| 已發佈的產品變體 | `EcoResReleasedProductVariantEntity` | 該實體用於匯入和導出已發佈產品變體。 允許更新。 需要先建立共用產品變體。 匯入新發佈的產品變體時，會發佈共用產品變體。 該實體不支援以 SQL 作業為基礎的設定。 可用於 OData。 儘管支援刪除作業，但由於當前平台中的錯誤，當前使用該作業會導致資料損壞。 該實體無法透過新增新的產品維度擴展。 |
| 按產品編號識別的已發佈產品變體 | `EcoResProductNumberIdentifiedReleasedProductVariantEntity` | 該實體代表 **已發佈產品變體**，但是整合金鑰是產品編號，而不是基準產品加上產品維度。 可以透過新增新的產品維度擴展。 |
| 可銷售的已發布產品 | `EcoResSellableReleasedProductEntity` | 該實體僅用於導出可銷售產品。 可銷售產品是具有銷售訂單中使用所需資料的產品。 當產品使用 **已發佈產品** 頁面的 **驗證** 功能時，具有相同的規則。 |
| 發佈獨特產品 V2 | `EcoResDistinctProductV2Entity` | 該實體用於導出獨特產品。 這些獨特產品可以是產品、子類型產品和產品變體。 |
| 已發佈基準產品 V2 | `EcoResProductMasterV2Entity` | 該實體用於匯入和導出基準產品。 無法啟用資料管理。 |
| 項目 - 條碼 | `EcoResProductBarcodeEntityV3` | 該實體用於導出產品和條碼代號。 該實體不允許變更追蹤、更新或刪除。 若要對條碼代號使用變更追蹤、更新或刪除，請使用 **項目 - 條碼關聯** 實體。 |
| 項目 - 條碼關聯 | `EcoResProductBarcodeAssociationEntity` | 該實體用於導出產品和條碼代號。 允許變更追蹤、更新和刪除。 若要使用實體，功能 *項目 - 改進條形碼* 必須於[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)中啟用。 其實體金要為`AssociationID`，可建立條碼代號和產品之間的關聯。 若要新增支援此金鑰，當您打開該功能時，資料表`InventitemBarcodeAssociation`將為現有的項目條碼填入資料。 該資料表是使批次作業填入的，如果您的條形碼資料表有大量記錄，則運行批次作業可能需要大量時間。 因此，我們建議您計劃在適合您的業務計劃時，再啟用該功能 (並因此執行批次作業)。 |
| 產品生命週期狀態 | `EcoResProductLifecycleSateEntity` | 該實體用於匯入和導出可指配給產品的不同產品生命週期狀態。 |

> [!NOTE]
> 您可以使用 **已發佈產品 V2**，僅當已建立共用產品時，才將產品導入系統的數據實體。 否則，若要將產品導入系統，您必須使用 **建立產品** 數據實體。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]