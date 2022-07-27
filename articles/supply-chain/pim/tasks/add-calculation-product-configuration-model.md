---
title: 對產品配置型號新增計算
description: 此流程展示如何將新的計算新增到產品配置型號。
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d201061ff47203f09f96dc08ff6fc8ac437a6f9e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448332"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>對產品配置型號新增計算

[!include [banner](../../includes/banner.md)]

此流程展示如何將新的計算新增到產品配置型號。 流程展示如何使用「If」運算符號建立邏輯運算式，將白色喇叭的高度設定為 10，將所有其他箱體飾面設定為 15。 本流程使用 USMF 示範資料公司的高品質喇叭組件。


## <a name="add-a-calculation"></a>新增計算

## <a name="create-calculation-expression"></a>建立計算運算式
1. 按一下編輯運算式。
2. 在 ConstraintBody 欄位中，輸入 'If[CabinetFinish=="White", 10, 15]'。
3. 按一下「驗證」。
4. 點選關閉。
5. 點選「確定」。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]