---
title: 裝載建構工作台
description: 本主題介紹如何使用裝載建構工作台。
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 306ca4f77d9c1d4879d750992e51c8b83917839e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448761"
---
# <a name="load-building-workbench"></a>裝載建構工作台

[!include [banner](../../includes/banner.md)]

裝載建構工作台可讓您在建立裝載時套用裝載建構策略。

## <a name="create-a-load-building-strategy"></a>建立裝載建構策略

您會使用裝載建構策略來自動建構裝載。 此功能在以下情況下很實用：

- 如果您定期運送一組特定產品，裝載策略有助於節省時間，因為您不必每次都建構相同的裝載。
- 如果您想避免半滿裝載以最大化效率表現，則裝載策略可以幫助盡可能多填滿每個裝載。

一種稱為 `TMSLoadBuildingVolumeStrategy` 的裝載建構策略類別提供了一個名為 *體積型裝載建構策略* 的裝載建構策略。 此策略允許您使用負載範本中高度和重量的指定最大值，或者您可以輸入新值來覆蓋設定。 此策略是立即可用的唯一策略。 (但是，您可能有一些自訂策略。)

如要使用立即可用的 *體積型裝載建構策略* 策略，請在 **裝載建構工作台** 頁面 (**運輸管理 &gt; 規劃 &gt; 裝載建構工作台**) 上的 **裝載建構策略** 欄位選擇該策略。

如要建立裝載建構策略，請遵循這些步驟。

1. 前往 **運輸管理 &gt; 設定 &gt; 裝載建構 &gt; 裝載建構策略**。
1. 在動作窗格上，選擇 **產生類別清單** 以確保您擁有所有可用類別的最新版本。
1. 在動作窗格上，選擇 **新增**。
1. 輸入策略的唯一名稱，為其選擇裝載建構策略類別，然後輸入描述。
1. 在動作窗格上，選擇 **儲存**。
1. 在動作窗格上，選擇 **參數**。
1. 在 **裝載建構策略參數** 頁面上的清單中選擇 **體積容量**，然後在 **值** 欄位中，輸入應套用於新裝載建構策略的裝載總體積容量百分比。
1. 在清單中選擇 **容重值**，然後在 **值** 欄位中，輸入應套用於新裝載建構策略的裝載總容重值百分比。
1. 關閉 **裝載建構策略參數** 頁面。
1. 關閉 **裝載建構策略** 頁面。

您現在可以將裝載建構策略指派給裝載建構範本。 或者，您可以直接在負載規劃工作台中使用它。

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a>在裝載建構工作台中使用裝載建構策略

1. 前往 **運輸管理 &gt; 規劃 &gt; 裝載建構工作台**。
1. 請執行以下其中一個步驟：

    - 在 **裝載建構策略** 欄位中選擇策略。
    - 如果您已定義裝載建構範本並為其指派裝載建構策略，則請在動作窗格的 **管理範本** 索引標籤上，選擇 **套用範本**。 然後，在 **套用裝載建構範本** 下拉式對話方塊中的 **裝載建構範本名稱** 欄位中選擇一個範本。

1. 在 **裝載範本順序** FastTab 上，選擇一個或多個[裝載範本](load-template.md)。 工作台將嘗試按照此處指定的順序，將裝載納入這些類型的容器中。 通常，您應將最小的容器放在清單頂部，以確保首先選擇最小的可能容器。
1. 在動作窗格上，選擇 **建議裝載**。
1. 檢閱建議的裝載和建議的裝載明細。
1. 在動作窗格上，選擇 **建立裝載** 以在 **建議的裝載明細** FastTab 上建立根據來源文件明細的裝載。
1. 關閉 **裝載建構工作台** 頁面。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]