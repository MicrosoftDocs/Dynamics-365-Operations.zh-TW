---
title: 在工作流程中設定條件決策
description: 使用以下程序設定條件式決策的屬性。
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fa708b4ac1f17a9ed6852a9eeb3e764b750a4a4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460357"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a>在工作流程中設定條件決策

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

使用以下程序設定條件式決策的屬性。

條件決策是工作流程分為兩個分支的點。 若要設定條件決策，請在工作流程編輯器中，按右鍵點選條件式決策，然後點選 **屬性** 以打開 **屬性** 表單。

## <a name="name-a-decision"></a>為決策命名

按照以下步驟輸入條件式決策的名稱。

1. 在左側窗格中，點選 **基本設定**。
2. 在 **名稱** 欄位中，輸入條件式決策的唯一名稱。

## <a name="set-conditions"></a>設定條件

系統透過評估送出的文件來確定使用哪個分支，以確定它是否滿足特定條件。

1. 在左側窗格中，點選 **基本設定**。
2. 點選 **新增條件**。
3. 輸入條件。
4. 如果需要，請輸入附加條件。
5. 若要驗證您輸入的條件是否設定正確，請完成以下步驟：

    1. 點選 **測試** 即可打開 **測試工作流程條件** 表單。
    2. 在表單的 **驗證條件** 區域中選取一條記錄。
    3. 點選 **測試**。 系統評估記錄以確定它是否滿足您定義的條件。
    4. 點選 **確定** 或 **取消** 返回至 **屬性** 表單。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]