---
title: 建立團隊行事曆
description: 在 Dynamics 365 Human Resources 檢視和建立團隊行事曆。
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ee39f35f9d81f47c5438ddf48451d24ab0c0ed3
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452112"
---
# <a name="view-team-and-company-calendars"></a>檢視團隊和公司行事曆


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以在 Dynamics 365 Human Resources 檢視團隊和公司行事曆。 團隊行事曆只顯示下屬，如直線階層架構的定義。

## <a name="view-your-team-calendar-as-an-employee"></a>以員工身份檢視您的團隊行事曆

- 請在 **Employee 自助服務** 工作區，**摘要** 下方選取 **團隊缺勤行事曆**。

## <a name="view-your-team-calendar-as-a-manager"></a>以經理身份檢視您的團隊行事曆

1. 請在 **Employee 自助服務** 工作區選取 **我的團隊**。

2. 選取 **請假和缺勤**，然後選取 **檢視經理缺勤行事曆**。

經理也可以從 **待核准我的團隊提出的休假要求**、**已核准的休假** 和 **休假要求** 存取團隊行事曆。 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>以缺勤經理的身份檢視您的缺勤經理行事曆

> [!NOTE]
> 若要檢視缺勤經理的行事曆，您必須先在功能管理中開啟 **(預覽版) 缺勤經理管理休假** 功能。 更多有關開啟預覽功能方式的資訊，請參閱[管理功能](hr-admin-manage-features.md)。

缺勤經理角色的使用者可以在他們的行事曆檢視休假要求。 請按照下列步驟存取請假行事曆。

1. 請在 **員工自助服務** 工作區選取 **請假管理** 和 **缺勤經理行事曆**。

2. 請在 **日期** 欄位中輸入想要的日期。

3. 按照需求更新視圖選項。

缺勤經理行事曆顯示所有在請假階層架構中向缺勤經理回報的員工記錄。

## <a name="view-a-company-calendar"></a>檢視公司行事曆

擔任人力資源角色的人員可以檢視公司行事曆。 公司行事曆顯示所有員工。 行事曆預設會顯示今天的日期加上 28 天，但您可以更改日期範圍。 您也可以按 **姓名**、**人事編號** 和 **請假類型** 篩選行事曆。

1. 請在 **請假和缺勤** 工作區選取 **連結**。

2. 請選取 **請假和缺勤行事曆**。

人力資源角色也可以從 **請假和缺勤要求**、**核准的休假** 和 **休假要求** 存取公司行事曆。 

行事曆現在包含額外的篩選條件和選項。 所有行事曆都包括下列視圖選項：

- 核准的要求
- 待核准要求
- 提出請假要求的員工
- 未提出請假要求的員工
- 員工生日
- 休假要求 
- 缺勤的請假要

在 **請假和缺勤參數** 頁面上的行事曆配置用來判定可用的視圖選項。

您也可以按經理或部門篩選行事曆。 主要職位指派可判定設定這些篩選條件時顯示的員工。 

> [!IMPORTANT]
> 您可以在功能管理中開啟 **跨公司請假視圖** 功能。 接著，您必須在 **人力資源共享參數** 頁面上啟用功能才能在行事曆顯示法律實體篩選條件。 更多資訊，請參閱[配置請假和缺勤參數](hr-leave-and-absence-parameters.md)。
> 
> 您可以按法律實體篩選行事曆。 若要檢視所有員工，不論法律實體與否，請清除篩選欄位，然後選取 **確定**。 

有關行事曆設定資訊，請參閱[配置行事曆參數](hr-leave-and-absence-parameters.md?configure-calendar-parameters)。

[!INCLUDE[footer-include](../includes/footer-banner.md)]
