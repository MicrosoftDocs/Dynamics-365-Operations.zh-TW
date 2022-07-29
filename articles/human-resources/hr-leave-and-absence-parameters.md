---
title: 配置請假和缺勤參數
description: 本主題說明在 Dynamics 365 Human Resources 中定義請假和缺勤的人力資源參數方式。
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7bd1aebd633af0530c550f8ec7510a0c09985ca1
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452337"
---
# <a name="configure-leave-and-absence-parameters"></a>配置請假和缺勤參數


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

在 Dynamics 365 Human Resources 設定請假和缺勤計劃之前，最好先驗證所有相關的 **人力資源參數** 設定，包括：

- 請假要求的編號順序
- 家庭醫療和請假法 (FMLA) 設定
- 請假和缺勤要求的員工自助服務設定
- 請假和缺勤參數

## <a name="view-and-change-human-resources-parameters"></a>檢視和變更人力資源參數

1. 請在 **請假和缺勤** 頁面上選取 **連結** 索引標籤。

2. 請在 **設定** 下方選取 **人力資源參數**。

3. 請在 **編號順序** 索引標籤上驗證 **請假要求識別碼** 的 **編號順序代碼**，必要時變更之。 本項設定可判定自動指派識別碼給請求要求時採用的順序。

4. 請在 **FMLA** 索引標籤上驗證 FMLA 設定，必要時變更之。

5. 請在 **Employee 自助服務** 索引標籤上指明經理是否可以代表旗下員工輸入請假和缺勤要求。

7. 選取 **儲存**。

>[!IMPORTANT]
>跨公司的請假和缺勤檢視動作目前在預覽模式。 您將需要在您的 **沙箱** 環境啟用才能顯示請假和缺勤選項。 更多有關啟用預覽功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

## <a name="view-and-change-human-resources-shared-parameters"></a>檢視和變更人力資源共用參數

1. 請在 **人事管理** 頁面上選取 **連結** 索引標籤。

2. 請在 **設定** 下方選取 **人力資源共用參數**。

3. 請在 **進階存取** 索引標籤上，**啟用跨公司請假檢視功能** 選取 **是**，允許跨公司檢視請假情況。

4. 選取 **儲存**。

## <a name="view-and-change-leave-and-absence-parameters"></a>檢視並變更請假和缺勤參數

1. 請在 **請假和缺勤** 頁面上選取 **連結** 索引標籤。

2. 請在 **設定** 下方選取 **請假和缺勤參數**。

3. 請在 **一般** 索引標籤上設定下列參數：
 
    - 請設定 **請假和缺勤單位** 為幾小時或幾天。 如果以天為單位，您可以選取 **啟用半天定義**，允許員工在他們的請假要求中選擇上半天或下半天。 

    - 請選取 **服務生效日期所屬月份**，設定請假計劃使用服務月數的累計費率何時生效。

    - 選取 **剩餘天數計算** 以便顯示截至今天或截至累計期間為止的剩餘天數。 如果您選取 **截至今天的剩餘天數**，剩餘天數會顯示截至今天，所有累計、調整和要求的總天數。 如果您選取 **截至累計期間的剩餘天數**，剩餘天數會顯示截至請假計劃中定義頻率的累計期間為止，所有的累計、調整和要求的總天數。 

    - 設定 **結轉到期** 批次工作的 **開始時間**。  
    
    - **允許員工購買請假** 和 **允許員工銷售請假** 選取 **是**。 如果這些選項您選取 **是**，您可以建立買賣請假政策，並讓員工提交買賣請假要求。

## <a name="configure-calendar-parameters"></a>配置行事曆參數

1. 請在 **請假和缺勤** 頁面上選取 **連結** 索引標籤。

2. 請在 **設定** 下方選取 **請假和缺勤參數**。

3. 必要時，請在 **行事曆** 索引標籤上變更行事曆設定。

4. 選取 **儲存**。

## <a name="see-also"></a>也請參閱

- [請假和缺勤概觀](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
