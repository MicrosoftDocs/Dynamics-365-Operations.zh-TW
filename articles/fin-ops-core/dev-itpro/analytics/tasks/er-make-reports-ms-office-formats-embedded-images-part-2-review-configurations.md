---
title: 查看設定以產生具有內嵌影像的 Office 格式的報告
description: 本主題介紹如何設計報告設定以產生包含內嵌影像的電子文件。 (第 1 章節 - 設定參數)。
author: NickSelin
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f209fcbac310dffb654f7830a4d4b12fa95d7a461b681864b8c9b547f4a4986c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460461"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>查看設定以產生具有內嵌影像的 Office 格式的報告

[!include [banner](../../includes/banner.md)]

若要完成這些步驟，您必須先完成「ER 製作帶有內嵌影像的 MS Office 格式的報告 (第 1 部分：設定參數)」工作指南中的步驟。

此程序說明如何設計電子報告 (ER) 設定以產生包含 Microsoft Excel 和 Microsoft Word 中內嵌影像的電子文件。 在本範例中，您將查看樣本公司 Litware, Inc. 的 ER 設定。 

此程序適用於指派有系統管理員或電子報表開發人員角色的使用者。 這些步驟可以透過使用 USMF 資料集來完成。


## <a name="review-the-imported-data-model"></a>查看匯入的資料模型
1. 進入組織管理 > 電子報表 > 設定。
2. 在樹狀結構中，選取「Model for cheques」。
3. 點選設計工具。
    * 此模型旨在從業務角度代表付款支票，並將該模型對應到應用程式的資料來源。 由 ER Operations 設計工具查看此模型。 請注意顯示的模型元素的屬性：結構、名稱、描述、資料類型等。   
4. 在樹狀結構中，展開「root」。
5. 在樹狀結構中，選取「root\cheques」。
6. 在樹狀結構中，展開「root\cheques」。
7. 在樹狀結構中，展開「root\cheques\attributes」。
8. 在樹狀結構中，展開「root\payer」。
9. 在樹狀結構中，選取「root\istestrun」。
10. 在樹狀結構中，選取「root\layout」。
    * 此模型的配置元素表示所選銀行帳戶的列印支票表單配置的詳情。 它還包括兩個容器資料類型的節點來儲存影像。   
11. 在樹狀結構中，展開「root\layout」。
12. 在樹狀結構中，選取「root\layout\company logo」。
13. 在樹狀結構中，展開「root\layout\company logo」。
14. 在樹狀結構中，選取「root\layout\company logo\image」。
15. 在樹狀結構中，選取「root\layout\company logo\isprinted」。
16. 在樹狀結構中，選取「root\layout\signature」。
17. 在樹狀結構中，展開「root\layout\signature」。
18. 在樹狀結構中，選取「root\layout\signature\image」。
19. 在樹狀結構中，選取「root\layout\signature\isprinted」。
    * 請注意，兩個影像資料模型元素繫結到包含公司標誌影像和二進位格式授權人簽名的資料表欄位。  
20. 在樹狀結構中，展開「root\layout\watermark」。
21. 點選將模型對應到資料來源。
22. 點選設計工具。
23. 在樹狀結構中，「chequesselected」。
24. 在樹狀結構中，展開「layout」。
25. 在樹狀結構中，展開「layout\company logo」。
26. 在樹狀結構中，展開「layout\signature」。
27. 在樹狀結構中，展開「layout\watermark」。
28. 打開「顯示詳情」。
    * 請注意，支票資料模型元素繫結到 TmpChequePrintout 表，該表在執行階段將包含使用者選取列印的支票記錄。   
29. 關閉頁面。
30. 關閉頁面。
31. 關閉頁面。

## <a name="review-the-imported-format"></a>查閱已匯入的格式
1. 在樹狀結構中，展開「Model for cheques」。
2. 在樹狀結構中，選取「Model for cheques\Cheques printing format」。
3. 點選設計工具。
4. 點選附件。
5. 點選開啟。
    * 在 Excel 中打開附加報告的範本。  
    * 查看所附報告的 Excel 範本，該範本將用於列印支票。 該範本每頁包含兩張支票，旨在將支票列印到預印表格中。 請注意，嵌入了兩個空白影像。 這些空白影像用於公司標誌和授權付款人的簽名。 驗證影像在 Excel 中分別命名為 CompLogo 和 SignatureImage。   
6. 關閉頁面。
7. 在樹狀結構中，展開「Report」。
8. 在樹狀結構中，展開「Report\ChequeLines」。
9. 在樹狀結構中，選取「Report\ChequeLines\CompLogo」。
10. 打開「顯示詳情」。
    * 請注意，「CompLogo」格式的儲存格元素表示用於在報告中填入公司標誌影像的 Excel 項。 此格式元素繫結到影像資料模型元素，該元素在執行階段包含二進位格式的公司標誌影像。   
11. 點選對應索引標籤。
12. 點選啟用編輯。
    * 請注意，您可以使「CompLogo」格式的儲存格元素不再啟用。 在這種情況下，相關的 Excel 影像元素將在產生的報告中隱藏公司標誌。 如果啟用的運算式回傳 TRUE 並且定義的繫結沒有影像，則關聯的 Excel 影像元素將顯示已儲存在 Excel 範本中的影像。   
13. 關閉頁面。
14. 在樹狀結構中，展開「labels: Container」。
    * 在為測試目的建立報告時，預印本檢查表中顯示的一些標籤將包含在報告中。 但是，在實際列印過程中不會列印這些標籤，因為預列印表單已經包含它們。  
15. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]