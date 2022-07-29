---
title: 使用自動清理任務來最佳化效能
description: 本主題說明如何在 Microsoft Dynamics 365 Human Resources 藉由清理批次工作歷史記錄改善效能。
author: twheeloc
ms.date: 08/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a293b128364b8b0b293da03495d55e46f6b01fd6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452196"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>使用自動清理任務來最佳化效能


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**問題**

如果批次工作歷史記錄筆數增加幅度太大，Microsoft Dynamics 365 Human Resources 會經歷效能問題。

**原因**

頻繁執行的批次工作會導致批次工作記錄不再持續增加的狀況。 這會導致效能問題。 

**解決方案**

排程自動任務來清理您的批次工作記錄。 我們建議設定每週執行任務一次，但您可能需要增加或減少清理的頻率，一切端賴您的環境而定。 下列程序包含我們建議的設定，但您可以根據需求更改這些設定。

1. 請在人力資源選取 **系統管理**。

2. 請在 **搜尋** 列輸入 **批次工作記錄清理**。

   ![搜尋批次工作記錄清理。](media/talent-batch-history-cleanup-search-bar.png)

3. 請在 **記錄限制 (天)** 中輸入 **30**。

   ![將記錄限制為 30。](media/talent-batch-history-cleanup-history-limit.png)

4. 選取 **背景執行** 和 **重覆**。

   ![設定重覆。](media/talent-batch-history-cleanup-recurrence.png)

5. 請在 **定義重覆** 下方設定 **開始日期** 和 **開始時間** 在非工作時間或週末發生，然後選取 **沒有結束日期**。 

   ![定義重覆開始日期和時間。](media/talent-batch-history-cleanup-define-recurrence.png)

6. 請在 **重覆樣式** 下方選取 **天** 並設定 **指定間隔後重複天數** 到 **7**。

   ![將清理設定為每週重覆一次。](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. 選取 **確定**。

8. 依需求變更 **背景執行** 下方的任何其他參數，然後選取 **確定**。



[!INCLUDE[footer-include](../includes/footer-banner.md)]
