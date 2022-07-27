---
title: 裝運集裝箱
description: 本主題描述如何為 [到岸成本] 模組設定裝運集裝箱。
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 4759faa4882bb559221708fb31e969bff12ebb0b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448143"
---
# <a name="shipping-container-setup"></a>裝運集裝箱設定

[!include [banner](../../includes/banner.md)]

本主題描述如何為 **到岸成本** 模組設定裝運集裝箱。

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a>設定裝運集裝箱類型

運輸集裝箱類型定義了在運輸和航行期間可用的運輸集裝箱類型。

若要使用運輸集裝箱類型，請移至 **到岸成本 \> 集裝箱設定 \> 運輸集裝箱類型**。 您可以在那裡查看、新增和移除集裝箱類型的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 裝運集裝箱類型 | 為裝運集裝箱類型輸入唯一的識別名稱/編號。 |
| 描述 | 輸入裝運集裝箱類型的描述。 |
| 體積 | 輸入此類運輸集裝箱中允許的最大體積。 |
| 重量 | 輸入此類運輸集裝箱中允許的最大重量。 |
| 可退貨 | 指定此類型的運輸集裝箱在航程中使用後是否可以退還給廠商。 如果此選項設定為 *是*，將這種類型的集裝箱運回始航港可能會產生額外費用。 |

## <a name="set-up-shipping-containers"></a>設定裝運集裝箱

您可以使用運輸集裝箱記錄來識別您在航程中使用的每個集裝箱。 建立航程時，您可以在此處定義的所有運輸集裝箱記錄清單中，為航程選擇特定集裝箱。 如果您的公司擁有自己的運輸集裝箱，則此功能會非常實用。

您不必為僅使用一次的裝運集裝箱輸入運輸集裝箱編號。 而是可以在建立航程時新增運輸集裝箱編號。

運輸集裝箱記錄僅用於到岸成本。 它們在標準 **運輸管理** 模組 (TMS) 中不可用。

若要使用運輸集裝箱，請移至 **到岸成本 \> 集裝箱設定 \> 運輸集裝箱**。 您可以在那裡查看、新增和移除裝運集裝箱的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 裝運集裝箱 | 為裝運集裝箱輸入唯一的識別名稱/編號。 |
| 裝運集裝箱類型 | 選擇運輸集裝箱的類型。 有關詳細資訊，請參閱本主題前面的[設定運輸集裝箱類型](#shipping-container-types)一節。 |

> [!NOTE]
> - 運輸集裝箱設定是可選的。 通常，只有當您的公司擁有自己的運輸集裝箱或經常重複使用相同的運輸集裝箱時，您才會使用它。
> - 不會計算運輸集裝箱編號的檢查碼。

## <a name="set-up-unit-types"></a><a name="unit-types"></a>設定單位類型

單元類型為運輸集裝箱建立了額外的分組和識別方法。 單位類型通常用於識別包裝貨物的集裝箱類型，例如托盤或桶。 您可以在 **所有集裝箱** 頁面上設定集裝箱時，選擇單元類型。

單位類型僅用於 [到岸成本]。 它們在 TMS 中不可用。

若要使用單位類型，請移至 **到岸成本\>容器設定\>單位類型**。 您可以在那裡查看、新增和移除單位類型的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 單位類型 | 為單位類型輸入唯一的識別名稱/編號。 |
| 描述 | 輸入單位類型的描述。 |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a>設定冷凍類型

冷凍類型為運輸集裝箱 (通常是冷凍集裝箱) 建立了額外的分組和識別方法。 您可以在 **所有集裝箱** 頁面上設定集裝箱時，選擇冷凍類型。

若要使用冷凍類型，請存取 **到岸成本 \> 集裝箱設定 \> 冷凍類型**。 您可以在那裡查看、新增和移除冷凍類型的記錄。 下表說明每筆記錄的可用欄位。

| 欄位 | 描述 |
|---|---|
| 冷凍類型 | 為冷凍類型輸入唯一的識別名稱/編號。 |
| 描述 | 輸入冷凍類型的描述。 |
