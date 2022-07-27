---
title: ER 設定格式以進行計數和求和 (第 4 節 - 執行格式)
description: 本主題介紹如何設定電子報表格式以根據已產生的文字輸出的資料進行計數和求和。 (第 4 節)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5202f8be275df08142c9848a2381fe5bc2ed7289a1f1fe1f8e6d349e38c2b14d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460436"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a>ER 設定格式以進行計數和求和 (第 4 節 - 執行格式)

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何設定電子報表 (ER) 格式以根據已產生的文字輸出的資料進行計數和求和。 這些步驟可以在 DEMF 公司進行。

若要完成這些步驟，您必須先填入「ER 設定格式以進行計數和求和 (第3部分：使用計算來製造輸出)」程序中的步驟。

此程序是 Dynamics 365 for Operations 版本 1611 中增加的函數。


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>測試此設定以產生 intrastat 報表
1. 進入組織管理 > 工作區 > 電子報表。
2. 點選報表設定。
3. 在樹狀結構中，展開「Intrastat model」。
4. 在樹狀結構中，展開「Intrastat model\Intrastat (DE)」。
5. 在樹狀結構中，選取「Intrastat model\Intrastat (DE)\Intrastat (DE) withcounting & summing」。
6. 在動作窗格上，點選設定。
7. 點選使用者參數。
8. 在執行設定欄位中選取是。
9. 點選確定。
10. 點選編輯。
11. 在執行草稿欄位中選取是。
12. 點選儲存。
13. 進入稅收 > 設定 > 外貿 > 外貿參數。
14. 展開電子報表部分。
15. 選取「intrastat (de) 與計數和求和」設定。
16. 選取「intrastat (de) 與計數和求和」設定。
17. 點選儲存。
18. 關閉頁面。
19. 進入稅務 > 報表 > 外貿 > Intrastat。
20. 點選輸出。
21. 點選報表。
    * 執行 Intrastat 報表產生過程。  
22. 在開始日期欄位中，將日期設為「2000-01-01」。
    * 定義報表期間的開始和結束日期，包括表單上的現有交易。  
23. 在結束日期欄位中，將日期設定為「2022-12-31」。
    * 定義報表期間的開始和結束日期，包括表單上的現有交易。  
24. 在方向欄位中，選取「Arrivals」。
25. 在產生檔案欄位中選取是。
26. 點選確定。
    * 使用最後的摘要行查看建立的輸出。  
27. 點選「新增」。
28. 在清單中，標示選取的列。
29. 在方向欄位中，選取「Dispatches」。
30. 在商品號碼欄位中，輸入或選取一個值。
31. 在商品欄位中，輸入或選取一個值。
32. 將權重設定為「10」。
33. 將發票金額設定為「10000」。
34. 將統計金額設定為「10000」。
35. 點選輸出。
36. 點選報表。
37. 在方向欄位中，選取「Dispatches」。
38. 點選確定。
    * 使用最後的摘要行查看建立的輸出。 請注意，它與第一次執行相比已更改。  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>在偵錯模式下執行此設定以查看收集的計數和求和資料
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，展開「Intrastat model」。
3. 在樹狀結構中，展開「Intrastat model\Intrastat (DE)」。
4. 在樹狀結構中，選取「Intrastat model\Intrastat (DE)\Intrastat (DE) withcounting & summing」。
5. 在動作窗格上，點選設定。
6. 點選使用者參數。
7. 在以偵錯模式執行欄位中選取是。
8. 點選確定。
9. 關閉頁面。
10. 進入稅務 > 報表 > 外貿 > Intrastat。
11. 點選輸出。
12. 點選報表。
13. 點選確定。
14. 關閉頁面。
15. 進入組織管理 > 電子報表 > 設定。
16. 在樹狀結構中，展開「Intrastat model」。
17. 在樹狀結構中，展開「Intrastat model\Intrastat (DE)」。
18. 在樹狀結構中，選取「Intrastat model\Intrastat (DE)\Intrastat (DE) withcounting & summing」。
19. 點選偵錯記錄。
    * 請注意，已為所選設定的執行過程建立了偵錯記錄。  
20. 點選連結。
21. 點選開啟。
    * 查看建立的 XML 檔案，其中包含在執行所選設定期間收集的計數和匯總詳情。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]