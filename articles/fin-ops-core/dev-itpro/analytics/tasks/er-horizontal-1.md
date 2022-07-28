---
title: 'ER 使用水平擴展範圍在 Excel 報表中動態新增列 (第 1 節 - 設計格式) '
description: 本主題介紹如何設定電子報表 (ER) 格式以將報表產生為 OPENXML 工作表 (Excel) 檔案。 (第 1 節)
author: NickSelin
ms.date: 04/23/2021
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
ms.openlocfilehash: ab360c259af37ce3995d3cd2560bc2e765e0bceb
ms.sourcegitcommit: e3290eb58ae569a59d6ae2e6922e7d8be8f1980f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2021
ms.locfileid: "8460360"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a>ER 使用水平擴展範圍在 Excel 報表中動態新增列 (第 1 節 - 設計格式) 

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以將報表產生為 OPENXML 工作表 (Excel) 檔案，其中可以將所需資料欄動態建立為水平擴展範圍。 這些步驟可以在任何公司進行。

若要完成這些步驟，您必須先完成這三個工作指南：

「ER 建立設定提供者並將其標記為作用中」

「ER 使用財務維度作為資料來源 (第 1 節：設計資料模型)」

「ER 使用財務維度作為資料來源 (第 2 節：模型對應)」

您還必須下載並儲存範本的本地副本以及此處的範例報表，[樣本財務維度 Web 服務報表](https://download.microsoft.com/download/3/1/3/313e2090-bc0a-421f-bf96-c58da9bc0dea/SampleFinDimWsReport.xlsx)。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。

## <a name="create-a-new-report-configuration"></a>建立新的報表設定

1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，選取 `Financial dimensions sample model`。
3. 點選建立設定即可打開下拉式對話方塊。
4. 在新建欄位中，輸入 `Format based on data model Financial dimensions sample model`。
    * 使用預先建立的模型作為新報表的資料來源。  
5. 在名稱欄位，輸入 `Sample report with horizontally expandable ranges`。
    * 具有水平可擴展範圍的樣本報表  
6. 在描述資料欄中，輸入 `To make Excel output with dynamically adding columns`。
    * 使用動態新增資料欄進行 Excel 輸出  
7. 在資料模型定義欄位，選取輸入資料。
8. 點選建立設定。

## <a name="design-the-report-format"></a>設計報表格式

1. 點選設計工具。
2. 打開 `Show details` 切換按鈕。
3. 在動作窗格上，點選匯入。
4. 點選從 Excel 匯入。
5. 點選附件。
    * 匯入報表的範本。 使用您為此下載的 Excel 檔案。  
6. 點選「新增」。
7. 點選檔案。
8. 關閉頁面。
9. 在範本欄位中，輸入或選取一個值。
    * 選取下載的範本。  
10. 點選確定。
    * 新增新範圍以動態建立 Excel 輸出，其中包含您為財務維度選取的資料欄 (在使用者對話方塊表單中)。 每資料欄的每個儲存格將代表一個財務維度的名稱。  
11. 點選新增以開啟下拉式對話方塊。
12. 在樹狀結構中，選取 `Excel\Range`。
13. 在 Excel 範圍欄位中，輸入 `DimNames`。
    * DimNames  
14. 在複寫方向欄位中，選取 `Horizontal`。
15. 點選確定。
16. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`。
17. 點選上移。
18. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Cell<DimNames>`。
19. 點選剪下。
20. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`。
21. 點選貼上。
22. 在樹狀結構中，展開 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`。
23. 在樹狀結構中，展開 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`。
24. 在樹狀結構中，展開 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`。
25. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`。
    * 新增新範圍以動態建立 Excel 輸出，其中包含您為財務維度選取的資料欄 (在使用者對話方塊表單中)。 每資料欄的每個儲存格將代表每個報表交易的單個財務維度的值。  
26. 點選新增範圍。
27. 在 Excel 範圍欄位中，輸入 `DimValues`。
    * DimValues  
28. 在複寫方向欄位中，選取 `Horizontal`。
29. 點選確定。
30. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>`。
31. 點選剪下。
32. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`。
33. 點選貼上。
34. 在樹狀結構中，展開 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`。

## <a name="map-format-elements-to-data-sources"></a>將格式元素對應到資料來源

1. 點選對應索引標籤。
2. 在樹狀結構中，展開 `model: Data model Financial dimensions sample model`。
3. 在樹狀結構中，展開 `model: Data model Financial dimensions sample model\Journal: Record list`。
4. 在樹狀結構中，展開 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`。
5. 在樹狀結構中，展開 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`。
6. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>`。
7. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String`。
8. 點選繫結。
9. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`。
10. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`。
11. 點選繫結。
12. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>`。
13. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real`。
14. 點選繫結。
15. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>`。
16. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real`。
17. 點選繫結。
18. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>`。
19. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String`。
20. 點選繫結。
21. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>`。
22. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date`。
23. 點選繫結。
24. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>`。
25. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String`。
26. 點選繫結。
27. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>`。
28. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`。
29. 點選繫結。
30. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`。
31. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`。
32. 點選繫結。
33. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>`。
34. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`。
35. 點選繫結。
36. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`。
37. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Journal: Record list`。
38. 點選繫結。
39. 在樹狀結構中，展開 `model: Data model Financial dimensions sample model\Dimensions setting: Record list`。
40. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String`。
41. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>`。
42. 點選繫結。
43. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Dimensions setting: Record list`。
44. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`。
45. 點選繫結。
46. 在樹狀結構中，選取 `Excel = "SampleFinDimWsReport"\Cell<CompanyName>`。
47. 在樹狀結構中，選取 `model: Data model Financial dimensions sample model\Company: String`。
48. 點選繫結。
49. 點選儲存。
50. 關閉頁面。

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
