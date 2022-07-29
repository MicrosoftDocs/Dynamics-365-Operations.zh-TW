---
title: 使用排程分發問卷
description: 問卷程排允許您計劃問卷並分發給多位受訪者。
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4885c11f0cb508edb8ebf3aef14748e819113264
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452343"
---
# <a name="distribute-questionnaires-using-scheduling"></a>使用排程分發問卷


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

問卷程排允許您計劃問卷並分發給多位受訪者。 用來建立此程序的示範資料公司為 USMF。

## <a name="create-a-questionnaire-schedule"></a>建立問券排程

1. 前往 **問卷** > **分發** > **問卷日程**。

2. 點選 **新增**。

3. 請在 **排程** 欄位中輸入一值。

4. 在 **描述** 欄位中，輸入一個值。
    * 如果匿名相關回應應該詳實記錄，則應將日程設定為 **匿名**。  
    * 允許匿名結果先在人力資源參數中設定。  

5. 請在 **類型** 欄位中選取規劃類型。  我們將在本範例使用 **滿足** 類型。

6. 在清單中，尋找並選取所需的記錄。

7. 在清單中，點選已選取列的連結。

8. 請在 **日期** 欄位中輸入日期。

9. 展開 **員工自助服務電子郵件** 專區。

10. 請在 **主旨** 欄位中輸入一值。

    * 範例：開放使用的問卷  

11. 請在 **文字** 欄位中鍵入您的電子郵件本文。 請注意，變數可用來替代系統中的數值。

    * 範例：親愛的 %P%，請登入 Employee Self Service 完成 Workforce Health 問卷。  Contoso  

12. 點選 **儲存**。

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>請使用設定細節選取要回答的問卷以及用來選取受訪者的任何查詢。

1. 點選 **設定細節**。

2. 請在清單選取查詢，用來搜尋系統有無問卷受訪者。

    * 範例：背景工作角色  

3. 點選 **檢視或修改查詢** 來選取特定人士或調整查詢以便尋找符合特定條件的人士。

    * 請注意，所有受訪者也必須是系統的使用者。  

4. 請在清單中標記個人專用列。

5. 在 **條件** 欄位中，輸入或選取一個值。

    * 請選取 Julia Funderburk  

6. 請在清單選取 Julia Funderburk。

7. 點選 **確定**。

8. 點選 **問券** 索引標籤。

9. 請展開樹狀圖的 **滿意度調查** 問券類型節點。

10. 請勾選樹狀圖的 'Workforce Health Assessment'。

11. 點選 **確定**。

12. 點選 **已規劃的回答工作階段**。

    * 請注意，**已規劃的回答工作階段** 已針對每位選取/查詢的使用者建立。  

13. 關閉頁面。

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>開始問卷日程，開放受訪者填完問卷。

1. 點選 **功能**。

2. 點選 **開始**。

3. 點選 **確定**。

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>傳送電子郵件告知受訪者開放填寫的問卷。

1. 點選 **功能**。

2. 點選 **傳送電子郵件**。

3. 點選 **取消**。

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>使用已規劃的回答工作階段來監督需要填完問卷的人。

1. 點選 **已規劃的回答工作階段**。

    * 當您準備好結束已經排程的工作階段時，刪除任何已規劃剩餘的回答工作階段。  

2. 點選 **刪除**。

3. 點選 **是**。

4. 關閉頁面。

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>當所有受訪者都已填完問卷和/或所有已規劃剩餘的回答工作階段皆已刪除時，即結束日程。

1. 點選 **功能**。
2. 點選 **結束**。
3. 點選 **確定**。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
