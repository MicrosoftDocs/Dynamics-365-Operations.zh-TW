---
title: 建立工單
description: 本主題說明如何在資產管理中建立工單。
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c1477e3c1b99172d84d2cdc64fc0ed01c057e0fa59422b30c17868ca400de4d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446931"
---
# <a name="creating-work-orders"></a>建立工單

[!include [banner](../../includes/banner.md)]

您排定預防性維護工作後，下一步就是為其建立工單。 您可以使用其中一個維護排程來完成此步驟。 維修時程中排定時程的工作可以有不同的參考類型，如下表所述。

| 參考類型 | 描述 |
|---|---|
| 維護計畫 | 預防性維護工作的依據為 *時間* 或 *計數器* 維護計劃類型。 |
| 維護週期 | 包含多個需要類似維護類型的資產的預防性維護工作。 |
| 維護要求 | 手動建立的資產維護或維修要求。 此要求可以轉換為工單。 |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a>根據您的維護時程建立工單

如欲依據您的維護排程建立工單，請按照以下步驟操作。

1. 請依據您希望為工單選擇的排程項目開啟以下頁面之一：

    - 所有維護排程 (**資產管理 \> 管理排程 \> 所有維護排程**)
    - 開啟維護排程明細行 (**資產管理 \> 管理排程 \> 所有維護排程明細行**)
    - 開啟維護排程集區 (**資產管理 \> 管理排程 \> 所有維護排程集區**)

1. 在網格中針對每項要建立工單的排程維護工作選擇核取方塊。 然後在動作窗格選擇 **工單**。

    隨即顯示 **建立工單** 對話方塊。 **維護預測時間** 欄位會顯示所選明細行的預測總時數。

    ![建立工單對話方塊。](media/18-preventive-maintenance.png)

1. 在 **參數** 區段指定應建立的工單數。 選擇下列其中一個選項：

    - **每行一個工單** – 為每個維護排程明細行建立一個工單。
    - **每項目一個工單** – 建立工單並根據您選擇此選項時可用的其他選項設定進行分組。

1. 在 **工單類型** 欄位選擇工單類型，用於您建立的所有工單。
1. 選擇 **確定** 以依據設定建立工單。

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a>將維護計劃執行時自動建立的工單明細行聚集在一起

系統設定根據維護計劃自動產生工單時，此功能可讓您定義規則，將單一工單之下的工單明細行聚集在一起。 之前自動產生的工單只能包含一個明細行。 不過您現在可以依據資產、資產類型或功能位置等項目對工單進行分組。 (如本主題前一節所述，手動產生工單可能已利用這種方式分組。)

### <a name="enable-grouping-for-automatically-generated-work-orders"></a>為自動產生工單啟用分組

使用此功能之前，您必須先在系統中開啟。 管理員可利用[功能管理](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)設定檢查功能狀態，並開啟該功能。 在 **功能管理** 工作區，該功能會依以下方式列出：

- **模組：***資產管理*
- **功能名稱：***在執行維護計劃時套用工單分組規則*

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a>為自動產生工單設定分組

如欲為自動產生工單設定分組，請按照以下步驟操作。

1. 前往 **資產管理 \> 設定 \> 預防性維護 \> 維護計劃**。
1. 請對您要產生分組工單的每個計劃執行以下步驟：

    1. 在清單窗格中選擇計劃。
    1. 在 **明細行** FastTab 確保選擇每個明細行的 **自動建立** 核取方塊。

1. 前往 **資產管理 \> 定期 \> 預防性維護 \> 排程維護計劃**。
1. 在 **排程維護計劃** 對話方塊的 **時期** 區段，指定計劃的時間範圍 (尋找排程維護工作以產生工作時的未來時間範圍)。
1. 將 **自動由排程建立工單** 選項設定為 *是*。
1. 在 **工單** 區段選擇以下選項之一：

    - **每行一個工單** – 為每個維護排程明細行建立一個工單。 (此選項提供的功能與 *執行維護計劃時套用工單分組規則* 功能關閉時的可用功能相同。)
    - **每項目一個工單** – 建立工單並根據您選擇此選項時可用的其他選項設定進行分組。

1. 如果您希望選項僅在執行部分維護計劃時套用，請在 **預計包括的記錄** FastTab 之中新增所需的篩選條件，就像在 Microsoft Dynamics 365 Supply Chain Management 處理其他批次工作的方式一樣。
1. 在 **於背景執行** FastTab 根據需求設定批次和排程選項，就像您在 Supply Chain Management 中處理其他批次工作的方式一樣。
1. 選擇 **確定** 以執行和/或排程選擇的維護計劃。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]