---
title: 對產品配置型號新增運算式限制
description: 此流程展示如何將新的限制型運算式新增到產品配置型號。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77e8b991a2615a8f5d238acc4655f231edb6ca98
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448227"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>對產品配置型號新增運算式限制

[!include [banner](../../includes/banner.md)]

此流程展示如何將新的限制型運算式新增到產品配置型號。 顯示如果用戶選擇了金屬前罩，如何才能要求對喇叭強制套用邊角保護。 本流程使用 USMF 示範資料公司的高品質喇叭組件。

## <a name="create-an-expression-constraint"></a>建立運算式限制

1. 移至 **產品資訊管理\>產品\>產品設定模型**。
3. 在清單中，尋找並選擇所需紀錄。
    * 此範例使用高品質喇叭型號。  
4. 在列表中，選擇所選行中的連結。
5. 展開 **限制** 區段。
6. 選取 **新增**。
7. 選取 **建立**。
8. 在 **名稱** 欄位中，輸入一個值。

## <a name="enter-expression"></a>輸入運算式

1. 選取 **編輯運算式**。
    * 如果您在此階段的工作記錄中解除鎖定使用者介面，則可以使用 IntelliSense 和符號列表來組建限制運算式。  
2. 在 **ConstraintBody** 欄位，輸入 'Implies[FrontGrill=="Metal", CornerProtection] '。
    * 此運算式邏輯指出：如果前罩是金屬的，則必須選取邊角保護選項。  
3. 選取 **驗證**。
    * 驗證函式執行完限制運算式並檢查語法錯誤。  
4. 選取 **關閉**。
5. 選取 **確定**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]