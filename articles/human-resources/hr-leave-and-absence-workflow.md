---
title: 建立請假要求工作流程
description: 在 Dynamics 365 Human Resources 建立請假和缺勤要求工作流程，以便一致性地管理請假要求。
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
ms.openlocfilehash: 707b986c41cde2d4e26bdb4c5218b87b27702cee
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452100"
---
# <a name="create-a-leave-request-workflow"></a>建立請假要求工作流程


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

您可以在 Dynamics 365 Human Resources 建立工作流程，一致性地管理您的請假與缺勤要求。 **請假和缺勤** 工作流程讓您：

- 定義任務
- 判定必須完成任務的人
- 指明可以核准或駁回要求的人

## <a name="create-a-leave-and-absence-request-workflow"></a>建立請假與缺勤要求工作流程

1. 請在 **請假和缺勤** 頁面上選取 **連結** 索引標籤。

2. 請在 **設定** 下方選取 **人力資源工作流程**。

3. 選取 **新增**，然後選取 **請假和缺勤要求**。 

4. 當出現 **打開本檔案** 訊息方塊時，請選取 **打開** 並使用貴公司的憑證登入。

5. 使用工作流程編輯器建立您請假要求的工作流程。 更多有關搭配工作流程的資訊，請參閱[建立工作流程概觀](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)。

## <a name="leave-and-absence-request-workflow-data-elements"></a>請假與缺勤要求工作流程資料元素

您可以使用下列資料元素在工作流程針對請假和缺勤要求建立條件式或自動核准：

- **金額**
- **註解**
- **公司**
- **建立者**
- **建立日期和時間**
- **結束日期**
- **請假類型**
- **修改者**
- **修改日期和時間**
- **原因代碼**
- **要求識別碼**
- **開始日期**
- **狀態** 
- **提交日期**
- **送出者**
- **由人力資源提交**
- **由經理提交**
- **代為提交**
- **工作人員**
- **背景工作角色類型**

這些範例展示如何藉由使用這些資料元素建立不同類型的工作流程條件：

- 在條件式句子使用 **原因代碼** 路由病假要求，連同 **手術** 送交人力資源核准，同時路由所有其他原因代碼給經理。 更多有關條件式句子的資訊，請參閱[在工作流程中配置條件式決策](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md)。 

- 在自動的動作中使用 **由人力資源提交** 和 **由經理提交**，可自動核准這些角色代表員工提交的請假要求。 更多有關自動操作的動作資訊，請參閱[在工作流程配置核准流程](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md)。

- 在條件式句子或自動操作的動作中使用 **請假類型** 可控制工作流程路由含有特定請假類型的要求。

## <a name="see-also"></a>也請參閱

- [請假和缺勤概觀](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
