---
title: 設定行項目工作流程
description: 本主題說明如何設定行項目工作流程元素。
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d6d9dcb99e00d4ce3f99e525a72421cb12af178
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460356"
---
# <a name="configure-line-item-workflows"></a>設定行項目工作流程

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題說明如何設定行項目工作流程元素。

若要設定行項目工作流程元素，請在工作流程編輯器中右鍵點選該元素，然後點選 **屬性** 以打開 **屬性** 頁面。 然後可以使用以下過程來設定行項目工作流程元素的屬性。

## <a name="name-the-line-item-workflow-element"></a>命名行項目工作流程元素

按照以下步驟輸入行項目工作流程的名稱。

1. 在左側窗格中，點選 **基本設定**。
2. 在 **名稱** 欄位中，輸入行項目工作流程元素的唯一名稱。

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>指定是否使用相同的工作流程處理所有行項目

按照以下步驟指定是否使用相同的工作流程來處理文件上的所有行項目。

1. 在左側窗格中，點選 **基本設定**。
2. 如果同一工作流程應處理文件上的所有行項目，請點選 **為所有訂單項目調用單個工作流程**。 然後選取用於處理行項目的工作流程。
3. 如果特定工作流程應處理滿足一組特定條件的行項目，請點選 **為每個行項目調用工作流程**。 然後按照以下步驟定義條件集：

    1. 選點 **新增**。
    2. 選取資料表中的條件。
    3. 在 **條件名稱** 索引標籤，輸入您定義的條件集的名稱。
    4. 點選 **新增條件** 輸入條件。
    5. 輸入所需的任何附加條件。
    6. 若要驗證您輸入的一組條件是否設定正確，請點選 **測試**。 在 **測試工作流程條件** 頁上，在 **驗證條件** 區域中，選取記錄，然後點選 **測試**。 系統評估記錄以確定它是否滿足您定義的條件。 點選 **確定** 或 **取消** 返回至 **屬性** 頁。

    在 **工作流程** 索引標籤，選取工作流程選取用於處理滿足您定義的一組條件的行項目的工作流程。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]