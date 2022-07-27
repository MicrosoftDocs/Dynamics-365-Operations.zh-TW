---
title: ER 使用財務維度作為資料來源 (第 1 節 - 設計資料模型)
description: 本主題介紹如何設定電子報表 (ER) 模型以使用財務維度作為 ER 報表的資料來源。 (第 1 節)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e165901fdbaf723ea0122f00f79c2ab2050e33db2fcad8e6d6a8d0ba53e41b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460257"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a>ER 使用財務維度作為資料來源 (第 1 節 - 設計資料模型)

[!include [banner](../../includes/banner.md)]

以下步驟說明系統管理員或電子報表開發人員如何設定電子報表 (ER) 模型以使用財務維度作為 ER 報表的資料來源。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成「建立設定提供者並將其標記為有效」程序中的步驟。


## <a name="create-a-new-data-model"></a>建立新的資料模型
1. 進入組織管理 > 工作區 > 電子報表。
    * 確保「Litware, Inc.」 提供者可供使用並標記為有效。  
2. 點選報表設定。
3. 點選建立設定即可打開下拉式對話方塊。
4. 在名稱欄位中，輸入「Financial dimensions sample model」。
5. 點選建立設定。
6. 點選設計工具。
7. 按一下新增以開啟下拉式對話方塊。
8. 在名稱欄位，輸入「Entry」。
9. 選點新增。
10. 按一下新增以開啟下拉式對話方塊。
11. 在名稱欄位，輸入「Company」。
12. 選點新增。
    * 我們將向我們的模型新增一個新的記錄清單。 此清單將顯示 (對於使用此模型作為資料來源的任何 ER 報表) 選定財務維度的設定。 每個財務維度將在此清單中顯示為一條記錄，其中包含表示維度設定的適當欄位。  
13. 按一下新增以開啟下拉式對話方塊。
14. 在名稱欄位，輸入「Dimensions setting」。
15. 在項目類型欄位中，選取「記錄清單」。
16. 選點新增。
17. 按一下新增以開啟下拉式對話方塊。
18. 在名稱欄位，輸入｢Code」。
19. 在項目類型欄位中，選取「字串」。
20. 選點新增。
21. 按一下新增以開啟下拉式對話方塊。
22. 在名稱欄位，輸入「Name」。
23. 選點新增。
24. 在樹狀結構中，選取「Entry」。
25. 按一下新增以開啟下拉式對話方塊。
26. 在名稱欄位，輸入「Journal」。
27. 在項目類型欄位中，選取「記錄清單」。
28. 選點新增。
29. 按一下新增以開啟下拉式對話方塊。
30. 在名稱欄位，輸入「Batch」。
31. 在項目類型欄位中，選取「字串」。
32. 選點新增。
33. 按一下新增以開啟下拉式對話方塊。
34. 在名稱欄位，輸入「Transaction」。
35. 在項目類型欄位中，選取「記錄清單」。
36. 選點新增。
37. 按一下新增以開啟下拉式對話方塊。
38. 在名稱欄位，輸入「Date」。
39. 在項目類型欄位中，選取「日期」。
40. 選點新增。
41. 按一下新增以開啟下拉式對話方塊。
42. 在名稱欄位，輸入「Debit」。
43. 在項目類型欄位中，選取「實數」。
44. 選點新增。
45. 按一下新增以開啟下拉式對話方塊。
46. 在名稱欄位，輸入「Credit」。
47. 選點新增。
48. 按一下新增以開啟下拉式對話方塊。
49. 在名稱欄位，輸入「Currency」。
50. 在項目類型欄位中，選取「字串」。
51. 選點新增。
52. 按一下新增以開啟下拉式對話方塊。
53. 在名稱欄位，輸入「Voucher」。
54. 選點新增。
55. 按一下新增以開啟下拉式對話方塊。
56. 在名稱欄位，輸入「Dimensions data」。
57. 在項目類型欄位中，選取「記錄清單」。
58. 選點新增。
    * 我們向我們的模型新增了一個新的記錄清單。 此清單將顯示 (對於使用此模型作為資料來源的任何 ER 報表) 選定財務維度的值。 每個財務維度將在此清單中顯示為一條記錄，其中包含表示維度值的適當欄位。 如果需要，維度名稱也將作為欄位顯示在此記錄中，以用於選取目的。  
59. 按一下新增以開啟下拉式對話方塊。
60. 在名稱欄位，輸入｢Code」。
61. 在項目類型欄位中，選取「字串」。
62. 選點新增。
63. 按一下新增以開啟下拉式對話方塊。
64. 在名稱欄位，輸入「Description」。
65. 選點新增。
66. 按一下新增以開啟下拉式對話方塊。
67. 在名稱欄位，輸入「Name」。
68. 選點新增。
69. 點選儲存。
70. 關閉頁面。

![ER 資料模型設計工具頁面。](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]