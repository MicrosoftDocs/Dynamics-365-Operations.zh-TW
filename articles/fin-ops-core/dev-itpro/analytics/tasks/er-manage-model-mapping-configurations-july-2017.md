---
title: 在單獨的 ER 設定中管理 ER 模型對應
description: 本主題介紹如何在單獨的 ER 設定中管理電子報表 (ER) 模型對應。
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
ms.openlocfilehash: cf4896bec7aa68cc6616756ef07c4db95e20a5cf7ebde3102f482cd5abad1420
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460238"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a>在單獨的 ER 設定中管理 ER 模型對應

[!include [banner](../../includes/banner.md)]

以下步驟說明指派給系統管理員或電子報表開發人員角色的使用者如何在單獨的 ER 設定中管理電子報表 (ER) 模型對應。 在本工作指南中，您將為樣本公司 Litware, Inc 創建所需的 ER 設定。若要完成本工作指南，您必須首先完成工作指南「ER 創建設定提供者」中的步驟並將其標記為活動。 

由於 ER 設定在公司之間共享，因此您可以使用您選取的公司資料集來完成此工作指南。 如果您已安裝以下修補程式之一，則此工作指南的函數可用：https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 (適用於 Dynamics AX 7.0 版本) 或 https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 適用於 Dynamics 365 for Operations 版本。

1. 進入組織管理 > 工作區 > 電子報表。
    * 驗證樣本公司 Litware, Inc. 的設定提供者是否可用並標記為作用中。 如果您沒有看到此設定提供者，您必須首先完成工作指南中的步驟，創建設定提供者，並將其標記為作用中。   

## <a name="add-a-new-er-model-configuration"></a>新增新的 ER 模型配置
1. 點選報表設定。
    * 新增新的模型設定。 該名稱在設定樹狀結構中必須是唯一的。  
2. 點選建立設定即可打開下拉式對話方塊。
3. 在名稱欄位中，輸入「Sample data model」。
    * 樣本資料模型  
4. 點選建立設定。
5. 點選設計工具。
6. 按一下新增以開啟下拉式對話方塊。
7. 在名稱欄位，輸入｢Root」。
    * 根  
8. 選點新增。
9. 按一下新增以開啟下拉式對話方塊。
10. 在名稱欄位，輸入「Company」。
    * 公司  
11. 選點新增。
12. 在描述欄位中，輸入文字，即使用者在執行階段登入的法律實體或公司的描述。 
    * 使用者在執行階段登入的法律實體或公司的描述。  
13. 點選根參考。
14. 點選確定。
15. 點選儲存。
16. 關閉頁面。
17. 點選更改狀態。
18. 點選完成。
19. 點選確定。

## <a name="add-a-new-er-model-mapping-configuration"></a>新增新的 ER 模型對應設定
1. 點選建立設定即可打開下拉式對話方塊。
2. 在新增欄位中，輸入「Model Mapping based on data model Sample data model」。
3. 在名稱欄位，輸入「Sample mapping」。
    * 樣本對應  
4. 點選建立設定。
5. 展開先決條件區段。
    * 實施先決條件組已自動新增。 該組包含參考父資料模型設定並標記為實現的必備組件。 這代表這個樣本對應模型對應設定被認為是資料模型 (樣本資料模型) 的實施。 因此，當模型設定樣本資料模型被下載時，此組件將強制 ER 從 ER 儲存庫下載模型對應設定樣本對應。   
6. 點選設計工具。
    * 創建的模型對應設定包含一個與創建的設定同名的新空白對應。 當選定的父模型設定包含模型對應時，它們將被複製到新的模型對應設定中。   
7. 點選設計工具。
8. 在樹狀結構中，選取「Dynamics 365 for Operations\資料表」。
9. 點選新增根。
10. 在名稱欄位，輸入「Company」。
    * 公司  
11. 在資料表欄位，輸入「CompanyInfo」。
    * CompanyInfo  
12. 點選確定。
13. 在樹狀結構中，展開「公司」。
14. 在樹狀結構中，展開「公司\尋找 ()」。
15. 在樹狀結構中，選取「公司\尋找 ()\名稱」。
16. 點選繫結。
17. 點選儲存。
18. 關閉頁面。
19. 關閉頁面。
20. 在動作窗格上，點選設定。
21. 點選使用者參數。
22. 在執行設定欄位中選取是。
23. 點選確定。
24. 點選編輯。
25. 在執行草稿欄位中選取是。

## <a name="add-a-new-er-format-configuration"></a>新增新的 ER 格式設定
1. 在樹狀結構中，選取「樣本資料模型」。
2. 點選建立設定即可打開下拉式對話方塊。
3. 在新增欄位中，輸入「Format based on data model Sample data model」。
4. 在名稱欄位，輸入「Sample format」。
    * 樣本格式  
5. 點選建立設定。
6. 點選設計工具。
7. 點選新增根以開啟下拉式對話方塊。
8. 在樹狀結構中，選取「文字\字串」。
9. 點選確定。
10. 點選對應索引標籤。
11. 在樹狀結構中，展開「模型」。
12. 在樹狀結構中，選取「模型\公司」。
13. 點選繫結。
14. 點選儲存。
15. 關閉頁面。
    * 執行所創建格式的草稿版本以進行測試。  
16. 點選執行。
    * 在版本 FastTab 上，點選執行。  
17. 點選確定。
    * 查看包含執行此格式設定的使用者登入的公司名稱的輸出。 此格式設定使用創建的模型對應設定，因為只有一個可用的設定包含所需的模型對應。   

## <a name="add-alternative-er-model-mapping-configuration"></a>新增替代的 ER 模型對應設定
1. 在樹狀結構中，選取「樣本資料模型」。
2. 點選建立設定即可打開下拉式對話方塊。
3. 在新增欄位中，輸入「Model Mapping based on data model Sample data model」。
4. 在名稱欄位，輸入「Sample mapping (alternative)」。
    * 樣本對應 (替代)  
5. 點選建立設定。
6. 點選設計工具。
7. 點選設計工具。
8. 在樹狀結構中，選取「Dynamics 365 for Operations\資料表」。
9. 點選新增根。
10. 在名稱欄位，輸入「Company」。
    * 公司  
11. 在資料表欄位，輸入「CompanyInfo」。
    * CompanyInfo  
12. 點選確定。
13. 點選編輯。
14. 在樹狀結構中，選取「字串\連接」。
15. 點選新增函數。
16. 在樹狀結構中，展開「公司」。
17. 在樹狀結構中，展開「公司\尋找 ()」。
18. 在樹狀結構中，選取「公司\尋找 ()\名稱」。
19. 點選新增資料來源。
20. 在公式欄位中，輸入一個值。
    * CONCATENATE(Company.'find()'.Name, ";",  
21. 在樹狀結構中，選取「Company\find()\Company(DataArea)」。
22. 點選新增資料來源。
23. 在公式欄位中，輸入一個值。
    * CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)  
24. 點選儲存。
25. 關閉頁面。
26. 點選儲存。
27. 關閉頁面。
28. 關閉頁面。
29. 在執行草稿欄位中選取是。

## <a name="use-an-existing-er-model-mapping-configuration"></a>使用現有的 ER 模型對應設定
1. 在樹狀結構中，選取「樣本資料模型\樣本格式」。
2. 點選執行。
    * 無法執行所選的 ER 格式設定草稿版本，因為有多個模型對應設定可用於已選為執行 ER 格式的資料來源的未定義資料模型。   
    * 接下來，您將定義替代模型對應設定作為模型對應將用作執行 ER 格式的資料來源的設定。   
3. 在樹狀結構中，選取「Sample data model\Sample mapping (alternative)」。
4. 在模型對應的預設欄位中選取是。
5. 在樹狀結構中，選取「樣本資料模型\樣本格式」。
6. 點選執行。
7. 點選確定。
    * 此格式設定使用預設模型對應設定來產生電子文件 (創建的輸出包含公司代碼)。  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]