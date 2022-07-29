---
title: 建立封閉式問題
description: 封閉式問題允許您提供受訪者選擇的選項。
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3b90bb2a4981f32feb10ee1192e9c4d2e604e7a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452349"
---
# <a name="create-a-closed-ended-question"></a>建立封閉式問題


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



封閉式問題允許您提供受訪者選擇的選項。 首先，您必須建立含有答案的答案群組，然後建立將使用答案群組的問題。 用來建立此程序的示範資料公司為 USMF。


## <a name="create-an-answer-group"></a>建立答案群組
1. 前往 **問卷** > **設計** > **答案群組**。
2. 點選 **新增**。
3. 請在 **答案群組** 欄位中輸入一值。
4. 在 **描述** 欄位中，輸入一個值。
    * 每次問題使用答案群組時，請使用 **隨機化** 功能將答案以不同順序隨機放置答案。  
5. 點選 **答案**。
6. 點選 **新增**。
    * 序列編號控制答案的顯示順序，除非 **答案群組** 選取 **隨機化**。  
    * 評分問券時可使用判給答案的點數。  
7. 請在 **點數** 欄位中輸入數字。
    * 可以標記正確答案指出選取的答案正確。 這可以用在評分問券。  
8. 請在 **答案** 欄位中輸入一值。
    * 繼續為答案群組建立答案選取選項。  
9. 點選 **新增**。
10. 請在 **點數** 欄位中輸入數字。
11. 請在 **答案** 欄位中輸入一值。
12. 點選 **新增**。
13. 請在 **點數** 欄位中輸入數字。
14. 請在 **答案** 欄位中輸入一值。
15. 點選 **新增**。
16. 請在 **點數** 欄位中輸入數字。
17. 請在 **答案** 欄位中輸入一值。
18. 點選 **新增**。
19. 請在 **點數** 欄位中輸入數字。
20. 請在 **答案** 欄位中輸入一值。
21. 關閉頁面。
22. 關閉頁面。

## <a name="create-the-question"></a>建立問題
1. 前往 **問卷** > **設計** > **問題**。
2. 點選 **新增**。
3. 使用 **類型** 欄位將相關問題分在一組。
    * 您可以將 **勾選方塊**、**替代按鈕** 或 **組合方塊** 的輸入類型用在封閉式問題。  
4. 請在 **輸入類型** 欄位中選取選項。
5. 請在 **答案群組** 欄位中輸入或選取一值。
6. 請在 **文字** 欄位中輸入一值。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
