---
title: 採購與開源工作流程
description: 某些組織需要由非輸入交易的使用者核准採購申請和採購訂單。 若要設定核准流程，您可以建立工作流程。
author: Henrikan
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a819093d9ee6f999e637281e54905968fe361566
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448827"
---
# <a name="procurement-and-sourcing-workflows"></a>採購與開源工作流程

[!include [banner](../includes/banner.md)]

某些組織需要由非輸入交易的使用者核准採購申請和採購訂單。 若要設定核准流程，您可以建立工作流程。

工作流程代表一個業務流程。 它定義文件在系統中的流程，並指出誰必須完成工作或核准文件。 在您的組織中使用工作流系統有數個好處：

- **一致的流程** — 您可以定義特定文件的核准流程，例如採購申請和費用報告。 使用工作流程系統有助於確保能以一致和有效的方式處理和核准文件。
- **流程可見性** — 您可以追蹤特定工作流程執行個體的狀態、歷程及效能指標。 這能幫助您決定是否應對工作流程進行變更以提高效率。
- **集中工作清單** — 使用者可使用集中工作清單在其參與的所有工作流程之間檢視指派給他們的工作流程工作與核准。 此清單位於工作項目頁面。

## <a name="the-types-of-workflows-that-you-can-create"></a>您可以建立的工作流程類型

以下工作流程類型適用於採購與開源。

| 類型 | 使用此類型可 |
|---|---|
| 採購申請審查 | 為採購申請建立審查與核准工作流程。 |
| 採購申請行審查 | 為採購申請行建立審查與核准工作流程。 |
| 採購訂單工作流程 | 為採購訂單建立審查與核准工作流程。 |
| 採購訂單行工作流程 | 為採購訂單行建立審查與核准工作流程。 |
| 廠商新增申請工作流程 | 建立審查與核准工作流程以透過廠商要求新增新廠商。 |

> [!IMPORTANT]
> 當您正在新增新工作流程時，您可能也會看見在 **建立工作流程** 對話方塊中列出下列過時的工作流程。 這些工作流程與 *收貨確認* 功能相關，該功能位於 [Dynamics AX 2012 ](/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows) 中，但現在已過時。 目前不支援這些工作流程。
> 
> - 交貨到期日通知工作流程
> - 發票收到通知工作流程
> - 產品收貨失敗通知工作流程
> - 拒絕未確認產品收貨通知工作流程

## <a name="creating-a-workflow"></a>建立工作流程

若要建立工作流程，請移至 [採購與開源] &gt; [設定] &gt; [採購與開源工作流程]，並透過選取您想要建立的工作流程類型來建立新工作流程。 

在工作流程畫布中，您可以將工作流程元素拖曳到設計工具中，並將元素連結到流程。 應設定工作流程元素。 對於核准和任務工作流程元素，您可以設定應該採取動作的參與者。

## <a name="types-of-participants"></a>參與者類型

您可以將核准步驟指派給下列參與者群組。

| 使用者群組 | 描述 |
|---|---|
| 參與者 | 將核准步驟指派給群組的成員或角色。 |
| 階層 | 將核准步驟指派給特定組織階層中的使用者。 |
| 工作流程使用者 | 將核准步驟指派給此工作流程的使用者。 |
| 佇列 | 將核准步驟指派給工作項目佇列。 |
| 使用者 | 將核准步驟指派給特定使用者。 |

## <a name="additional-resources"></a>其他資源

- [定義採購申請的業務流程工作流程](https://www.microsoft.com/download/details.aspx?id=101821)
- [採購申請工作流程](purchase-requisitions-workflow.md)
- [Onboard 廠商](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]