---
title: 銷售記錄清除效能改善
description: 本主題將介紹銷售記錄清除效能改善功能以及如何啟用它。
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3c8ad7b0bd46c49fc989be091f44630a6a3eebc1
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449766"
---
# <a name="sales-history-cleanup-performance-improvements"></a>銷售記錄清除效能改善

[!include [banner](../includes/banner.md)]

如果 **銷售更新記錄清除** 定期批次作業不常在具有大量銷售更新的環境中執行，這可能需要很長的時間。 在這些情況下，*銷售記錄清除效能改善* 功能可以幫助減少執行時間並提高可靠性。

該功能會用以下方式改善現有的清除作業：

- 它將清除分成批次處理 （可透過自訂變更批次大小）。
- 它將最多執行 2 小時 (可透過自訂變更持續時間)。
- 在可能的情況下，它會利用資料庫功能來把鎖定爭用降至最低，並避免在清除期間交易表。

啟用該功能後，**銷售更新記錄清除** 批次作業 (**銷售和行銷 \> 期間任務 \> 清除 \> 銷售更新記錄清除**) 將像以前一樣執行，但效能更好，最多執行 2 小時。 這代表可能需要多次執行才能清除特定保留時間範圍內的所有資料。

## <a name="turn-on-the-sales-history-cleanup-performance-improvements-feature"></a>開啟銷售記錄清除效能改善功能

使用此功能之前，您必須先在系統中開啟。 管理員可利用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：***銷售和行銷*
- **功能名稱：***銷售記錄清除效能改善功能*
