---
title: 定義週期盤點
description: 週期盤點是一個倉庫處理程序，您可以用來稽核現有庫存項目。
author: Mirzaab
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45107dca67ac13669c468c4c32fb4adfdab2195b
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449535"
---
# <a name="define-cycle-counting"></a>定義週期盤點 

[!include [banner](../../includes/banner.md)]

週期盤點是一個倉庫處理程序，您可以用來稽核現有庫存項目。 此工作記錄會說明如何設定預設盤點工作優先順序、啟用行動裝置功能表項目來處理揀貨和盤點操作、啟用位置變成空的時候的盤點閾值觸發條件，以及如何啟用特定倉庫特定項目的週期盤點計劃。 通常，這些任務由倉庫經理執行。 您能以 USMF 示範資料公司或自己的資料執行此程序。


## <a name="set-the-priority-of-counting-work"></a>設定盤點工作優先順序
1. 在 **瀏覽窗格** 中，移至 **模組 > 倉庫管理 > 設定 > 倉庫管理參數**。
2. 按一下 **週期盤點** 索引標籤。
3. 在 **預設週期盤點工作優先順序** 欄位中，輸入一個數字。 此步驟會改變週期盤點工作相較倉庫中其他類型工作的優先順序。 若輸入的數字小於其他工作類型，代表您提高週期盤點工作的順序。  
4. 按一下 **儲存**。
5. 關閉頁面。

## <a name="enable-the-mobile-device"></a>啟用行動裝置
1. 在 **瀏覽窗格** 中，移至 **模組 > 倉庫管理 > 設定 > 行動裝置 > 行動裝置功能表項目**。
2. 按一下 **新增**。
3. 在 **功能表項目名稱** 欄位中，輸入一個值。
4. 在 **標題** 欄位中，輸入一個值。
5. 在 **模式** 欄位中，選擇「工作」。
6. 將 **使用現有工作** 選項設定為是。 此選項設定為是時，系統會在使用行動裝置功能表項目時尋找現有工作。  
7. 在 **導向** 欄位中，選擇「系統導向」。 選擇「系統導向」後，倉庫工作人員將會導向至所定義的工作類別中的未結工作。 (我們接著將建立這些工作類別。)  
8. 展開 **工作類別** fastTab。 接下來，我們將建立兩個將與此行動裝置功能表項目搭配使用的工作類別。 使用功能表項目時，將查詢這些工作類別，且使用者將看見優先順序最高的工作。  
9. 按一下 **新增**。
10. 在 **工作類別識別碼** 欄位中，選擇一個值。
11. 按一下 **新增**。
12. 在 **工作類別識別碼** 欄位中，選擇一個值。
13. 在 **動作窗格** 上，按一下 **儲存**。
14. 關閉頁面。
15. 在 **瀏覽窗格** 中，移至 **模組 > 倉庫管理 > 設定 > 行動裝置 > 行動裝置功能表**。
16. 在清單中，尋找並選擇所需紀錄。
17. 在樹狀圖中，選擇「您剛建立的功能表項目」。
18. 按一下 **編輯**。
19. 按一下箭頭，將功能表項目新增至功能表。
20. 按一下 **儲存**。

## <a name="create-a-counting-threshold"></a>建立盤點閾值
1. 在 **瀏覽窗格** 中，移至 **模組 > 倉庫管理 > 設定 > 週期盤點 > 週期盤點閾值**。
2. 按一下 **新增**。
3. 在 **週期盤點閾值識別碼** 欄位中，輸入一個值。
4. 將 **立即處理週期盤點** 選項設為是。
5. 在 **描述** 欄位中，輸入一個值。
6. 按一下 **儲存**。
7. 按一下 **選擇位置**。
8. 在清單中，標記所選資料列。
9. 在 **標準** 欄位中，選擇一個值。
10. 按一下 **確定**。
11. 關閉頁面。

## <a name="create-a-cycle-count-plan"></a>建立週期盤點計劃
1. 在 **瀏覽窗格** 中，移至 **模組 > 倉庫管理 > 設定 > 週期盤點 > 週期盤點計劃**。
2. 按一下 **新增**。
3. 在 **週期盤點計劃識別碼** 欄位中，輸入一個值。
4. 在 **描述** 欄位中，輸入一個值。
5. 在 **最大週期盤點數量** 欄位中，輸入一個數字。
6. 按一下 **儲存**。
7. 按一下 **選擇位置**。
8. 在清單中，標記所選資料列。
9. 在 **標準** 欄位中，選擇一個值。
10. 按一下 **確定**。
11. 在 **週期盤點之間的天數** 欄位中，輸入一個數字。 例如，若 **週期盤點之間的天數** 欄位設為 5，則週期盤點工作將每五天建立一次。 然而，如果在第三天處理週期盤點工作，則下一個週期盤點工作將落在上次處理週期盤點的五天後，也就是第 8 天。  
12. 按一下 **儲存**。
13. 按一下 **新增**。
14. 在 **序號** 欄位中輸入數字。 從數字最小到最大排序。 值必須大於 0 (零)。  
15. 在清單中，標記所選資料列。
16. 在 **描述** 欄位中，輸入一個值。
17. 按一下 **儲存**。
18. 按一下 **定義產品** 查詢。
19. 在清單中，標記所選資料列。
20. 在 **準則** 欄位中，輸入或選取一個值。
21. 按一下 **確定**。
22. 關閉頁面。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]