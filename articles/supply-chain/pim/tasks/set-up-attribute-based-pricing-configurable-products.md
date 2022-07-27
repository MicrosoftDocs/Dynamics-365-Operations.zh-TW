---
title: 為可設定產品設定屬性型定價
description: 本主題說明如何設定屬性型定價。
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4acd7b423396124dd1059602f5aa6460ec5e259
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449079"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>為可設定產品設定屬性型定價

[!include [banner](../../includes/banner.md)]

本主題說明如何設定屬性型定價。 首先您必須擁有一個具有一個或多個組件和屬性的產品設定模型。 本範例使用 USMF 示範資料公司中的 [高端喇叭] 產品型號。 通常是產品經理會使用此程序。


## <a name="create-a-new-price-model"></a>建立新的價格模型

1. 移至 **產品資訊管理\>產品\>產品設定模型**。
1. 在清單中選擇 **高端喇叭** 行，但不要選擇名稱的連結。
1. 在動作窗格上，選擇 **模型**。
1. 選擇 **價格模型**。
1. 選取 **新增**。
1. 在 **價格模型名稱** 欄位中，輸入一個值。 使用易於識別的模型名稱。  
1. 在 **描述** 欄位中，輸入一個值。
1. 選取 **儲存**。

## <a name="add-price-elements"></a>新增價格元素

1. 選擇 **編輯**。 產品模型中的每個組件都可以有一個基本價格元素和任意數量的價格運算式規則。 您還可以新增不同貨幣的價格。  
2. 在 **基價價格運算式** 欄位，輸入一個值。 例如，輸入 100。 基本價格運算式可以是一個數值，也可以由涉及一個或多個屬性的算術計算組成。  
3. 選取 **新增**。
4. 在 **名稱** 欄位，輸入 `Rosewood`。 價格運算式名稱有助於識別價格元素所代表的內容。 在此範例中，我們正在為 Rosewood 喇叭箱體飾面選項建立價格元素。  
5. 選取 **編輯條件**。 價格條件有助於保證僅當存在特定屬性組合時，銷售價格中才包含價格運算式元素。  
6. 在 **ConstraintBody** 欄位中，輸入 `CabinetFinish=="Rosewood"`。
7. 選擇 **確定**。
8. 在 **運算式** 欄位中，輸入一個值。 例如，輸入 `50`。 
9. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]