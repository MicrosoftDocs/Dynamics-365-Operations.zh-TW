---
title: 匯入設定以產生具有應用程式資料的文件
description: 若要完成此過程中的步驟，您必須先完成「ER 建立設定提供者並將其標記為有效」的程序。
author: NickSelin
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08ab90d6f53dbb9eabeea3c2cf020792e8957c7b71ed27fc491008fcad114c72
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460435"
---
# <a name="import-configurations-to-generate-documents-that-have-application-data"></a>匯入設定以產生具有應用程式資料的文件

[!include [banner](../../includes/banner.md)]

若要完成此過程中的步驟，您必須先完成「ER 建立設定提供者並將其標記為有效」的程序。

此程序中的步驟說明如何設計電子報表 (ER) 設定以產生電子文件。 在此程序中，您將匯入為樣本公司 Litware, Inc. 建立的所需 ER 設定，並使用它們產生電子文件。 此程序是為指派了系統管理員或電子報表開發人員角色的使用者建立的。 這些步驟可以使用 DEMF 資料集完成。 在開始之前，請下載並儲存說明主題「使用 ER 工具產生電子文件和更新應用程式資料」中列出的檔案 (generate-electronic-documents-update-application-data/)。 這些檔案是 Intrastat (model).xml、Intrastat (mapping).xml 和 Intrastat (format).xml。

1. 進入組織管理 > 工作區 > 電子報表。
    * 確保樣本公司 Litware, Inc. 的設定提供者可用並標記為有效。 如果您沒有看到此設定廠商，請完成「建立設定廠商並將其標記為有效」程序中的步驟。  
    * 此程序中的步驟顯示如何使用 ER 函數完成應用程式資料更新以及如何產生 Intrastat 報表。 報表過程的詳情歸檔在應用程式表中。 目前，當從 Intrastat 表單啟用 Intrastat 報表流程時，歸檔是根據現有原始程式碼中程式碼的邏輯完成的。 在此程序中，您將僅使用 ER 架構設定類似但簡化的應用程式資料邏輯。 不會對原始程式碼進行任何更改。   

## <a name="import-er-configurations"></a>匯入 ER 設定
1. 點選報表設定。
2. 點選 Exchange。
3. 點選從 XML 檔案載入。
    * 匯入包含資料模型的 ER 模型設定，該資料模型旨在用作產生 Intrastat 報表的資料來源。 稍後，您將擴展此資料模型定義以將其用於應用程式資料更新，以歸檔 Intrastat 報表流程的詳情。   
    * 點選瀏覽並選取 Intrastat (model).xml 檔案。  
4. 點選確定。
5. 在樹狀結構中，選取「Intrastat (model)」。
6. 點選設計工具。
7. 在樹狀結構中，展開「For outgoing document」。
8. 在樹狀結構中，展開「For outgoing document\Transactions」。
    * 查看匯入的資料模型的結構。 請注意，根項目「For outgoing document」被定義為指定從應用程式獲取資料並將其用作資料來源以產生 Intrastat 報表的資料流程。 「交易 (記錄清單)」用於表示必須報表的 Intrastat 交易清單。 由於您將歸檔報表的商品代碼，因此此資料流程中需要單個商品代碼「Commodity rec id (Int64)」的唯一識別碼。   
9. 關閉頁面。
10. 點選 Exchange。
11. 點選從 XML 檔案載入。
    * 匯入 ER 對應設定，該設定指定從應用程式獲取資料的資料流程，然後使用它來產生 Intrastat 報表。 稍後，您將擴展此模型對應定義以從 Intrastat 報表中獲取資料，並將其用於應用程式資料更新以歸檔 Intrastat 報表流程的詳情。   
    * 點選瀏覽並選取 Intrastat (mapping).xml 檔案。  
12. 點選確定。
13. 在樹狀結構中，展開「Intrastat (model)」。
14. 在樹狀結構中，選取「Intrastat (model)\Intrastat (mapping)」。
15. 點選設計工具。
    * 請注意，現行模型對應在方向欄位中包含值「建模」。 這代表此模型對應旨在從應用程式獲取資料並將其儲存在資料模型中。  
16. 點選設計工具。
17. 在樹狀結構中，展開「List」。
18. 在樹狀結構中，展開「Transactions= List」。
    * 查看模型對應的結構，該結構使用基於根項「For outgoing document」過濾的資料模型。 請注意，新增的資料來源「List」提供對所需應用程式資料的存取，這是來自 Intrastat 表的記錄清單。  
19. 關閉頁面。
20. 關閉頁面。
21. 點選 Exchange。
22. 點選從 XML 檔案載入。
    * 匯入 ER 格式設定，該設定指定 Intrastat 報表的配置以及將資料填入到報表的過程。 稍後，您將擴展此格式定義以將 Intrastat 報表中的資料放入資料模型，然後使用它來更新應用程式資料以歸檔 Intrastat 報表流程的詳情。   
    * 點選瀏覽並選取 Intrastat (format).xml 檔案。  
23. 點選確定。
24. 在樹狀結構中，選取「Intrastat (model)\Intrastat (format)」。
25. 點選設計工具。
26. 點選展開/摺疊。
27. 在樹狀結構中，選取「File\Declaration」。
28. 點選對應索引標籤。
29. 在樹狀結構中，選取「File」。
    * 查看用於產生 Intrastat 報表的格式的結構。 請注意，它旨在透過填入資料模型中的資料來產生 XML 檔案，該資料模型基於根項「For outgoing document」。 驗證產生檔案的名稱是否已在使用者對話方塊表單上定義 (為此使用了「fn」資料來源)。   
30. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]