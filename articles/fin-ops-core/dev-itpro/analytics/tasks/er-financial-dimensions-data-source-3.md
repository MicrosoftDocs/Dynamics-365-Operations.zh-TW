---
title: ER 使用財務維度作為資料來源 (第 3 節 - 設計報表)
description: 本主題介紹如何設定電子報表 (ER) 模型以使用財務維度作為 ER 報表的資料來源。 (第 3 節)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c854e9d30006dfa2deed63983a3a6b67f6ae9717
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460250"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a>ER 使用財務維度作為資料來源 (第 3 節 - 設計報表)

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 模型以使用財務維度作為 ER 報表的資料來源。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成「ER 使用財務維度作為資料來源 (第 2 節：模型對應)」過程中的步驟。


## <a name="design-a-report-to-present-financial-dimensions"></a>設計報表以呈現財務維度
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，選取「財務維度樣本模型」。
3. 點選建立設定即可打開下拉式對話方塊。
4. 在新增欄位中，輸入「Format based on data model Financial dimensions sample model」。
    * 使用預先建立的模型作為新報表的資料來源。  
5. 在名稱欄位中，輸入「Ledger journal report」。
6. 在資料模型定義欄位，選取輸入資料。
7. 點選建立設定。
8. 點選設計工具。
9. 點選新增根以開啟下拉式對話方塊。
10. 在樹狀結構中，選取「XML\元素」。
11. 在名稱欄位，輸入｢Root」。
12. 點選確定。
13. 點選新增以開啟下拉式對話方塊。
14. 在樹狀結構中，選取「XML\Attribute」。
15. 在名稱欄位，輸入「Company」。
16. 點選確定。
17. 點選新增以開啟下拉式對話方塊。
18. 在樹狀結構中，選取「XML\元素」。
19. 在名稱欄位，輸入「Journal」。
20. 點選確定。
21. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element」。
22. 點選新增以開啟下拉式對話方塊。
23. 在樹狀結構中，選取「XML\Attribute」。
24. 在名稱欄位，輸入「Batch」。
25. 點選確定。
26. 點選新增以開啟下拉式對話方塊。
27. 在樹狀結構中，選取「XML\元素」。
28. 在名稱欄位，輸入「Transaction」。
29. 點選確定。
30. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element」。
31. 點選新增以開啟下拉式對話方塊。
32. 在樹狀結構中，選取「XML\Attribute」。
33. 在名稱欄位，輸入「Voucher」。
34. 點選確定。
35. 點選新增屬性。
36. 在名稱欄位，輸入「Date」。
37. 點選確定。
38. 點選新增屬性。
39. 在名稱欄位，輸入「Currency」。
40. 點選確定。
41. 點選新增屬性。
42. 在名稱欄位，輸入「Dt」。
43. 點選確定。
44. 點選新增屬性。
45. 在名稱欄位，輸入「Ct」。
46. 點選確定。
47. 點選新增以開啟下拉式對話方塊。
48. 在樹狀結構中，選取「XML\元素」。
49. 在名稱欄位，輸入「Dimensions」。
50. 點選確定。
51. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element」。
52. 點選新增以開啟下拉式對話方塊。
53. 在樹狀結構中，選取「XML\Attribute」。
54. 在名稱欄位，輸入｢Code」。
55. 點選確定。
56. 點選新增屬性。
57. 在名稱欄位，輸入「Value」。
58. 點選確定。
59. 點選新增屬性。
60. 在名稱欄位，輸入「Desc」。
61. 點選確定。
![格式設計工具頁面樹狀結構。](../media/er-financial-dimensions-guides-format1.png)

## <a name="map-report-elements-to-data-sources"></a>將報表元素對應到資料來源
1. 點選對應索引標籤。
2. 在樹狀結構中，展開「model: Data model Financial dimensions sample model」。
3. 在樹狀結構中，展開「model: Data model Financial dimensions sample model\Journal: Record list」。
4. 在樹狀結構中，展開「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list」。
5. 在樹狀結構中，展開「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list」。
6. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute」。
7. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String」。
8. 點選繫結。
9. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute」。
10. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String」。
11. 點選繫結。
12. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute」。
13. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String」。
14. 點選繫結。
15. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list」。
16. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element」。
17. 點選繫結。
18. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute」。
19. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real」。
20. 點選繫結。
21. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute」。
22. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real」。
23. 點選繫結。
24. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute」。
25. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String」。
26. 點選繫結。
27. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute」。
28. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date」。
29. 點選繫結。
30. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute」。
31. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String」。
32. 點選繫結。
33. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Transaction: XML Element」。
34. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list」。
35. 點選繫結。
36. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element\Batch: XML Attribute」。
37. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list\Batch: String」。
38. 點選繫結。
39. 在樹狀結構中，選取「Root: XML Element\Journal: XML Element」。
40. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Journal: Record list」。
41. 點選繫結。
42. 在樹狀結構中，選取「Root: XML Element\Company: XML Attribute」。
43. 在樹狀結構中，選取「model: Data model Financial dimensions sample model\Company: String」。
44. 點選繫結。
45. 點選儲存。
46. 關閉頁面。
![格式設計工具頁面，對應到資料來源的報表元素。](../media/er-financial-dimensions-guides-format2.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
