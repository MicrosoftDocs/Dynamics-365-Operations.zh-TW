---
title: 建立銷售價格選擇標準
description: 此程序說明如何為屬性型銷售價格模型建立銷售價格選擇標準。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed7083f289948033782f74dd9ed1b3c2d2a73aea
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448110"
---
# <a name="create-sales-price-selection-criteria"></a>建立銷售價格選擇標準

[!include [banner](../../includes/banner.md)]

此程序說明如何為屬性型銷售價格模型建立銷售價格選擇標準。 此程序需要至少一個可用的銷售價格模型。 此範例會使用 USMF 示範資料公司喇叭解決方案的銷售價格模型。 通常是產品經理會使用此程序。

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>為現有銷售價格模型新增標準

1. 移至 **產品資訊管理\>產品\>產品設定模型**。
1. 於清單中選擇喇叭解決方案產品模型該列，但不要選擇模型名稱的連結。
1. 在動作窗格上，選擇 **模型**。
1. 選擇 **價格模型標準**。
1. 選擇 **新增**。
1. 在 **名稱** 欄位中，輸入「Customer group 10」。
    * 價格模型標準名稱有助於識別基礎選擇標準。  
1. 在 **價格模型** 欄位中，輸入或選擇一個值。
1. 在 **訂單類型** 欄位中，選擇 *銷售訂單*。
    * 訂單類型會決定選擇查詢可用的資料庫欄位。  
1. 在 **生效日期** 欄位中，輸入一個日期。
1. 在 **到期時間** 欄位中，輸入一個日期。
1. 選擇 **儲存**。

## <a name="create-the-query-for-the-selection-criteria"></a>為選擇標準建立查詢

1. 選擇 **編輯**。
2. 在 **資料表** 欄位中，選擇 *客戶*。
3. 在 **欄位** 欄位中，選擇 *客戶群組*。
    * 在此範例中，我們將以特定客戶群組做為選擇標準。  
4. 在 **標準** 欄位中，選擇 *Customer group 10*。
5. 選擇 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]