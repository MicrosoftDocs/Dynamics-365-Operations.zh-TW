---
title: 派遣工單
description: 本主題說明如何在資產管理中派遣工單。
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 87f67f4db143fabbfae926e30e7e5d97ac6af0f6fa5469218e4ab3605aa44dcb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447300"
---
# <a name="dispatch-work-order"></a>派遣工單

[!include [banner](../../includes/banner.md)]

 

您可以使用 **派遣** 功能排程一份工單或多項工單工作至一位工作人員。

1. 按一下 **資產管理** > **一般** > **工單** > **所有工單** 或 **進行中工單**。

2. 在清單中選擇工單。

3. 在 **一般** 索引標籤上，點選 **派遣**。

4. 在 **排程工單** 對話方塊中，於 **工作人員** 欄位選擇工作人員。

5. 在 **排程時數** 欄位，您可以插入預期工作時數，以防預期工作時數與預測時數不同。

6. 在 **排程開始** 欄位，您可以根據需要編輯開始日期和時間。

7. 如果排程流程應遵守為其他作業排程資源有關的產能限制，請確保 **資產**、**工具** 和 **工作人員** 切換按鈕設定為 **是**。 如果您要查看有關排程流程的詳細資訊，請將 **詳細資訊** 切換按鈕選為 **是**。 這代表有關工單計算分數的詳細資訊將顯示在資訊記錄中。

8. 在 **忽略時程** 按鈕選擇 **是** 以忽略行事曆中的關閉天數 (適用於資產、工作人員和工具)。 在 **忽略排程執行** 切換按鈕選擇 **是** 以忽略可能已在工單選擇的排程相關限制。 

    有關排程執行設定的相關資訊，請參閱[排程執行](../setup-for-work-orders/scheduled-execution.md)章節。

9. 按一下 **確定**。 工單生命週期狀態自動更新為指定的 **已排程** 生命週期狀態 **資產管理** > **設定** > **工單** > **生命週期模型**。

下圖顯示了 **排程工單** 對話之中的派遣選擇範例。

![圖 1。](media/04-work-order-scheduling.png)

[!NOTE]
如果要刪除工單上的排程，請在 **所有工單** 選擇工單，然後在 **一般** 索引標籤按一下 **刪除排程**。如果您刪除排程，請記住手動更新工單生命週期狀態。



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]