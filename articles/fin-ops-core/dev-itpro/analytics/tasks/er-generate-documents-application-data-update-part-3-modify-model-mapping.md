---
title: 修改模型和對應以產生具有應用程式資料的文件
description: 本主題介紹如何設計報表設定以產生電子文件和更新應用程式資料。  (第 2 區段 - 產生文件)。
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d7df46bab244d11509b86a27eeed3c2725400b5eb4d0fbf50af1750e7de45d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460432"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a>修改模型和對應以產生具有應用程式資料的文件

[!include [banner](../../includes/banner.md)]

若要完成此程序中的步驟，您必須先完成程式「ER 產生具有應用程式資料更新的文件 (第 2 區段：產生文件) 」。 

此程序中的步驟說明如何設計電子報表 (ER) 設定以產生電子文件和更新應用程式資料。 在此程序中，您將修改 ER 設定以開始使用它們來產生電子文件和更新應用程式資料。 此程序是為指派了系統管理員或電子報表開發人員角色的使用者建立的。 這些步驟可以使用 DEMF 資料集完成。


## <a name="modify-data-model"></a>修改資料模型
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，選取「Intrastat (model)」。
    * 您將擴展使用資料模型的方式。 除了將其用作產生 Intrastat 報告的資料來源外，該資料模型還將用於收集有關 Intrastat 報告流程的詳情。 然後，這些詳情將用於更新應用程式資料。   
3. 點選設計工具。
4. 按一下新增以開啟下拉式對話方塊。
5. 在作為欄位的新節點中，輸入「Model root」。
6. 在名稱欄位中，鍵入「用於應用程式資料更新」。
    * 用於應用程式資料更新  
7. 選點新增。
8. 在樹狀結構中，選取「用於應用程式資料更新」。
    * 新增此新根項以指定將資料從 Intrastat 報告 (用作資料來源) 移動到應用程式表 (更新目的地) 的資料流程。 請注意，必須使用不同的根項目來獲取發佈到傳出文件的資料以及從用於更新應用程式資料的文件中獲取資料。   
9. 按一下新增以開啟下拉式對話方塊。
10. 在名稱欄位，輸入「Archive header」。
    * 封存標題  
11. 在項目類型欄位中，選取「記錄清單」。
12. 選點新增。
    * 因為您將為產生的每個 Intrastat 報告創建一個記錄，所以您必須為此創建一個新項目。  
13. 按一下新增以開啟下拉式對話方塊。
14. 在名稱欄位，輸入「File name」。
    * 檔案名稱  
15. 在項目類型欄位中，選取「字串」。
16. 選點新增。
17. 按一下新增以開啟下拉式對話方塊。
18. 在名稱欄位，輸入「Number of lines」。
    * 明細數  
19. 在項目類型欄位中，選取「整數」。
20. 選點新增。
    * 新增此項以表示在現行報告過程中報告的 Intrastat 交易數量。  
21. 按一下新增以開啟下拉式對話方塊。
22. 在名稱欄位，輸入「Archive lines」。
    * 封存明細  
23. 在項目類型欄位中，選取「記錄清單」。
24. 選點新增。
    * 新增此項以表示在現行報告過程中報告的 Intrastat 交易清單。  
25. 按一下新增以開啟下拉式對話方塊。
26. 在名稱欄位，輸入「Amount」。
    * 金額  
27. 在項目類型欄位中，選取「實數」。
28. 選點新增。
29. 按一下新增以開啟下拉式對話方塊。
30. 在名稱欄位中，輸入「Commodity rec id」。
    * 商品記錄 ID  
31. 在項目類型欄位中，選取「Int64」。
32. 選點新增。
33. 按一下新增以開啟下拉式對話方塊。
34. 在名稱欄位，輸入「Item number」。
    * 品項編號  
35. 在項目類型欄位中，選取「字串」。
36. 選點新增。
37. 點選儲存。
38. 關閉頁面。

## <a name="modify-model-mapping"></a>修改模型對應
1. 在樹狀結構中，展開「Intrastat (model)」。
2. 在樹狀結構中，選取「Intrastat (model)\Intrastat (mapping)」。
    * 修改現有模型對應以開始將其用於應用程式資料更新和封存 Intrastat 報告詳情。  
3. 點選設計工具。
4. 點選新建。
5. 在名稱欄位，輸入「Update archive」。
    * 更新封存  
6. 在方向欄位中，選取「前往目的地」。
7. 點選儲存。
    * 此新對應指定將資料 (Intrastat 報告詳情) 從資料模型移動到應用程式表 (更新目標) 的資料流程。 請注意，必須使用不同模型的根項從應用程式中獲取資料以進行報告過程，然後將資料模型中的資料用於應用程式資料更新。   
8. 點選設計工具。
9. 在樹狀結構中，選取「資料模型\資料模型」。
    * 新增所需的資料來源。 這是包含必須封存的已報告 Intrastat 交易詳情的資料模型。  
10. 點選新增根。
11. 在名稱欄位，輸入「model」。
    * 模型  
12. 在定義欄位中，輸入或選取值「For application data update」。
    * 用於應用程式資料更新  
13. 點選確定。
14. 在樹狀結構中，展開「模型」。
15. 在樹狀結構中，選取「函數\匯出欄位」。
16. 在樹狀結構中，選取「模型\封存標題」。
17. 選點新增。
    * 因為您要列舉報告的 Intrastat 交易以進行封存，所以必須新增適當的資料來源。  
18. 在名稱欄位，輸入「Enumerated lines」。
    * 列舉明細  
19. 點選編輯公式。
20. 在樹狀結構中，選取「清單\列舉」。
21. 點選新增函數。
22. 在樹狀結構中，展開「模型」。
23. 在樹狀結構中，展開「模型\封存標題」。
24. 在樹狀結構中，選取「模型/封存標題/封存明細」。
25. 點選新增資料來源。
26. 在公式欄位中，輸入「ENUMERATE(model.'Archive header'.'Archive lines')」。
    * ENUMERATE(model.'Archive header'.'Archive lines')  
27. 點選儲存。
28. 關閉頁面。
29. 點選確定。
30. 點選新增目的地。
    * 將應用程式表新增為需要更新以歸檔報告的 Intrastat 交易詳情的所需目的地。  
31. 在名稱欄位，輸入「Archive」。
    * 封存  
32. 在資料表名稱欄位，輸入「IntrastatArchiveGeneral」。
    * IntrastatArchiveGeneral  
    * 保留記錄操作「插入」，以便您可以在每個 Intrastat 報告流程的詳細封存期間新增記錄。  
33. 在記錄資訊記錄欄位中選取是。
    * 選取是以獲取有關應用程式資料更新問題的資訊。  
34. 在跳過記錄操作驗證欄位中選取是。
    * 選取是以隱藏有關空的「Intrastat 封存 ID」欄位的驗證錯誤。 這將在新增記錄後根據在外貿參數表單中為此表設定的序列號設定完成。  
35. 點選確定。
    * 將新增的資料來源 (基於所選根項的過濾模型) 的元素與新增的目標中的元素繫結。  
36. 在樹狀結構中，展開「封存」。
37. 在樹狀結構中，展開「封存\<關係」。
38. 在樹狀結構中，展開「封存\<Relations/IntrastatArchiveDetail」。
39. 在樹狀結構中，選取「存檔\<關係/IntrastatArchiveDetail/Amount(AmountMST)」。
40. 在樹狀結構中，展開「模型\封存標題\列舉明細」。
41. 在樹狀結構中，展開「模型\封存標題\列舉明細\值」。
42. 在樹狀結構中，選取「模型\封存標題\列舉明細\值\金額」。
43. 點選繫結。
44. 在樹狀結構中，選取「存檔\<關係\IntrastatArchiveDetail\商品 (IntrastatCommodity)」。
45. 在樹狀結構中，選取「模型\封存標題\列舉行\值\商品記錄 ID」。
46. 點選繫結。
47. 在樹狀結構中，選取「存檔\<關係\IntrastatArchiveDetail\品項編號 (ItemId)」。
48. 在樹狀結構中，選取「模型\封存標題\列舉明細\值\品項編號」。
49. 點選繫結。
50. 在樹狀結構中，選取「存檔\<關係\IntrastatArchiveDetail\明細編號 (LineNumber)」。
51. 在樹狀結構中，選取「模型\封存標題\列舉明細\編號」。
52. 點選繫結。
53. 在樹狀結構中，選取「封存\<關係\IntrastatArchiveDetail」。
54. 在樹狀結構中，選取「模型\封存標題\列舉明細」。
55. 點選繫結。
56. 在樹中，選取「封存\檔案名稱 (FileName)」。
57. 在樹狀結構中，選取「模型\封存標題\檔案名稱」。
58. 點選繫結。
59. 在樹狀結構中，選取「封存\明細編號 (NumberOfLines)」。
60. 在樹狀結構中，選取「模型\封存標題\明細編號」。
61. 點選繫結。
62. 在樹狀結構中，選取「封存」。
63. 在樹狀結構中，選取「模型\封存標題」。
64. 點選繫結。
65. 點選儲存。
66. 關閉頁面。
67. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]