---
title: 將任務指引儲存到 LCS 並且重播它們
description: 本主題說明如何將任務指引儲存到 Microsoft Dynamics Lifecycle Services (LCS)，然後重播它們。
author: twheeloc
ms.date: 08/23/2021
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
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 54251aed1a54f626e5cd6cbd983e3eb4589a02e8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452439"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>將任務指引儲存到 LCS 並且重播它們


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**環境細節** 

Microsoft Dynamics 365 Human Resources 透過 Microsoft Dynamics Lifecycle Services (LCS) 部署

**問題**

客戶希望將新任務記錄儲存到 LCS 專案，然後重播儲存的任務指引。

**解決方案**

請按照下列步驟將任務記錄儲存到 LCS。

1. 登入 LCS 並選取專案。
2. 選取 **業務流程建模工具** 圖格。
3. 檢視 “更新的 BPM 體驗” 頁。
4. 選取資源庫，然後選取 **複製**。
5. 輸入業務流程建模工具 (BPM) 模型名稱。
6. 從 LCS 登入人力資源。
7. 請在 **搜尋** 欄位輸入 **小幫手**。 已打開 Lifecycle Services 小幫手。
8. 選取 Lifecycle Services 小幫手組態的 **重新整理** 按鈕。

    您的新 BPM 庫此時應該出現，並且應該在有效狀態。

9. 關閉頁面。
10. 建立任務記錄。
11. 完成後，請選取 **儲存到 Lifecycle Services**。

    ![儲存到 Lifecycle Services。](media/task-guides.png)

12. 選取要儲存任務記錄的 BPM 庫和節點。

請按照下列步驟從 LCS 重播任務指引。

1. 啟動任務記錄器。
2. 請選取 **從 LCS 打開**。
3. 請選取已經儲存任務指引的庫和 BPM 節點。
4. 打開任務指引。


[!INCLUDE[footer-include](../includes/footer-banner.md)]
