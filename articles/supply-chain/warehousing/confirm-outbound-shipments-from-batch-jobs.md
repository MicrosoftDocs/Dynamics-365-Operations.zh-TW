---
title: 從批次作業確認出庫貨物
description: 本主題說明如何設定批次工作，以自動確認可供運送貨物的出庫轉移訂單貨物。
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f68dcfc0c1454ee5b095e186c52faa6c83bf8dc6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450048"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>從批次作業確認出庫貨物

[!include [banner](../includes/banner.md)]

本主題說明如何設定批次工作，以自動確認可供運送貨物的出庫轉移訂單貨物。 此處提及的批次工作僅適用於轉移訂單貨物，不適用於銷售訂單。

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>開啟或關閉從批次工作確認出庫貨物功能

若要使用本主題中說明的功能，必須為您的系統開啟 *從批次工作確認出庫貨物* 功能。 從 Supply Chain Management 版本 10.0.21 開始，此功能預設開啟。 從 Supply Chain Management 10.0.25 開始，此功能為強制性開啟，且不能關閉。 如果您執行的版本為 10.0.25 之前的版本，管理員可以前往 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 工作區並搜尋 *從批次工作確認出庫貨物* 功能，然後開啟或關閉此功能。

## <a name="process-outbound-shipments"></a>處理出庫貨物

若要設定排程批次工作以執行可供運送貨物的出庫運送確認：

1. 依序前往 **倉庫管理 \> 定期任務 \> 處理出庫貨物**。
1. **確認運送** 對話方塊開啟。 在 **記錄內容包括** FastTab 上，選擇 **篩選**。
1. 查詢編輯器對話方塊開啟。 在 **範圍** 索引標籤中，新增列並加入以下的值：
    - **資料表** - *貨物*
    - **衍生資料表** - *貨物*
    - **欄位** - *貨物狀態*
    - **條件** - *已裝載*
1. 選擇 **確定**，返回 **確認運送** 對話方塊。
1. 在 **在背景執行** FastTab 上，將 **批次處理** 設為 **是**。
1. 在 **背景執行** FastTab 上，選取 **重複執行**。
1. **定義重複執行** 對話方塊隨之打開。 根據您的業務需要設定執行排程。
1. 選擇 **確定**，返回 **確認運送** 對話方塊。
1. 選擇 **確認運送** 對話方塊上的 **確定**，將批次工作新增到批次佇列。

如需相關資訊，請參閱[批次處理概覽](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md)。


[!INCLUDE[footer-include](../../includes/footer-banner.md)]