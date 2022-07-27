---
title: ER 設定格式以進行計數和求和 (第 3 節 - 使用計算以製造輸出)
description: 本主題介紹如何設定電子報表格式以根據已產生的文字輸出的資料進行計數和求和。 (第 3 節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a59dc2ff4e4e2092911e0aec092ae8182f7601413fc220fda47766a3a0bc061
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460434"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a>ER 設定格式以進行計數和求和 (第 3 節 - 使用計算以製造輸出)

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以根據已產生的文字輸出的資料進行計數和求和。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成「ER 設定格式以進行計數和求和 (第 2 節：設定計算)」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>設定此報表以使用計數和求和資訊
1. 進入組織管理 > 工作區 > 電子報表。
2. 點選報表設定。
3. 在樹狀結構中，展開「Intrastat model」。
4. 在樹狀結構中，展開「Intrastat model\Intrastat (DE)」。
5. 在樹狀結構中，選取「Intrastat model\Intrastat (DE)\Intrastat (DE) withcounting & summing」。
6. 點選設計工具。
7. 點選對應索引標籤。
8. 點選新增根以開啟下拉式對話方塊。
    * 新增新資料來源以取得已記憶區塊的清單。  
9. 在樹狀結構中，選取「函數\匯出欄位」。
10. 在名稱欄位，輸入「$BlocksList」。
    * $BlocksList  
11. 點選編輯公式。
12. 在樹狀結構中，選取「Data collection functions\COLLECTEDLIST」。
13. 點選新增函數。
14. 點選新增資料來源。
15. 在公式欄位中，輸入「COLLECTEDLIST('$BlockName',」。
    * COLLECTEDLIST('$BlockName',  
16. 在公式欄位中，輸入「COLLECTEDLIST('$BlockName', "*")」。
    * COLLECTEDLIST('$BlockName', "*")  
17. 點選儲存。
    * 模式「*」表示所有區塊都將包含在該記錄的清單中。  
18. 關閉頁面。
19. 點選確定。
20. 點選格式索引標籤。
21. 在樹狀結構中，選取「Intrastat\Data」。
22. 點選新增以開啟下拉式對話方塊。
23. 在樹狀結構狀狀結構中，選取「Text\Sequence」。
24. 在名稱欄位中，輸入「Totals by blocks」。
    * Totals by blocks  
25. 在特殊字元欄位，選取「New line - Windows (CR LF)」。
26. 點選確定。
27. 在樹狀結構中，選取「Intrastat\Data\Totals by blocks」。
28. 點選新增以開啟下拉式對話方塊。
29. 在樹狀結構中，選取「文字\字串」。
30. 在名稱欄位，輸入｢Block code」。
    * Block code  
31. 點選確定。
32. 點選新增字串。
33. 在名稱欄位，輸入「Lines counting」。
    * Lines counting  
34. 點選確定。
35. 點選新增字串。
36. 在名稱欄位，輸入「Total amount」。
    * Total amount  
37. 點選確定。
38. 點選對應索引標籤。
39. 在樹狀結構中，選取「$BlocksList」。
40. 點選繫結。
    * 為每個記憶塊建立一個摘要行。  
41. 點選格式索引標籤。
42. 在樹狀結構中，選取「Intrastat\Data\Totals by blocks\Block code」。
43. 點選對應索引標籤。
44. 點選編輯公式。
45. 在公式欄位中，輸入「"Block id: " &」。
    * "Block id: " &  
46. 在樹狀結構中，展開「$BlocksList」。
47. 在樹狀結構中，選取「$BlocksList\Value」。
48. 點選新增資料來源。
49. 點選儲存。
50. 關閉頁面。
51. 點選格式索引標籤。
52. 在樹狀結構中，選取「Intrastat\Data\Totals by blocks\Lines counting」。
53. 點選對應索引標籤。
54. 點選編輯公式。
    * 為此報表中顯示的每個區塊的行數建立輸出。  
55. 在公式欄位中，輸入「"Number of lines in this block: " &」。
    * "Number of lines in this block: " &  
56. 在公式欄位中，輸入「"Number of lines in this block: " & TEXT(」。
    * "Number of lines in this block: " & TEXT(  
57. 在樹狀結構中，選取「Data collection functions\COUNTIFS」。
58. 點選新增函數。
59. 點選新增資料來源。
60. 在公式欄位中，輸入「"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',」。
    * "Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',  
61. 在樹狀結構中，展開「$BlocksList」。
62. 在樹狀結構中，選取「$BlocksList\Value」。
63. 點選新增資料來源。
64. 在公式欄位中，輸入「"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,」。
    * "Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,  
65. 在樹狀結構中，選取「$RecName」。
66. 點選新增資料來源。
67. 在公式欄位中，輸入「"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))」。
    * "Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
68. 點選儲存。
69. 關閉頁面。
70. 點選格式索引標籤。
71. 在樹狀結構中，選取「Intrastat\Data\Totals by blocks\Total amount」。
72. 點選對應索引標籤。
73. 點選編輯公式。
    * 建立輸出，該輸出將是此報表中顯示的每個區塊的發票金額的總和。  
74. 在公式欄位中，輸入「"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))」。
    * "Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
75. 點選儲存。
76. 關閉頁面。
77. 點選儲存。
78. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]