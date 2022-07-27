---
title: 為已設定的產品變體建立產品編號命名法
description: 此程序說明如何為已設定的產品變體設定產品編號命名法，以及如何將其指派到可配置的基準產品。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7711d9832288327e700acd47fb30cce0c76e5e9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448107"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>為已設定的產品變體建立產品編號命名法

[!include [banner](../../includes/banner.md)]

此程序說明如何為已設定的產品變體設定產品編號命名法，以及如何將其指派到可配置的基準產品。 此程序還示範如何為產品配置模型元件構建設定命名法。 建立此程序的示範資料公司為 USMF。 新的產品編號命名法指派至 D0004 基準產品。 此工作通常由產品設計師完成。

## <a name="create-a-product-number-nomenclature"></a>建立產品編號命名法

1. 前往 **產品資訊管理\>設定\>產品命名法**。
1. 選擇 **新增**。
1. 在 **名稱** 欄位中，輸入一個值。
1. 在 **描述** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **基準產品編號**。
1. 選擇 **新增**。
1. 選擇 **文本常數**。
1. 在清單中，標記所選資料列。
1. 在 **文本** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **設定**。
1. 關閉頁面。

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>將產品編號命名法指派至基準產品

1. 前往 **產品資訊管理 \> 產品 \> 基準產品**。
1. 使用快速篩選器尋找記錄。 例如，在 **產品編號** 欄位使用「D」值進行篩選。
1. 在列表中，選擇所選行中的連結。
1. 選擇 **編輯**。
1. 選擇 **使用命名法** 欄位中的 *是*。
1. 在 **產品變體編號命名法** 欄位中，輸入或選擇一個值。
1. 關閉頁面。
1. 關閉頁面。

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>為產品組態模型元件創建命名法

1. 移至 **產品資訊管理\>產品\>產品設定模型**。
1. 在清單中，尋找並選擇所需紀錄。
1. 在列表中，選擇所選行中的連結。
1. 選擇 **編輯**。
1. 選擇 **使用組態命名法** 欄位中的 *是*。
1. 選擇 **新增**。
1. 選擇 **屬性值**。
1. 在清單中，標記所選資料列。
1. 在 **屬性** 欄位中，輸入或選擇一個值。
1. 選擇 **新增**。
1. 選擇 **文本常數**。
1. 在清單中，標記所選資料列。
1. 在 **文本** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **屬性值**。
1. 在清單中，標記所選資料列。
1. 在 **屬性** 欄位中，輸入或選擇一個值。
1. 選擇 **新增**。
1. 選擇 **文本常數**。
1. 在清單中，標記所選資料列。
1. 在 **文本** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **屬性值**。
1. 在清單中，標記所選資料列。
1. 在 **屬性** 欄位中，輸入或選擇一個值。
1. 選擇 **新增**。
1. 選擇 **文本常數**。
1. 在清單中，標記所選資料列。
1. 在 **文本** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **屬性值**。
1. 在清單中，標記所選資料列。
1. 在 **屬性** 欄位中，輸入或選擇一個值。
1. 選擇 **新增**。
1. 選擇 **文本常數**。
1. 在清單中，標記所選資料列。
1. 在 **文本** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **編號序列值**。
1. 在清單中，標記所選資料列。
1. 在 **編號序列** 欄位中，輸入或選擇一個值。
1. 關閉頁面。
1. 關閉頁面。
1. 關閉頁面。

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]