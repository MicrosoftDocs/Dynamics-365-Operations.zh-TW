---
title: 根據上一個問題的答案提出問題
description: 條件式問題允許您根據前一個問題的答案指明將向受訪者提出的追蹤性問題。
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f28f75a902121f23c92a919b539517dbdb191447
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452259"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>根據上一個問題的答案提出問題


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



條件式問題允許您根據前一個問題的答案指明將向受訪者提出的追蹤性問題。 例如，如果您詢問 “您喜歡咖啡還是茶”，可根據受訪者選取咖啡或茶作為答案來判定合乎邏輯的追蹤性問題。 用來建立此程序的示範資料公司為 USMF。


## <a name="find-the-existing-questionnaire"></a>尋找既有的問卷
1. 前往 **問卷** > **設計** > **問卷**。
2. 請在清單中選取 WorkFH 問券。

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>新增所有問題和子問題到問卷裡
1. 點選 **問題**。
2. 點選 **新增**。
3. 請在 **問題** 欄位中選取問題編號 00016。
4. 在清單中，尋找並選取所需的記錄。
5. 在清單中，點選已選取列的連結。
6. 點選 **儲存**。
7. 關閉頁面。

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>將問卷順序設定為條件式，並根據適當問題提出問題
1. 點選 **編輯**。
2. 展開 **設定** 區段。
3. 在 **問題順序** 欄位中選取 '條件式'。
4. 點選 **條件式** 問題。
5. 請在樹狀圖中選取 '問題\解釋為什麼您以您的方式回答上一個問題？'。
6. 請在 **主要問題** 欄位中選取問題編號 00009。
7. 在清單中，點選已選取列的連結。
8. 請在 **答案** 欄位中輸入要使問題成為依據的答案選項順序識別碼。 例如，第一個答案選項輸入 1。
9. 點選 **儲存**。
10. 請在樹狀圖中選取 '問題\我的工作與報酬相當。'。
    * 請注意，問題樹已經更新顯示相依性。  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
