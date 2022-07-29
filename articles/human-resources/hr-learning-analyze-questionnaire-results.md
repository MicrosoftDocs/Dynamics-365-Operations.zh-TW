---
title: 分析問卷結果
description: 問卷統計可用來根據一套人口統計資料計算平均值、總數和佔比。
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1ad98638810206dad04c34a8abbc8f757058cc0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452352"
---
# <a name="analyzing-questionnaire-results"></a>分析問卷結果


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



問卷統計可用來根據一套人口統計資料計算平均值、總數和佔比。 若要開始這段程序，請前往 **問卷** > **檢視和分析結果** > **問卷統計**。 用來建立此程序的示範資料公司為 USMF。


## <a name="create-a-questionnaire-statistics-record"></a>建立問卷統計記錄
1. 前往 **問卷統計**。
2. 點選 **新增**。
3. 在清單中，標示選取的列。
4. 請在 **統計** 欄位中輸入一值。
5. 在 **描述** 欄位中，輸入一個值。
6. 請在 **問券** 欄位中點選下拉式按鈕打開查閱功能。
7. 在清單中，點選已選取列的連結。
8. 按一下 **一般** 索引標籤。
    * 選取您是否希望從背景工作角色、聯絡和申請人納入匿名結果。  
9. 選取或清除 **背景工作角色** 勾選方塊。
    * 如果您將按資歷或年齡檢視結果，請指明您希望用來分組結果的間隔時間。  
    * 年齡間隔輸入 5 將根據五年的年齡間隔分組結果。  
10. 請在 **年齡** 欄位中輸入數字。
    * 選取您是否希望對整份問卷、各個結果群組、問題或問題行執行計算動作。  
    * 選取您希望分組結果的方式。  
    * 例如，如果您計算各問題的平均點數，您可能希望查看按結果群組分組的問題。  
    * 選取作為計算依據的資料。  
    * 例如，如果您希望查看您的背景工作角色在問卷上收到的平均佔比，與您的背景工作角色達到的平均點數之間的差異。  
11. 點選 **範圍** 索引標籤。
    * 使用範圍將您的結果集合限制為只符合範圍標準。  
12. 點選 **分組依據** 索引標籤。
    * 使用分組來判定結果的顯示方式。  
    * 例如，先按照性別，再按照年齡分組結果。  
13. 在清單中，尋找並選取所需的記錄。
    * 將分組區塊移入 **已選取** 端並按想要的順序放置。  

## <a name="execute-the-statistics-calculation"></a>執行統計計算
1. 點選 **執行**。
    * 選取您希望對結果執行的計算功能。  
    * 例如，計算選取的分組區塊問卷的平均佔比，或加總選取的分組區塊結果群組點數。  
2. 選取或清除 **刪除之前搜尋** 的勾選方塊。
3. 點選 **確定**。

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a>檢視問卷統計的執行結果。
1. 點選 **結果**。
2. 點選 **結果**。
3. 關閉頁面。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
