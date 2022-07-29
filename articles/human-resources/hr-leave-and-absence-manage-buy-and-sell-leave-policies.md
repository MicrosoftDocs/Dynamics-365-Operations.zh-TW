---
title: 管理買賣請假政策
description: 您可以讓員工在 Dynamics 365 Human Resources 買賣請假。
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1fe7ce7eafdec175e3395a6ac37b33cb2bb8dbda
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452253"
---
# <a name="manage-buy-and-sell-leave-policies"></a>管理買賣請假政策


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以藉由建立買賣請假政策讓員工可以買賣請假。 您可以配置這些政策使用工作流程核准、設定最大金額和費率，以及設定買賣費率。 

## <a name="enable-employees-to-buy-and-sell-leave"></a>讓員工買賣請假

1. 請在 **請假和缺勤參數** 頁面上，針對 **允許員工購買請假** 和 **允許員工銷售請假** 選取 **是**。

## <a name="create-a-buy-and-sell-leave-policy"></a>建立買賣請假政策

1. 請在 **請假和缺勤** 頁面上選取 **連結** 索引標籤。 

2. 選取 **買賣請假政策**。

3. 選取 **新增**。

4. 請在 **買賣請假政策** 下方，針對政策輸入 **姓名** 和 **說明**。 

5. 選取 **政策類型**。 

   開放的政策類型是 **金額** 與 **每週時數**。 針對員工可以買賣的最大金額，請選取 **金額** 並輸入 **固定金額**。 如果您選取 **每週時數**，在員工指派的工作時間行事曆定義的工作時間會用來判定本政策的最大金額。 

6. 針對政策，請選取 **開始日期** 和 **結束日期**。 購買或銷售請假的要求只開放此時間範圍內提交。 

7. 針對政策，選取 **工作流程識別碼**。 任何買賣要求都將使用此工作流程審核與核准。 

8. 請在 **購買政策** 下方選取 **全職等效** (FTE)，根據員工職位定義的 FTE 按比例指派最大金額。 如果政策略類型 **金額**，請輸入 **最大固定金額**。 

9. 選取 **新增** 以便增加員工購買請假的請假類型。 您可以將多種請假類型新增到政策。 

10. 請假類型請輸入 **服務月數**，以便啟用不同月數的服務來判定員工可以購買的最大金額。 

11. 請假類型請輸入 **最大金額**。 

12. 請輸入員工將購買請假的 **費率**。 

13. 可選擇性輸入預計用在購買請假的 **收入代碼**。 

14. 可選擇性設定是否使用 FTE 判定請假類型的最大金額。 

15. 若要建立銷售政策，請按照 **銷售政策** 下方的步驟 8 到 14。 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>新增買賣請假政策到請假和缺勤計劃

1. 請在 **請假和缺勤** 頁面上選取請假和缺勤計劃。

2. 請在 **規則** 下方選取 **買賣請假政策**。

## <a name="see-also"></a>也請參閱

[請假和缺勤概觀](hr-leave-and-absence-overview.md)</br>
[配置請假和缺勤類型](hr-leave-and-absence-types.md)</br>
[累計請假與缺勤計劃](hr-leave-and-absence-accrue.md)</br>
[買賣請假](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
