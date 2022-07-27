---
title: 在波次期間排程波次標籤列印
description: 本主題說明如何設定和使用任務型波次標籤列印功能。
author: perlynne
ms.date: 06/09/2021
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 1323538765308ec3dd366456e31f5e08b08ce5ab
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449559"
---
# <a name="schedule-wave-label-printing-during-wave"></a>在波次期間排程波次標籤列印

[!include [banner](../../includes/banner.md)]

在波次處裡中使用 *任務型的波次標籤列印* 功能作以提高效率，並讓系統建立波次標籤並在單獨的任務中運作。

設定波次標籤列印的過程很複雜，並依賴準確的設定和主資料。 波次標籤記錄的生成失敗並不少見，當它失敗時，整個波次處理都會退回。 *任務型波次標籤列印* 功能可幫助您避免每次波次標籤列印錯誤時都必須重新建立工作和工作明細。

當您使用 *任務型波次標籤列印* 功能，系統會先建立工作和工作明細。 然後便會建立並列印波次標籤。 最後，如果正確建立了波次標籤，它會發布工作和波次以進行揀選。

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>在功能管理中開啟任務型波次標籤列印功能

若要使用本主題說明的功能，必須在系統中將其開啟。 使用 [功能管理](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 工作區，依下列順序開啟功能：

1. *波次標籤列印*–必須要開啟此功能才能為波次標籤列印啟用波次處理方法。
1. *組織範圍的工作封鎖* - 此功能對手動和自動配置排程工作建立皆為必要。 (從 Supply Chain Management 版本 10.0.21 開始，此功能為強制性的，因此預設開啟且無法再次關閉。)
1. *任務型波次標籤列印*–必須啟用此功能才能將波次標籤列印拆分到單獨的交易範圍。

## <a name="manually-enable-the-new-wave-step-method"></a>手動啟用新的波次步驟方法

您必須先建立新的波次步驟方法並在平行異步工作處理啟用它。

1. 移至 **倉庫管理 \> 設定 \> 波次 \> 波次處理方法**。
1. 在動作窗格上，選取 **重新產生方法**。 請注意 *波次標籤列印* 已新增到在裝運波次範本中可以使用的波次處理方法清單中。
1. 選取其 **方法名稱** 欄位設定為 *waveLabelPrinting* 的記錄，然後在動作窗格上，選取 **任務設定**。
1. 在動作窗格上選取 **新增**，將資料列新增至格線。 接著，在新的一列上，設定以下欄位：

    - **倉庫** – 選取您將用來排程工作建立處理的倉庫。 (如果您使用示範資料進行測試，您可以選取倉庫 *24*。)
    - **最大批次任務數量** - 指定批次任務的最大數量。 在大多數情況下，該值應該是從 *8* 到 *16*。 但是，我們建議為您的方案進行嘗試，以找到最佳設定。
    - **波次處理批次群組** - 選取一個專門的波次處理批次群組，以最佳化您的批次佇列處理。

您現在可以更新現有的波次範本，讓其使用 *波次標籤列印* 波次處理方法。 或者，您可以建立一個新的波次範本來使用它。

1. 前往 **倉庫管理 \> 設定 \> 波次 \> 波次範本**。
1. 在動作窗格上，選擇 **編輯**。
1. 在清單窗格中，選取要更新的波次模板。 (如果您使用示範資料進行測試，您可以選取倉庫 *24 裝運預設*。)
1. 在 **方法** FastTab 的 **其餘方法** 欄中，選取 **名稱** 欄位設為 *waveLabelPrinting* 的列。
1. 選取 **新增** (右箭頭按鈕) 將選定的列移動至 **已選定方法** 欄。
1. 在 **波次步驟代碼** 欄位中，輸入的波次步驟代碼，這將用於連接波次範本和波次標籤範本。

## <a name="set-wave-task-processing-threshold-data"></a>設定波次任務處理閾值資料

首次使用任何任務型處理執行波次處理時，系統會建立預設的波次工作處理閾值資料。 資料用於控制波次處理是否異步執行且是否為任務型，使其能處理及建立平行波次標籤。

預設資料最初將使用閾值 *1* 作為工作識別碼的最小數量 (`MinimumWorkThresholdForLabelPrinting`)。 因此，當系統處理具有多個工作識別碼的波次時，它將在單獨的交易中使用任務型波次標籤處理。 您可以在測試環境的 `WHSWaveTaskProcessingThresholdParameters` 資料表中手動插入或更新此資料。 若要在生產環境中變更此設定，您必須連絡 Microsoft 支援服務以請求更新。

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>使用任務型波次標籤列印時，變更波次處理的邏輯

如果波次標籤處理超過波次任務處理閾值，則啟動任務型的處理。 在下一個適合波次範本的波次處理中，工作建立後，波次標籤列印將立即獨立執行 *ttsbegin*/*ttscommit* 交易。 如果在波次範本上設定工作釋放 (解封) 以自動執行，則只有在波次標籤列印過程成功完成後才會發生。

如果波次標籤生成失敗 (例如，如果將工作數量轉換為波次標籤數量失敗並導致錯誤)，則只有相應的交易會失敗。 之前建立的工作仍然凍結。 若要更正錯誤並列印波次標籤，請執行以下步驟。

1. 前往 **倉庫管理 \> 出庫波次 \> 裝運波次 \> 所有波次**。
1. 在網格中選取相關的波次。
1. 在動作窗格的 **波次** 索引標籤上，在 **列印** 群組中選取 **波次標籤**。
1. 按照螢幕上的說明發送標籤以進行列印。
1. 在動作窗格上，在 **波次** 索引標籤，在 **波次** 群組，選取 **發布** 手動發布選定波次的工作。

## <a name="additional-resources"></a>其他資源

- [波次標籤列印](configure-wave-label-printing.md)
- [排程波次期間的工作建立](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
