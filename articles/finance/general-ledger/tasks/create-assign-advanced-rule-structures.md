---
title: 建立和分配進階規則結構
description: 本主題說明如何建立進階規則結構並將其分配給科目結構。
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 769f3cb44830a4bc9ef48e5bcfda5a47b87954c20f65d1d3eef5d02af9ed5bd1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450534"
---
# <a name="create-and-assign-advanced-rule-structures"></a>建立和分配進階規則結構

[!include [banner](../../includes/banner.md)]

本主題說明如何建立進階規則結構並將其分配給科目結構。 本指南使用 USMF 示範公司。

## <a name="create-an-advanced-rule-structure"></a>建立進階規則結構
1. 前往 **瀏覽窗格 > 模組 > 總帳 > 會計科目表 > 結構 > 進階規則結構**。
2. 選取 **新增** 打開下拉式對話方塊。
3. 在 **進階規則結構** 欄位，鍵入名稱來描述規則結構。
4. 選取 **確定**。
5. 選取 **新增區段**。
6. 在區段清單中，選擇財務維度。 例如，**商店**。  
7. 選取 **新增區段**。
8. 選擇 **啟用**。

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>將進階規則結構套用於科目結構
1. 前往 **瀏覽窗格 > 模組 > 總帳 > 會計科目表 > 結構 > 設定科目結構**。
2. 在清單中，找到並選擇要套用進階規則的科目結構。
3. 選擇 **編輯**。 您還可以選擇 **進階規則**，系統會提示您將科目結構設定為 **草稿模式**。  
4. 選取 **進階規則**。
5. 選取 **新增** 打開下拉式對話方塊。
6. 在 **進階規則** 欄位中輸入值。
7. 在 **名稱** 欄位中，輸入一個值。
8. 選取 **建立**。
9. 選取 **新增條件**。
10. 在 **位置** 欄位，選擇主科目或財務維度。
11. 在 **運算子** 欄位，選擇一個選項，例如 **介於** 和 **包括**。
12. 在 **值** 欄位中輸入值。
13. 在 **範圍** 欄位中輸入值。
14. 選取 **新增** 打開下拉式對話方塊。
15. 在清單中，找到滿足您輸入的條件時要使用的進階規則結構。
16. 選取 **新增**。
17. 關閉頁面。
18. 選擇 **啟用**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]