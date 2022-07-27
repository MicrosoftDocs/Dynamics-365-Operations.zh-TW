---
title: ER 設定格式以進行計數和求和 (第 2 節 - 設定計算)
description: 本主題介紹如何設定電子報表格式以根據已產生的文字輸出的資料進行計數和求和。 (第 2 節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66b911a7cec6bc1506edb0e4cd6757cb6834a9e977c5e43052725cfa58c1342e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460437"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a>ER 設定格式以進行計數和求和 (第 2 節 - 設定計算)

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以根據已產生的文字輸出的資料進行計數和求和。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成「ER 設定格式以進行計數和求和 (第 1 節：建立格式)」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>建立格式設定以新增計數和求和詳情
1. 進入組織管理 > 工作區 > 電子報表。
2. 點選報表設定。
3. 在樹狀結構中，展開「Intrastat model」。
4. 在樹狀結構中，選取「Intrastat model\Intrastat (DE)」。
    * 假設您需要透過在 Intrastat 報表末尾新增帶有摘要詳情的行來自訂 Microsoft 提供的格式。 為此，您需要從 Microsoft 實體衍生我們自己的 Intrastat 設定實體以進行修改。  
5. 點選建立設定即可打開下拉式對話方塊。
6. 在新建欄位中，輸入「Derive from Name: Intrastat (DE), Microsoft」。
7. 在名稱欄位中，輸入「Intrastat (DE) with counting & summing」。
8. 點選建立設定。

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>設定此報表以根據輸出詳情進行計數和匯總
1. 點選設計工具。
2. 在收集輸出詳情欄位中選取是。
    * 此標幟將在執行階段啟用收集輸出詳情以產生 Intrastat 檔案的流程。  
    * 您需要對不同的 Intrastat 方向進行計數，因此將專用模型列舉新增到此格式設定的資料來源清單中。  
3. 點選對應索引標籤。
4. 點選新增根以開啟下拉式對話方塊。
5. 在樹狀結構中，選取「Data model\Enumeration」。
6. 在名稱欄位，輸入「Direction」。
7. 在模型列舉欄位中，輸入或選取一個值。
    * 選取值方向。  
8. 點選確定。
9. 點選新增根以開啟下拉式對話方塊。
10. 在樹狀結構中，選取「函數\匯出欄位」。
11. 在名稱欄位，輸入「$BlockName」。
12. 點選編輯公式。
13. 在公式欄位中，輸入「block」。
14. 點選儲存。
15. 關閉頁面。
16. 點選確定。
17. 點選新增根以開啟下拉式對話方塊。
18. 在樹狀結構中，選取「函數\匯出欄位」。
19. 在名稱欄位，輸入「$RecName」。
20. 點選編輯公式。
21. 在公式欄位中，輸入「record」。
22. 點選儲存。
23. 關閉頁面。
24. 點選確定。
25. 點選新增根以開啟下拉式對話方塊。
26. 在樹狀結構中，選取「函數\匯出欄位」。
27. 在名稱欄位，輸入「$InvName」。
28. 點選編輯公式。
29. 在公式欄位中，輸入「InvoicedAmountEUR」。
30. 點選儲存。
31. 關閉頁面。
32. 點選確定。
33. 在樹狀結構中，選取「Intrastat\Data」。
34. 點選「收集的資料關鍵名稱」欄位的編輯按鈕
35. 點選新增資料來源。
    * $BlockName  
36. 點選儲存。
37. 關閉頁面。
38. 點選收集的資料關鍵值欄位的編輯按鈕。
39. 在公式欄位中，輸入「IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")」。
    * IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")  
40. 點選儲存。
41. 關閉頁面。
    * 計算這個序列的行數。 結果將分別與名稱｢block」一起用於不同的方向。 值「Import」將用於任何到達 Intrastat 交易。 「Export」值將用於任何 Intrastat 調度交易。 將其視為虛擬 Excel 試算表。 對於每個交易，第一資料欄「block」的資料列相應地填入了值「Import」和「Export」。  
42. 在樹狀結構中，展開「Intrastat\Data: Sequence」。
43. 在樹狀結構中，選取「Intrastat\Data: Sequence\Arrivals?」。
44. 點選「收集的資料關鍵名稱」欄位的編輯按鈕。
    * 計算這個序列的行數。 結果將使用名稱「記錄」來記憶。  
45. 在樹狀結構中，選取「$RecName」。
46. 點選新增資料來源。
47. 點選儲存。
48. 關閉頁面。
49. 點選「收集的資料關鍵值」欄位的編輯按鈕
50. 在公式欄位中，輸入「Intrastat.CommodityRecord.CommodityCode」。
51. 點選儲存。
52. 關閉頁面。
    * 計算這個序列的行數。 結果將與名稱「record」分別用於不同的商品代碼。 將其視為虛擬 Excel 試算表。 對於每筆交易，其中第一資料欄「block」相應地用值「Import」和「Export」填入，第二個區塊「record」用商品代碼值填入。  
53. 在樹狀結構中，選取「Intrastat\Data: Sequence\Dispatches?」。
54. 點選「收集的資料關鍵名稱」欄位的編輯按鈕
55. 在樹狀結構中，選取「$RecName」。
56. 點選新增資料來源。
57. 點選儲存。
58. 關閉頁面。
59. 點選「收集的資料關鍵值」欄位的編輯按鈕。
60. 在公式欄位中，輸入「Intrastat.CommodityRecord.CommodityCode」。
61. 點選儲存。
62. 關閉頁面。
63. 在樹狀結構中，展開「Intrastat\Data: Sequence\Dispatches: Sequence?」。
64. 在樹狀結構中，展開「Intrastat\Data: Sequence\Dispatches: Sequence?\Record = Intrastat.CommodityRecord」。
65. 點選格式索引標籤。
66. 在樹狀結構中，選取「Intrastat\Data\Dispatches\Record\Invoice amount EUR」。
67. 點選對應索引標籤。
68. 點選「收集的資料關鍵名稱」欄位的編輯按鈕。
69. 在樹狀結構中，選取「$InvName」。
70. 點選新增資料來源。
71. 點選儲存。
72. 關閉頁面。
    * 匯總此序列行的開票金額值。 結果將分別與名稱「InvoicedAmountEUR」一起用於不同的 Intrastat 方向和商品代碼。 將其視為 Excel 試算表中的虛擬建立。 對於每個交易，第一資料欄「block」的資料列相應地填入了值「Import」和「Export」。 第二區塊「record」填入商品代碼值，第三資料欄「InvoicedAmountEUR」填入發票金額值。  
73. 在樹狀結構中，展開「Intrastat\Data\Arrivals?」。
74. 在樹狀結構中，展開「Intrastat\Data\Arrivals?\Record = Intrastat.CommodityRecord」。
75. 點選格式索引標籤。
76. 在樹狀結構中，選取「Intrastat\Data\Arrivals\Record\Invoice amount EUR」。
77. 點選對應索引標籤。
78. 點選「收集的資料關鍵名稱」欄位的編輯按鈕。
79. 在樹狀結構中，選取「$InvName」。
80. 點選新增資料來源。
81. 點選儲存。
82. 關閉頁面。
83. 點選儲存。
84. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]