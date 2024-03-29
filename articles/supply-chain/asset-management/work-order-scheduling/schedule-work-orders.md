---
title: 排程工單
description: 本主題說明如何在資產管理中排程工單。
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderSchdulePreviewPart, EntAssetWorkOrderScheduleExclusively, EntAssetWorkOrderSchduleInfoPart, EntAssetWorkOrderScheduleListPage, EntAssetWorkOrderSchedule, EntAssetWorkOrderScheduleDelete
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: becd06c46afd92bf07d9a69147b7768e780aefa57f9045c11698c04154d6ddb8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446673"
---
# <a name="schedule-work-orders"></a>排程工單

[!include [banner](../../includes/banner.md)]

 

本主題說明如何在資產管理中排程工單。 

工單所需小時數的定義為預測小時數之和減去過帳小時數。 如果需要更多時間，則必須相應調整預測。 在 **資產管理** > **常用** > **工單** > **所有工單** 或 **進行中工單** 中，可以查看或編輯工作訂單的預測，方法是在 **工單** 索引標籤上選擇工單，然後點選 **預測**。建立和估計工單後，完成工單的下一步是分配所需的維護工作人員和工具。

只能排程其工單生命週期狀態允許排程的工單。 可使用 **資產管理** > **設定** > **工單** > **生命週期狀態** > **一般** FastTab >**允許排程** 切換按鈕設定允許排程。

1. 點選 **資產管理** > **常用** > **工單** > **所有工單**。

2. 在清單中選擇要排程的工單。 例如，依 **目前生命週期狀態** 排序清單。

3. 在 **一般** 索引標籤上，點選 **排程**。

4. 在 **排程工單** 對話方塊中，可依需要新增有關預期開始日期和服務等級的選項。 如果排程流程應遵守與已為其他作業排程的資源有關的產能限制，請確保 **資產**、**工具** 和 **工作人員** 切換按鈕設定為 [是]。

    [!NOTE]
    如果將 **資產**、**工具** 和 **工作人員** 切換按鈕設定為 [否]，將忽略現有保留。 在資訊記錄中將顯示重疊工單排程的清單，如有需要，可點選訊息打開工單並重新排程。

5. 若要查看有關排程流程的詳細資訊，請將 **詳細資訊** 切換按鈕選為 [是]。 這代表有關工單和維護工作人員計算分數的詳細資訊將顯示在資訊記錄中。

6. 點選 **確定** 以開使排程流程。

7. 計劃完成後，資訊記錄會顯示已排程的工單數量，以及更詳細的資訊 (如果 **詳細資訊** 切換按鈕設定為 [是])。

>[!NOTE]
>工單的排程週期為每個工單一個，而不是每個工單作業一個。 您也可以直接在 **資產管理** > **定期** > **工單** > **排程工單** 中打開 **排程工單** 對話方塊。 進行選擇並點選 **確定** 以開始排程工單。 可以在 **排程工單** 對話方塊 >**在背景執行** FastTab 中，將排程工單設定為批次作業。

*範例：* 在下圖中，**預計開始** 欄位中插入的公式將為所有工單產生預計開始日期為一週後的工單排程。 若要持續執行工單排程，但又希望確保不會重新排程接下來 5-6 天排程的工單，此公式可能會很實用。

![圖 1。](media/03-work-order-scheduling.png)

與工單相關的工單類型可以為一位維護工作人員設定排程 (**資產管理** > **設定** > **工單** > **工單類型** > **一位維護工作人員** 切換按鈕設定為 [是])。 這代表如果在工單中使用工單類型，則 **所有工單** 詳細資料頁面 >**標題** 檢視表 >**排程** FastTab 上的 **一位維護工作人員** 切換按鈕將自動設定為 [是]。 在工單排程期間，將把為該工單建立的所有工單作業隨後會安排給同一位維護工作人員。 如果需要，可編輯 **所有工單** 中 **一位維護工作人員** 切換按鈕上的選項，以允許為工單作業安排多位工作人員或一位工作人員。

資產管理中的排程流程包括排程計算中的多個因素：

- 工單和維護工作人員的計算分數。 工單和維護工作人員的分數設定在 **資產管理參數** 中設定。 
- 檢查執行作業所需的相符專長認證，即技能和證書。 技能和證書是在 **人力資源** 模組 (**人力資源** > **工作人員** > **工作人員**> 在清單中選擇工作人員 >**工作人員** 索引標籤 >**專長認證** 區段 >**技能** 和 **證書** 按鈕) 中對維護工作人員設定的。 此外，還可以將技能和證書新增到維護作業類型和維護作業工種。 有關專長認證和維護工作類型的詳細資訊，請參閱[維護作業類型類別和維護作業類型、維護作業類型變體、維護作業工種和維護檢查清單](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)。  

## <a name="scores-used-in-work-order-scheduling"></a>工單排程中使用的分數

工單作業的分數是根據預期開始日期和工單的服務等級計算。

**開始日期** 計算：對於從預期開始日期計算的每個未來日期，將從分數中減去並乘以分數，在以下範例中為「10」。

**關鍵性** 計算：關鍵性分數乘以工單的關鍵性。

**服務等級** 計算：服務等級分數除以工單上的服務等級。

在以下範例中，關鍵性分數為「2」，服務等級分數為「5」和「100」。

**範例 1：**

| 工單識別碼 | 預期的開始日期 | 工單關鍵性 | 工單服務等級 | 計算               | 分數      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | 明天            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | 從現在開始兩天後   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | 從現在開始兩天後   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

工單將依以下順序排程：WO-000108 **16**、WO-000108 **18**、WO-000108 **17**。

**範例 2：**

| 工單識別碼 | 預期的開始日期 | 工單關鍵性 | 工單服務等級 | 計算                 | 分數    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | 明天            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | 從現在開始兩天後   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | 從現在開始兩天後   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

如果服務等級分數增加到「100」，而不是「5」，則排程順序將為：WO-000108 **18**、WO-000108 **16**、WO-000108 **17**。

與計算哪些維護工作人員應處理工單相關的評分均設定為數字，在排程工單期間將其新增到每個維護工作人員的計算中。 將為工單選擇分數最高的維護工作人員。 以下是維護工作人員分數的簡短描述：

| 維護工作人員分數| 描述 |
|---|---|
| 負責的工作人員 | 如果將維護工作人員選為工單的負責工作人員，則加上此分數。 |
| 負責的維護工作人員群組 | 如果將維護工作人員選擇為工單的負責維護工作人員群組，則加上此分數。 |
| 慣用的維護工作人員         | 如果將工作人員選擇為資產的慣用維護工作人員，則加上分數。 |
| 慣用的維護工作人員群組   | 如果工作人員是資產的慣用維護工作人員，則加上此分數。  |
| 位置  | 如果公司使用功能位置，且維護工作人員位於與資產相關的功能位置，則這些維護工作人員將獲得滿分。 如果資產的功能位置具有上層位置，則該功能位置的維護工作人員將獲得 1/2 分數。 如果該位置也有上層，則該位置的維護工作人員將獲得 1/3 分數。 如果該位置也有上層，則該位置的維護工作人員將獲得 1/4 分數，以此類推。 如果公司使用資產位置 (不建議使用)，則使用位置、地區和區域來計算位置分數。 若工作人員的位置與相關資產的位置、地區和區域相同，則他們會獲得滿分。 如果工作人員位置僅與位置和區域相符，則維護工作人員的評分為滿分的 2/3。 如果維護工作人員位置僅與位置相符，則維護工作人員的評分為滿分的 1/3。 |
| 工作人員的開始日期  | 對於排程的開始日期晚於預期開始日期的每個日期，將減去此分數。  |

>[!NOTE]
>如果分數設定為「0」，則不計算該分數。 如果不想在排程時包括負責工作人員，這會很實用。

## <a name="competencies-used-in-work-order-scheduling"></a>工單排程中使用的專長認證

可以對維護作業類型 （**資產管理** > **設定** > **作業** > **維護作業類型**）和維護作業工種 （**資產管理** > **設定** > **作業** > **維護作業工種**） 設定技能和證書要求。 

在工單作業中選擇維護作業類型和維護作業工種。 如果已在維護作業類型或維護作業工種中選擇技能或證書，且該維護作業類型或維護作業工種用於工單作業，則只會安排具有相符技能和證書的維護工作人員來處理工單。

<a name="gantt"></a>

## <a name="work-with-scheduled-work-orders-using-a-gantt-chart"></a>使用甘特圖處理排程工單

**排程工單甘特圖** 提供圖形化介面，您可以在其中查看和重新排程工單。

若要查看和使用甘特圖：

1. 移至 **資產管理 > 工單 > 排程工單甘特圖**。

1. 使用 **設置** 區段的下拉式清單和欄位以設定要在甘特圖中顯示的功能位置、時間跨度和時間刻度。

1. 選擇 **套用**。

    - 甘特圖會更新以顯示與您的設定相符的排程工單。 每個工單都由一個藍色矩形表示。
    - 若要重新排程顯示的工單，請選擇它並將其拖動到適當的新日期和時間。

1. 如果進行了任何變更，請選擇動作窗格上的 **儲存** 進行儲存。


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]