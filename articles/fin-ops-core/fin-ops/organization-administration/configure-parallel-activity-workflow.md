---
title: 在工作流程中設定並行活動
description: 若要設定並行活動，請在工作流程編輯器中完成以下程序。
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 054d62e2ff094aee987f8c6e04e2f2e173da633d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460457"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>在工作流程中設定並行活動

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

若要設定並行活動，請在工作流程編輯器中完成以下程序。

並行活動由同時運行的工作流程分支組成。

## <a name="name-a-parallel-activity"></a>命名並行活動

按照以下步驟輸入並行活動的名稱。

1. 按右鍵點選並行活動，然後點選 **屬性** 打開 **屬性** 表單。
2. 在左側窗格中，點選 **基本設定**。
3. 在 **名稱** 欄位中，輸入並行活動的唯一名稱。
4. 點選 **關閉**。

## <a name="configure-the-branches-of-a-parallel-activity"></a>設定並行活動的分支

按照以下步驟新增和設定此並行活動的分支。

1. 按兩下點選並行活動以顯示並行活動的分支。
2. 若要新增 **分支**，請將分支元素從 **工作流程元素** 區域拖曳到畫布上的插入點。 下圖顯示了一個插入點。

    ![插入點。](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > 分支的順序並不重要，因為並行活動的所有分支同時運行。

3. 若要設定每個分支，請參閱[在工作流程中設定並行分支](configure-parallel-branch-workflow.md)。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]