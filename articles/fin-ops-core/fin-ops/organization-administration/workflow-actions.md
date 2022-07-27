---
title: 工作流程核准流程中的動作
description: 本文介紹了工作流程核准流程中的每個參與者可以執行的動作。
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e546dc57692e31d4501984dafa21fbae23a48fe
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460289"
---
# <a name="actions-in-workflow-approval-processes"></a>工作流程核准流程中的動作

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本文介紹了工作流程核准流程中的每個參與者可以執行的動作。

一個工作流程可以涉及幾組人：發起者、工作指派者、決策者和核准者。 例如，在以下費用報表工作流程中，Sam 是發起者，佇列成員是工作指派者，John 是決策者，Frank、Sue 和 Ann 是核准者。

[![Workflow\_WithManualDecision.](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)

以下部分解釋了每個組可以執行的工作流程動作。

## <a name="actions-that-an-originator-can-perform"></a>發起者可以執行的動作

發起者透過送出文件進行處理來啟動工作流程實體。 例如，Sam 必須點選 **費用報表** 頁面上的 **送出** 按鈕來送出他的費用報表。

## <a name="actions-that-a-task-assignee-can-perform"></a>工作指派者可以執行的動作

一個工作可以指派給多個人，也可以指派給由幾個人監控的工作項目佇列。 但是，只有一個人可以完成一項工作。 例如，Sam 送出了一份費用報表，並將其收據發送到其組織的費用報表部門進行審查。

Adventure Works 費用報表部門的成員監控佇列。 該部門的成員 Julie 接受了審查 Sam 的費用報表和收據的工作。 她現在可以執行以下動作之一：完成、拒絕、委託、請求更改、重新指派或釋放。

> [!NOTE]
> 可用的動作會有所不同，具體取決於軟體開發人員設計工作的方式。

### <a name="complete"></a>完成

當使用者完成工作時，如果有下一個使用者，送出處理的文件將指派給工作流程中的下一個使用者。 如果不需要額外處理，則工作流程結束。

例如，Adventure Works 費用報表部門的成員 Julie 接受了審查 Sam 的費用報表和收據的工作。 在 Julie 完成她的審查後，該文件將指派給 John。

### <a name="reject"></a>拒絕

當使用者拒絕文件時，工作流程結束。

例如，Adventure Works 費用報表部門的成員 Julie 接受了審查 Sam 的費用報表和收據的工作。 如果 Julie 拒絕費用報表，則工作流程結束。

然後 Sam 可以重新送出費用報表。 他可以先進行更改，也可以重新送出原始版本。 如果 Sam 重新送出費用報表，則工作流程流程會從人工審核工作開始。

### <a name="delegate"></a>委派

當使用者委派工作時，該工作將指派給另一個使用者。

例如，Adventure Works 費用報表部門的成員 Julie 接受了審查 Sam 的費用報表和收據的工作。 Julie 將此工作委託給她的助手 Tim。

然後 Tim 代表 Julie 行事。 因此，當 Tim 完成他的審核時，費用報表將指派給 John，就像 Julie 完成了工作一樣。

### <a name="request-change"></a>要求變更

當使用者請求更改已送出的文件時，該文件將被發送回發起者。

例如，Adventure Works 費用報表部門的成員 Julie 接受了審查 Sam 的費用報表和收據的工作。 Julie 注意到費用報表中的一些錯誤並請求更改。 費用報表將發送回 Sam。

Sam 可以重新送出費用報表。 他可以先進行請求的更改，也可以重新送出原始版本。 如果 Sam 重新送出費用報表，工作項目佇列的成員必須再次查看費用報表和收據。

### <a name="reassign"></a>重新指派

工作項目佇列的成員可以將該佇列中的文件重新指派給另一個佇列。

例如，Adventure Works 費用報表部門的成員 Julie 正在監控佇列。 為了幫助平衡工作負載，她可以將費用報表以及其中包含的收據重新指派到另一個佇列。

### <a name="release"></a>釋出

有時，工作項目佇列的成員可能會接受一項工作，但隨後決定他或她無法完成該工作。 在這種情況下，接受工作的人可以將文件釋放回工作項目佇列。

例如，Adventure Works 費用報表部門的成員 Julie 接受了審查 Sam 的費用報表和收據的工作。 如果 Julie 決定她無法完成工作，她可以發布文件。 費用報表回傳到佇列中，以便 Adventure Works 費用報表部門的其他成員可以完成工作。

## <a name="actions-that-a-decision-maker-can-perform"></a>決策者可以執行的動作

通常，將文件指派給決策者，因為存在決策者必須回答的問題。 問題的答案通常是 **是** 或 **否**，或 **True** 或 **False**。 如果決策者沒有選取這些選項之一，他或她可以委託該決定。

### <a name="choice-1-or-choice-2"></a>\[選取 1\]或\[選取 2\]

決策者必須回答與文件相關的問題。 問題的答案通常是 **是** 或 **否**，或 **True** 或 **False**。 決策者選取的答案決定了用於處理文件的工作流程分支。

例如，將 Sam 的費用報表指派給 John。 John 必須決定文件中的資訊是否需要致電 Sam 的經理。 如果 John 決定需要致電，則費用報表將指派給 Aretha，Aretha 必須隨後致電 Sam 的經理。 如果 John 決定不需要致電，則會將費用報表指派給 Frank 以供核准。

### <a name="delegate"></a>委派

當決策者委派決策時，文件將指派給另一個必須做出決策的使用者。

例如，將 Sam 的費用報表指派給 John。 John 將決定委託給他的助手 Maria。

然後 Maria 代表 John 行事。 如果 Maria 決定需要致電 Sam 的經理，則會將費用報表指派給 Aretha，Aretha 必須隨後致電 Sam 的經理。 如果 Maria 決定不需要致電，則會將費用報表指派給 Frank 以供核准。

## <a name="actions-that-an-approver-can-perform"></a>核准者可以執行的動作

將文件指派給核准者後，核准者可以執行以下動作之一：核准、拒絕、委派或請求更改。

### <a name="approve"></a>核准

當核准者核准文件時，如果有下一個使用者，該文件將指派給工作流程中的下一個使用者。 如果不需要額外處理，則工作流程結束。

例如，Sam 送出了 6,000 美元的費用報表，該文件指派給了 Frank。 當 Frank 核准該文件時，它會指派給 Sue 以供核准。 當 Sue 核准費用報表時，工作流程結束。

### <a name="reject"></a>拒絕

當核准者拒絕文件時，工作流程結束。

例如，Sam 送出了 12,000 美元的費用報表，該文件指派給了 Sue。 如果 Sue 拒絕費用報表，則工作流程結束。

Sam 可以重新送出費用報表。 他可以先進行更改，也可以重新送出原始版本的費用報表。 如果 Sam 重新送出費用報表，則工作流程會從核准流程開始。

### <a name="delegate"></a>委派

當核准者委派文件時，該文件將指派給其他使用者進行核准。

例如，Sam 送出了 12,000 美元的費用報表，該文件指派給了 Frank。 Frank 將費用報表委託給 Ann。

然後 Ann 代表 Frank 行事。 因此，當 Ann 核准該檔案時，它被指派給 Sue 進行核准，就像 Frank 核准了它一樣。 Sue 核准該檔案後，則將其發送給 Ann 以供核准。

### <a name="request-change"></a>要求變更

當核准者請求更改文件時，該文件將被發送回發起者。

例如，Sam 送出了 12,000 美元的費用報表，該文件指派給了 Sue。 如果 Sue 請求更改，則會將費用報表發送回 Sam。

Sam 可以重新送出費用報表。 他可以先進行請求的更改，也可以重新送出原始版本的費用報表。 如果 Sam 重新送出費用報表，則會將其發送給 Frank 進行核准，因為 Frank 是核准流程中的第一個核准人。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]