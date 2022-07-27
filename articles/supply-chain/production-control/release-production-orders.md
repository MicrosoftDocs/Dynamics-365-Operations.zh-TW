---
title: 釋出生產訂單
description: 已釋出的生產訂單是已授權進行生產的訂單。 「已釋出」一詞用於描述生產訂單生命週期中的狀態，其中生產訂單可用於在工廠生產線和倉庫流程中執行。
author: johanhoffmann
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 740ac516ffa01d8930aedabb9873834b07b7debf700dc61b14d93ac8d6dcd086
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446679"
---
# <a name="release-production-orders"></a>釋出生產訂單

[!include [banner](../includes/banner.md)]

已釋出的生產訂單是已授權進行生產的訂單。 「已釋出」一詞用於描述生產訂單生命週期中的狀態，其中生產訂單可用於在工廠生產線和倉庫流程中執行。

## <a name="characteristics-of-the-released-state"></a>「已釋出」狀態的特點

**已釋出** 狀態是生產訂單生命週期中的一種狀態。 狀態為 **已釋出** 的生產訂單可在工廠生產線和倉庫流程中執行。 **已釋出** 狀態具有以下特點：

- 生產訂單可以從生產訂單或透過使用批次處理更改為 **已釋出** 狀態。 生產訂單還可以從使用 **主計劃** 頁面的 **確認時界** 欄位確定的計劃生產訂單自動更新。
- **已釋出** 狀態是向工廠操作員發出信號以開始在工廠執行生產作業。
- 生產文件 (例如：途程卡、途程工作和工作卡) 提供有關生產工作的資訊並且可以發出。
- 對於實際預留的物料，會產生倉庫工作以揀選生產訂單的物料。

## <a name="releasing-jobs-to-the-shop-floor"></a>將工作釋出到工廠

在釋出生產訂單後，可以看見並登記與該訂單相關的生產工作。 操作員可在 **工作卡終端** 頁面或 **工作卡裝置** 頁面登記工作，例如開始、停止和完成。 登記的時間和數量將自動從登記頁面轉移到生產日記帳，以追蹤所用的時間和數量。

## <a name="route-cards"></a>途程卡

途程卡提供來自途程和作業設定，以及作業和工作排程方法的資訊之概覽。

## <a name="route-jobs"></a>途程工作

途程工作詳細列出作業的每個工作，包括設定、處理、佇列和運輸時間。 例如，噴漆之類的作業可能需要個別工作，例如：設定時間、用於噴漆流程執行時間和用於乾燥佇列時間。

## <a name="job-cards"></a>工作卡

工作卡列出特定作業的各個工作編號。 每頁顯示一個工作。 工作卡中包括的工作及其預估時間來自途程和作業設定資訊。 從工作卡中，您可以開啟 **生產日記帳明細**,**工作卡** 頁面。 執行作業資源的人員可提供有關生產流程的反饋。 您可以在某些欄位中輸入消耗統計和錯誤數量等資訊。

## <a name="warehouse-work-for-raw-material-picking"></a>原物料揀選的倉庫工作

原物料揀選工作是在釋出期間產生的。 只針對釋出訂單之前為生產訂單實際預留的物料數量產生工作。 為原物料揀選產生倉庫工作需要以下設定：

- 確定在哪個倉庫位置揀選物料的原物料揀選位置指令
- 原材料的波次範本，其中設定執行倉庫工作的策略
- 確定物料放置位置的生產輸入位置

當使用牌照控制位置時，可以選擇在處理原物料揀選工作時，是應揀選已訂購數量還是物料的全部可用數量。 若要設定此選項：

1. 移至 **產品資訊管理 \> 產品 \> 已發佈產品**，然後開啟相關物料。
1. 展開 **倉庫** FastTab。
1. 為 **牌照位置的物料揀選** 欄位選擇以下其中一個選項：
    - *訂單揀貨*：只揀選訂購的數量。
    - *暫存*：只要有可能，應揀選牌照可用的全部數量。 為了讓工作人員能夠揀選全部牌照數量，牌照不能包含混合品項，且不能有混合維度。 如果牌照包含混合維度或品項，揀貨將像設定為 *訂單揀貨* 一樣進行。

[!INCLUDE[footer-include](../../includes/footer-banner.md)]