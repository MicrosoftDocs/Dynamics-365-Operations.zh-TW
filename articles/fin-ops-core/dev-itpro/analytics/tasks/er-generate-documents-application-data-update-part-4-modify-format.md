---
title: 修改格式以產生具有應用程式資料的文件
description: 本主題介紹如何設計報表設定以產生電子文件和更新應用程式資料。
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
ms.openlocfilehash: 312a49fc524cc7359d2c1815597214656df11c018034da384d30bfb9d9efee4b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460431"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>修改格式以產生具有應用程式資料的文件

[!include [banner](../../includes/banner.md)]

若要完成此程序中的步驟，您必須先完成程序「ER 產生具有應用程式資料更新的文件 (第 3 節：修改模型和對應)」。

此程序中的步驟說明如何設計電子報表 (ER) 設定以產生電子文件和更新應用程式資料。 在此程序中，您將修改 ER 設定，使其不僅用於產生電子文件，還用於更新應用程式資料。 此程序是為指派了系統管理員或電子報表開發人員角色的使用者建立的。 這些步驟可以使用 DEMF 資料集完成。


## <a name="modify-format-to-collect-details-of-reporting"></a>修改格式以收集報表的詳情
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，展開「Intrastat (model)」。
3. 在樹狀結構中，選取「Intrastat (model)\Intrastat (format)」。
4. 點選設計工具。
5. 在樹狀結構中，展開「檔案」。
6. 在樹狀結構中，展開「File\Declaration」。
7. 在樹狀結構中，選取「File\Declaration\Data」。
8. 在多重性欄位，選取「一對多」。
    * 設定此格式元素以封存 Intrastat 報表流程的詳情。 此項目代表封存的標題記錄。  
9. 在樹狀結構中，展開「File\Declaration\Data」。
10. 在樹狀結構中，選取「File\Declaration\Data\Item」。
11. 在多重性欄位，選取「零對多」。
    * 設定此格式元素以封存 Intrastat 報表流程的詳情。 該項目將代表已封存行的清單。  
12. 在樹狀結構中，展開「File\Declaration\Data\Item」。
13. 在樹狀結構中，選取「File\Declaration\Data\Item\Dim1」。
14. 在排除欄位中選取是。
    * 您不會封存此資料，因此您可以從 Intrastat 報表詳情的資料來源中排除此格式元素。  
15. 在樹狀結構中，展開「File\Declaration\Data\Item\Dim1」。
16. 在樹狀結構中，選取「File\Declaration\Data\Item\Dim1\property」。
17. 在排除欄位中選取是。
18. 在樹狀結構中，選取「File\Declaration\Data\Item\Dim1\date」。
19. 在排除欄位中選取是。
20. 在樹狀結構中，選取「File\Declaration\Data\Item\Dim2」。
21. 在排除欄位中選取是。
22. 在樹狀結構中，展開「File\Declaration\Data\Item\Dim2」。
23. 在樹狀結構中，選取「File\Declaration\Data\Item\Dim2\property」。
24. 在排除欄位中選取是。
25. 在樹狀結構中，選取「File\Declaration\Data\Item\Dim2\code」。
26. 在排除欄位中選取是。
27. 在樹狀結構中，選取「File\Declaration\Data\Item\Dim3」。
    * 多個格式元素可以具有相同的名稱。 例如，Dim。當您將此格式用作封存 Intrastat 報表詳情的資料來源時，您無法明確識別它們，因此您需要為這些格式元素定義替代名稱。   
28. 在名稱欄位，輸入「Amount」。
    * 金額  
29. 在多重性欄位，選取「剛好一個」。
30. 在樹狀結構中，選取「File\Declaration\Data\Item\Dim4」。
31. 在名稱欄位，輸入｢Item」。
    * 項目  
32. 在多重性欄位，選取「剛好一個」。
    * 除了設計格式元素之外，還必須封存以下 Intrastat 報表詳情：每個報表商品項目的唯一記錄識別和產生檔案的名稱。 由於該資料不會填入到 Intrastat 報表中，因此您需要將與這些明細元素相關的格式新增為資料來源項。  
33. 在樹狀結構中，選取「File\Declaration\Data」。
34. 點選新增以開啟下拉式對話方塊。
35. 在樹狀結構中，選取「Data source\Item」。
36. 在名稱欄位，輸入「File name」。
    * 檔案名稱  
37. 在日期類型欄位中，選取「字串」。
38. 點選確定。
39. 在樹狀結構中，選取「File\Declaration\Data\Item」。
40. 點選新增項目。
41. 在名稱欄位中，輸入「Commodity rec ID」。
    * 商品記錄 ID  
42. 在資料類型欄位中，選取「Int64」。
43. 點選確定。
44. 點選對應索引標籤。
45. 在樹狀結構中，選取「File\Declaration\Data\File name」。
46. 點選繫結。
47. 在樹狀結構中，展開「模型」。
48. 在樹狀結構中，展開「model\Transactions」。
49. 在樹狀結構中，選取「File\Declaration\Data\Item = model.Transactions\Commodity rec ID」。
50. 在樹狀結構中，選取「model\Transactions\Commodity rec ID」。
51. 點選繫結。
52. 點選儲存。

## <a name="modify-format-to-memorize-details-of-reporting"></a>修改格式以記住報表的詳情

1. 點選將格式對應到模型。
2. 點選「新增」。
3. 在定義欄位中，輸入或選取「For application data update」根項目。
    * 用於應用程式資料更新。
4. 在名稱欄位中，輸入「Mapping to update data」。
    * 對應以更新資料  
5. 點選儲存。
    * 此對應定義如何在資料模型中收集 Intrastat 報表的詳情，其結構由選定的根項「用於應用程式資料更新」指定。 這些細節，具有相同根項「用於應用程式資料更新」的模型對應，以及「前往目的地」方向將用於應用程式資料更新。 產生傳出 Intrastat 報表後立即開始應用程式資料更新。 應用程式資料更新可以在執行階段跳過，但資料模型必須為空 (包含空記錄清單)。
6. 點選設計工具。
    * 在預設情況下，將新增傳出 Intrastat 報表格式作為此模型對應的資料來源。  
    * 將設計報表的元素 (呈現為資料來源) 繫結到資料模型的元素，資料模型的元素基於所選模型的根項進行過濾。  
7. 在樹狀結構中，展開「封存標題」。
8. 在樹狀結構中，展開「Archive header\Archive lines」。
9. 在樹狀結構中，展開「格式」。
10. 在樹狀結構中，展開「format\Declaration: XML Element(Declaration)」。
11. 在樹狀結構中，展開「format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)」。
12. 在樹狀結構中，展開「format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)」。
13. 在樹狀結構中，展開「format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)」。
14. 在樹狀結構中，展開「format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)」。
15. 在樹狀結構中，選取「Archive header\Number of lines」。
16. 點選編輯。
17. 在樹狀結構中，選取「List\COUNT」。
18. 點選新增函數。
19. 在樹狀結構中，展開「格式」。
20. 在樹狀結構中，展開「format\Declaration: XML Element(Declaration)」。
21. 在樹狀結構中，展開 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`。
22. 在樹狀結構中，選取 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`。
23. 點選新增資料來源。
24. 在「公式」欄位中，輸入「COUNT(format.Declaration.Data.Item)」。
    * COUNT(format.Declaration.Data.Item)  
25. 點選儲存。
26. 關閉頁面。
27. 在樹狀結構中，選取「Archive header\File name」。
28. 在樹狀結構中，選取「format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\File name: Item String(File name)」。
29. 點選繫結。
30. 在樹狀結構中，選取 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)`。
31. 在樹狀結構中，選取「Archive header\Archive lines\Item number」。
32. 點選繫結。
33. 在樹狀結構中，選取 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)`。
34. 在樹狀結構中，選取「Archive header\Archive lines\Amount」。
35. 點選繫結。
36. 在樹狀結構中，選取 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec ID: Item Int64(Commodity rec ID)`。
37. 在樹狀結構中，選取「Archive header\Archive lines\Commodity rec ID」。
38. 點選繫結。
39. 在樹狀結構中，選取「Archive header\Archive lines」。
40. 在樹狀結構中，選取 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`。
41. 點選繫結。
42. 在樹狀結構中，選取「Archive header」。
43. 在樹狀結構中，選取 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`。
44. 點選繫結。
45. 點選儲存。
46. 關閉頁面。
47. 關閉頁面。
48. 關閉頁面。


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]