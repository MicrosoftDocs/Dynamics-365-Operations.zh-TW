---
title: ER 使用財務維度作為資料來源 (第 2 節 - 模型對應)
description: 本主題介紹如何設定電子報表 (ER) 模型以使用財務維度作為 ER 報表的資料來源。 (第 2 節)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc7c6bc299dd0af83db3b09b06276a210ecfada5
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460256"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a>ER 使用財務維度作為資料來源 (第 2 節 - 模型對應)

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 模型以使用財務維度作為 ER 報表的資料來源。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成「ER 使用財務維度作為資料來源 (第 1 節：設計資料模型)」過程中的步驟。


## <a name="add-required-data-sources-to-model-mapping"></a>將所需的資料來源新增到模型對應
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，選取「財務維度樣本模型」。
3. 點選設計工具。
4. 點選將模型對應到資料來源。
5. 點選新建。
6. 在定義欄位中，選取資料輸入。
7. 在名稱欄位中，輸入「Dimensions data mapping」。
8. 在描述欄位中，輸入「Dimensions data mapping」。
9. 點選儲存。
10. 點選設計工具。
11. 在樹狀結構中，選取「Dynamics 365 for Operations\資料表」。
12. 點選新增根。
13. 在名稱欄位，輸入「Company」。
14. 在資料表欄位，輸入「CompanyInfo」。
15. 點選確定。
16. 在樹狀結構中，選取「功能\財務維度詳情」。
17. 點選新增根。
    * 此資料來源指定如何為將使用此模型作為資料來源的任何報表定義財務維度的範圍。  
18. 在名稱欄位中，輸入一個值。
19. 在詢問維度欄位中選取是。
    * 選取是以允許使用者在執行階段在使用者對話方塊表單上選取維度。 如果設定為否，則預設使用現行實體的所有財務維度。  
20. 在財務維度選取欄位中，選取「法律實體」。
    * 選取全部以允許使用者在查詢欄位中為現行實體選取所需的維度。  選取法律實體以允許使用者在查詢欄位中選取公司的維度。  選取維度以允許使用者使用單個維度集選取維度。  
21. 在詢問主科目欄位中選取是。
    * 將詢問主科目設定為是，以允許使用者選取主科目作為維度清單的一部分。   如果設定為否，則主科目將不包含在維度清單中，並且啟用「主科目是否為強制性」選項。 如果「主科目是否維強制性」設定為是，則無論使用者選取如何，都將主科目包括在維度清單中。  
22. 點選確定。
![財務維度的明細資料來源屬性滑出。](../media/er-financial-dimensions-guides-model-mapping1.png)
23. 在樹狀結構中，選取「Dynamics 365 for Operations\資料表記錄」。
24. 點選新增根。
25. 在名稱欄位，輸入「LedgerJournal」。
26. 在詢問查詢欄位中選取是。
27. 在資料表欄位，輸入「LedgerJournalTable」。
28. 點選確定。
![模型對應設計工具頁面，資料表記錄資料來源類型。](../media/er-financial-dimensions-guides-model-mapping2.png)

## <a name="map-data-model-elements-to-added-data-sources"></a>將資料模型元素對應到新增的資料來源
1. 在樹狀結構中，展開「Journal」。
2. 在樹狀結構中，展開「Journal\Transaction」。
3. 在樹狀結構中，展開「Journal\Transaction\Dimensions data」。
4. 在樹狀結構中，展開「Dimensions setting」。
5. 在樹狀結構中，展開「LedgerJournal」。
6. 在樹狀結構中，展開「LedgerJournal\<Relations」。
7. 在樹狀結構中，展開「LedgerJournal\<Relations\LedgerJournalTrans」。
8. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Voucher」。
9. 在樹狀結構中，選取「Journal\Transaction\Voucher」。
10. 點選繫結。
11. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)」。
    * 請注意，對於任何設定為 LedgerDimension 的財務維度的參考，對應的資料來源項是可用的 (LedgerDimension.Dimension)。 此資料來源項提供該維度集的財務維度作為記錄清單。  
12. 在樹狀結構中，展開「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)」。
13. 在樹狀結構中，展開「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions」。
14. 在樹狀結構中，展開「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value」。
15. 在樹狀結構中，展開「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition」。
16. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name」。
17. 在樹狀結構中，選取「Journal\Transaction\Dimensions data\Name」。
18. 點選繫結。
19. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description」。
20. 在樹狀結構中，選取「Journal\Transaction\Dimensions data\Description」。
21. 點選繫結。
22. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code」。
23. 在樹狀結構中，選取「Journal\Transaction\Dimensions data\Code」。
24. 點選繫結。
25. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions」。
26. 在樹狀結構中，選取「Journal\Transaction\Dimensions data」。
27. 點選繫結。
!模型對應設計工具頁面，對應索引標籤，資料來源樹狀結構。](../media/er-financial-dimensions-guides-model-mapping3.png)
28. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)」。
29. 在樹狀結構中，選取「Journal\Transaction\Debit」。
30. 點選繫結。
31. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)」。
32. 在樹狀結構中，選取「Journal\Transaction\Date」。
33. 點選繫結。
34. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)」。
35. 在樹狀結構中，選取「Journal\Transaction\Currency」。
36. 點選繫結。
37. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)」。
38. 在樹狀結構中，選取「Journal\Transaction\Credit」。
39. 點選繫結。
40. 在樹狀結構中，選取「LedgerJournal\<Relations\LedgerJournalTrans」。
41. 在樹狀結構中，選取「Journal\Transaction」。
42. 點選繫結。
43. 在樹狀結構中，選取「LedgerJournal\Journal batch number(JournalNum)」。
44. 在樹狀結構中，選取「Journal\Batch」。
45. 點選繫結。
46. 在樹狀結構中，選取「LedgerJournal」。
47. 在樹狀結構中，選取「Journal」。
48. 點選繫結。
49. 在樹狀結構中，展開「Dimensions」。
50. 在樹狀結構中，展開「Dimensions\Main account and dimensions」。
51. 在樹狀結構中，展開「Dimensions\Main account and dimensions\Definition」。
52. 在樹狀結構中，選取「Dimensions\Main account and dimensions\Definition\Name」。
53. 在樹狀結構中，選取「Dimensions setting\Code」。
54. 點選繫結。
55. 在樹狀結構中，選取「Dimensions\Main account and dimensions\Definition\Report column name」。
56. 在樹狀結構中，選取「Dimensions setting\Name」。
57. 點選繫結。
58. 在樹狀結構中，選取「Dimensions\Main account and dimensions」。
59. 在樹狀結構中，選取「Dimensions setting」。
60. 點選繫結。
61. 在樹狀結構中，選取「Company」。
62. 點選編輯。
63. 在 expressionAsStringText 欄位中，輸入「Company.'find()'.'name()'」。
    * Company.'find()'.'name()'  
64. 點選儲存。
![ER 模型對應設計工具頁面。](../media/er-financial-dimensions-guides-model-mapping4.png)
65. 關閉頁面。
66. 點選儲存。
67. 關閉頁面。

## <a name="complete-this-draft-models-version"></a>完成此草稿模型的版本
1. 關閉頁面。
2. 關閉頁面。
3. 點選更改狀態。
4. 點選完成。
5. 點選確定。
![ER 設定頁面。](../media/er-financial-dimensions-guides-model-mapping5.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
