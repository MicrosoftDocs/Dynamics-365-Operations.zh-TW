---
title: 為預定義的產品變體建立產品編號命名法
description: 本主題說明如何為預定義的產品變體，設定產品編號命名法，以及如何將其分配給適當的產品維度群組。
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5179dd54f22de11dc4c0f54113376f13b2f59c48
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448218"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>為預定義的產品變體建立產品編號命名法

[!include [banner](../../includes/banner.md)]

本主題說明如何為預定義的產品變體，設定產品編號命名法，以及如何將其分配給適當的產品維度群組。 建立此程序的示範資料公司為 USMF。 新的產品編號命名法分配給顏色和大小產品維度群組。 此工作通常由產品設計師完成。


## <a name="create-a-product-number-nomenclature"></a>建立產品編號命名法

1. 前往 **產品資訊管理\>設定\>產品命名法**。
1. 選擇 **新增**。
1. 在 **名稱** 欄位中，輸入有助於識別目標產品維度群組的命名法名稱，例如：`ColorSize`。
1. 在 **描述** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **基準產品** 編號。
1. 選擇 **新增**。
1. 選擇 **文本常數**。
1. 在 **文本** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **顏色**。
1. 選擇 **新增**。
1. 選擇 **文本常數**。
1. 在 **文本** 欄位中，輸入一個值。
1. 選擇 **新增**。
1. 選擇 **大小**。
1. 關閉頁面。

## <a name="assign-the-nomenclature-to-a-product-master"></a>將命名法指派至基準產品

1. 選擇 **產品維度群組**。
2. 選擇 **SizeCol 產品維度** 群組。
3. 選擇 **編輯**。
4. 選擇 **使用命名法** 欄位中的 **是**。
5. 在 **產品變體編號命名法** 欄位中，輸入或選擇一個值。
6. 關閉頁面。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]