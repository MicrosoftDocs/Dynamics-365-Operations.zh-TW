---
title: 建立工作流程概述
description: 本主題說明如何建立工作流程。
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "195583"
- intro-internal
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: abdb8ce3186806ac1b756c9161d53547dd8ae40b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460454"
---
# <a name="create-workflows-overview"></a>建立工作流程概述

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題說明如何建立工作流程。

## <a name="open-the-workflow-editor"></a>打開工作流程編輯器

您正在使用的模組決定了您可以建立的工作流程類型。 按照以下步驟選取要建立的工作流程類型並打開工作流程編輯器。

1. 開啟要為其建立新工作流程的模組。 例如，要為採購申請建立工作流程，請點選 **採購和尋源**。
2. 點選 **安裝**&gt;**\[模組名稱\]工作流程**。
3. 在出現的清單頁面上的操作窗格中，點選 **新建**。
4. 在 **建立工作流程** 頁面，選取要建立的工作流程類型，然後點選 **建立工作流程**。 工作流程編輯器出現。 您現在可以使用以下過程來設計工作流程。

## <a name="drag-workflow-elements-onto-the-canvas"></a>將工作流程元素拖曳到畫布上

工作流程編輯器的 **工作流程元素** 區域包含您可以新增到工作流程中的元素。 若要將元素新增到工作流程，請將它們拖曳到畫布上。

## <a name="connect-the-elements"></a>連線元素

若要將一個工作流程元素連線到另一個元素，請將指標停在一個元素上，直到出現連線點。 點選一個連線點，然後將其拖曳到另一個元素。 確保連線所有元素。

## <a name="configure-the-properties-of-the-workflow"></a>設定工作流程的屬性

按照以下步驟設定工作流程的屬性。

1. 點選畫布以確保未選取任何工作流程元素。
2. 點選 **屬性** 以打開工作流程的 **屬性** 頁面。
3. 遵循[設定工作流程屬性](configure-workflow-properties.md)主題中的程序。

## <a name="configure-the-elements-of-the-workflow"></a>設定工作流程的元素

設定您拖曳到畫布上的每個元素。 如需如何設定每個工作流程元素的相關信息，請參閱以下主題：

- [在工作流程中設定手動工作](configure-manual-task-workflow.md)
- [在工作流程中設定自動工作](configure-automated-task-workflow.md)
- [在工作流程中設定核准流程](configure-approval-process-workflow.md)
- [在工作流程中設定核准步驟](configure-approval-step-workflow.md)
- [在工作流程中設定手動決策](configure-manual-decision-workflow.md)
- [在工作流程中設定條件決策](configure-conditional-decision-workflow.md)
- [在工作流程中設定並行分支](configure-parallel-activity-workflow.md)
- [設定並行分支](configure-parallel-branch-workflow.md)
- [設定行項目工作流程](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>解決任何錯誤或警告

工作流程編輯器底部的 **錯誤和警告** 窗格顯示已為工作流程產生的訊息。 若要查詢發生錯誤或警告的元素，請按兩下點選錯誤或警告訊息。 您必須先解決所有錯誤和警告，然後才能啟用工作流程。

## <a name="save-and-activate-the-workflow"></a>儲存並啟用工作流程

當您準備好儲存並啟用工作流程時，請按照以下步驟操作。

1. 點選 **儲存並關閉** 以關閉工作流程編輯器並打開 **儲存工作流程** 頁面。
2. 輸入有關您對工作流程所做更改的註解，然後點選 **確定**。
3. 如果所有錯誤和警告都已解決，將顯示 **啟用工作流程** 頁面。 選取下列其中一個選項：

    - 若要啟用此版本的工作流程，請點選 **啟用新版本**。 當工作流程處於有效狀態時，使用者可以將文件送出給它進行處理。
    - 如果您不想啟用此版本，請點選 **不要啟用新版本**。 您可以稍後啟用工作流程。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]