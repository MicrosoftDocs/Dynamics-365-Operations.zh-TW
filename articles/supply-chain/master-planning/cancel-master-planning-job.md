---
title: 取消主計劃作業
description: 本主題說明如何使用內建計劃功能取消啟用中的計劃作業。
author: ChristianRytt
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 27a48473a934e0db9986d6e588fc769ba9d2f605d72b2465976cb20a1ad93d16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446670"
---
# <a name="cancel-a-master-planning-job"></a>取消主計劃作業

[!include [banner](../includes/banner.md)]

在 Microsoft Dynamics 365 Supply Chain Management，有多個選項可用於取消主計劃作業。 例如，當主計劃作業被錯誤地啟動或執行時間超過預期以至於想要結束它時，您可能想要取消它。 從 **未完成的計劃流程** 頁面取消計劃工作是最佳方法。 替代選項是從 **批次作業** 和 **批次作業增強** 頁面，只有在 **未完成的計劃流程** 頁面沒有在幾分鐘內完成取消主計劃作業時使用。

## <a name="preferred-cancel-option"></a>首選的取消選項
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a>於 **未完成的計劃流程** 頁面取消主計劃作業
1. 前往 **主計劃 > 查詢和報告 > 主計劃 > 未完成的計劃流程**。
2. 選擇要取消的計劃流程所在的明細。
3. 按一下 **取消**。

## <a name="additional-cancel-options"></a>其他取消選項
只有在 **未完成的計劃流程** 頁面沒有在幾分鐘內完成取消主計劃作業時使用。

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>從 **批次作業** 頁面刪除主計劃作業
1. 移至 **系統管理 > 查詢 > 批次作業**。
2. 選取要刪除的計劃作業所在的明細。
3. 按一下 **刪除**。

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>從 **批次作業增強** 頁面刪除主計劃作業工作
1. 移至 **系統管理 > 查詢 > 批次作業**。
2. 如果清單中未顯示作業識別碼，請按一下 **切換到增強表單**，否則繼續下一步。
3. 打開批次作業。 對於您要結束的批次作業，按一下 **作業編號**。
4. 在 **批次任務**，選取要結束的任務。
5. 按一下 **變更狀態**，選擇 **取消** 並按一下 **確定**。
6. 在 **批次工作** FastTab，選取 **刪除**。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]