---
title: 工作流程系統概觀
description: 本主題介紹工作流程系統。
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "56381"
- intro-internal
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70776ba0a0461998d2c1f62ba05b55cd4307a0f7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460503"
---
# <a name="workflow-system-overview"></a>工作流程系統概觀

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

本主題介紹工作流程系統。

## <a name="what-is-workflow"></a>什麼是工作流程？

術語 *工作流程* 可以用兩種方式定義：作為系統和作為業務流程。

### <a name="workflow-is-a-system"></a>工作流程是一個系統

工作流程是在應用程式物件伺服器 (AOS) 上執行的系統。 工作流程系統提供可用於建立單個工作流程或業務流程的函數。

### <a name="workflow-is-a-business-process"></a>工作流程是一個業務流程

工作流程代表一個業務流程。 它透過顯示誰必須完成工作、做出決定或核准文件來定義文件如何在系統中流動或行動。 例如，下圖顯示了費用報表的工作流程。

![具有指派給使用者的元素的工作流程。](./media/workflow_user.gif)

為了更好地理解此工作流程，假設 Sam 送出了 7,000 美元的費用報表。 在這種情況下，Ivan 必須查看 Sam 發送給他的收據。 然後 Frank 和 Sue 必須核准費用報表。 現在假設 Sam 送出了 11,000 美元的費用報表。 在這種情況下，Ivan 必須審查收據，而 Frank、Sue 和 Ann 必須核准費用報表。

## <a name="benefits-of-using-the-workflow-system"></a>使用工作流程系統的好處

在您的組織中使用工作流程系統有數個好處：

- **一致的流程**- 您可以定義如何處理特定文件，例如採購申請和費用報表。 透過使用工作流程系統，您可以確保以一致且有效的方式處理和核准文件。
- **流程可見性**- 您可以追蹤工作流程執行個體的狀態、歷史和效能指標。 這能幫助您決定是否應對工作流程進行變更以提高效率。
- **集中工作清單**- 使用者可以查看顯示指派給他們的工作流程工作和核准的集中工作清單。


## <a name="workflow-content"></a>工作流程內容

+ [工作流程系統架構](workflow-system-architecture.md)
+ [工作流程元素](workflow-elements.md)
+ [工作流程核准流程中的動作](workflow-actions.md)
+ [建立工作流程概述](create-workflow.md)
+ [設定工作流程屬性](configure-workflow-properties.md)
+ [在工作流程中設定手動工作](configure-manual-task-workflow.md)
+ [在工作流程中設定自動工作](configure-automated-task-workflow.md)
+ [在工作流程中設定核准流程](configure-approval-process-workflow.md)
+ [在工作流程中設定核准步驟](configure-approval-step-workflow.md)
+ [在工作流程中設定手動決策](configure-manual-decision-workflow.md)
+ [在工作流程中設定條件決策](configure-conditional-decision-workflow.md)
+ [在工作流程中設定並行活動](configure-parallel-activity-workflow.md)
+ [在工作流程中設定並行分支](configure-parallel-branch-workflow.md)
+ [設定行項目工作流程](configure-line-item-workflow.md)
+ [工作流程常見問題](workflow-FAQ.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]