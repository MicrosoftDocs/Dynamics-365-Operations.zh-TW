---
title: 波次配置
description: 本主題介紹如何設定波次配置步驟，包括如何為其啟用平行處理。
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 527bd24d7f2e9a05f6e617c222005186520f9968
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450036"
---
# <a name="wave-allocation"></a>波次配置

[!include [banner](../includes/banner.md)]

波次處理可能很耗時，並且大部分處理時間都花在配置步驟和工作建立步驟中。

現在可以平行執行其中每個步驟，這可以提高波次處理的效能，並允許在同一倉庫中實現更大的波次輸送量。 本主題說明如何設定波次配置方法以平行執行。 有關如何設定工作建立以平行執行的更多資訊，請參閱[在波次期間排程工作建立](configure-wave-schedule-work-creation.md)。

以前，一次只能在倉庫中設定一個波次。 此條件約束已移除並替換為新條件約束，即僅鎖定位於預留階層中位置上方的品項和維度。 位置上方的尺寸一律包括產品維度。 例如，如果使用 *顏色* 設定品項，則可以平行處理 *紅*、*藍* 和 *黃* 的變型。

這代表如果一個波次配置了該位置上方具有相同維度的相同品項，則其他波次將必須等待獲取對相同品項和維度的鎖定。 如果不能及時獲取鎖定就會發生錯誤，並導致波次處理失敗。

為了利用平行處理，必須以批次執行波次。

## <a name="performance-improvements"></a>效能改善

平行處理的效能優點可分為兩類：

- **提高輸送量** - 即使未設定平行處理，波次的輸送量通常也會提高，特別是對於波次中的品項沒有重疊的情況。
- **改進單一波次的配置** - 在轉換為平行配置後，對客戶資料的測試表明效能提高了近 50%。 平行處理是根據位置上方的品項和維度進行的，因此改進取決於波次包含多少不同的品項、可用的基礎結構以及配置的持續時間與工作建立的持續時間。

## <a name="configure-parallel-allocation"></a>設定平行配置

### <a name="warehouse-management-parameters"></a>倉庫管理參數

若要使用平行配置處理，請前往 **倉庫管理 > 設定 > 倉庫管理參數**，打開 **波次處理** 索引標籤，然後進行以下設定：

- **波次處理批次群組** - 選擇波次的初始處理應使用的批次群組。 配置的後續處理可以使用不同的波次群組來完成。
- **批次處理波次** - 將此項設定為 *是* 以使用平行處理。
- **等待鎖定 (毫秒)** - 輸入配置步驟等待由另一個配置步驟鎖定的系統資源的時間 (以毫秒為單位)。 超過此時間時，將不會處理波次並顯示錯誤訊息。 建議您至少等待幾秒鐘，以允許完成一個邏輯單元的配置。

有關這些選項和 **倉庫管理參數** 頁面上的其他波次處理選項的資訊，請參見[波次處理的倉庫參數](wave-warehouse-parameters.md)。

## <a name="wave-process-methods"></a>波次處理方法

若要設定平行處理：

1. 前往 **倉庫管理 > 設定 > 波次 > 波次處理方法**。
1. 在格線中選取 `allocateWave` 方法。
1. 在動作窗格上，選取 **工作設定**。
1. **波次張貼方法工作設定** 頁面打開。 此格線列出了配置了 `allocateWave` 方法的每個倉庫。 平行處理將僅用於列出的倉庫。 根據需要使用動作窗格按鈕在格線中新增或刪除倉庫。 
1. 對於各個倉庫，請進行下列設定：
    - **最大批次工作數** - 指定應用於所選倉庫配置的批次工作數。 批次工作的最佳數量取決於可用的基礎結構以及伺服器上正在處理的其他批次作業。 在專用於波次處理的四個核心環境上進行的測試表明，使用八項工作可產生良好的結果。
    - **波次處理批次群組** - 特定波次群組可用於不同倉庫，以允許按倉庫擴增配置處理。

## <a name="enable-or-disable-parallelization-across-all-legal-entities"></a>在所有法律實體中啟用或停用平行化

建議您設定 `allocateWave` 方法以在所有法律實體中平行執行，因為這有助於提高波次處理的效能。 從 Supply Chain Management 版本 10.0.17 開始，預設為所有新的和更新的安裝啟用 *配置波次方法的波次平行化* 功能，且無法再次關閉該功能。 啟用此功能後，將發生以下情況：

- 已更新 `allocateWave` 方法以包含工作配置設定，讓您可使用 **波次處理方法** 頁面來定義將同時執行的工作數，這相當於平行處理的數量。 因此，設定波步驟所用的時間 (通常是總處理時間的 30% 到 60%) 減少了大致相當於工作數量的係數。 也可以選擇指派哪個批次來處理這些工作。 請務必注意，您的所有法律實體都將設定為批次處理波次。 對於已設定為批次處理波次的倉庫，以及對於已設定為使用 `allocateWave` 方法平行的倉庫，將保留現有設定。
- 根據預設，所有新法律實體都設定為批次處理波次。 啟用了 **倉庫管理流程** 選項的所有新倉庫都將 `allocateWave` 方法設定為在預設情況下平行執行。
- 在 **倉庫管理參數** 頁面上，**批次處理波次** 設定為 *是*，**等待鎖定 (毫秒)** 設定為預設的 15 秒。 這代表所有波次都將以批次執行。 當波次執行時，它會在配置步驟期間獲取對位置上方的品項和維度的鎖定。 當其他波次處理工作嘗試為相同的記錄獲取相同的鎖定時，它會被阻止，直到目前流程完成。 **等待鎖定 (毫秒)** 設定確定系統在釋放鎖定之前將等待的最長時間。

平行配置處理需要批次執行波次處理。 因此，如果關閉 **批次處理波次** 設定，將降低波次處理效能，尤其是在波次處理使用如相關波次方法的工作設定定義的平行流程時。

如有必要，您可以復原在為您的執行個體自動啟用 *配置波次方法的波次平行化* 功能時預設進行的每個設定。 若要實現此操作：

- 前往 **倉庫管理 \> 設定 \> 倉庫管理參數**。 在 **波次處理** 索引標籤上，套用 **批次處理波次** 和 **等待鎖定 (毫秒)** 的首選值。
- 移至 **倉庫管理 \> 設定 \> 波次 \> 波次處理方法**。 選取 `allocateWave` 方法。 在動作窗格上，選擇 **工作設定** 以打開一個頁面，其中列出了將方法設定為平行執行的每個倉庫。 根據需要修改或刪除每個列出的倉庫批次工作數量和指派的波次群組。

## <a name="troubleshooting"></a>疑難排解

### <a name="troubleshoot-using-the-infolog"></a>使用資訊記錄進行疑難排解

由於使用了批次框架，因此將擷取在波次處理期間發生的錯誤將作為批次作業資訊記錄的一部分。 若要讀取與波次相關的批次作業：

1. 前往 **倉庫管理 \> 出庫波次 \> 裝運波次 \> 所有波次**。
1. 選擇要檢查的波次。
1. 在動作窗格上，開啟 **波次** 索引標籤上，然後，從 **波次** 群組中選擇 **批次作業**。

波次處理將自動修正，因此在處理過程中檢測到的任何錯誤都應使用資訊記錄報告。

與平行處理相關的典型錯誤可能是兩個波次嘗試同時配置同一個品項，但一個波次並未完成，因此另一個波次無法在指定時間內獲取鎖定。 如果發生這種情況，批次作業記錄將包含說明無法獲取品項鎖定的資訊，在這種情況下，必須重新處理失敗的波次。

由於是平行處理，因此必須在不同的資料表中維護資料以追蹤處理的狀態。 這代表批次作業的記錄可能包含錯誤，例如索引鍵重複錯誤。

批次工作中的錯誤也是批次作業記錄的一部分。 最重要的資訊通常位於底部。

在極少數情況下，例如，如果 SQL 連接結束，則波次處理可能會以不一致的狀態結束，在該狀態下批次作業似乎正在執行，但處理已停止。 波次無法處理這樣的錯誤，因此在下一個波次執行時嘗試清理失敗的波次。 或者，如果目前波次處於不一致狀態，請執行以下步驟：

1. 前往 **倉庫管理 \> 出庫波次 \> 裝運波次 \> 所有波次**。
1. 選擇需要清理的波次。
1. 在動作窗格上，開啟 **波次** 索引標籤上，然後在 **波次** 群組中選擇 **清理波次資料**。

### <a name="troubleshoot-using-the-wave-progress-log"></a>使用波次進度記錄進行疑難排解

如果在 **倉庫管理參數** 頁面上啟用了 **建立波進度記錄** 選項，則在每次開始和結束配置品項及其維度時都會建立記錄。 您應該僅在需要時 (例如，在初始測試期間或故障排除期間) 啟用此記錄。 啟用此選項後，您可以透過以下步驟查看記錄：

1. 前往 **倉庫管理 \> 出庫波次 \> 裝運波次 \> 所有波次**。
1. 選擇要檢查的波次。
1. 在動作窗格上，開啟 **波次** 索引標籤上，然後在 **波次** 群組中選擇 **進度**。
