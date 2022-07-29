---
title: 藉由排程下班後的批次工作來最佳化效能
description: 本主題說明如何藉由排程下班後長時間執行批次工作解決 Microsoft Dynamics 365 Human Resources 的效能問題。
author: andreabichsel
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 14354ba9454b8837246b75cd413497553423511e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452130"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>藉由排程下班後的批次工作來最佳化效能


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>問題

如果在典型營業期間長時間執行批次工作，Ｍicrosoft Dynamics 365 Human Resources 會經歷效能問題。

## <a name="resolution"></a>解決方案

排程非工作時間執行下列批次工作。 我們也建議審核頻繁執行的批次工作頻率。 可能的話，請減少批次工作的重覆性。 許多情況下，預設頻率就已足夠。

下列批次工作應在夜間或下班後執行。 請務必檢查這些重覆性批次工作的時區。 某些批次工作可能使用太平洋標準時間 (PST)。

| 批次工作 | 預設發生 |
| --- | --- |
| 批次工作記錄清理 | 每個月 1 次 |
| 匯出暫存清理 | 每天 1 次 |
| Common Data Service 整合錯過請求同步 | 每天 1 次 |
| 需要在非工作時間照常執行的資料庫壓縮系統工作 | 每天 1 次 |
| 需要在非工作時間照常執行的資料庫索引重建系統工作 | 每天 1 次 |

1. 請在人力資源選取 **系統管理**。

2. 請在 **搜尋** 列搜尋上述其中一件批次工作。

3. 請選取 **背景執行** 和 **重覆性**。

   ![設定重覆性。](media/talent-batch-history-cleanup-recurrence.png)

4. 請在 **定義重覆** 下方設定 **開始日期** 和 **開始時間** 在非工作時間或週末發生。 請選取 **沒有結束日期**。 

   ![定義重覆開始日期和時間。](media/talent-batch-history-cleanup-define-recurrence.png)

5. 請選取 **確定**。

6. 如果有需要，請在 **背景執行** 下方變更任何其他參數，然後選取 **確定**。

## <a name="additional-resources"></a>其他資源

[使用自動清理任務來最佳化效能](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
