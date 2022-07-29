---
title: Excel 的預算計劃範本
description: 本主題介紹如何建立可用於預算計劃的 Microsoft Excel 範本。
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: roschlom
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8297548bee83d1e982f50c4e5adae748f9f40137362f4ad47ad837ea2af96c29
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450813"
---
# <a name="budget-planning-templates-for-excel"></a>Excel 的預算計劃範本

[!include [banner](../includes/banner.md)]

本主題介紹如何建立可用於預算計劃的 Microsoft Excel 範本。

本主題說明如何使用標準示範資料集和管理使用者登入建立可用於預算計劃的 Excel 範本。 有關預算計劃的詳細資訊，請參閱[預算計劃概觀](budget-planning-overview-configuration.md)。 您也可以按照[預算計劃](budget-plan.md)教學課程了解基本的模組設定和使用原則。

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>使用預算計劃文件版面配置產生工作表

可以使用一種或多種版面配置查看和編輯預算計劃文件。 每個版面配置都可以有一個關聯的預算計劃文件範本，以在 Excel 工作表中查看和編輯預算計劃資料。 在本主題中，將使用現有版面配置設定產生預算計劃文件範本。 

1. 打開 **預算計劃清單** (**預算編製** &gt; **預算計劃**)。 
2. 點擊 **新增** 以建立新的預算計劃文件。 

   [![預算計劃清單。](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. 使用 **新增** 行選項來新增行。 點擊 **版面配置** 來查看預算計劃文件版面配置設定。 

   [![預算計劃新增。](./media/bpt2-1024x274.png)](./media/bpt2.png) 

您可以查看版面配置設定並根據需要進行調整。 
1. 前往 **範本** &gt; **產生**，為這個版面配置建立一個 Excel 檔案。 
2. 產生範本後，前往 **範本** &gt; **檢視**，以打開並查看預算計劃文件範本。 您可以將 Excel 檔案儲存到本機磁碟。 

[![另存新檔。](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> 與 Excel 範本關聯後，無法編輯預算計劃文件版面配置。 要修改版面配置，請刪除關聯的 Excel 範本文件並重新產生它。 若要讓版面配置中的欄位和工作表中的欄位保持同步，就需要執行此動作。 

Excel 範本將包含預算計劃文件版面配置中的所有元素，其中 **在工作表中可用** 欄設定為 True。 Excel 範本中不允許有重疊的元素。 例如，如果版面配置包含 Request Q1、Request Q2、Request Q3 和 Request Q4 欄，以及表示所有 4 個季度欄之和的要求總計欄，則只有季度欄或總計欄可用於 Excel 範本。 Excel 檔案無法在更新期間更新重疊欄，因為資料表中的資料可能超出日期範圍，因此不精確。

> [!NOTE] 
> 為避免使用 Excel 查看和編輯預算計劃資料時可能出現問題，應使用相同使用者登入 Microsoft Dynamics 365 Finance 和 Microsoft Dynamics Office 增益集資料連接器。

## <a name="add-a-header-to-budget-plan-document-template"></a>為預算計劃文件範本新增標題
要新增標題資訊，請選擇 Excel 檔案中的首欄，然後插入空白欄。 點擊 **資料連接器** 中的 **設計**，將標題欄位新增到 Excel 檔案。

在 **設計** 索引標籤，點擊 **新增** 欄位，然後選擇 **BudgetPlanHeader** 作為實體資料來源。

將游標指向 Excel 檔案中的所需位置。 點擊 **新增標籤** 將欄位標籤新增到所選位置。 選擇 **新增價值** 將值欄位新增到所選位置。 點擊 **完成** 以關閉設計工具。

## <a name="select-add-valuemediabpt7png"></a>[![選取新增值。](./media/bpt7.png)](./media/bpt7.png)

## <a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>為預算計劃文件範本資料表新增計算欄

接下來，將把計算欄新增到產生的預算計劃文件範本中。 一個 **總計要求** 欄，用於計算 Request Q1 到 Request Q4 欄之和，以及一個 **調整** 欄，用於按先預定義的係數重新計算 **總要求** 欄。

點擊 **資料連接器** 中的 **設計**，向資料表新增欄。 點擊 **BudgetPlanWorksheet** 資料來源旁邊的 **編輯** 開始新增欄。

[![開始新增欄。](./media/bpt8-1024x301.png)](./media/bpt8.png) 

所選的欄位群組將顯示範本中可用的欄。 點擊 **公式** 新增新欄。 命名新欄，然後將公式貼到 **公式** 欄位中。 點擊 **更新** 以插入欄。

[![新增和插入欄。](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> 要定義公式，請在試算表中建立公式，然後將其複製到 **設計** 視窗。 財務和營運繫結表通常命名為 "AXTable1"。 例如，若要計算試算表中的 Request Q1 到 Request Q4 欄之和，則公式 = AxTable1\[Request Q1\]+AxTable1\[Request Q2\]+AxTable1\[Request Q3\]+AxTable1\[Request Q4\]。

重複這些步驟以插入 **調整** 欄。 為此欄使用公式 = AxTable1\[Total request\]\*$I$1。 這將取得儲存格 I1 中的值並乘以 **總要求** 欄來計算調整金額。

儲存並關閉 Excel 檔案。 在 **版面配置** 中，點擊 **範本 &gt; 上傳**，上傳已儲存的 Excel 範本以用於預算計劃。 

[![上傳 Excel 範本。](./media/bpt10-1024x352.png)](./media/bpt10.png) 

關閉 **版面配置** 滑桿。 在 **預算計劃** 文件中，點擊 **工作表** 以在 Excel 中查看和編輯文件。 請注意，此預算計劃工作表是使用調整後的 Excel 範本建立的，並使用在前面的步驟中定義的公式更新計算欄。 

[![在 Excel 中查看和編輯文件。](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>建立預算計劃範本的提示和技巧
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>是否可以為預算計劃範本新增和使用其他資料來源？

是的，可使用 **設計** 功能表以將其他實體新增到 Excel 範本中的相同或其他工作表。 例如，您可以新增 **BudgetPlanProposedProject** 資料來源，以在 Excel 中處理預算計劃資料時，建立和維護提議專案清單。 請注意，包含大量資料來源可能會影響 Excel 活頁簿的效能。 

您可以使用 **資料連接器** 中的 **篩選** 選項，將所需的篩選新增到其他資料來源。

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>是否可以為其他使用者隱藏資料連接器中的設計選項？

可，打開 **資料連接器** 選項，以對其他使用者隱藏 **設計** 選項。

[![打開資料連接器選項。](./media/bpt13-1024x565.png)](./media/bpt13.png)

展開 **資料連接器選項** 並清除 **啟用設計** 核取方塊。 這將在 **資料連接器** 中隱藏 **設計** 選項。

[![隱藏資料連接器中的設計選項。](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>是否可以防止使用者在處理資料時意外關閉資料連接器？

建議鎖定範本以防止使用者關閉它。 要打開鎖定，請點擊 **資料連接器**，右上角會出現一個箭頭。 

[![開啟鎖定。](./media/bpt15-1024x285.png)](./media/bpt15.png) 

點擊箭頭以顯示其他功能表。 選擇 **鎖定**。

### <a name="select-lockmediabpt16png"></a>[![選擇鎖定。](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>是否可以在我的預算計劃範本中使用其他 Excel 功能，例如儲存格格式、顏色、條件格式和圖表？

可以，大多數標準 Excel 功能都可以在預算計劃範本中使用。 建議使用者使用顏色編碼來區分唯讀欄和可編輯欄。 條件格式可用於醒目顯示預算的問題區域。 使用標準 Excel 公式在資料表上方可以輕鬆顯示欄總數。

您還可以建立和使用樞紐表和圖表來對預算資料進行其他分組和視覺化。 在 **資料** 索引標籤上的 **連接** 群組中，點擊 **全部重新整理**，然後點擊 **連接屬性**。 點擊 **使用方式** 索引標籤。在 **重新整理** 下選擇 **打開文件時重新整理資料** 核取方塊。 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]