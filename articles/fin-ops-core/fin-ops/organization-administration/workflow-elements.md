---
title: 工作流程元素
description: 本主題介紹構成工作流程的各種元素。
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9491b8ee6da69ba93c830bf0721c1d58fd4385b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460288"
---
# <a name="workflow-elements"></a>工作流程元素

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題介紹構成工作流程的各種元素。

工作流程由元素組成。 以下部分描述了每種類型的元素。

## <a name="tasks"></a>工作

*工作* 是必須執行的工作單位。 可以將兩種類型的工作新增到工作流程中：手動工作和自動化工作。

### <a name="manual-task"></a>手動工作

*手動工作* 是必須由使用者執行的工作單位。 例如，費用報表工作流程可以具有需要指派的使用者完成以下動作的手動工作：

- 查看與費用報表一起送出的收據。
- 打電話給員工的經理。

### <a name="automated-task"></a>自動化工作

*自動化工作* 是必須由系統執行的工作單位。 無需人工互動。 例如，銷售訂單工作流程可以具有需要係統完成以下動作的自動化工作：

- 進行信用檢查。
- 如果記錄尚不存在，則為客戶建立客戶記錄。

## <a name="approval-processes"></a>核准流程

*核准流程* 是由多個單獨步驟組成的流程。 在每個核准步驟中，使用者可以執行以下動作：

- 核准文件。
- 拒絕文件。
- 要求更改文件。
- 將文件指派給其他使用者進行核准。

## <a name="line-item-workflow-elements"></a>訂單項工作流程元素

可以建立工作流程來處理文件或文件上的訂單項。 例如，您為時程表建立了核准工作流程。 (我們將此工作流程稱為 *文件工作流程*。) 您可以向該文件工作流程新增 *訂單項工作流程* 元素。 執行訂單項元素時，將送出文件上的每個訂單項以供處理。 您可能希望所有訂單項由同一個訂單項工作流程處理，或者您可能希望每個訂單項由不同的訂單項工作流程處理。 假設一名員工送出了類似於下圖的時程表。

![含有訂單項的工作流程。](./media/workflow_lineitemworkflow.gif)

在這種情況下，您可能希望建立以下訂單項工作流程：

- **訂單項工作流程 1**– 此工作流程用於處理專案 ID 為 1111 的訂單項。
- **訂單項工作流程 2**– 此工作流程用於處理專案 ID 為 2222 的訂單項。
- **訂單項工作流程 3**– 此工作流程用於處理專案 ID 為 3333 的訂單項。

## <a name="flow-control-elements"></a>流程控制元素

以下元素可讓您設計具有交替分支或同時執行的分支的工作流程。

### <a name="manual-decision"></a>手動決策

*手動決策* 是工作流程分為兩個分支的點。 使用者必須做出決定，該決定決定了使用哪個分支來處理送出的文件。

### <a name="conditional-decision"></a>條件式決策

*條件式決策* 也是工作流程分為兩個分支的點。 但是，系統決定使用哪個分支來處理送出的文件。 為了做出此決定，系統會評估文件以確定它是否滿足指定條件。

### <a name="parallel-activity"></a>並行活動

*並行活動* 是包含同時執行的兩個或多個工作流程分支的工作流程元素。

### <a name="subworkflow"></a>子工作流程

*子工作流程* 是在其他工作流程環境內執行的工作流程。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]