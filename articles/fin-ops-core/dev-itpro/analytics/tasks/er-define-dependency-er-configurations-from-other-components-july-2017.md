---
title: 定義 ER 設定對其他組件的相依性關係
description: 本主題介紹如何設計電子報表 (ER) 設定並指定其與其他軟件組件的相依性關係。
author: NickSelin
ms.date: 07/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2901092938dae5ae14480716eeeb2b0386848332e91ad388ce5d34437f8492ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460267"
---
# <a name="define-the-dependency-of-er-configurations-on-other-components"></a>定義 ER 設定對其他組件的相依性關係

[!include [banner](../../includes/banner.md)]

若要完成這些步驟，您必須先完成工作指南 ER 管理模型對應設定中的步驟，並且您必須有權存取 Microsoft Dynamics Lifecycle Services (LCS)。

此程序說明如何設計電子報表 (ER) 設定並指定其與其他軟件組件的相依性關係，以便您可以幫助確保將設定正確下載到特定版本的 Finance and Operations。 在此範例中，您將為樣本公司 Litware, Inc. 建立所需的 ER 設定。 

此程序適用於指派有系統管理員或電子報表開發人員角色的使用者。 這些步驟可以在任何公司中執行，因為 ER 設定在公司之間共用。 

1. 進入組織管理 > 電子報表 > 設定。
    * 確保設定樹狀結構包含「樣本資料模型」設定和從屬項。 否則，請完成工作指南 ER 管理模型對應設定中的步驟，然後重新開始本指南。   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a>定義 ER 設定與其他組件的相依性關係
1. 在樹狀結構中，展開「樣本資料模型」。
2. 在樹狀結構中，選取「Sample data model\Sample mapping」。
    * 我們選取了「樣本對應」模型對應設定的草稿版本。 我們現在將定義它與其他軟件組件的相依性關係。 此步驟被認為是控制從 ER 存放庫下載此設定版本以及進一步使用此版本的先決條件。   
3. 展開先決條件區段。
    * 請注意，「實施」先決條件組已在此階段自動新增。 此組包含參考資料模型設定的先決條件，並打開了實施標幟。 此標幟指示「樣本對應」對應設定被視為「樣本資料模型」資料模型的實施。 每當下載「樣本資料模型」模型設定時，此組件將強制 ER 從 ER 存放庫下載「樣本對應」對應設定。   
4. 點選編輯。
    * 可以透過使用組件類型的定義以及組件版本或組件版本範圍來指定軟件組件的現行設定版本的單個相依性關係。  
    * 所需的相依性關係可以組合在一起。 當選取「全部」分組類型時，當滿足該組和從屬組的每個相依性條件時，認為滿足該組的相依性條件。 當選取「其中一個」分組類型時，當滿足該組的至少一個相依性條件時，認為滿足該組的相依性條件。   
5. 點選「新增」。
6. 選取產品必備組件。
7. 選取 Microsoft Dynamics 365 for Operations (1611)。
8. 在版本欄位，輸入「[7.1.1541.3036,8)」。
    * [7.1.1541.3036,8)  
    * 當從任何 ER 存放庫下載此設定時，將評估您輸入的相依性項。 當「樣本資料模型」設定的版本 1 已經到位或提前下載時，將從 ER 存放庫下載此設定版本。 如果提前下載，必須在 Finance and Operations 版本 7.1.1541.3036 或更高版本中完成，但不得超過主要版本 8。   
9. 點選儲存。
10. 關閉頁面。
11. 點選更改狀態。
12. 點選完成。
13. 點選確定。
14. 在樹狀結構中，選取「Sample data model\Sample mapping (alternative)」。
15. 點選編輯。
16. 點選新建。
17. 選取產品必備組件。
18. 選取 Microsoft Dynamics AX 7.0 RTW。
19. 在版本欄位，輸入「[7.0.1265.3015,7.1)」。
    * [7.0.1265.3015,7.1)  
    * 當從任何 ER 存放庫下載設定時，將評估相依性關係。 當「樣本資料模型」設定的版本 1 已經到位或提前下載時，將從 ER 存放庫下載此設定版本。 如果提前下載，必須在 Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 中完成，其版本必須為 7.0.1265.3015 或更高版本，但不得超過次要版本 1。   
20. 點選儲存。
21. 關閉頁面。
22. 點選更改狀態。
23. 點選完成。
24. 點選確定。

## <a name="configure-the-er-repository"></a>設定 ER 存放庫
1. 關閉頁面。
2. 進入組織管理 > 工作區 > 電子報表。
    * 開啟現行 ER 提供商 Litware, Inc. 的 ER 存放庫清單。  
3. 在清單中，標示選取的列。
4. 點選存放庫。
5. 點選顯示過濾器。
6. 使用「包含」過濾器運算子在「類型名稱」欄位中輸入過濾器值「LCS」。
    * 如果 LCS 存放庫已為現行 ER 提供者註冊，您可以跳過此子工作中的剩餘步驟。 如果 LCS 存放庫尚未註冊，請完成剩餘步驟。   
7. 點選新增以開啟下拉式對話方塊。
8. 在設定存放庫類型欄位中，輸入「LCS」。
9. 點選建立存放庫。
10. 在專案欄位中，輸入或選取一個值。
    * 從「專案」欄位的查詢中選取所需的 LCS 項目。  
11. 點選確定。
12. 關閉頁面。

## <a name="upload-configurations-to-lcs"></a>將設定上傳到 LCS
1. 點選報表設定。
2. 在樹狀結構中，選取「樣本資料模型」。
3. 選取此設定的完整版本。
4. 點選更改狀態。
5. 點選共用。
6. 點選確定。
    * 此模型設定的版本 1 已使用先前設定的 ER 存放庫的 LCS 項目上傳到 LCS。   
7. 在樹狀結構中，展開「樣本資料模型」。
8. 在樹狀結構中，選取「Sample data model\Sample mapping」。
9. 選取此設定的完整版本。
10. 點選更改狀態。
11. 點選共用。
12. 點選確定。
    * 此模型對應設定的版本 1.1 已使用先前設定的 ER 存放庫的 LCS 項目上傳到 LCS。   
13. 在樹狀結構中，選取「Sample data model\Sample mapping (alternative)」。
14. 選取此設定的完整版本。
15. 點選更改狀態。
16. 點選共用。
17. 點選確定。
    * 此模型對應設定的版本 1.1 已使用先前設定的 ER 存放庫的 LCS 項目上傳到 LCS。   

## <a name="evaluate-er-configuration-dependencies"></a>評估 ER 設定相依性
我們將從系統中刪除建立的設定並從 LCS 存放庫中下載它們。  
1. 在樹狀結構中，選取「Sample data model\Sample mapping」。
2. 點選刪除。
3. 點選是。
4. 在樹狀結構中，選取「Sample data model\Sample mapping (alternative)」。
5. 點選刪除。
6. 點選是。
7. 在樹狀結構中，選取「樣本資料模型\樣本格式」。
8. 點選刪除。
9. 點選是。
10. 在樹狀結構中，選取「樣本資料模型」。
11. 點選刪除。
12. 點選是。
13. 關閉頁面。
    * 開啟現行 ER 提供商 Litware, Inc. 的 ER 存放庫清單。  
14. 點選存放庫。
15. 點選顯示過濾器。
16. 使用「包含」過濾器運算子在「類型名稱」欄位中輸入過濾器值「LCS」。
17. 點選開啟。
18. 在樹狀結構中，選取「樣本資料模型」。
    * 請注意，您可以查看對現行存放庫的每個版本的 ER 設定是否滿足先決條件的評估。 若要查看此評估，請點選檢查先決條件。   
19. 點選檢查先決條件。
20. 點選匯入。
21. 點選是。
22. 關閉頁面。
23. 關閉頁面。
24. 關閉頁面。
25. 進入組織管理 > 電子報表 > 設定。
26. 在樹狀結構中，展開「樣本資料模型」。
    * 請注意，模型「樣本對應」對應設定已與所選資料模型設定一起下載。 這兩個檔案是一起下載的，因為「樣本對應」已被定義為實現選定的資料模型，並且因為它適用於應用程式。 由於不滿足所需應用程式版本的條件，尚未下載「樣本對應 (替代)」設定。   
    * 如果您登入 Finance and Operations，註冊相同的提供者，存取相同的 LCS 項目，並下載相同的資料模型設定，則會下載「樣本對應 (替代) 」設定，而「樣本對應」設定將被跳過。  

## <a name="additional-resources"></a>其他資源

[管理電子報表 (ER) 設定生命週期](../general-electronic-reporting-manage-configuration-lifecycle.md)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
