---
title: 建立工作時間行事曆
description: 在 Dynamics 365 Human Resources 中定義工作時間行事曆、假期和非工作時間。
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
ms.openlocfilehash: 54aa85acb43c1e9a474bea9996c72c7e7017c245
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452496"
---
# <a name="create-a-working-time-calendar"></a>建立工作時間行事曆


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources 中的工作時間行事曆顯示員工在貴組織工作的天數和時數。 當員工提交休假要求時，他們不必擔心假日和公休日問題。

若要簡化休假要求，請針為貴組織配置項目如下：

- 工作時間行事曆
- 假日和公休日
- 非工作時間

您可以在設定工作時間行事曆時新增最後兩項。 您也可以分開配置或更新它們。

## <a name="set-up-a-working-time-calendar"></a>設定工作時間行事曆

至少設定一個顯示您的作業天數和時數的工作時間行事曆。 如果您在多個國家和地區都有工作地點，您可能希望為每個地區設定工作時間行事曆。

1. 請在 **組織行政管理** 頁面上選取 **行事曆**。

2. 選取 **新增** 並輸入行事曆的名稱和說明。

3. 請在 **產生選項** 下方針對貴組織選取工作日並輸入工作時間。 
   - 若要新增假日或公休日，請選取 **假日和公休日** 旁邊的 **新增** 按鈕。
   - 若要新增非工作時間，例如午餐或休息時間，請選取 **非工作時間** 下方的 **新增** 並輸入名稱和時間範圍。

4. 請在 **天數** 下方選取 **產生** 以便在您的行事曆產生天數。 輸入行事曆的日期範圍，然後選取 **產生天數**。

5. 若要新增工作日程表，請在 **工作日程表** 下方選取 **新增** 然後輸入每個工作日程表的時間。

## <a name="configure-holidays-and-closures"></a>配置假日和公休日

您可以分開從工作時間行事曆新增或變更假日和公休日。

1. 請在 **組織行政管理** 頁面上選取 **假日和公休日**。

2. 選取 **新增** 並輸入假日或公休日的名稱和日期。

## <a name="configure-non-work-time"></a>配置非工作時間

您可以分開從工作時間行事曆新增或變更非工作時間。

1. 請在 **組織行政管理** 頁面上選取 **非工作時間**。

2. 選取 **新增** 並輸入非工作時間的名稱和時間範圍。

如果您啟用請假和缺勤銀行假日改正預覽功能，人力資源會使用假日和公休日判定調整行事曆註冊員工的天數。

## <a name="see-also"></a>也請參閱

- [請假和缺勤概觀](hr-leave-and-absence-overview.md)
- [配置請假和缺勤類型](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
