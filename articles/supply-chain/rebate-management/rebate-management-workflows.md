---
title: 回扣管理交易工作流程
description: 本主題說明如何設定回扣管理交易工作流程以核准和啟用交易。
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f18c3bd95901303379c460d026bc944cee809b7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448926"
---
# <a name="rebate-management-deal-workflows"></a>回扣管理交易工作流程

[!include [banner](../includes/banner.md)]

若要核准回扣交易，回扣管理使用與其他財務和營運應用程式相同的工作流程平台。 每個工作流程與兩個作業流程相關聯：

- 工作流程的一個元素用於核准交易。
- 工作流程的一個元素用於啟用交易，以便使用者或工作流程可以核准交易。

使用回扣交易之前，必須先啟用 **回扣管理** 模組。 若要啟用交易，必須先建立和設定 *回扣管理交易工作流程*。

使用者無法手動核准交易。 務必使用工作流程。

## <a name="create-and-manage-rebate-management-deal-workflows"></a>建立和管理回扣管理交易工作流程

若要使用回扣管理交易工作流程，則移至 **回扣管理 \> 設定 \> 回扣管理工作流程**。 在此處，您可以根據需要查看、建立和更新工作流程。 一次只能啟用此類型的一個工作流程。 有關工作流程的詳細資訊、如何使用 **回扣管理工作流程** 頁面，以及如何建立工作流程，請參閱[工作流程系統概觀](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md)及其相關主題。

## <a name="use-a-workflow-to-activate-a-deal"></a>使用工作流程啟用交易

若要經由工作流程啟用交易，則開啟交易 (例如，在 **所有回扣管理交易** 頁面中)。 然後，在動作窗格上，選擇 **工作流程 \> 提交**。 在經由工作流程處理和核准新交易後，它將處於啟用狀態並可以使用。

交易啟用後，其大部分設定無法更改。 如果您必須更改啟用的交易，請先將其停用，然後建立新交易。 如果新交易與舊交易相似，您可以透過複製舊交易來建立。

啟用後，您可以更改以下的交易設定：

- 對帳依據
- 累積保證
- 過帳檔案
- 保證過帳設定檔
- 文件附註
- 貨幣
- 開始日期
- 結束日期

此外，可以刪除回扣明細。
