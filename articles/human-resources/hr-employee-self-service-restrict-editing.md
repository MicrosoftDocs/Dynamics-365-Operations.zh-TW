---
title: 限制個人資訊的編輯
description: 限制員工在 Dynamics 365 Human Resources 編輯聯絡細節。
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
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e10db35996d31dc6c40a4253a324139c346be8c9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452661"
---
# <a name="restrict-editing-of-personal-information"></a>限制個人資訊的編輯


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

本主題說明如何限制員工在 Dynamics 365 Human Resources 編輯聯絡細節。 您可能希望防止員工編輯特定聯絡細節，例如他們的營業地點或電子郵件地址。

> [!NOTE]
> 若要使用此功能，您必須先在功能管理中啟用 **(預覽版) 限制員工為達特定目的新增或編輯地址與聯絡資訊**。 更多有關啟用預覽功能的資訊，請參閱[管理功能](hr-admin-manage-features.md)。<br><br>![啟用預覽功能。](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>選擇員工可以新增或編輯的資訊

1. 請在人力資源中選取 **人事管理**、**連結** 和 **人力資源參數**。

   ![前往人力資源參數。](./media/hr-employee-self-service-human-resources-parameters.png)

2. 請在 **人力資源參數** 頁面上選取 **Employee 自助服務** 索引標籤。

   ![選取 Employee 自助服務。](./media/hr-employee-self-service-tab.png)

3. 請在 **Employee 自助服務** 索引標籤上取消勾選您不希望員工新增或編輯 **地址和聯絡資訊** 專區裡的資訊。 本範例中，我們已經取消勾選 **商業** 聯絡資訊。

   ![限制編輯業務聯絡資訊。](./media/hr-employee-self-service-restrict-business.png)

4. 選取 **儲存**。

   ![儲存變更。](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>員工體驗

待您已經限制員工新增或編輯聯絡細節後，他們可以查看資訊，但不能更改。

本範例中，員工被限制編輯 **商業** 聯絡細節，但他們仍然可以在 **Employe 自助服務** 中查看資訊：

![檢視業務聯絡細節。](./media/hr-employee-self-service-restrict-view.png)

不過，當他們選取業務聯絡細節時，**編輯地址** 窗格以唯讀形式出現，他們不能更改任何欄位。

![業務聯絡細節以唯讀形式顯示。](./media/hr-employee-self-service-restrict-read-only.png)

此外，如果他們選取 **新增** 來新增地址，他們無法從 **目的** 下拉式方塊選取 **商業**。

![員工不能新增公司地址。](./media/hr-employee-self-service-restrict-add.png)

員工在 **個人資訊** 頁面上選取 **聯絡細節** 和新增地址時，能獲得相同體驗。 **目的** 下拉式方塊只顯示他們可以新增的資訊類型。 

![員工不能在目的下拉式清單選取業務。](./media/hr-employee-self-service-restrict-purpose.png)

**聯絡細節** 現在顯示在格線中的 **目的**。

![目的顯示在聯絡細節格線中。](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>也請參閱

[Employee 和 Manager 自助服務概觀](hr-employee-manager-self-service-overview.md)<br>
[配置人力資源參數](hr-setup-parameters.md)<br>
[編輯個人資訊](hr-employee-manager-self-service-edit-personal-information.md)
