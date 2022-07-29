---
title: 預算計劃
description: 本實驗的用途是提供預算計劃區域中 Microsoft Dynamics 365 Finance 功能更新的指導性檢視表。 本實驗的用途是說明預算計劃模組的快速設定範例，並顯示如何使用此設定完成預算計劃。
author: panolte
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0420887c35bbb07aaf8cce05a68173ab6c534f92
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451026"
---
# <a name="budget-planning"></a>預算計劃

[!include [banner](../includes/banner.md)]

本實驗的用途是提供預算計劃區域中 Microsoft Dynamics 365 Finance 功能更新的指導性檢視表。 本實驗的用途是說明預算計劃模組的快速設定範例，並顯示如何使用此設定完成預算計劃。  本實驗將重點介紹以下業務流程或工作：
- 為預算計劃和設定使用者安全性建立組織階層
- 定義預算計劃方案、預算計劃欄、版面配置和 Excel 範本
- 建立和啟用預算計劃流程
- 透過從總帳中提取實際值來建立預算計劃文件
- 使用分配調整預算計劃文件資料
- 在 Excel 中編輯預算計劃文件資料 

## <a name="prerequisites"></a>先決條件 

對於本教學課程，您需要存取包含 Contoso 示範資料的 Microsoft Dynamics 365 Finance 環境，並以管理員身份在執行個體上進行佈建。 請勿在此實驗中使用私人瀏覽器模式 - 如果需要，請從瀏覽器中的其他帳戶退出並使用管理員認證登入。 登入後，**必須** 選取「保持登入狀態」核取方塊。 這將建立 Excel 應用程式目前需要的持久 Cookie。 如果使用 IE 以外的瀏覽器登入應用程式，系統會提示您在 Excel 應用程式中登入。 當您在 Excel 應用程式中點擊「登入」時，將打開 IE 快顯視窗，登入時 **必須** 選取「保持登入狀態」核取方塊。 如果在 Excel 應用程式中點擊「登入」似乎沒有執行任何操作，那麼應清除 IE cookie 快取。

## <a name="scenario-overview"></a>**方案概觀**
Julia 擔任德國 Contoso Entertainment Systems (DEMF) 財務經理。 隨著 2016 財年的臨近，她需要著手製定公司來年的預算。 預算編製如下：

1.  Julia 使用上一年的實際金額作為建立預算的起點。
2.  根據上一年的實際情況，她為來年的 12 個月建立了估計值
3.  Julia 與首席財務長一起審查預算。 完成後，她會對預算計劃進行必要的調整並完成預算編製。

該方案的預算計劃設定結構描述如下所示：

![預算計劃設定結構描述。](./media/screenshot1-300x152.png)

Julia 使用以下 Excel 範本來編製預算：

[![Excel 範本。](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

## <a name="exercise-1-configuration"></a>練習 1：設定

### <a name="task-1-create-organizational-hierarchy"></a>**工作 1：建立組織階層**
由於所有預算流程都發生在財務部門，因此 Julia 需要建立一個非常簡單的組織階層 - 僅包括財務部門。 

1.1. 瀏覽到組織階層 (組織管理 &gt; 組織 &gt; 組織階層)，然後點擊 [新增] 按鈕。

![組織階層。](./media/screenshot3.png) 

1.2. 在名稱方塊中鍵入組織階層的名稱，然後點擊 [分配用途]。

1.3. 選擇預算計劃用途，點擊 [新增並分配新建立的組織階層]。 

[![分配用途。](./media/screenshot5.png)](./media/screenshot5.png)

1.4. 對安全性組織用途重複上述步驟。 完成後關閉表單。

1.5. 在組織階層表單中，點擊 [查看]。 在階層設計工具中點擊 [編輯]，然後點擊 [插入] 建立階層。

[![插入。](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. 為預算階層選擇財務部門。 

[![財務。](./media/screenshot8.png)](./media/screenshot8.png)

1.7. 完成後，點擊 [發佈] 和 [關閉]。 選擇 1/1/2015 作為階層發佈的生效日期。

[![生效日期。](./media/screenshot9.png)](./media/screenshot9.png)

### <a name="task-2-configure-user-security"></a>工作 2：設定使用者安全性
預算計劃使用特殊的安全性原則來設定對預算計劃資料的存取權。 Julia 需要授與自己對財務預算計劃的存取權。 

2.1. 切換到 DEMF 法律實體內容。 


2.2. 瀏覽到預算 &gt; 設定 &gt; 預算計劃 &gt; 預算計劃設定。 在參數索引標籤中，將資訊安全模型值設定為 [根據安全性組織]。 

[![參數。](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. 瀏覽到系統管理 &gt; 使用者 &gt; 使用者。 授予使用者管理員 (Julia Funderburk) 預算經理角色。 

[![預算經理。](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. 選擇使用者角色並點擊 [分配組織]。 

[![分配組織。](./media/screenshot13.png)](./media/screenshot13.png)

2.5. 選取 [將存取權限授與特定組織]。 在第一步中選擇建立的組織階層。 選擇財務節點，然後點擊 [授予組織及其子組織的存取權] 按鈕。 

***重點！** _ _確保您在執行此工作時處於 DEMF 法律實體環境中，因為組織安全性套用於每個法律實體* 

### <a name="task-3-create-scenarios"></a>工作 3：建立方案
3.1. 瀏覽到預算編製 &gt; 設定 &gt; 預算計劃 &gt; 預算計劃設定。 在方案頁面中，請注意我們將在本實驗中進一步使用的方案：上一年的實際值和預算值。 

*請注意：如果需要，您可以為此練習建立新方案並使用這些方案。* 

[![新案例。](./media/screenshot15.png)](./media/screenshot15.png) 

*請注意：由於 Julia 沒有使用正式的核准流程來編制預算，我們將跳過本實驗中的工作流程、階段和工作流程階段設定，並將使用現有設定進行自動核准工作流程。有關此工作流程設定，請參見附錄。*

### <a name="task-4-create-budget-plan-columns"></a>工作 4：建立預算計劃欄
預算計劃欄是可以在預算計劃文件版面配置中使用的根據貨幣或數量的欄。 在我們的範例中，需要為上一年的實際值建立一個欄，並建立 12 個欄來表示預算年度中的每個月。 可以透過簡單地點擊 [新增] 按鈕並填寫值來建立欄，也可以在資料實體說明下建立欄。 在本實驗中，我們將使用資料實體來填入值。 

4.1. 在預算編製 &gt; 設定 &gt; 預算規劃 &gt; 預算計劃設定，打開「欄」頁面。 點擊表單右上角的 Office 按鈕，然後選擇 [欄] (未篩選)。 

[![未篩選的欄。](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. 系統將打開用於填寫值的 Excel 活頁簿。 如果出現提示，請點擊 [啟用編輯] 和 [信任此應用程式]。 

4.3. 我們需要更多的欄來填寫值。 點擊右側窗格上的 [設計] 以將欄新增到格線中。 

[![設計。](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. 點擊 PlanColumns 旁邊的鉛筆按鈕以查看要新增到格線的可用欄。 

[![編輯。](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. 按兩下每個可用欄位以將它們新增到所選欄位，然後點擊 [更新]。 

4.6. 在 Excel 表中，新增所有需要建立的欄。 使用 Excel 中的自動填寫功能快速新增行。 確保將行新增為資料表的一部分 (使用垂直滾動時，您應該能夠在格線頂端看到欄標題)。 

4.7. 返回應用程式並重新整理頁面。 將顯示發佈的值。 

[![重新整理。](./media/screenshot23.png)](./media/screenshot23.png)

### <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>工作 5：建立預算計劃文件版面配置和範本
版面配置定義了使用者打開預算計劃文件時，預算計劃文件行格線的外觀。 還可以切換預算計劃文件的版面配置，從不同的角度查看相同的資料。 現在，由於她定義了要與我們的預算計劃文件一起使用的欄，因此 Julia 需要建立一個預算計劃文件版面配置，該版面配置看起來類似於她用於建立預算資料的 Excel 表 (請參閱本實驗中的「方案概觀」區段) 

5.1. 在預算編製 &gt; 設定 &gt; 預算計劃 &gt; 預算計劃設定，打開版面配置頁面。 為每月預算分錄建立新版面配置：

-   選擇 MA+BU 維度集以將主科目和業務單位包括到版面配置中。
-   列出在「元素」區段的上一步中建立的所有預算計劃欄。 使除上一年的實際值之外的所有值都可以編輯。
-   點擊 [描述] 按鈕以選擇哪些財務維度應在格線中顯示描述。

[![描述。](./media/screenshot24.png)](./media/screenshot24.png) 

根據預算計劃版面配置定義，我們可以建立一個 Excel 範本，作為編輯預算資料的替代方法。 由於 Excel 範本必須符合預算計劃版面配置定義，產生 Excel 範本後您將無法編輯預算計劃版面配置，因此該工作應在定義所有版面配置元件後完成。 

5.2. 對於步驟 5.1 中建立的版面配置， 點擊按鈕 [範本] &gt; [產生]。 確認警告資訊。 要查看範本，請點擊 [範本] &gt; [查看]。 

*請注意：確保選擇 [另存新檔] 並選擇範本應儲存以便對其進行編輯的位置。如果使用者在對話方塊中選擇 [打開] 而不儲存，則在關閉文件時不會保留對文件所做的變更。* 
[![範本檢視表。](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt;可選步驟&gt; 修改 Excel 範本使其更方便使用者使用 - 新增總計公式、標題欄位、格式等。儲存變更並透過點擊 [版面配置] &gt; [上傳] 將文件上傳到預算計劃版面配置。 


### <a name="task-6-create-a-budget-planning-process"></a>工作 6：建立預算計劃流程
Julia 需要建立並啟用一個新的預算計劃流程，結合上述所有設定以開始輸入預算計劃。 預算計劃流程定義了將用於建立預算計劃的預算組織、工作流程、版面配置和範本。 

6.1. 瀏覽到 [預算編製] &gt; [設定] &gt; [預算計劃] &gt; [預算計劃流程]，並建立新記錄。

-   預算計劃流程 - DEMF 預算編製 FY2016
-   預算週期 – FY2016
-   分類帳 – DEMF
-   預設帳戶結構 - 製造損益表
-   組織階層 - 選擇在實驗開始時建立的階層
-   預算計劃工作流程 - 分配自動 - 財務部門核准工作流程
-   在預算計劃階段規則和範本中，對於每個工作流預算計劃階段選擇是否允許新增行和修改行以及預設情況下應使用什麼版面配置

*請注意：您可以建立其他文件版面配置，並透過點擊 [備用版面配置] 按鈕指定它們可用於預算計劃工作流階段。* 

[![備用版面配置。](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. 選擇 [動作] &gt; [啟用] 以啟用此預算計劃工作流程。 

[![啟用。](./media/screenshot28.png)](./media/screenshot28.png)

## <a name="exercise-2-process-simulation"></a>練習 2：流程模擬

### <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>工作 7：從總帳產生預算計劃的初始資料
7.1. 瀏覽到 [預算] &gt; [定期] &gt; [從總帳產生預算計劃]。 填寫定期流程參數，然後點擊 [產生]。 

7.2. 瀏覽到 [預算編製] &gt; [預算計劃] 以尋找由 [產生] 流程建立的預算計劃。 

[![預算計劃。](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. 點擊文件編號超連結打開文件詳細資料。 預算計劃按照本實驗期間建立的版面配置中的定義顯示。 

[![預算計劃顯示。](./media/screenshot31.png)](./media/screenshot31.png)

### <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>工作 8：根據前一年的實際情況建立本年度預算
分配方法可用於預算計劃中，以便輕鬆地將預算計劃的資訊從一個方案複製到另一個方案/跨期間分佈/分配到維度。 我們將使用分配來根據上一年的實際情況建立本年度的預算。 

8.1. 選擇預算計劃文件格線中的所有行，然後點擊 [分配預算]。 

[![所有行。](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. 選擇分配方法、期間索引鍵、來源和目標方案，然後點擊 [分配]。 

[![分配。](./media/screenshot33.png)](./media/screenshot33.png)

上一年的實際金額將複製到本年度的預算中，並使用銷售曲線期間索引鍵跨期間分配它們。 

[![銷售曲線。](./media/screenshot34.png)](./media/screenshot34.png)

### <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>工作 9：使用 Excel 調整預算計劃文件並完成文件
9.1. 點擊 [工作表] 按鈕以在 Excel 中打開文件內容。

9.2. Excel 活頁簿打開後，調整預算計劃文件中的數字，然後點擊 [發佈] 按鈕。

9.3. 返回預算計劃文件。 點擊 [工作流程] &gt; [提交] 以自動核准文件。

[![自動核准。](./media/screenshot37.png)](./media/screenshot37.png) 

工作流程完成後，預算計劃文件階段變更為已核准。 [![已核准。](./media/screenshot38.png)](./media/screenshot38.png)

## <a name="appendix"></a>附錄

### <a name="auto-approve-workflow-configuration"></a>自動核准工作流程設定

A. [預算] &gt; [設定] &gt; [預算計劃] &gt; [預算編製工作流程]。 使用範本 [預算計劃工作流程] 建立新的工作流程：

[![建立新工作流程。](./media/screenshot39.png)](./media/screenshot39.png)

此工作流程將僅包含一項工作 - 階段過渡預算計劃。 

[![階段過渡預算計劃。](./media/screenshot40.png)](./media/screenshot40.png) 

儲存並啟動工作流程。 

B. 瀏覽到預算 &gt; 設定 &gt; 預算計劃 &gt; 預算計劃設定。 在「階段」索引標籤中，建立 2 個階段 - 初始和已提交。 

[![初始和已提交。](./media/screenshot41.png)](./media/screenshot41.png)

C. 瀏覽到預算 &gt; 設定 &gt; 預算計劃 &gt; 預算計劃設定。 在「工作流程階段」索引標籤中，將步驟 A 中建立的工作流「自動核准」與「初始」和「已提交」階段相關聯。

[![預算編製和預算計劃。](./media/screenshot42.png)](./media/screenshot42.png)  





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
