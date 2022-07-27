---
title: 排程波次期間的工作建立
description: 本主題說明如何設定及使用排程工作建立波次處理方法。
author: perlynne
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5b1e798ac0558e7c5b0bbe4b6a732cbdcf5729a1
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449556"
---
# <a name="schedule-work-creation-during-wave"></a>排程波次期間的工作建立

[!include [banner](../../includes/banner.md)]

使用 *排程工作建立* 功能作為波次處理的一部分，透過讓系統使用平行處理建立工作來幫助提高波次處理輸送量。

啟用該功能後，將自動建立規劃的工作，系統最終將處理這些工作以建立實際工作。 如果波次負載明細的數量達到預定閾值，系統將透過套用平行非同步處理更快地建立實際工作。

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>在功能管理中開啟規劃的工作建立功能

若要使用本主題說明的任一項功能，必須在系統中將其開啟。 使用[功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)工作區，依下列順序開啟以下功能：

1. **組織範圍的工作封鎖** - 對手動和自動配置排程工作建立皆為必要。 (從 Supply Chain Management 版本 10.0.21 開始，此功能為強制性的，因此預設開啟且無法再次關閉。)
1. **排程工作建立** - 對手動和自動配置排程工作建立皆為必要。
1. **組織範圍的「排程工作建立」波次方法** - 對自動配置排程工作建立為必要。 如果您只使用手動配置，則不需要此功能。

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>自動配置排程工作建立

如果啟用 *組織範圍的「排程工作建立」波次方法* 功能，您的系統上會自動發生以下情況：

- *排程工作建立* 波次方法 (`WHSScheduleWorkCreationWaveStepMethod`) 已新增並設定為在所有法人實體中平行執行。
- **波次範本類型** 設為 *運送* 且 **範本狀態** 設為 *有效* 的所有法人實體的波次範本的 *建立工作* 方法將由 *排程工作建立* 方法取代。 但是，波次範本允許可重複的法律實體的 *建立工作* 方法不可修改。
- *排程工作建立* 方法的工作配置將為啟用 **使用倉庫管理流程** 的所有法人實體的所有倉庫建立。 這代表 *排程工作建立* 方法現在將預設平行執行。 您將 **使用倉庫管理流程** 從 *否* 變更為 *是* 的現有倉庫預設也會平行執行此方法。
- 所有法律實體將批次處理波次，如果先前設為 *0* 毫秒，**等待鎖定 (毫秒)** 將設為預設值 *60,000* 毫秒。
- 您建立的所有新波次範本都將使用 *排程工作建立* 波次方法，而非 *建立工作* 方法。

現有工作和波次處理配置也將保留給所有已配置為批次處理波次的法律實體，及所有已配置為平行使用 *排程工作建立* 方法的所有倉庫。

如有必要，您可以手動恢復啟用 *組織範圍的排程工作建立波次方法* 功能時自動進行的任何或所有設定，方法如下：

- 如為波次範本，請移至 **倉庫管理 \> 設定 \> 波次 \> 波次範本**。 將 *排程工作建立* 方法取代為 *建立工作*。
- 如為倉庫參數，請移至 **倉庫管理 \> 設定 \> 倉庫管理參數**。 在 **波次處理** 索引標籤上，套用 **批次處理波次** 和 **等待鎖定 (毫秒)** 的首選值。
- 如為波次方法，請移至 **倉庫管理 \> 設定 \> 波次 \> 波次處理方法**。 選擇 `WHSScheduleWorkCreationWaveStepMethod` 並在動作窗格上，選擇 **工作配置**。 根據需要修改或刪除每個列出的倉庫批次工作數量和指派的波次群組。

## <a name="manually-configure-scheduled-work-creation"></a>手動配置排程工作建立

如果您沒有啟用 [*組織範圍內的「排程工作建立」波次方法* 特徵](#Auto-enable-schedule-work-creation)，然後您可以根據需要使用本節提供的過程手動配置計劃工作建立。

### <a name="manually-enable-batch-processing-of-waves"></a>手動啟用波次的批次處理

若要利用平行非同步方法建立倉庫工作，您的波次處理必須批次執行。 要進行此設定：

1. 前往 **倉庫管理 \> 設定 \> 倉庫管理參數**。
1. 在 **一般** 索引標籤上，將 **批次處理波次** 設為 *是*。 或者，您也可以選擇專用的 **波次處理批次群組**，以防止您的批次佇列處理與其他程序同時執行。
1. 設定 **等待鎖定 (毫秒) 時間**，其會在系統同時處理多個波次時套用。 對於多數較大的波次處理，建議值為 *60000*。

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>為現有波次範本手動啟用新的波次步驟方法

首先建立新的波次步驟方法並為平行非同步工作處理啟用。

1. 移至 **倉庫管理 \> 設定 \> 波次 \> 波次處理方法**。
1. 選擇 **重新產生方法**，並注意 *WHSScheduleWorkCreationWaveStepMethod* 已新增到您可以在運送波次範本中使用的波次處理方法清單中。
1. 選擇 **方法名稱** 為 *WHSScheduleWorkCreationWaveStepMethod* 的記錄，並選擇 **工作配置**。
1. 若要新增新的列至網格，請在動作窗格上選擇 **新增**，然後使用以下設定：

    - **倉庫** - 選擇您將用於排程工作建立處理的倉庫。
    - **最大批次工作數量** - 指定批次工作的最大數量。 在大多數情況下，此值應介於 8 至 16，但我們建議您根據自己的案例嘗試最佳的設定。
    - **波次處理批次群組** - 選擇一個專門的波次處理批次群組，以最佳化您的批次佇列處理。

現在您已準備好更新現有的波次範本 (或建立一個新範本)，以使用 *排程工作建立* 波次處理方法。

1. 前往 **倉庫管理 \> 設定 \> 波次 \> 波次範本**。
1. 在動作窗格上，選擇 **編輯**。
1. 在清單窗格中，選擇您要更新的波次範本 (如果您使用示範資料進行測試，則可以使用 *24 貨件預設*)。
1. 展開 **方法** FastTab 並選擇 **其餘方法** 網格中 **名稱** 為 *排程工作建立* 的列。
1. 選擇指向 **已選定方法** 資料行的箭頭，將選擇的列移到該資料行。 (您一次只能選擇一種方法，可使用 `WHSScheduleWorkCreationWaveStepMethod` 或 `createWork`，因此 **方法名稱** 為 `createWork` 的現有列會自動移到 **其餘方法** 網格。)

## <a name="set-wave-task-processing-threshold-data"></a>設定波次任務處理閾值資料

波次處理首次使用任何工作型處理執行時，系統將建立預設的波次工作處理閾值資料。 資料用於控制波次處理何時非同步執行並基於工作，使其能平行處理及建立工作。

預設資料最初將使用閾值 15 作為負載明細的最小數量 (`MINIMUMWAVELOADLINES`)。 這代表當系統處理超過 15 個負載明細的波次時，其將使用非同步工作處理。 您可以在測試環境的 `WHSWaveTaskProcessingThresholdParameters` 資料表中手動插入/更新此資料。 如果您需要在生產環境中變更此設定，您必須連絡 Microsoft 支援以請求更新。

## <a name="work-with-the-scheduled-work-creation"></a>使用計劃的工作建立

有關如何使用排程工作建立的詳細資料，請參閱[波次建立和處理](wave-processing.md)。 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
