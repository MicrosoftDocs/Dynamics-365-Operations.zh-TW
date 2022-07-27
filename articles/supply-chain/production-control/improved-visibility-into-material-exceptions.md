---
title: 掌握材料例外狀況
description: 本主題介紹如何更充分掌握生產訂單和批次訂單的原料例外狀況。
author: johanhoffmann
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, WHSProdWaveTableListPage, WHSProdWaveTableManageBOMPool
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: d3ea260535e76d7ac3d73d4bca930b7b4b2d22b2b2c076d4d1346785eaed85b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446742"
---
# <a name="visibility-into-material-exceptions"></a>掌握材料例外狀況

[!include [banner](../includes/banner.md)]

在 **生產車間管理** 工作區中，您可透過三個磚更充分瞭解生產訂單和批次訂單的原料例外狀況：

- 需要注意的未發佈物料行
- 需要注意的未處理波次
- 需要注意的未完成倉庫作業

對於所有三個磚，物料清單 (BOM) 行和配方行的原料日期會與工作區日期進行比較，此外也會與 **設定我的工作空間** 功能表之中設定的 **生產單位**、**資源群組** 和 **資源** 篩選條件進行比較。 依據預設，工作區日期設定為當前日期，但您可以對其進行調整。

如果未發佈的 BOM 行或配方行的原料日期與工作區日期相同或早於工作區日期，並且符合工作區篩選條件定義的條件，則需要注意。

在下圖中，藍色條表示在資源排程的生產作業。 該工作排程於 2017 年 5 月 1 日開始 (2017/05/01)。 此日期為原料日期。 換句話說，在 BOM 和配方行上指派給作業的材料必須在此日期準備好。 圖中的另一個日期 2017 年 5 月 6 日 (2017/05/06) 表示工作區日期。 在此範例中，原料日期早於工作區日期。 因此，原料開始消耗的日期已經過去，而且 BOM 和配方行符合需要注意的標準。

![原料日期早於工作區日期的生產作業範例。](./media/improved-visibility.png)

## <a name="unreleased-material-lines-needing-attention"></a>需要注意的未發佈物料行

可以透過三種方式將 BOM 或配方行發佈到倉庫：

- 作為生產訂單或批次訂單發佈的一部分
- 作為手動發佈
- 自動透過批次作業

有關詳細資訊，請參閱[將 BOM 和配方行發佈到倉庫](releasing-bom-and-formula-lines-to-warehouse.md)。 

如果 BOM 或配方行尚未發佈或僅部分發佈，且如果滿足工作區的日期和篩選條件，則該行將包含在 **需要注意的未發佈物料行** 磚顯示的數字計算中。

選擇磚時，會開啟 **發佈到倉庫** 頁面。 此頁面顯示未發佈的 BOM 和配方行數量，由磚上的數字指示。 未發佈的行出現在上部格線中。 此格線顯示最初為該行估計的數量、已發佈的數量以及仍必須發佈的剩餘數量。 您可以將行從上部格線新增到下部格線。 然後，您可以從較低的格線將選定的行發佈到倉庫。 從下方的格線中，您還可以調整要發佈的數量，以便只發佈部分數量。

## <a name="unprocessed-waves-needing-attention"></a>需要注意的未處理波次

發佈 BOM 或配方行時，會新增至新的生產波次或現有的開放波次中，視生產波次範本的設定而定。 透過設定波次範本，您還可以設定波次，以便在發佈 BOM 或配方行時自動處理。 處理波次時，會產生原料揀選的倉庫工作。 如果設定波次範本在發佈時不處理波次，則波次保持未處理狀態。 **需要注意的未處理波次** 磚顯示已針對未處理波次發佈到倉庫，且原料日期早於或與工作區日期相同的 BOM 和配方行數量。 這些行還必須由適用於工作區篩選條件的作業資源使用。

選擇磚時，**所有生產波次** 頁面開啟。 此頁面是由包含已發佈 BOM 波次行和配方行且符合磚條件的開放波次數量進行篩選。

### <a name="manually-maintain-production-waves"></a>手動維護生產波次

在 **所有生產波次** 頁面，您可以使用動作窗格的 **波次** 索引標籤按鈕手動 **處理** 和 **發佈** 波次。 您還可以使用 **維護生產** 選項以檢視和維護 **產品 BOM 集區** 資料，用於處理波次過程。

## <a name="open-warehouse-work-needing-attention"></a>需要注意的未完成倉庫作業

**需要注意的未完成倉庫作業** 磚顯示已發佈到倉庫、仍有未處理工作，且原料日期早於或與工作區日期相同的 BOM 和配方行數量。 這些行還必須由適用於工作區篩選條件的作業資源使用。

選擇磚時，**所有工作** 頁面開啟。 此頁面是由包含已發佈 BOM 波次行和配方行且符合磚條件工作行的未完成工作標題數量進行篩選。 您可由 **所有工作** 頁面手動處理工作。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]