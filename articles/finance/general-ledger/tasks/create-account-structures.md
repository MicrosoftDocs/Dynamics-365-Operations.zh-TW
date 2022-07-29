---
title: 建立科目結構
description: 此程序將說明如何建立科目結構。
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9ba43e243df4ba4b7c0eb6188629686206ff09b
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450918"
---
# <a name="create-account-structures"></a>建立科目結構

[!include [banner](../../includes/banner.md)]

此程序將說明如何建立科目結構。 這些步驟使用示範資料公司 USMF。

1. 前往 **瀏覽窗格 > 模組 > 總帳 > 會計科目表 > 結構 > 設定科目結構**。
2. 在 **動作窗格**，點擊 **新增** 以打開下拉式對話方塊。
3. 在 **科目結構** 欄位，輸入一個名稱來描述科目結構的用途。
4. 在 **描述** 欄位，輸入說明科目結構用途的描述。
5. 點擊 **建立**。
6. 在 **區段和允許值**，點擊 **新增區段**。
7. 在維度清單中，選擇要新增到科目結構的維度。
8. 在清單結尾，點擊 **新增區段**。
9. 根據需要重複步驟 6 到 9。
10. 在 **允許值詳細資料** 部分，選擇區段以編輯允許的值。
    例如，點擊 **主科目** 欄位。  
11. 在 **運算子** 欄位，選擇一個選項，例如 [介於並包括]。
12. 在 **值** 欄位中輸入值。 例如：600000。  
13. 在 **範圍** 欄位中輸入值。 例如：699999。  
14. 在 **允許值詳細資料** 部分，點擊 **套用**。
15. 根據需要重複步驟 10 到 15。  
16. 在 **允許值詳細資料** 部分，點擊 **新增條件**。
17. 在 [運算子] 欄位，選擇一個選項，例如 [介於並包括]。
18. 在 **值** 欄位中輸入值。 例如：033。  
19. 在 **範圍** 欄位中輸入值。 例如：034。  
20. 點擊 **套用**。
21. 在格線中，選擇區段以編輯允許的值。 例如，成本中心。  
22. 在 **成本中心** 欄位中輸入值。 例如：007..021。  
23. 在 **區段和允許值**，點擊 **新增**。
24. 在 **主科目** 欄位中，輸入一個值。 例如，600000..699999  
25. 在格線中，選擇區段以編輯允許的值。 例如：部門。  
26. 在 [部門] 欄位中輸入值。 例如：032。  
27. 在 [成本中心] 欄位中輸入值。 例如：086。  
28. 在 **動作窗格** 上，點擊 **驗證**。
29. 在 **動作窗格** 上，點擊 **啟用**。
30. 點擊 **啟用**。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
