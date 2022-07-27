---
title: 定義部分位置週期盤點處理程序
description: 使用週期盤點計畫來建立盤點工作時，您可要求僅盤點特定產品和產品變型，而非盤點該位置上所有現有庫存，藉此引導實際的盤點操作。
author: Mirzaab
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c179b7f6e0b8546e20204a971cb2951c7b62d7b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449253"
---
# <a name="define-partial-location-cycle-counting-process"></a>定義部分位置週期盤點處理程序 

[!include [banner](../../includes/banner.md)]

使用週期盤點計畫來建立盤點工作時，您可要求僅盤點特定產品和產品變型，而非盤點該位置上所有現有庫存，藉此引導實際的盤點操作。 透過篩選特定產品，倉庫經理可以減少審查費用、有助避免合併錯誤並節省時間。 通常，倉庫經理會執行這些設定工作。 您能以 USMF 示範資料公司或自己的資料執行此程序。


## <a name="create-a-cycle-counting-work-template"></a>建立週期盤點工作範本
1. 移至倉庫管理 > 設定 > 工作 > 工作範本。
2. 在工單類型欄位中，選擇「週期盤點」。
3. 按一下新增。
4. 在序號欄位中，輸入一個數字。
    * 從數字最小到最大來排序順序。 值必須大於 0 (零)。  
5. 在清單中，標記所選資料列。
6. 在 [工作範本] 欄位輸入值。
7. 在工作範本描述欄位中，輸入一個值。
8. 在工作集區識別碼欄位中，輸入或選擇一個值。
9. 在工作優先順序欄位中，輸入一個數字。
10. 按一下儲存。
11. 按一下新增。
12. 在清單中，標記所選資料列。
13. 在工作類型欄位中，選擇「盤點」。
14. 在工作類別識別碼欄位中，輸入或選擇一個值。
15. 按一下儲存。
16. 按一下工作換行符號。
17. 按一下新增。
18. 在序號欄位中，輸入一個數字。
    * 從數字最小到最大來排序順序。 值必須大於 0 (零)。  
19. 按一下儲存。
20. 關閉頁面。
21. 關閉頁面。

## <a name="create-a-cycle-counting-plan"></a>建立週期盤點計劃
1. 移至倉庫管理 > 設定 > 週期盤點 > 週期盤點計劃。
2. 按一下新增。
3. 在週期盤點計劃識別碼欄位中，輸入一個值。
4. 在 [描述] 欄位中輸入一個值。
5. 在最大週期盤點數量欄位中，輸入一個數字。
6. 在工作範本欄位中，輸入或選擇一個值。
7. 按一下新增。
8. 在序號欄位中，輸入一個數字。
    * 從數字最小到最大來排序順序。 值必須大於 0 (零)。  
9. 在 [描述] 欄位中輸入一個值。
10. 按一下儲存。
11. 按一下定義產品查詢。
12. 在清單中，標記所選資料列。
13. 在標準欄位中，輸入或選擇一個值。
14. 按一下確定。
15. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]