---
title: 福利管理工作區
description: 本主題說明 Dynamics 365 Human Resources 中的福利管理工作區。
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 424f4a2098e05b4f7dc6fa84df133dda81cc59f0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452289"
---
# <a name="benefits-management-workspace"></a>福利管理工作區


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

本主題說明 Dynamics 365 Human Resources 中的 **福利管理** 工作區。

> [!NOTE]
> 若要檢視 **福利管理** 工作區，您必須先啟用功能管理中的 **(預覽)福利管理工作區** 功能。 更多有關啟用預覽功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。<br><br>![啟用福利管理工作區。](./media/hr-benefits-management-workspace-enable.png)

**福利管理** 工作區讓您快速檢視需要您特別留意的福利項目。 您可以在本頁面看到：

- 等待動作的項目總數
- 尚未確認選取項目的背景工作角
- 最近註冊福利的背景工作角
- 有未來生活事件的背景工作角
- 並未註冊的新進員工
- 生活事件有效的背景工作角
- 未曾選擇任何計劃的開放註冊背景工作角

![福利管理工作區。](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>檢視動作項目

您可以選取圖格或索引標籤檢視您的操作項目。如果您選取索引標籤，就能從工作區頁面檢視和選取背景工作角色。

![動作項目。](./media/hr-benefits-management-workspace-action-items.png)

如果您選取圖格，您將前往該區域的頁面。 例如，選擇這些圖格當中任何一個就會顯示 **背景工作色角色計劃** 頁面，進而篩選您需要採取動作的員工：

- **尚未確認的選取項目**
- **未簽出計劃的開放註冊**
- **註冊福利**
- **並未註冊的新進員工**

![背景工作角色福利計劃。](./media/hr-benefits-management-workspace-plans.png)

選取 **有效生活事件** 或 **未來生活事件** 將帶您到有效或未來生活事件清單。

![生活事件。](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>正在處理

若要處理註冊資格、生活事件或費率變更與更新，請在瀏覽列上選取適當項目。

![處理中。](./media/hr-benefits-management-workspace-processing.png)

若要檢視流程結果，請在頁面上選取 **處理結果**。

![處理結果。](./media/hr-benefits-management-workspace-process-results.png)

更多有關福利處理資訊，請參閱：

- [處理註冊資格](hr-benefits-process-enrollment-eligibility.md)
- [處理生命事件變更](hr-benefits-process-life-event-changes.md)
- [處理生命事件資格](hr-benefits-process-life-event-eligibility.md)
- [處理生活事件](hr-benefits-process-life-events.md)
- [處理費率變更](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>變更期間

若要檢視不同的福利期間，請從 **期間** 下拉式清單選取。

![變更期間。](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>打開註冊索引標籤

您可以選取圖格或索引標籤檢視動作項目。如果您選取索引標籤，就能在工作區頁面檢視和選取背景工作角色。
**開放註冊** 索引標籤提供開放註冊流程的關鍵指標。 

有關開放註冊的資訊將在 **註冊開始日期** 前顯示 30 天。 這在 **註冊開始日期** 欄位中的 **福利管理** > **連結** > **期間** 的 **期間** 設定。  若要變更這項設定，請前往 **人力資源共用參數** > **福利管理** > **開放註冊選項** 並更新 **數字** 欄位。  

**開放註冊** 索引標籤開放資訊如下：
 - 尚未開始開放註冊流程的員工
 - 正在挑選的員工
 - 已經完成挑選流程的員工
 - 尚未確認的選取項目

**摘要圖格**

- **尚未開始** - **尚未開始** 圖格顯示尚未開始註冊流程的員工計數。 **尚未開始** 圖格是篩選清單，只顯示開放註冊計劃期間並未選取、放棄或簽出任何計劃的員工。 系統會忽略強制性計劃且不包括在內，因為預設已針對員工選取。  您可以回溯此圖格查看尚未在 **背景工作角色福利計劃** 頁開放註冊流程的員工清單。

  > [!NOTE]
  > 如果您不想要追蹤 **計劃類型** 的開放註冊進度，您可以前往 **福利管理** > **連結** > **員工自助服務參數** > **福利計劃圖格設定** 並更新 **追蹤開放註冊進度** 欄位將它排除。  例如，您可能有計劃在 **計劃類型** = **其他** 的地方建立。 這些計劃可能是您不希望追蹤註冊進度的非必要計劃。 如果您不選取這個計劃類型，則當 **開放註冊** 索引標籤上的追蹤註冊進度或註冊完成時，會忽略這個類型的計劃。本項設定適用針對所有期間和法人實體選取的計劃類型。

- **進行中** - **進行中** 圖格給您正在挑選的員工計數。 **進行中** 圖格是篩選清單，只顯示至少放棄或選取一項計劃的員工。 系統會忽略強制性計劃且不包括在內，因為預設已針對員工選取。 您可以從這個圖格回頭切入查看 **背景工作角色福利計劃大量更新** 頁面上已選取和放棄的計劃。

- **已註冊福利** - **已註冊福利** 圖格給您完整註冊福利的員工計數。 **已註冊福利** 圖格是篩選清單，顯示已經選取或放棄所有計劃的員工。 此項查詢將排除未在 **員工自助服務參數** 頁面上追蹤開放註冊的計劃。 您可以從這個圖格回頭切入查看 **背景工作角色福利計劃** 頁面上的員工清單。

- **尚未確認的選取項目** - **尚未確認的選取項目** 圖格顯示已經選取或放棄並且需要確認計劃的員工計數。 您可以從這個圖格回頭切入顯示 **背景工作角色福利計劃大量更新** 頁面。

**活動**

- **尚未開始** - **尚未開始** 索引標籤顯示尚未開始註冊流程的員工清單。 **尚未開始** 圖格是篩選清單，顯示開放註冊計劃期間並未選取、放棄或簽出任何計劃的員工。 系統會忽略強制性計劃且不包括在內，因為預設已針對員工選取。 您可以向下切入背景工作角色以顯示 **背景工作角色福利計劃詳情** 頁面。

- **挑選中** - **挑選中** 索引標籤顥示正在挑選的員工清單。 **挑選中** 圖格是篩選清單，顯示至少放棄或選取一項計劃的員工。 系統會忽略強制性計劃且不包括在內，因為預設已針對員工選取。 您可以向下切入背景工作角色以顯示 **背景工作角色福利計劃詳情** 頁面。

## <a name="view-more-options"></a>檢視更多選項

若要檢視更多資訊和/或其他動作，請選取 **連結**。

![連結。](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>也請參閱

[福利管理概觀](hr-benefits-management-overview.md)
