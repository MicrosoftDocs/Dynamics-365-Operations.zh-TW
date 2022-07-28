---
title: ER 建立所需的配置以從外部檔案匯入資料
description: 本主題介紹如何設計電子報表配置以將資料從外部檔案匯入 Microsoft Dynamics 365 Finance 應用程式。
author: NickSelin
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERSolutionCreateDropDialog, EROperationDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula, Tax1099Summary, VendSettlementTax1099
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7eaa35baae8e030d8a8b7ce903554c4876c874b48cfd72d6ac278cf4c0e8a6e8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460392"
---
# <a name="er-create-required-configurations-to-import-data-from-an-external-file"></a>ER 建立所需的配置以從外部檔案匯入資料

[!include [banner](../../includes/banner.md)]

以下步驟說明了系統管理員或電子報表開發人員角色的使用者如何設計電子報表 (ER) 配置以將資料從外部檔案匯入應用程式。 在此範例中，您將為樣本公司 Litware, Inc 建立所需的 ER 配置。要完成這些步驟，您必須先完成工作指南「ER 建立配置提供者並將其標記為作用中」中的步驟。 這些步驟可以使用 USMF 資料集完成。 您還必須在本地下載並儲存以下檔案： 

| 內容描述                       | 檔案名稱                                     |
|-------------------------------------------|-----------------------------------------------|
| ER 資料模型設定 - 1099 | [1099model,xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)                  |
| ER 格式設定 - 1099    | [1099format.xml](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)                  |
| XML 格式的傳入文件樣本                          | [1099entries.xml](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)        |
| 用於管理傳入文件資料的活頁簿樣本                          | [1099entries.xlsx](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx) |

ER 使商務使用者能夠配置將外部資料檔案匯入 .XML 或 .TXT 格式的表的過程。 先，必須設計一個抽像資料模型和一個 ER 資料模型配置來表示您正在匯入的資料。 接下來，您需要定義要匯入的檔案的結構以及將用於將資料從檔案移植到抽像資料模型的方法。 必須為該抽像資料模型建立對應到設計資料模型的 ER 格式配置。 然後，必須使用對應來擴展資料模型配置，該對應描述瞭如何將匯入的資料作為抽像資料模型資料儲存以及如何使用它來更新資料表。  ER 資料模型配置必須附加一個新模型對應，該對應描述資料模型與應用程式目的地的繫結。  

以下場景展示了 ER 資料匯入功能。 這包括在外部追蹤的廠商交易，然後匯入以稍後在廠商的 1099 結算中報表。   

## <a name="add-a-new-er-model-configuration"></a>新增新的 ER 模型配置
1. 進入組織管理 > 工作區 > 電子報表。

    驗證樣本公司"Litware, Inc. "的配置提供者 是否可用並被標記為作用中。 如果您沒有看到此設定提供者，則必須先完成「建立設定提供者並將其標記為作用中」程序中的步驟。   

2. 點選報表設定。

    無需建立新模型來支援資料匯入，而是載入您之前下載的檔案 1099model.xml。 此檔案包含廠商交易的自訂資料模型。 此資料模型對應到 AOT 資料實體中的資料組件。   

3. 點選 Exchange。
4. 點選從 XML 檔案載入。

    點選瀏覽並導覽到您之前下載的 1099model.xml 檔案。  

5. 點選確定。
6. 在樹狀結構中，選取「1099 Payments model」。

## <a name="review-data-model-settings"></a>查看資料模型設定
1. 點選設計工具。

    該模型旨在從業務角度表示廠商的交易，並與實作分開。   

2. 在樹狀結構中，展開「1099-MISC」。
3. 在樹狀結構中，選取「1099-MISC\Transactions」。
4. 在樹狀結構中，展開「1099-MISC\Transactions」。

    該模型的交易元素代表單個交易。 子元素用於為每個交易指定所需的詳情，例如廠商帳戶和交易日期。   

5. 關閉頁面。

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>新增支援資料匯入的新 ER 格式配置
此子工作中的步驟向您展示如何建立新的格式配置來管理從外部檔案匯入的資料。   
1. 點選建立設定即可打開下拉式對話方塊。
2. 在新建欄位中，輸入「Format based on data model 1099 Payments model」。
3. 在支援資料匯入欄位中選取是。
4. 按 ESC 鍵關閉此頁面。

    載入您之前下載的 1099format.xml 檔案，而不是建立 ER 格式來支援資料匯入。 此檔案包含您正在匯入的檔案的定義結構以及該結構到廠商交易的自訂資料模型的對應。   
5. 點選 Exchange。
6. 點選從 XML 檔案載入。
    點選瀏覽並導覽到您之前下載的 1099format.xml 檔案。  
7. 點選確定。
8. 在樹狀結構中，展開「1099 Payments model」。
9. 在樹狀結構中，選取「1099 Payments model\Format for importing vendors' transactions」。

## <a name="review-format-settings"></a>查看格式設定
1. 點選設計工具。
2. 打開「顯示詳情」。
3. 點選展開/摺疊。
4. 點選展開/摺疊。

    設計的格式代表了外部檔案的預期結構。 此檔案必須為 XML 格式並具有結算根元素。 每個廠商的交易由定義為具有零對多多重性的交易元素表示。 這代表傳入的檔案可能包含從零到多個交易的任何地方。 「交易」元素的巢狀元素表示單個交易的屬性。 請注意，除國家/地區之外的所有屬性都被標記為強制，這意味著需要將它們包含在匯入檔案中。   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>查看格式對應到資料模型的設定
1. 點選將格式對應到模型。

    對應「用於匯入廠商的交易」包含從傳入 XML 檔案到自訂資料模型的選定部分的資料傳輸規則，該部分透過選取 1099-MISC 定義來定義。  

2. 點選設計工具。
3. 打開「顯示詳情」。
4. 在樹狀結構中，展開「格式：記錄」。
5. 在樹狀結構中，選取「格式：記錄」。

    請注意，設計的格式在此處顯示為資料來源組件。  

6. 在樹狀結構中，展開 `format: Record\*settlement: XML Element 1..1 (settlement): Record`。
7. 在樹狀結構中，展開 `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list`。
8. 在樹狀結構中，展開 `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record`。
9. 在樹狀結構中，展開 `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\country: XML Element 0..1 (country): Record`。
10. 在樹狀結構中，選取 `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record`。

    請注意，在預定義的「格式」資料來源組件中，強制和可選格式元素的表示是不同的。  
11. 在樹狀結構中，展開「Transactions: Record list= format.settlement.'$enumerated'」。

    請注意，定義匯入檔案結構的格式元素繫結到自訂資料模型的元素。 基於這些繫結，匯入的 XML 檔案的內容將在執行階段儲存在現有資料模型中。 注意國家/地區元素的繫結。 對於傳入檔案中沒有此類元素的任何交易元素，將在資料模型中填入預設國碼 (地區碼)「USA」。  

12. 點選驗證索引標籤。

    此格式對應可能包含使用者定義的邏輯，以從業務角度驗證匯入資料的準確性。 例如，根據設定，對於匯入檔案中沒有定義國碼 (地區碼) 的任何交易，資訊記錄中將產生警告訊息，通知使用者該案例並指示交易的序號。  

13. 關閉頁面。

## <a name="run-the-format-mapping-to-the-data-model"></a>運行到資料模型的格式對應
出於測試目的執行此格式對應。 使用您之前下載的檔案 1099entries.xml。 您可以從用於管理廠商交易的 1099entries.xlsx 活頁簿中匯出此檔案。 產生的輸出將從選定的 XML 檔案中匯入，並在實際匯入時填入自訂資料模型。  

1. 點選執行。

    點選瀏覽並導覽到您之前下載的 1099entries.xml 檔案。  

2. 點選確定。

    請注意有關匯入檔案中交易缺少國碼 (地區碼) 的警告訊息。  
    
    查看 XML 格式的輸出，該輸出表示已從選定檔案匯入並移植到資料模型的資料。   

3. 關閉頁面。
4. 關閉頁面。

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>查看模型對應到目的地的設定
1. 在樹狀結構中，選取「1099 Payments model」。
2. 點選設計工具。
3. 點選將模型對應到資料來源。

    1099 手動交易匯入的對應已使用至目的地方向類型定義。 這意味著它已被輸入以支援資料匯入，並包含定義匯入的外部檔案和作為抽像資料模型資料如何用於更新應用程式中的表的規則設定。  

4. 點選設計工具。
5. 在樹狀結構中，展開「模型：資料模型 1099 付款模型」。
6. 在樹狀結構中，展開「模型：資料模型 1099 付款模型\交易：記錄清單」。

    請注意，設計的模型在此處顯示為資料來源元素。 在執行階段，它將包含從外部檔案匯入的資料。 增加了幾張表作為資料來源元素，保證匯入的資料與目前應用的資料一致，包括系統中是否存在進口交易商帳戶，進口國和州代碼組合是否存在等。  

7. 在樹狀結構中，選取「model: Data model 1099 Payments model\Transactions: Record list\$failed: Calculated field = IF(OR(ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Boolean」。
8. 點選編輯。
9. 點選編輯公式。

    當單個匯入交易的至少一個驗證失敗時，該交易將被資料來源屬性「$failed」標記為失敗。  

10. 關閉頁面。
11. 點選取消。
12. 在樹狀結構中，選取「tax1099trans：Table 'VendSettlementTax1099' records= model.Validated」。
13. 點選編輯目的地。

    新增此 ER 目標以指定匯入的資料將如何更新應用程式表。 在本案例中，已選取資料表 VendSettlementTax1099。 因為已經選取了記錄動作插入，所以匯入的交易將被插入到表 VendSettlementTax1099 中。 請注意，單個模型對應可能包含多個目的地。 這代表匯入的資料可用於一次更新多個應用程式的表。 資料表、檢視表和資料實體可用作 ER 目的地。   

    如果將從專門為此動作設計的應用程式中的某個點 (例如按鈕或選單項目) 調用對應，則應將 ER 目的地標記為整合點。 在此範例中，這是 ERTableDestination#VendSettlementTax1099 點。  

14. 點選取消。
15. 點選顯示全部。
16. 點選僅顯示對應。
17. 在樹狀結構中，展開「tax1099trans: Table 'VendSettlementTax1099' records= model.Validated」。

    請注意，包含唯一經過已驗證交易的資料來源元素繫結到建立的目的地。 您可以篩選匯入的交易以跳過與應用程式資料不相容的交易。  

18. 在樹狀結構中，選取「failed: Table 'VendSettlementTax1099Entity' records= model.Failed」。
19. 點選驗證索引標籤。

    此模型對應可能包含使用者定義的邏輯，以驗證從現有應用程式資料匯入資料的正確性。 例如，基於現行的設定，對於匯入檔案中的任何交易，其廠商帳戶不在系統中，將產生警告訊息通知使用者並指示錯誤的廠商帳戶代碼。  

    請注意，驗證後動作選項可用於每個驗證，以指定是否必須繼續或停止匯入過程，以及是否可以保留或回滾已執行的插入/更新。  

20. 點選僅顯示對應。
21. 點選顯示全部。
22. 關閉頁面。

    執行此模型對應以測試設計的格式和模型對應。 使用檔案 1099entries.xml。 所選檔案中的資料將被匯入系統。  

23. 點選執行。

    請注意，該對話方塊不包含有關必須用於解析匯入檔案然後將資料移植到資料模型的格式對應的其他問題。 這是因為目前只有一種格式使用該模型，它被標記為旨在支援資料匯入。  
    
    定義憑證 ID 以將匯入的交易與可能已經手動輸入或匯入的其他交易區分開來。  

24. 在輸入憑證編號欄位，輸入「IMPORT-001」。

    瀏覽以取得「1099entries.xml」檔案。  

25. 點選確定。

    產生的警告清單提供有關不正確的廠商帳戶、不正確的稅號 1099 方塊代碼、缺少國碼 (地區碼) 等的資訊。將此警告清單與執行 XML 檔案中包含的內容進行比較。  

26. 關閉頁面。
27. 關閉頁面。
28. 關閉頁面。
29. 關閉頁面。
30. 進入應付帳款 > 定期工作 > 稅 1099 > 1099 的廠商結算。

    此表單顯示 Tax1099Summary 表中基於匯入的交易記錄建立的累計交易記錄。  

31. 在開始日期欄位中，將日期設為「2000-01-01」。
32. 點選手動 1099 筆交易。

    此表單包含手動新增的交易清單和我們剛剛匯入的交易清單。  

33. 打開憑證欄篩選器。
34. 使用「開始於」篩選運算子在「憑證」欄位中輸入篩選值「IMPORT-001」。

## <a name="review-the-relationship-between-model-and-format-mappings"></a>查看模型和格式對應之間的關係
1. 關閉頁面。
2. 關閉頁面。
3. 進入組織管理 > 工作區 > 電子報表。
4. 點選報表設定。
5. 在樹狀結構中，選取「1099 Payments model」。

    假設您希望支援從 .TXT 檔案格式匯入相同的資料。   

6. 點選建立設定即可打開對話方塊。 
7. 在新建欄位中，輸入「Format based on data model 1099 Payments model」。
8. 在名稱欄位中，輸入「Import data from TXT file」。
9. 在支援資料匯入欄位中選取是。
10. 點選建立設定。
11. 點選設計工具。
12. 點選將格式對應到模型。
13. 點選新增。
14. 在定義欄位中，輸入或選項值。

    選取「1099-MISC」選項。  

15. 在名稱欄位中，輸入「Import data from TXT file」。
16. 在描述欄位中，輸入「Import data from TXT file」。
17. 點選儲存。
18. 關閉頁面。
19. 關閉頁面。
20. 點選編輯。

    如果您安裝了「KB 4012871 支援 GER 模型對應的分離配置，能夠指定不同種類的先決條件在不同版本的 Dynamics 365 Finance 上進行部署」([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)) 的修補程式，請為輸入的格式配置執行下一步「打開『模型對應的預設』標幟」。 否則跳過下一步。  

21. 在模型對應的預設欄位中選取是。
22. 在樹狀結構中，選取「1099 Payments model」。
23. 點選設計工具。
24. 點選將模型對應到資料來源。
25. 點選執行。

    如果您安裝了熱修復程式，KB 4012871 支援 GER 模型對應的分離配置，能夠指定不同種類的先決條件在不同的版本上進行部署 ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871))，在查詢欄中選取偏好的模型對應。 如果您尚未安裝修補程式，請跳到下一步，因為預設格式配置的定義已經選取了對應。  
    
    如果您尚未安裝修補程式 KB 4012871，請注意該對話方塊包含一個額外的模型對應問題，用於分析您正在匯入的檔案。 然後將資料從對話方塊移植到資料模型。 目前，您可以根據計劃匯入的檔案類型選取必須使用的格式對應。  
    
    如果您計劃從應用程式中專門為動作設計的點調用此模型對應，則必須將 ER 目標和格式對應標記為整合的一部分。  

26. 點選取消。
27. 關閉頁面。
28. 關閉頁面。



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
